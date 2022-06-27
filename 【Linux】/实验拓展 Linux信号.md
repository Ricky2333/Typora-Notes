# 实验拓展2 Linux信号



## 实验目的



## 实验内容

### Signal Basics

> signal通信有一个巨大的缺点，没法在两个进程之间传输数据，只能通过信号的方式做某些操作

#### signal_1.c

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <signal.h>

void sig_usr(sig_num);

int main(){

        signal(SIGALRM,sig_usr);
        alarm(3);

        //this while loop forces the users to end this process by using signals
        while(1){
                pause();
        }
        return 0;

}

void sig_usr(int sig_num){
        printf("signal %d has been received\n",sig_num);
}
```

![image-20220602163535448](https://tva1.sinaimg.cn/large/e6c9d24ely1h2tzir1ajsj216i048ta6.jpg)



#### signal_2.c

```c
#include <stdio.h>
#include <stdlib.h>
#include <signal.h>
#include <unistd.h>

int main(){
        int i;

        if(signal(1,SIG_IGN) == SIG_ERR)
                printf("signal 1 can't be ignored\n");

        if(signal(9,SIG_IGN) == SIG_ERR)
                printf("signal 9 can't be ignored\n");

        for (i=1;i<=64;i++)
                if(signal(i,SIG_IGN) == SIG_ERR)
                        printf("signal %d can't be ignored\n",i);

        return 0;
}
```

![image-20220602162302528](https://tva1.sinaimg.cn/large/e6c9d24ely1h2tz5oxexlj217m080myz.jpg)



### Signal Communication

#### signal_3.c

```c
#include <stdio.h>
#include <stdlib.h>
#include <signal.h>
#include <unistd.h>

void sig_usr(int sig_num);

int main(){
        int i;

        signal(1,sig_usr);
        signal(2,sig_usr);

        while(1){
                pause();
        }

        return 0;
}

void sig_usr(int sig_num){
        printf("signal %d has been received\n",sig_num);
}
```

Processs 1

![image-20220602170522039](https://tva1.sinaimg.cn/large/e6c9d24ely1h2u0dqbaldj216q03aab5.jpg)

Process 2

![image-20220602165911904](https://tva1.sinaimg.cn/large/e6c9d24ely1h2u07b1hdhj21cs048wgc.jpg)

Process 2

![image-20220602170113974](https://tva1.sinaimg.cn/large/e6c9d24ely1h2u09fedf4j21bs07277f.jpg)

Process 1

![image-20220602170231414](https://tva1.sinaimg.cn/large/e6c9d24ely1h2u0arkjxqj21b2084q4v.jpg)



### Pipe_Basics

#### Pipe

> 管道和普通fork来读写文件的最大区别是，管道再读完数据后，管道里的内容就没了，而普通的不会

```c
#include <fcntl.h>              
#include <unistd.h>

int pipe(int pipefd[2]);
```



```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <sys/types.h>
#include <fcntl.h>
#include <string.h>
#define BUF_SIZE 1024

int main(){
        int fd[1],pid,n,i,status;
        char buf[BUF_SIZE];
        char *rd="message read from the pipe: ";
        pipe(fd);

        //puts(buf);
        if( (pid = fork())< 0 ){
                perror("fork failed\n");

        }else if( pid == 0 ){     //now in child process, read message from the pipe
                close(fd[1]);
                while((n = read(fd[0],buf,BUF_SIZE)) > 0 ){
                        write(STDOUT_FILENO,rd,strlen(rd));
                        write(STDOUT_FILENO,buf,n);
                }
                close(fd[0]);
                exit(0);
        }else{                    //now in parent process, write message to the pipe
                close(fd[0]);
                while((n = read(STDIN_FILENO,buf,BUF_SIZE)) > 0){
                        write(fd[1],buf,n);
                }
                close(fd[1]);

        }
        return 0;
}
```

![image-20220604113944547](https://tva1.sinaimg.cn/large/e6c9d24ely1h2w27iig77j21f0092jt6.jpg)



#### FIFO

##### mkfifo.c

```c
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#define BUF_SIZE 1024

int main(){
        int fd,n;
        char buf[BUF_SIZE];

        //make a fifo
        if (mkfifo("fifo1",0666) < 0)
                perror("mkfifo failed\n");

        //open fifo
        if ((fd = open("fifo1",O_WRONLY)) < 0 )
                perror("read file failed\n");

        //witre data to fifo
        n = read(STDIN_FILENO,buf,BUF_SIZE);
        write(fd,buf,n);

        close(fd);
        return 0;
}
```

##### rdfifo.c

```c
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <unistd.h>
#include <fcntl.h>
#define BUF_SIZE 1024

int main(){
        int n,fd;
        char buf[BUF_SIZE];

        //open fifo
        if ((fd = open("fifo1",O_RDONLY)) < 0)
                perror("open fifo failed\n");

        //read data to buf
        if ((n = read(fd,buf,BUF_SIZE)) < 0)
                perror("read file failed\n");

        //write data to the screen
        write(STDOUT_FILENO,buf,n);

        close(fd);
        return 0;
}
```

Process1

![image-20220604153330688](https://tva1.sinaimg.cn/large/e6c9d24ely1h2w8ypivb0j21de03yabv.jpg)

Process2

![image-20220604153729272](https://tva1.sinaimg.cn/large/e6c9d24ely1h2w92ud5jdj21ew06un0s.jpg)



### Shared Memory

```c
#include <sys/ipc.h>
#include <sys/shm.h>

int shmget(key_t key, size_t size, int shmflg);
```

#### ipcs -m

查看当前所有共享内存

![image-20220604165048533](https://tva1.sinaimg.cn/large/e6c9d24ely1h2wb74x6qzj21bm0l2wkz.jpg)



#### shmget()

创建一块共享进程

```c
#include <sys/ipc.h>
#include <sys/shm.h>

int shmget(key_t key, size_t size, int shmflg);
```



#### shmat()

允许进程访问一块共享进程，即连接一块共享内存

```c
#include <sys/types.h>
#include <sys/shm.h>

void *shmat(int shmid, const void *shmaddr, int shmflg);
```


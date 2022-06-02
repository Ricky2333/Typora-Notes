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

> 管道和普通fork来读写文件的最大区别是，管道再读完数据后，管道里的内容就没了，而普通的不会



## 实验作业
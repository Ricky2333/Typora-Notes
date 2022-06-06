```latex
26
```

$$
26^。C
$$





```c
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <unistd.h>

int main(){
        pid_t pid;
        int status;

        if( (pid = fork()) < 0 ){
                perror("fork failed\n");
        }else if(pid == 0){
                printf("child process 1\n");
                exit(100);
        }else{
                wait(&status);
                printf("parent process 1\n");
        }

        if( (pid = fork()) < 0 ){
                perror("fork failed\n");
        }else if(pid == 0){
                printf("child process 2\n");
                abort();
        }else{
                wait(&status);
                printf("parent process 2\n");
        }

        return 0;
}
```



各位同学，大家好



今天我们正式**进入第二章**的学习



首先我们先来看一下第二章的章节标题，是信息系统的支撑技术



那么我们就要问，什么是信息系统？什么是支撑技术？



那在之前的学习中，我们已经掌握了关于信息系统的相关概念



来，这位同学，请你回答一下，什么是信息系统？ 很好，信息系统就是：



那么什么是支撑技术呢？简单来说，信息系统的支撑技术由以下五个部分组成，我们将在之后的课程中逐一学习



而我们今天呢，就要学习其中的第一块内容，**计算机硬件**。



硬件的基本概念



硬件的形态与计算机的发展息息相关，在不同阶段，计算机的硬件是各部相同的



计算机硬件的历史



计算机硬件的未来 




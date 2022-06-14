```latex
26
```

$$
26^。C
$$



#### 3.4 pthread_cancel()

##### pthread_cancel()功能

>  **杀死一个线程**，类似于用 **`kill命令`** 杀死进程

##### pthread_cancle()原型

```C
#include <pthread.h>

int pthread_cancel(pthread_t thread);
```

##### pthread_cancel()返回值

> 如果操作成功，**返回0**；如果操作失败，**返回错误值**

##### pthread_cancel()参数解释

>  **`pthread_t thread`**  表示想要杀死的子线程的ID

##### pthread_cancel()编程实例

```C
pthread_cancel(tid1)  //杀死线程ID为tid1的线程
```





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



浙江师范大学，位于浙江省金华市，是一所以教师教育为特色的综合性省属重点大学，是浙江省首批重点建设高校，入选国家“111计划”、“卓越教师培养计划”、“新工科研究与实践项目”、教育部“教育援外基地、商务部“中国基础教育援外研修基地”、中国—东盟教育培训中心、中国政府奖学金来华留学生接收院校、浙江省十佳对外合作单位、“浙江省国际化特色高校”建设单位，建有浙江省唯一的教育学一级学科重点研究基地。



宁波外国语学校创办于 1991年，目前是宁波市教育局直属的寄宿制完全中学。2011 年，学校被全国外语特色学校教育研究会吸纳为常务理事单位，之后被评为“全国首批示范性外语特色学校”。学校坐落于东钱湖畔，占地 270 亩，建筑面积 8.1 万平方米，绿化面积 8 万多平方米，是浙江省内办学条件最现代化的中学之一。目前，学校包括初中部、国际高中部，在校教职员工 200 多人，在校学生 1200 余人。


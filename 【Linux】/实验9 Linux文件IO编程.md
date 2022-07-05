# 实验九 Linux文件IO编程

![【封面】Linux实验报告](https://tva1.sinaimg.cn/large/e6c9d24ely1h3spimoc4qj21ds0l4whu.jpg)

作者｜Ricky的水果摊

时间｜2022年6月2日

---

## 实验目的

了解Linux系统基本文件I/O编程，掌握常用的五个函数：open、read、write、lseek、以及close



## 实验原理

### 1. 背景知识

#### 1.1 文件描述符

> + 对于Linux内核而言，所有打开的文件都通过 **文件描述符** 引用，文件描述符是一个非负整数
> + 当 **打开或者创建**一个文件时，**内核向进程返回一个文件描述符**
> + 一个 Linux 进程启动后，会在内核空间中创建一个 **PCB 控制块**，PCB 内部有一个 **文件描述符表**（File descriptor table），记录着当前进程所有可用的文件描述符，也即当前进程所有打开的文件

除了文件描述符表，系统还需要维护另外两张表：

- **打开文件表**（Open file table）
- **i-node 表**（i-node table）

文件描述符表每个进程都有一个，打开文件表和 i-node 表整个系统只有一个，它们之间的关系如下图所示

![Linux文件描述符表示意图](http://c.biancheng.net/uploads/allimg/190410/1-1Z4101H45S13.gif)

[上表的具体解释—C语言中文网](http://c.biancheng.net/view/3066.html)

有了以上对文件描述符的认知，容易理解以下情形：

- 同一个进程的不同文件描述符可以指向同一个文件；
- 不同进程可以拥有相同的文件描述符；
- 不同进程的同一个文件描述符可以指向不同的文件（一般也是这样，除了 0、1、2 这三个特殊的文件）；
- 不同进程的不同文件描述符也可以指向同一个文件。



### 2. 基本的5个文件函数

#### 2.1 open函数

##### open函数功能

>  一般用来 **打开文件**，可以根据参数来定制我们需要的文件的属性和 **用户权限** 等各种参数

##### open函数原型

```C
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h>

int open(const char *pathname, int flags);
int open(const char *pathname, int flags, mode_t mode);
//fd = open("",O_RDONLY)
```

##### open函数返回值

> open函数如果操作成功，它将返回一个 **文件描述符**；如果操作失败，它将 **返回-1**

##### open函数参数解释

> **`pathname `**  可以设置为该文件的 **绝对路径名**，也可以是文件名（若只有文件名，则是在当前路径下）

> **`flags`** 表示 **打开文件所采用的操作**，必须指定为以下三个常量的一种
>
> | 参数     | 功能     |
> | :------- | -------- |
> | O_RDONLY | 只读模式 |
> | O_WRONLY | 只写模式 |
> | O_RDWR   | 可读可写 |

##### open函数编程实例

```C
if((fd = open("/home/parallels/Desktop/test/str.txt",O_RDONLY))<0){
	perror("read_error\n");
  exit(0);
}
```



##### open函数与fopen函数区别

+ open函数是 **Unix下系统调用函数**，操作成功返回的是 **文件描述符**，操作失败返回的是-1

+ fopen是 **ANSI C标准中C语言库函数**，所以 **在不同的系统中调用不同的内核的API**，返回值是一个**指向文件结构的指针**

+ 同时open函数没有缓冲，fopen函数有缓冲，open函数一般和write配合使用，fopen函数一般和fwrite配合使用

  

#### 2.2 read函数

##### read函数功能

> 接收 **标准输入(键盘)**或者 **文件描述符的输入**,将数据放入一个标准变量中

##### read函数原型

```C
#include <unistd.h>

ssize_t read(int fd,void *buf,size_t count)
```

##### read函数返回值

> read函数如果操作成功，它将返回 **实际读取的字节数**（例外：读取文件时，未到要求的字节数前，就已经到达文件末尾，此时返回字节数不等于要求字节数）；如果操作失败，**返回-1**
>
> 读操作完成后，**文件位置改变 **为已读取末尾位置的下一个位置

##### read函数参数解释

> **`fd`** 为文件描述符

> **`buf`** 表示读出数据缓冲区地址

> **`count` **表示需要读取的字节数

##### read函数编程实例

```C
read(fd,buf,3);     //将文件fd的2个字符读入buf中
read(STDIN,buf,2)   //将键盘输入的2个字符读入buf中
```



#### 2.3 write函数

##### write函数功能

> 一般用来把内容写入文件，具体是把参数buf所指的内容写入count个字节到fd所指的文件内

##### write函数原型

```C
#include <unistd.h>

ssize_t write(int fd,void *buf,size_t count)
```

##### write函数返回值

> 如果操作成功，返回实际写入的字节数；操作失败，返回-1，错误代码存入errno中

##### write函数参数解释

> **`fd`** 为文件描述符

> **`buf`** 表示写入数据缓冲区地址

> **`count` **表示需要写入的字节数

##### write函数编程实例

```C
write(fd,buf,3)            //将buf中的3个字节写入到文件fd中
write(STDOUT_FILENO,buf,3) //将buf中的3个字节写入到屏幕上
```



#### 2.4 lseek函数

##### lseek函数功能

> 一般用来更改 **文件指针位置**

##### lseek函数原型

```C
#include <sys/types.h>
#include <unistd.h>

off_t lseek(int fd, off_t offset, int whence);
```

##### lseek函数返回值

> 返回文件指针的位置

###### lseek函数参数含义

> **`fd`** 为文件描述符

> **`offset`** 表示 **偏移量**，其数据类型 **off_t** 为一个宏定义，底层就是 **long int** 类型，其值 **可正可负**

> **`whence`** 表示初始移动位置
>
> **SEEK_SET**：从 **文件头** 开始偏移（文件头 + offset值）
>
> **SEEK_CUR**：从 **当前位置** 开始偏移（当前位置 + offset值）
>
> **SEEK_END**：从 **文件结尾** 开始偏移（结尾位置 + offset值）

##### lseek函数编程实例

```C
lseek(fd, 0, SEEK_SET);   //移动文件指针到文件头
lseek(fd,0,SEEK_CUR);     //移动文件指针到文件当前位置
lseek(fd,0,SEEK_END);     //移动文件指针到文件结尾

lseek(fd,100,SEEK_END);   //拓展文件长度，增加100字节
write(fd," ",1);          //必须有这一步，写入空数据，否则无法拓展
```



#### 2.5 close函数

##### close函数功能

>  一般用来 **关闭文件**

##### close函数原型

```C
#include <unistd.h>

int close(int fd);
```

##### close函数返回值

> 如果操作成功，返回0；操作失败，返回-1，同时失败原因会被记录在errno中

##### close函数参数解释

> **`fd`** 为文件描述符

##### close函数编程实例

```C
close(fd);     //关闭当前文件fd
```



### 3. 综合实例

```c
#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>
#include <stdlib.h>
#include <fcntl.h>
        int fd;
        char buf[100];

        //打开str.txt文件
        if((fd = open("/home/parallels/Desktop/test/str.txt",O_RDONLY))<0){
                perror("read_error\n");
                exit(10);
        }

        //读取文件内容至buf中，并打印在屏幕上
        read(fd,buf,3);
        write(STDOUT_FILENO,buf,3);

        //文件指针向后移动1位
        lseek(fd,1,SEEK_CUR);

        //读取文件内容至buf，并打印在屏幕上
        read(fd,buf,3);
        write(STDOUT_FILENO,buf,3);

        //关闭str.txt文件
        close(fd);
        return 0;
}
```

---




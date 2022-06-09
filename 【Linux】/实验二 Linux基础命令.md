# 实验二 Linux基础命令



## 实验目的

了解Linux系统，熟悉Linux常用命令



## 实验原理

### 1.Linux文件系统

Linux 文件系统是**树状结构**，系统中每个分区都是一个文件系统，都有自己的目录层。Linux 会将这些分属不同分区的、单独的文件系统按照树状的方式形成一个系统的总目录层次结构。目录提供了一个管理文件方便而有效的途径，最上层是根目录，其它所有目录都是从根目录出发而生成的，如下图所示。

![](https://tva1.sinaimg.cn/large/e6c9d24ely1h288e2pnidj20y208waag.jpg)

**/root：**一般根目录下只存放目录，不存放文件。

**/bin：**存放可执行二进制文件的目录，如常用命令 ls、tar、mv、cat 等。 

**/home：**为用户设置的目录，如用户 user 的主目录就是/home/user，也可以用~user 表示。

**/dev：**device系统硬件设备目录，Linux系统所有的硬件都通过文件表示，访问该目录下某个文件，相当于访问某个设备，比如/dev/cdrom是光驱。

**/etc：**存放系统配置文件的目录，比如：/ect/passwd 用于存储用户信息的文件、/etc/group 用于存储组别信息的文件。

**/lib：**存放根文件系统程序运行所需要的共享库及内核模块。共享库又叫作动态链接共享库，作用类似Windows里的.dll文件，存放了根文件系统程序运行所需的共享文件。

**/sbin：**放置系统管理员使用的可执行命令， 如 fdisk、shutdown、mount 等。与/bin 不同的是，这几个目录是给系统管理员 root 使用的命令，一般用户只能"查看"而不能设置和使用。

**/tmp：**临时文件目录，用于存放各种临时文件，是公用的临时文件存储点，系统重启后不会被保存。

**/usr：**unix system resource，应用程序存放目录，/usr/bin 存放应用程序，/usr/share 存放共享数据，/usr/lib 存放一些函数库文件， /usr/local存放软件升级包等。

**/var：**存放运行时需要改变数据的的文件， 如随时更改的日志文件 /var/log 。

**/mnt：**系统管理员安装临时文件系统的安装点，系统提供这个目录是让用户临时挂载其他的文件系统。

**/boot：**放置 Linux 系统启动时用到的一些文件，如Linux 的内核文件、引导程序等。

**/opt：**给主机额外安装软件所摆放的目录。

**/proc：**内存映射目录，该目录可以查看系统的相关信息。操作系统运行时，进程信息及内核信息(比如cpu、硬盘分区、内存信息等)存放在这里。



### 2.Linux存储位置

+ **/bin**

+ **/sbin**

+ **/usr/bin**

+ **/usr/sbin**

#### 常用命令存放位置

![image-20220524193310243](https://tva1.sinaimg.cn/large/e6c9d24ely1h2jq2qaic9j20vk03gdgg.jpg)

#### 头文件存放位置

![image-20220524194203751](https://tva1.sinaimg.cn/large/e6c9d24ely1h2jqbxsn5tj211009wtbk.jpg)



### 3.Linux常用命令

- ### 路径

```bash
pwd									#print work directory
ls									#list files
cd folder_path			#enter folder_path
cd .. 							#back to previous folder
cd ~    						#back to Home directory
exit								#exit bash
```

- ### 文件夹

```bash
mkdir new_folder		#create new_folder in work directory

rm -ri folder_name	#remove folder with interaction
rm -rf folder_name	#remove folder without interaction
rmdir empty_folder	#remove empty_folder(not recommended)
```

- ### 文件

```bash
touch new.txt 						#create new.txt in work directory

echo "hello" > new.txt		#create new.txt with content "hello"
echo "world" >> new.txt	  #append "world" to new.txt

cat test.txt							#show the content of test.txt

cat > test.txt            #create test.txt with new_content
new_content
⌃+D
cat >> test.txt           #append new content to test.txt
new_content
⌃+D

vi test.txt								#open "vi" to modify test.txt
vim test.txt							#open "vim" to modify test.txt
```



## 实验内容

### 1. Linux常用命令实践

#### 1.1 ls命令

> ls → list directory contents

##### ls

```bash
ls
```

![image-20220515164215572](https://tva1.sinaimg.cn/large/e6c9d24ely1h296k2o2bgj2158034wf2.jpg)

##### ls -l

```bash
ls -l  #以长格式列出文件的详细信息
```

![image-20220515164530190](https://tva1.sinaimg.cn/large/e6c9d24ely1h296nfymlmj20y40getct.jpg)

##### ls -a

```bash
ls -a  #列出目录下的所有文件，包括以 . 开头的隐含文件。
```

![image-20220515164807708](https://tva1.sinaimg.cn/large/e6c9d24ely1h296q6axo6j21r206mgnc.jpg)

##### ls -s

```bash
ls -s  #在每个文件名后输出该文件的大小。
```

![image-20220515164215572](https://tva1.sinaimg.cn/large/e6c9d24ely1h296k2o2bgj2158034wf2.jpg)



#### 1.2 cat命令

> cat → concatenate and print files

##### cat

```bash
cat file_name.txt  #显示输出文档的内容
```

![image-20220515170144998](https://tva1.sinaimg.cn/large/e6c9d24ely1h2974dn4lpj2112086752.jpg)

##### cat -n

```bash
cat -n file_name.txt  #显示输出文档时，对输出文档的行数进行编号，从1开始
```

![image-20220515170925160](https://tva1.sinaimg.cn/large/e6c9d24ely1h297cbns8pj212g088757.jpg)

##### cat -b

```bash
cat -b file_name.txt  #显示输出文档时，对输出文档的非空行数进行编号，从1开始
```

![image-20220515171057080](https://tva1.sinaimg.cn/large/e6c9d24ely1h297dx9nqfj212g084gmi.jpg)

##### cat -s

```bash
cat -s file_name.txt  #显示输出文档时，将输出文档的多行空格显示为一行空格
```

![image-20220515171611129](https://tva1.sinaimg.cn/large/e6c9d24ely1h297jdhdoaj212e06emy6.jpg)

##### cat -e

```bash
cat -e file_name.txt  #显示输出文档时，在每行结束处显示$
```

![image-20220515171755091](https://tva1.sinaimg.cn/large/e6c9d24ely1h297l62i7dj212c07uaba.jpg)

##### cat > 

```bash
cat >new_test.txt  #创建空白的new_test.txt文件，并且写入下面内容
add new text here.


There are 3 blank lines in this new file.
#输入control+D来结束输入
```

![image-20220515172620783](https://tva1.sinaimg.cn/large/e6c9d24ely1h297ty2l9jj213a07qt9m.jpg)

![image-20220515173021499](https://tva1.sinaimg.cn/large/e6c9d24ely1h297y4dldgj20zm0923zl.jpg)

##### cat >>

```bash
cat >>new_test.txt  #向new_test.txt文件中追加内容
This line is appended to the file by using >>
#输入control+D来结束输入
```

![image-20220515173434034](https://tva1.sinaimg.cn/large/e6c9d24ely1h2982hs9w6j214q0dcgoi.jpg)

##### cat [file1] [file2]

```bash
cat file1.txt file2.txt  #将file1与file2内容连接起来并显示（不改变原file1，file2内容）
```

![image-20220515174226239](https://tva1.sinaimg.cn/large/e6c9d24ely1h298aop9j9j216w0d2dgy.jpg)

##### cat [file1] [file2] >[file3]

```bash
cat file1.txt file2.txt >file3.txt  #创建file3，将file1与file2内容连接起来并且写入file3中
```

![image-20220515174850845](https://tva1.sinaimg.cn/large/e6c9d24ely1h298hczdyij21cy0g4766.jpg)



#### 1.3 chmod命令

> chmod → change file mode bits

##### ll [file]

```bash
ll file1.txt  #查看指定文档的权限
```

![image-20220517084621142](https://tva1.sinaimg.cn/large/e6c9d24ely1h2b41iftgbj210k09eabu.jpg)



##### chmod [user_type] [+/-] [r/w/x] [file]

```bash
chmod u-w file1.txt  #删除owner的写入权限
```

![image-20220517091613281](https://tva1.sinaimg.cn/large/e6c9d24ely1h2b4wkzr1ij214a086jtu.jpg)

```bash
chmod -w file1.txt  #删除file1.txt的写入权限
chmod +w file1.txt  #添加file1.txt的写入权限
```

![image-20220517085657642](https://tva1.sinaimg.cn/large/e6c9d24ely1h2b4cjjghqj21740lkjy3.jpg)

用户类型

| who  |  用户类型   |        说明         |
| :--: | :---------: | :-----------------: |
|  u   |    owner    |     文件所有者      |
|  g   |    group    |  文件所有者所在组   |
|  o   | other users |    所有其他用户     |
|  a   |     all     | 所有用户，相当于ugo |

> Linux/Unix的**文件调用权限**分为三级 : **文件所有者（Owner）**、**用户组（Group）**、**其它用户（Other Users）**

操作符号

| Operator |                          说明                          |
| :------: | :----------------------------------------------------: |
|    +     |                 添加指定用户类型的权限                 |
|    -     |                 删除指定用户类型的权限                 |
|    =     | 设置指定用户权限的设置，即将用户类型的所有权限重新设置 |

权限符号

| operator | 说明 |
| :------: | :--: |
|    r     | 读取 |
|    w     | 写入 |
|    x     | 执行 |



#### 1.4 cp命令

> cp → copy files or directories

##### cp [file1] [file2]

```bash
cp file1.txt file2.txt  #将file1.txt复制到file2.txt
```

![image-20220517093040562](https://tva1.sinaimg.cn/large/e6c9d24ely1h2b5bmreu8j217s08cdhq.jpg)

##### cp [file] [folder]

```bash
cp file1.txt test  #将file1.txt复制到test文件夹中
```

![image-20220517093828335](https://tva1.sinaimg.cn/large/e6c9d24ely1h2b5jqiyvfj2152082q50.jpg)



#### 1.5 mv命令

> mv → move(rename) files

##### mv [file1] [file2]

```bash
mv file1.txt file2.txt #将当前目录下的文件 file1 更名为 file2
```

![image-20220517140751174](/Users/rickyx/Library/Application Support/typora-user-images/image-20220517140751174.png)

##### mv [file] [folder]

```bash
mv file2.txt test  #将file2.txt移动至同一目录下的test文件夹中
```

![image-20220517141618133](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bdktpynaj21500d20vu.jpg)

```bash
mv file2.txt ~/Desktop  #将file2.txt移动至桌面
```

![image-20220517142106800](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bdptunddj21b00880vk.jpg)

##### mv [file] ..

```bash
 mv file1.txt ..  #将file1.txt移动至上一级目录中
```

![image-20220517143155906](https://tva1.sinaimg.cn/large/e6c9d24ely1h2be13bihoj213y09qdik.jpg)



#### 1.6 rm命令

> rm → remove files or directories

##### rm [file]

```bash
rm file1.txt  #删除file1.txt
```

![image-20220517151802470](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bfd2gi4vj210s07wjtc.jpg)

##### rm -i [file]

```bash
rm -i file1.txt  #以交互的方式删除file1.txt
```

![image-20220517150524405](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bezx6mmwj210i09mdie.jpg)

##### rm -rf [folder]

```bash
rm -rf folder7  #删除整个folder7目录，无交互
```

![image-20220517152304592](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bfib724bj20yw080jtc.jpg)

##### rm -ri [folder]

```bash
rm -ri folder2  #删除整个folder7目录，有交互
```

![image-20220517152721342](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bfmrens0j21300em78h.jpg)



#### 1.7 mkdir命令

> mk → make directories

##### mkdir [folder]

```bash
mkdir folder  #在当前工作目录中创建新的目录folder
```

![image-20220517143703047](https://tva1.sinaimg.cn/large/e6c9d24ely1h2be6eh8qcj216c082q56.jpg)

##### mkdir [folder1 folder2 folder3]

```bash
mkdir folder4 folder5 folder6  #在当前工作目录中创建新的目录folder
```

![image-20220517144031339](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bea1296nj217609iwh7.jpg)

##### mkdir -p [folder/subfolder]

```bash
mkdir -p folder7/test  #在当前工作目录中创建带有子目录的目录
```

![image-20220517144236875](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bec72q4fj21160b8dgk.jpg)



#### 1.8 rmdir命令

> rmdir → remove **empty** directories

##### rmdir [folder]

```bash
rmdir folder6 folder5 folder4  #删除空目录folder6/5/4
```

![image-20220517144830102](https://tva1.sinaimg.cn/large/e6c9d24ely1h2beibqxbyj21bs09ktbq.jpg)

注意点：rmdir命令仅支持删除空目录，若选择的目录是非空目录，则会报错。

![image-20220517145314120](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ben97dyzj21bo0640us.jpg)



#### 1.9 cd命令

##### cd [directory]

```bash
cd test  #切换至指定目录
```

![image-20220517082636083](https://tva1.sinaimg.cn/large/e6c9d24ely1h2b3gymervj20vq04sdgs.jpg)

##### cd ..

```bash
cd ..  #返回上一级目录
```

![image-20220517082932749](https://tva1.sinaimg.cn/large/e6c9d24ely1h2b3k197uaj20ww050aay.jpg)

##### cd ~

```bash
cd ~  #进入用户主目录
```

![image-20220517083307053](https://tva1.sinaimg.cn/large/e6c9d24ely1h2b3nqjnmgj20ti04wgmb.jpg)

##### cd /

```bash
cd /  #进入根目录
```

![image-20220517083456655](https://tva1.sinaimg.cn/large/e6c9d24ely1h2b3pmxlfwj20tc04m74v.jpg)



#### 1.10 pwd命令

> pwd → print name of current/working directory

##### pwd

```bash
pwd  #显示当前工作目录的绝对路径
```

![image-20220517082159157](https://tva1.sinaimg.cn/large/e6c9d24ely1h2b3c5y6huj20vk02u0t7.jpg)



### 2. Linux其他命令实践

#### 2.1 date命令

> date → print or set the system date and time

##### date

```bash
date  #显示当前日期信息
```

![image-20220516160754872](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ab6nifm3j20w402qaaj.jpg)



#### 2.2 echo命令

> echo → display a line of text

##### echo

```bash
echo "hello\tworld"   #显示字符串，一般起到提示的作用
```

![image-20220516200057058](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ahx49tr7j214q0300t8.jpg)

##### echo -e

```bash
echo -e "hello\tworld"   #显示字符串，转义字符生效
```

![image-20220516200347827](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ai033ylyj21680300t8.jpg)

##### echo -n

```bash
echo -n "hello\tworld"   #显示字符串，结尾不换行
```

![image-20220516200320603](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ahzllkz6j216m030my2.jpg)

##### echo string > file1

```bash
echo -e "hello\tworld" >file1.txt   #将"hello world"覆盖至file1.txt中
```

![image-20220516200938163](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ai65onttj21c20523zo.jpg)

##### echo string >> file1

```bash
echo -e "hello\tworld" >>file1.txt   #将"hello world"追加至file1.txt中
```

![image-20220516201206735](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ai8qe4w9j21bi06ggmw.jpg)

##### echo “\033[xxm……\033[0m”

```bash
echo -e "\033[33mhello\tworld\033[0m"  #显示彩色字体
```

![image-20220516201731150](https://tva1.sinaimg.cn/large/e6c9d24ely1h2aieck6xaj21es036dgh.jpg)

```bash
#彩色字体参数表
\033[30m 黑色字 \033[0m
\033[31m 红色字 \033[0m
\033[32m 绿色字 \033[0m
\033[33m 黄色字 \033[0m
\033[34m 蓝色字 \033[0m
\033[35m 紫色字 \033[0m
\033[36m 天蓝字 \033[0m
\033[37m 白色字 \033[0m
\033[40;37m 黑底白字 \033[0m
\033[41;37m 红底白字 \033[0m
\033[42;37m 绿底白字 \033[0m
\033[43;37m 黄底白字 \033[0m
\033[44;37m 蓝底白字 \033[0m
\033[45;37m 紫底白字 \033[0m
\033[46;37m 天蓝底白字 \033[0m
\033[47;30m 白底黑字 \033[0m
```



#### 2.3 cal命令

> cal → calendar 

##### cal

```bash
cal  #显示当前月份日历
```

![image-20220516160951028](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ab8nr6xhj20vi0d4q45.jpg)

##### cal month year

```bash
cal 10 2022  #显示指定月份日历
```

![image-20220516161330131](https://tva1.sinaimg.cn/large/e6c9d24ely1h2abcha2x8j20zw0eo75o.jpg)

##### cal -j

```bash
cal -j  #显示自1月1日起的总天数
```

![image-20220516161454632](https://tva1.sinaimg.cn/large/e6c9d24ely1h2abdxde8lj20xa0d4dhh.jpg)

##### cal -y

```bash
cal -y  #显示当前年历
```

![image-20220516194534708](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ahh4dsdvj20u00u343g.jpg)



#### 2.4 clear命令

> clear → clear the terminal screen

##### clear

```bash
clear  #使终端显示页向后翻一页，实现清屏
```



#### 2.5 ps命令

> ps → report a snapshot of the current processes

##### ps -l

```bash
ps -l  #较长、较详细的将属于本次登入用户的进程列出来
```

![image-20220517194126372](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bmz44l5ij215s06cdhj.jpg)

各个表头的含义为：

- F：代表这个进程的flag，如果是4，则代表使用者为 super user
- S：代表这个进程的状态stat
- UID：代表执行者的userId
- PID：进程的id
- PPID：父进程的id
- C：占用CPU资源的百分比
- PRI：指进程的执行优先级(Priority的简写)，其值越小越早被执行
- NI：代表进程的nice值，其表示进程可被执行的优先级的修正数值
- ADDR：代表进程的地址，它指出该进程在内存的哪个部分，如果是个正在运行的程序，一般都是"-"
- SZ：占用的内存大小
- WCHAN：判断当前进程是否正在运行，若为"-"，则代表正在运行；若该进程处于休眠状态，该值就是它在内核中的地址
- TTY：该进程是在那个终端机上面运行，若与终端机无关，则显示?，另外，tty1-tty6 是本机上面的登入者程序，若为 pts/0 等等的，则表示为由网络连接进主机的程序。
- TIME：占用CPU的时间
- CMD：所下达的指令名称

##### ps -aux

```bash
ps -aux  #显示后台运行的进程
```

![image-20220517191900654](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bmbsqemdj21900fo42c.jpg)

各个表头的含义为：

- USER：表示该进程属于哪个用户
- PID：进程id
- %CPU：该进程占用CPU资源的百分比
- %MEM：该进程占用内存的百分比
- VSZ：该进程使用掉的虚拟内存量 (Kbytes)
- RSS：该进程占用的固定的内存量 (Kbytes)
- TTY：该进程是在那个终端机上面运行，若与终端机无关，则显示?，另外，tty1-tty6 是本机上面的登入者程序，若为 pts/0 等等的，则表示为由网络连接进主机的程序。
- STAT：代表该进程目前的状态，主要的状态有：
  - R：该进程正在运行
  - S：该进程正在休眠，但可被某些信号(signal)唤醒
  - D：无法中断的休眠状态(通常为IO进程)
  - T：该进程已经停止
  - Z：僵死状态，该进程应该已经终止，但是其父进程却无法正常的终止它，造成zombie(疆尸)程序的状态
  - W：等待状态，等待内存的分配
  - <：高优先级的进程
  - N：低优先级的进程
- START：该进程被触发启动的时间
- COMMAND：该进程的实际指令

##### ps -u

```bash
ps -u  #显示属于自己的进程
```

![image-20220517191656939](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bm9no5jsj21940ban0p.jpg)

##### ps -ef | grep [xxx]

```bash
ps -ef | grep java  #查看指定进程，如关于java的进程
```

![image-20220517195239326](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bnau0ww6j215u036dgp.jpg)



#### 2.6 kill命令

> kill → send a signal to a process

##### kill -l

```bash
kill -l  #显示所有信号名称
```

![image-20220517192949958](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bmn1oe6nj218c0mstgu.jpg)

> 只有第9种信号 **“强制退出”** (SIGKILL)才可以无条件终止进程，其他信号进程都有权利忽略。

##### kill -9 [PID]

```bash
#先筛选出相关进程
> ps -ef | grep java
root     16934     1  0 Feb25 ?        00:18:13 java -jar demo.jar

#彻底杀死该进程
> kill -9 16934
```



#### 2.7 who命令

> who → show who is logged on

##### who 

```bash
who  #显示当前登录系统的用户
```

![image-20220517201556841](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bnz10qyqj20oy03a0t5.jpg)

##### who --version

```bash
who --version  #查看当前版本
```

![image-20220517201903969](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bo29le1qj218a0datbz.jpg)

##### whoami

```bash
whoami  #显示当前登录的用户名
```

![image-20220517201354675](https://tva1.sinaimg.cn/large/e6c9d24ely1h2bnwwonzuj20q002w3yq.jpg)





#### 2.8 reboot命令

> reboot → halt, power-off or reboot the machine

##### reboot 

```bash
reboot  #重新启动计算机，它的使用权限是系统管理者。
```



#### 2.9 passwd命令

> passwd → change user password

##### passwd

```bash
passwd  #修改当前用户登陆密码
```

![image-20220518095431116](https://tva1.sinaimg.cn/large/e6c9d24ely1h2cbmqu2mkj20uq09ujsw.jpg)

##### passwd -d [user]

```bash
passwd -d parallels  #删除用户parallels的密码
```

![image-20220518095431116](https://tva1.sinaimg.cn/large/e6c9d24ely1h2cbmqu2mkj20uq09ujsw.jpg)



#### 2.10 su命令

> su → run a command with **substitute user** and group ID

##### cat

```bash
>whoami #显示当前用户
ricky
>pwd    #显示当前目录
/home/ricky
>su root #切换到root用户
密码： 
>whoami #显示当前用户
root
```



#### 2.11 man命令

> man → an interface to the system reference manuals

##### man 

```bash
man ls  #显示ls命令的使用指南
```

![image-20220518094554866](https://tva1.sinaimg.cn/large/e6c9d24ely1h2cbdsuf8dj20z80u00wa.jpg)



## 实验作业

### 1.who 命令

1. 有多少用户正在使用你的Linux系统？给出显示的结果

![image-20220518101457337](https://tva1.sinaimg.cn/large/e6c9d24ely1h2cc80agybj20xg04umxl.jpg)

2. 哪个用户登录的时间最长？给出该用户登录的时间和日期。

![image-20220518101422734](https://tva1.sinaimg.cn/large/e6c9d24ely1h2cc7emn40j20sw03a0t7.jpg)



### 2.uname 命令

使用下面的命令显示有关你计算机系统信息：uname（显示操作系统的名称）， uname –n（显示系统域名），uname –p（显示系统的CPU名称）

1. 你的操作系统名字是什么？

![image-20220518101657785](https://tva1.sinaimg.cn/large/e6c9d24ely1h2cca39q5uj20u4038wer.jpg)

2. 你计算机系统的域名是什么？

![image-20220518101728024](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ccamdy8ij20vu036jru.jpg)

3. 你计算机系统的CPU名字是什么？

![image-20220518101838598](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ccbugx4hj20vs038glx.jpg)



### 3.passwd命令

1. 使用passwd命令修改你用whoami命令找到的用户的密码。

![image-20220518102204758](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ccff88gvj21080d2tas.jpg)

2. 然后使用who -a命令来看看你的用户名和同一系统其他用户的登录密码。

   ![image-20220518102402592](https://tva1.sinaimg.cn/large/e6c9d24ely1h2cchgmh7ij210606ewfm.jpg)



### 4.PS1提示符

1. 在shell提示符后，输入echo $PS1并按回车键，系统怎样回答？ 

![image-20220518102517782](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ccirishaj21ga04umym.jpg)

> ***PS1为shell命令行界面的主提示符。***

2. 在shell提示符后，输入PS1=%并按回车键，显示屏有什么变化？

![image-20220518103358099](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ccrsk25fj20vw09wq4h.jpg)

3. 在shell提示符后，输入set 并按回车键，系统显示环境变量。给出你系统中的环境变量和它的值。

![image-20220518103610752](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ccu3gtcnj21gc0jadk3.jpg)



### 5.综合实践

本实验用到的命令还有：date、cal、pwd、write、uptime、man等。

1. 登录你的Linux系统。

![image-20220518112316632](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ce73miwtj211u0iojrv.jpg)



2. 用命令date显示当前的时间，给出显示的结果。

```bash
date
```

![image-20220518103855653](https://tva1.sinaimg.cn/large/e6c9d24ely1h2ccwzca8aj20te036mxn.jpg)



3. 用cal命令显示下列年份的日历：4、52、1752、1952、2005、2006

a) 给出你显示以上年份年历的命令

```bash
cal 4
cal 52
cal 1752
cal 1952
cal 2005
cal 2006
```

b) 1752年有几天，为什么？

![image-20220518104447563](https://tva1.sinaimg.cn/large/e6c9d24ely1h2cd32wistj20yy0awmyn.jpg)

![image-20220518104853546](https://tva1.sinaimg.cn/large/e6c9d24ely1h2cd7cj882j212u096myw.jpg)

![image-20220518104516952](https://tva1.sinaimg.cn/large/e6c9d24ely1h2cd3lk1vaj20zc0d6acl.jpg)

> 1752年由于某些历史原因，在9月份少了11天，全年仅有355天。



4. 用pwd显示你的主目录(home directory)名字，给出pwd显示的结果。

```bash
pwd
```

![image-20220518105142466](https://tva1.sinaimg.cn/large/e6c9d24ely1h2cda9x6foj20q203it92.jpg)



5. 使用alias 命令显示系统中的命令的别名，给出显示的结果。

```bash
alias
```

![image-20220518105247054](https://tva1.sinaimg.cn/large/e6c9d24ely1h2cdbdb42pj21g40ge41l.jpg)



6. 使用uptime命令判断系统已启动运行的时间和当前系统中有多少登录用户，给出显示的结果。

```bash
uptime
```

![image-20220518105353859](https://tva1.sinaimg.cn/large/e6c9d24ely1h2cdcj7ealj20y403ggm7.jpg)



7. 通过因特网或 Linux的man命令得到下面的shell命令、系统调用和库函数功能描述及每个命令使用例子：

| Command |                      Short Description                       |                     Use Example                     |
| :-----: | :----------------------------------------------------------: | :-------------------------------------------------: |
|  touch  | update the access and modification times of each FILE to the current time |                    touch [file]                     |
|   cp    |                  copy files and directories                  |                   cp [file] [dir]                   |
|   mv    |                     move (rename) files                      |                   mv [file] [dir]                   |
|   rm    |                 remove files or directories                  |                    rm -rf [dir]                     |
|  mkdir  |                       make directories                       |                     mkdir [dir]                     |
|  rmdir  |                   remove empty directories                   |                     rmdir [dir]                     |
|   ls    |                   list directory contents                    |                         ls                          |
|   cd    |                       change directory                       |                      cd [dir]                       |
|   pwd   |           print name of current/working directory            |                         pwd                         |
|  open   |    open, openat, creat - open and possibly create a file     |           int fd=open("./file",O_RDONLY)            |
|  read   |                 read from a file descriptor                  |              read -p "prompt" [input]               |
|  write  |                send a message to another user                |               n=write(fp, p1+len, 3)                |
|  close  |                   close a file descriptor                    |                  int close(int fd)                  |
|  pipe   |                         create pipe                          | int pipe(int pipefd[2]);  #fd[0]为读端,fd[1] 为写端 |
| socket  |             create an endpoint for communication             |    int socket(int domain,int type,int protocol)     |
| mkfifo  |                   make FIFOs (named pipes)                   |    int mkfifo(const char* pathname, mode_t mode)    |
| system  |                   execute a shell command                    |          int system(const char  *command)           |
| printf  |                    format and print data                     |             printf [format] [arguments]             |


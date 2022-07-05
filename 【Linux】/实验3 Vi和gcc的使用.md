# 实验三 编辑器 vim 和编译器 gcc 的使用

![【封面】Linux实验报告](https://tva1.sinaimg.cn/large/e6c9d24ely1h3spimoc4qj21ds0l4whu.jpg)

作者｜Ricky的水果摊

时间｜2022年6月28日

---

## 实验目的

掌握编辑器 vim的基本操作，能够使用 vi 来编辑 C 语言源程序；学习indent缩进排版程序的使用；掌握用 gcc 进行编译；掌握用gdb进行调试



## 实验原理

### 1. vi和vim简介

[Vi的使用相关博文—CSDN](https://blog.csdn.net/weixin_44618906/article/details/105613454)

#### 1.1 vi

- `vi` 是 `Visual interface` 的简称，是 `Linux` 中 **最经典** 的文本编辑器

- `vi` 的核心设计思想 —— 让程序员的手指始终保持在键盘的核心区域，就能完成所有的编辑操作![image-20220627113058377](https://tva1.sinaimg.cn/large/e6c9d24ely1h3mn7ghgv9j21bw0l4wir.jpg)

- `vi`的特点：
  
  - **不是图形界面**
  
  - 只能编辑 **文本内容**，不能对字体、段落进行排版
  
  - **不支持鼠标操作**
  
  - **没有菜单**
  
  - **只有命令**
  
    

#### 1.2 vim

- `vim` 是从 `vi` 发展出来的一个文本编辑器，支持 **代码补全**、**编译** 及 **错误跳转** 等方便编程的功能特别丰富，在程序员中被广泛使用，被称为 **编辑器之神**



### 2. vi的三种工作模式

#### 2.1 **命令模式**

- 敲击键盘上的 **`ESC`** 进入
- **打开文件首先进入命令模式**，是使用 `vi` 的 **入口**
- 通过 **命令** 对文件进行常规的编辑操作，例如：**定位**、**翻页**、**复制**、**粘贴**、**删除**……
- 在其他图形编辑器下，通过 **快捷键** 或者 **鼠标** 实现的操作，都在 **命令模式** 下实现

#### 2.2 **末行模式**

- 敲击键盘上的 **`: `** 进入
- 要退出 `vi` 返回到控制台，需要在末行模式下输入命令
- **末行模式** 是 `vi` 的 **出口**

| 命令 | 英文         | 功能                           |
| ---- | ------------ | ------------------------------ |
| w    | write        | 保存                           |
| q    | quit         | 退出，如果没有保存，不允许退出 |
| q!   | quit         | 强行退出，不保存退出           |
| wq   | write & quit | 保存并退出                     |

#### 2.3 **编辑模式** 

- 敲击键盘上的 **i **进入
- 正常的编辑文字

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2dgydm5eqj212v0u0q4h.jpg" alt="image-20220519094412188" style="zoom: 33%;" />



### 3. vi的基本操作

#### 3.1 vi打开/新建文件

##### vi [file]

```bash
vi test.c  #若test.c存在，则打开test.c文件
vi new.c   #若new.c不存在，则新建new.c文件
```

![image-20220519095620094](https://tva1.sinaimg.cn/large/e6c9d24ely1h2dhayeox7j218u0aqmxv.jpg)

![image-20220519100802635](https://tva1.sinaimg.cn/large/e6c9d24ely1h2dhn4k7cmj21hg054mxg.jpg)

##### vi [file] +[line]

```bash
vi test.c +3  #打开test.c文件，并且定位至第3行
```

![image-20220519101502719](https://tva1.sinaimg.cn/large/e6c9d24ely1h2dhufppymj20yc0aut9d.jpg)

> PS：如果只带上 `+` 而不指定行号，会直接定位到文件末尾



####  3.2 vi光标移动

##### 1) 上、下、左、右

| 命令 | 功能 | 手指   |
| ---- | ---- | ------ |
| h    | 向左 | 食指   |
| j    | 向下 | 食指   |
| k    | 向上 | 中指   |
| l    | 向右 | 无名指 |

![image-20220627112926865](https://tva1.sinaimg.cn/large/e6c9d24ely1h3mn5vcjx8j21bq0l4q72.jpg)

##### 2) 行内移动

| 命令 |              功能              |
| :--: | :----------------------------: |
|  w   |        向后移动一个单词        |
|  b   |        向前移动一个单词        |
|  0   |              行首              |
|  ^   | 行首，第一个不是空白字符的位置 |
|  $   |              行尾              |

##### 3) 行数移动

|   命令   |                功能                |
| :------: | :--------------------------------: |
|    gg    |              文件顶部              |
|    G     |              文件末尾              |
| [line]gg |   行首，第一个不是空白字符的位置   |
| [line]G  |   行首，第一个不是空白字符的位置   |
|  :数字   | 行首，第一个不是不是空白字符的位置 |



#### 3.3 vi整行操作

##### 1) 删除整行

|  命令   |          功能           |
| :-----: | :---------------------: |
|   dd    | 删除当前光标所在的整行  |
| [num]dd | 删除当前光标开始的n整行 |

##### 2) 复制整行与粘贴

|  命令   |            功能            |
| :-----: | :------------------------: |
|   yy    |   复制当前光标所在的整行   |
| [num]yy |  复制当前光标开始的n整行   |
|    p    |  将复制内容粘贴光标的后面  |
|    P    | 将复制内容粘贴至当前光标前 |

##### 3) 撤销和恢复撤销

| 命令     | 英文 | 功能           |
| -------- | ---- | -------------- |
| u        | undo | 撤销上次命令   |
| CTRL + r | redo | 恢复撤销的命令 |



#### 3.4 vi末行搜索

|      命令       |                     功能                      |
| :-------------: | :-------------------------------------------: |
| /[string]+Enter | 搜索当前string,光标跳转至第一个string出现位置 |
|        n        |        光标跳转至下一个string出现位置         |
|     shift+n     |        光标跳转至上一个string出现位置         |



#### 3.5 vi行号显示与语法高亮

|       命令       |     功能     |
| :--------------: | :----------: |
|      set nu      | 添加行号显示 |
|     set nonu     | 取消行号显示 |
| syntax enable on | 显示语法高亮 |
|    syntax off    | 取消语法高亮 |



#### 3.6 vi的异常退出

假设使用vi编辑hello.c时，出现异常退出

![image-20220525235519697](https://tva1.sinaimg.cn/large/e6c9d24ely1h2l39r9qxhj21gu0iuadz.jpg)

系统会自动生成**.swp**隐藏文件

![image-20220525235623882](https://tva1.sinaimg.cn/large/e6c9d24ely1h2l3ave6arj21cu06ct9j.jpg)

再次使用vi进入hello.c时，会出现如下提示

![image-20220526000046611](https://tva1.sinaimg.cn/large/e6c9d24ely1h2l3fff3glj216k0u0tfo.jpg)

按D键后，之前的编辑未生效，.swp文件也被删除

![image-20220526000159376](/Users/rickyx/Library/Application Support/typora-user-images/image-20220526000159376.png)

![image-20220526000801005](https://tva1.sinaimg.cn/large/e6c9d24ely1h2l3n01qvdj21dm06ejsb.jpg)



### 4. indent缩进排版程序

##### indent程序的安装

```bash
sudo apt install indent  #安装indent程序
```

![image-20220519112839532](https://tva1.sinaimg.cn/large/e6c9d24ely1h2djz0q2o7j21860j477p.jpg)



##### indent [file.c]

```bash
indent test.c  #对test.c程序进行缩进排版
```

![image-20220519110244254](https://tva1.sinaimg.cn/large/e6c9d24ely1h2dj81q068j219h0u0juy.jpg)



### 5. gcc编译器

#### 5.1 gcc简介

> GCC（GNU Compiler Collection，GNU编译器套件）是由GNU开发的编程语言译器。GNU编译器套件包括C、C++、Objective-C、Java前端，也包括了这些语言的库，如libstdc++，libgcj等。



#### 5.2 gcc安装（以Ubuntu为例）

查看当前

```bash
cd /usr/bin #查看当前Linux系统是否安装了gcc编译器
find gcc
```

![image-20220519111115959](https://tva1.sinaimg.cn/large/e6c9d24ely1h2djgxm4njj20xa04wjs5.jpg)

未安装，执行下行命令

```bash
sudo apt-get install build-essential  #Ubuntu安装gcc
```

已安装，查看当前gcc版本

```bash
gcc -v  #查看当前gcc版本
```

![image-20220519111230722](https://tva1.sinaimg.cn/large/e6c9d24ely1h2dji7nirqj218e0ciwhv.jpg)



#### 5.3 gcc下的编译过程

![image-20220526200112865](https://tva1.sinaimg.cn/large/e6c9d24ely1h2m24iiamjj21m50u00wn.jpg)

##### gcc -E [file.c] -o [name.i] 

```bash
gcc -E test.c -o test.i    #预处理test.c，生成test.i文件
vim test.i                 #查看生成的汇编文件
```

![image-20220526201210897](https://tva1.sinaimg.cn/large/e6c9d24ely1h2m2fw2lqnj21h00ea0vj.jpg)

##### gcc -S [file.c] -o [name.s]

```bash
gcc -S test.c -o test.s  #编译test.c，生成test.s汇编文件
vim test.s               #查看生成的汇编文件
```

![image-20220526200530491](https://tva1.sinaimg.cn/large/e6c9d24ely1h2m28xzyp6j21gs0e4gn2.jpg)

##### gcc [file.c]

```bash
gcc test.c  #编译test.c，默认生成文件名为a.out的可执行文件
./a.out     #执行生成的a.out文件（./代表当前目录）
```

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2dk7nyzc7j21d605kjt2.jpg" alt="image-20220519113658431" style="zoom:67%;" />

##### gcc [file.c] -o [name]

```bash
gcc test.c -o test.out  #编译test.c，生成文件名为test.out的可执行文件
./test.out              #执行生成的test.out文件（./代表当前目录）
```

![image-20220519114144529](https://tva1.sinaimg.cn/large/e6c9d24ely1h2dkcmdot4j214i08w768.jpg)



### 6. gdb调试器

#### 5.1 gdb简介

> GDB（the GNU Project Debugger）是 GNU开源组织发布的一个强大的Linux下的程序调试工具，可以调试 C、C++、Objective-C 和 Pascal 等多种语言的程序



#### 5.2 gdb常用命令

|  命令   |         示例         |              功能              |
| :-----: | :------------------: | :----------------------------: |
|  file   |     file [name]      |    装入想要调试的可执行文件    |
|  break  |     break [line]     |            设置断点            |
| delete  |    delete [line]     |       清除单行的单个断点       |
|  clear  |     clear [line]     |       清除单行的所有断点       |
| disable |    disable [num]     |  设置序号为num的断点暂时失效   |
| enable  |     enable [num]     |  设置序号为num的断点重新生效   |
|   run   |         run          |          运行调试程序          |
|  list   | list [line1],[line2] |    查看line1-line2的源代码     |
|  next   |         next         | 执行一行源代码但不进入函数内部 |
|  step   |         step         | 执行一行源代码而且进入函数内部 |
|  info   |    info [command]    |      显示相关命令当前信息      |
|  kill   |         kill         |          结束当前调试          |
|  print  |     print [var]      |    在屏幕上打印var变量的值     |
|  quit   |         quit         |        退出gdb调试程序         |



#### 5.3 gdb基础调试过程

1. 编译文件，进入gdb调试器

![image-20220527152006587](https://tva1.sinaimg.cn/large/e6c9d24ely1h2mzmalrgpj21bk0pc46f.jpg)

2. 使用list命令显示当前文件源代码

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h2mzoev3twj20te0hogmz.jpg" alt="image-20220527152209097" style="zoom:67%;" />

3. 设置断点，显示断点信息

![image-20220527152402031](https://tva1.sinaimg.cn/large/e6c9d24ely1h2mzqdk5ndj21800aqjtw.jpg)

4. 运行程序至断点1

![image-20220527152512260](https://tva1.sinaimg.cn/large/e6c9d24ely1h2mzrlj79jj20vu06q754.jpg)

5. 单步调试运行

   ![image-20220527163348674](https://tva1.sinaimg.cn/large/e6c9d24ely1h2n1qzbyflj20sy0cw75g.jpg)

6. 结束当前调试

   ![image-20220527163739129](https://tva1.sinaimg.cn/large/e6c9d24ely1h2n1uz2jl7j20qu046wez.jpg)

7. 退出gdb调试程序

![image-20220527163807245](https://tva1.sinaimg.cn/large/e6c9d24ely1h2n1vgf1z4j20xc03474r.jpg)



## 实验作业

用 vi 编辑器写一段 C 语言的程序，并对这个程序的格式进行整理，对程序进行编译，最后运行这个程序。写出你的程序和实现以上操作的全部的指令。

```bash
touch test.c   #创建test.c文件
vi test.c      #使用vi编辑器修改test.c文件的内容
indent test.c  #使用indent程序对test.c文件内容缩进排版
gcc test.c -o test.out  #使用gcc对test.c编译
./test.out
```

![image-20220519153039644](https://tva1.sinaimg.cn/large/e6c9d24ely1h2dqysuj5qj217y0dwwff.jpg)

![image-20220519153004303](https://tva1.sinaimg.cn/large/e6c9d24ely1h2dqy6wyzcj214g050t9q.jpg)


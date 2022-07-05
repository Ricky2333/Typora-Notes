![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月5日



---

## 🌈 今日知识点总结

### 1. 赋值运算符

**赋值运算符** 就是将某个运算后的值，赋给指定的变量，分为 **基本赋值运算符** 和 **复合赋值运算符**。

![image-20220705104452198](https://tva1.sinaimg.cn/large/e6c9d24ely1h3vutxfprkj21c409qq4f.jpg)



🍉 **PS**：**复合赋值运算符** 在赋值时，会有 **隐式强制转换**。

```java
byte b = 2;
b = b + 2;    //编译错误，b + 2的结果为 int类型，无法赋值给 byte类型的变量b
b += 2;       //编译通过，相当于 b = (byte)(b + 2)

short k = 3;
k = k + 1;		//编译错误，k + 1的结果为 int类型，无法赋值给 short类型的变量k
k++;				  //编译通过，相当于 k = (short)(k + 1)
```

<br/>



### 2. 三元运算符

**三元运算符**：`result = [Condition]? [Exp1] : [Exp2]`

![image-20220705105100241](https://tva1.sinaimg.cn/large/e6c9d24ely1h3vv0bczdmj20ws07wt9r.jpg)

```java
int a = 10;
int b = 11;
int c = (a>b) ? a++ : b--;  //Condition为 false，c的值取 Exp2，即 c = b--；
```

<br/>

🍉 **PS**：`Exp1`和 `Exp2` 要为 **可以赋给接收变量的类型**(或可以自动转换)

**示例**：`int c = (3>7) ? 8.9 : 9.9;   //编译错误，将double类型的常量赋值给int类型变量c`



<br/>

### 3. 位运算符

![image-20220705110454915](https://tva1.sinaimg.cn/large/e6c9d24ely1h3vves1c5oj20z80duwfv.jpg)

| 符号 |   含义   |   示例   | 结果 |
| :--: | :------: | :------: | :--: |
|  &   |  按位与  |  -2 & 3  |  2   |
|  \|  |  按位或  |  -2 & 3  |  -1  |
|  ^   | 按位异或 |  -2 ^ 3  |  -3  |
|  ~   | 按位取反 |   ~-2    |  1   |
|  >>  | 算数右移 | 15 >> 3  |  1   |
|  <<  | 算数左移 | 15 << 3  | 120  |
| >>>  | 逻辑右移 | 15 >>> 3 |  1   |

**算术右移** >>：低位溢出，符号位不变，并用符号位补溢出的高位

**算术左移** << ：符号位不变，低位补 0

**逻辑（无符号）右移** >>> ：低位溢出，高位补 0

 ☘️ 知识拓展：原码、反码、补码与位运算过程



<br/>

### 4. Java 运算符优先级表

| 优先级 |                            运算符                            |  结合性   |
| :----: | :----------------------------------------------------------: | :-------: |
|   1    |                        .  ()  []  {}                         |   L → R   |
|   2    |                         ++  --  ~  !                         | **R → L** |
|   3    |                           *  /  %                            |   L → R   |
|   4    |                             +  -                             |   L → R   |
|   5    |                         >>  <<  >>>                          |   L → R   |
|   6    |                   <  >  <=  >=  instanceof                   |   L → R   |
|   7    |                            ==  !=                            |   L → R   |
|   8    |                              &                               |   L → R   |
|   9    |                              ^                               |   L → R   |
|   10   |                              \|                              |   L → R   |
|   11   |                              &&                              |   L → R   |
|   12   |                             \|\|                             |   L → R   |
|   13   |                             ? :                              |   L → R   |
|   14   | =   +=   -=  /=   %=   &=   \|=   ^=   ~=   >>=   <<=   >>>= | **R → L** |

+ 只有 **单目运算符**、**赋值运算符** 是 **从右向左** 运算。

+ 优先级关系 **助记口诀**：「 **单目乘除为关系，逻辑三目后赋值 **」



<br/>

### 5. Java 标识符规则与规范

**标识符的概念**：

 Java 中 **各种变量、方法和类 **等 **命名时使用的字符序列** 称为「**标识符**」



**标识符的命名规则（必须遵守）**：

+ 标识符由字母 `a-z / A-Z`，数字 `0-9` ，特殊字符 `_` 或 `$` 组成 

+ 标识符 **不可以由数字开头**，只能以字母或特殊字符开头。

+ 标识符 **不可以使用关键字和保留字**，但能包含关键字和保留字。
+ 标识符 **严格区分大小写**，但长度无限制。

+ 标识符 **不能包含空格**。



**标识符的命名规则规范（建议遵守）**：

+ **类、接口名**：采用「**大驼峰命名法**」，所有单词的首字母大写。形如：`XxxYyyZzz`，示例：`NewWork`

+ **变量名、方法名**：采用「**小驼峰命名法**」，第一个单词首字母小写，第二个单词开始每个单词首字母大写。形如：`xxxYyyZzz`，示例： `newWorkProject`

+ **常量名**：所有字母都大写，每个单词用下划线连接。形如：`XXX_YYY_ZZZ`，示例：`TYPING_SPEED`



### 6. Java 关键字表和保留字表

☘️ 知识拓展：[Java 关键字表和保留字表详解—CSDN](https://blog.csdn.net/qq_46025844/article/details/125624559?csdn_share_tail=%7B%22type%22%3A%22blog%22%2C%22rType%22%3A%22article%22%2C%22rId%22%3A%22125624559%22%2C%22source%22%3A%22qq_46025844%22%7D&ctrtid=x8An5)

**关键字表**

| abstract   | **assert**   | **boolean** | **break**  | **byte** |
| ---------- | ------------ | ----------- | ---------- | -------- |
| case       | catch        | char        | class      | const    |
| continue   | default      | do          | double     | else     |
| enum       | extends      | final       | finally    | float    |
| for        | goto         | if          | implements | import   |
| instanceof | int          | interface   | long       | native   |
| new        | package      | private     | protected  | public   |
| return     | strictfp     | short       | static     | super    |
| switch     | synchronized | this        | throw      | throws   |
| transient  | try          | void        | volatile   | while    |

「关键字」是被赋予了特殊含义，有专门用途的字符串（ **均为小写** ）

**保留字表**

| byValue | cast | future | generic | inner | operator |
| ------- | ---- | ------ | ------- | ----- | -------- |
| outer   | rest | var    | goto    | const |          |

「保留字」在现有 Java版本尚未使用，但以后版本可能会作为关键字使用，命名时要避免。



<br/>

## ✏️ 今日随记

学习 Java 的 **第 7 天**。⏰

今天把上一章剩下的内容整理的差不多了，还差 「位运算原理」这一块知识点没整理。打算之后把 **位运算、三码（原反补）** 等知识单独开一篇文章，仔细梳理梳理，敬请期待。🧑🏻‍💻

不多说了，今天整理还是花了很长时间的，耽误了不少看网课的时间，先润去看网课了 💨

---

**相关博客**：

[【Java】学习日记 Day6](https://blog.csdn.net/qq_46025844/article/details/125608129?spm=1001.2014.3001.5502)

[【Java】学习日记 Day5](https://blog.csdn.net/qq_46025844/article/details/125579422?spm=1001.2014.3001.5501)

[【Java】学习日记 Day4](https://blog.csdn.net/qq_46025844/article/details/125567560?spm=1001.2014.3001.5501)






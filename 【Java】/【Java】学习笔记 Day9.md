![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月7日



---

## 🌈 今日知识点总结

### Java 编程练习（程序控制结构专题）

🧑🏻‍💻 **程序框架** + **键盘输入** 源代码（练习代码均 **省略** 此部分代码）

```java
import java.util.Scanner;   //导入Scanner类
public class Exercise{
	public static void main(String[] args) {
		Scanner myScanner = new Scanner(System.in);   //创建一个Scanner类的对象myScanner
    
    int n = myScanner.nextInt(); //获取不同类型的输入值，此处以 int类型为例
    ...
	}
}
```



#### 🟢 1. 闰年判断（「分支结构」习题）

📝 **题目描述**：

>  判断一个年份是否是闰年。（请使用 `If` 语句实现）

🧑🏻‍💻 **源代码**：

```java
int year = myScanner.nextInt();

//判断year的变量值是否为闰年
if (year % 4 ==0 && year % 100 !=0 || year % 400 ==0){
	System.out.println(year + " is a leap year");
} else {
	System.out.println(year + " is not a leap year");
}
```

<br/>

#### 🟢 2. 季节判断（「分支结构」习题）

📝 **题目描述**：

> 键盘输入一个月份，打印该月份所属的季节，其中 3～5月 为春季、6～8月 为夏季、9～11为 秋季、12～2 月为冬季。（请使用 `Switch` 语句 ✖️ **穿透原理** 实现）

🍉 **提示**：利用Switch语句的穿透原理，可以减少输出语句的重复书写，提高效率。

🧑🏻‍💻 **源代码**：

```java
int month = myScanner.nextInt();

switch(month){
  case 3:
  case 4:
  case 5:
    System.out.println("Spring");  //利用Switch语句的穿透原理，减少了输出语句的重复
    break;
  case 6:
  case 7:
  case 8:
    System.out.println("Summer");
    break;
  case 9:
  case 10:
  case 11:
    System.out.println("Autumn");
    break;
  case 12:
  case 1:
  case 2:
    System.out.println("Winter");
    break;
  default:
    System.out.println("Input Error");
}
```

<br/>

#### 🟢 3. 9 ✖️ 9 乘法表（「循环结构」习题）

📝 **题目描述**：

> 打印 9 ✖️ 9 乘法表。

🍉 **提示**：

循环类问题可以采用「**化繁为简**」+ 「**先死后活**」的编程思想，逐步求解问题。

🧑🏻‍💻 **源代码**：

```java
for(int i = 1;i <= 9;i++){
  for(int j = 1;j <= i;j++){
    System.out.print(j + " * " + i + " = " + j * i + " ");
	}
  System.out.println("");
}
```

<br/>

#### 🟢 4. 过路费问题（「分支 + 循环结构」习题）

📝 **题目描述**：

> 张三有 100,000 元，他每经过一次路口，需要交费，规则如下：
> 1.当现金 >= 50000时，每次需要交费 5%
> 2.当现金 <= 50000时，每次需要交费 1000
>
> 计算张三可以经过多少个路口（请使用 `while` + `break`语句 实现）

🍉 **提示**：

此类问题可以采用「**化繁为简**」+ 「**先死后活**」的编程思想，逐步求解问题。

🧑🏻‍💻 **源代码**：

```java
double totalMoney = 100000;
int cnt = 0;
while(true){
  if(totalMoney > 50000){
    totalMoney *= 0.95;    //totalMoney -= totalMoney*0.05也可以
  }else if(totalMoney >= 1000){
    totalMoney -=1000;
  }else{									//totalMoney < 1000，退出循环
    break;
  }
  cnt ++;
}
System.out.println(cnt);
```

<br/>

#### 🟡  5. 用户登陆问题（「分支 + 循环结构 + String相等判断」习题）

📝 **题目描述**：

> 实现用户登录验证，有 3 次机会，如果用户名为「Ricky」 ,密码为「Overthinker」，则提示登录成功，否则提示还有几次机会。（请使用 `for` + `break`语句 实现）

🍉 **提示**：

`String` 类型的相等判断不能用 关系运算符 `==` 实现，而是用 `String1.equals("String2")`实现。

🧑🏻‍💻 **源代码**：

```java
int chances = 3;

for (int i = 1;i<=chances;i++){
  //输入用户名与密码
  System.out.print(">>Please enter your user name: ");
  String userName = myScanner.next();
  System.out.print(">>Please enter your password: ");
  String userPwd = myScanner.next();

  //验证
  if("Ricky".equals(userName) == false){
      System.out.println(">>Wrong User Name");
    }else if("Overthinker".equals(userPwd) ==false){
      System.out.println(">>Wrong Password");
    }else{
      System.out.println(">>Log in successfully");
      break;
    }

    if(i < chances)
      System.out.println(">>" + (chances - i) + " chances remained\n");
		else
    	System.out.println(">>Your chances has run out");
}
```

<br/>

#### 🟡  6. 三角形画图问题（「分支 + 循环结构」习题）

📝**题目描述**：

> 画出一个 **n行** 的 **实心与空心三角形**。效果如下：

```java
    *            *
   ***          * *
  *****        *   *
 *******      *     *
*********    *********  
```

🍉 **分析**：

「**化繁为简**」将问题转化为输出 5 层的三角形，**寻找层数与空格数、星号数的数量关系**，可以得到：

+ `空格数 = 总层数 - 当前层数`

+ `星号数 = 当前层数 - 1`

「**先死后活**」将层数由常量值 5 改为变量 `layerNum`

🧑🏻‍💻 **源代码**：

```java
int layerNum = myScanner.nextInt();

for(int i = 1; i <= layerNum; i++) {
    //输出空格 
    for (int j = 1; j <= layerNum - i; j++){
        System.out.print(" ");
    }

    //实心三角形输出 *
    //for (int j = 1; j <= 2 * i - 1; j++){
        //System.out.print("*");
    //}
    //System.out.println("");

    //空心三角形输出 *
    for (int j = 1; j <= 2 * i-1; j++){
       if(j == 1 || j == 2 * i-1 || i == layerNum){  //主要
           System.out.print("*");
       }else{
           System.out.print(" ");
       }
     }
     System.out.println("");
}
```

<br/>

#### 🔴  7. 菱形画图问题（「分支 + 循环结构」习题）

📝 **题目描述**：

> 画出一个 **边长为n** 的 **实心与空心菱形**。效果如下：

```java
    *            *
   ***          * *
  *****        *   *
 *******      *     *
*********    *       *  
 *******      *     *
  *****        *   *
   ***          * *
    *            *
```

🍉 **分析**：

在[『三角形画图问题』](#🟡  6. 三角形画图问题（「分支 + 循环结构」习题）)的基础上，将菱形的下半部分通过数量关系，转化为上半部分输出即可。 

🧑🏻‍💻 **源代码**：

```java
int sideLen = myScanner.nextInt();  //sideLen 为菱形边长，同时也是半个菱形的层数
int layerNum = sideLen * 2 -1;      //layerNum 为菱形总层数
int curLayerNum;
for(int i = 1; i <= layerNum; i++) {
    if(i < sideLen)
        curLayerNum = i;   //上半部分当前层数
    else
        curLayerNum = layerNum - i + 1;   //下半部分当前层数

    //输出空格
    for (int j = 1; j <= sideLen - curLayerNum; j++){
        System.out.print(" "); 
    }

    //实心菱形输出 *
    //for (int j = 1; j <= curLayerNum * 2 - 1; j++){
        //System.out.print("*"); 
    //}
    //System.out.println(""); 
  
    //空心菱形输出 *
    for (int j = 1; j <= curLayerNum * 2 - 1 ; j++){
        if(j == 1 || j == 2 * curLayerNum - 1){
            System.out.print("*");
        }else{
            System.out.print(" ");
        }
    }
}
```



<br/>

## ✏️ 今日随记

学习 Java 的 **第 9 天**。⏰

今天主要整理了本章的编程习题，摘录了几道较为经典的练习。

经过这几题的实战，回顾了一些简单的算法， Java 编程也变得更加熟练。

想在之后的随记中，摘录一些不错的句子，激励自己，就从 韩顺平老师 的金句开始吧。

>  *「**我亦无他，唯手熟尔**」—— 欧阳修 《卖油翁》*

---

**相关博客**：

[【Java】学习日记Day 8](https://blog.csdn.net/qq_46025844/article/details/125649393?spm=1001.2014.3001.5501)

[【Java】学习日记Day 7](https://blog.csdn.net/qq_46025844/article/details/125624935?spm=1001.2014.3001.5502)

[【Java】学习日记 Day6](https://blog.csdn.net/qq_46025844/article/details/125608129?spm=1001.2014.3001.5502)








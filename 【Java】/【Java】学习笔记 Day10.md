![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月11日



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



<br/>

## ✏️ 今日随记

学习 Java 的 **第 10 天**。⏰

今天主要整理了本章的编程习题，摘录了几道较为经典的练习。

经过这几题的实战，回顾了一些简单的算法， Java 编程也变得更加熟练。

想在之后的随记中，摘录一些不错的句子，激励自己，就从 韩顺平老师 的金句开始吧。

>  *「**我亦无他，唯手熟尔**」—— 欧阳修 《卖油翁》*

---

**相关博客**：

[【Java】学习日记Day 9](https://blog.csdn.net/qq_46025844/article/details/125669124?spm=1001.2014.3001.5501)

[【Java】学习日记Day 8](https://blog.csdn.net/qq_46025844/article/details/125649393?spm=1001.2014.3001.5501)

[【Java】学习日记Day 7](https://blog.csdn.net/qq_46025844/article/details/125624935?spm=1001.2014.3001.5502)










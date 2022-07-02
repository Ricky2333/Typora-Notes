![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月2日



---

## 🌈 今日知识点总结

### 1.  自动类型转换

当 Java 程序在进行赋值或者运算时，***精度小的*** 类型 **自动转换** 为 ***精度大的*** 数据类型，这个就是 **自动类型转换**。

+ 有多种类型的数据混合运算时，系统首先自动将所有数据 **转换成容量最大** 的数据类型，然后再进行计算。

+ 当把精度大的数据类型赋值给精度小的数据类型时，就会报错，反之就会进行自动类型转换。




🍉 **PS1**：`byte`、`short`、`char ` 类型之间 **不会相互自动转换**

故以下代码是会报错的 ❌  

```java
byte n1 = 10;
char c = n1;     //编译错误，byte类型 无法自动转换为 char类型
```



🍉 **PS2**：`byte`、`short`、`char ` 类型之间可以进行加减运算，在计算时首先转换为 `int` 类型

```java
byte n1 = 10;
char c = 20;

byte n2 = n1 + c;    //编译错误，int类型 无法自动转换为 byte类型
int n3 = n1 + c; 		 //编译通过
```

n1 和 c 进行加法运算时，得到的结果为 `int` 类型，故无法赋值给 `byte` 类型的 n2，但是可以赋值给 `int` 类型的 n3。所以 **程序编译到第 4 行会报错**。



🍉 **PS3**：`byte`、`short`、`char ` 类型 ***本身*** 进行加减运算，**需添加强制转换符号**（**极易出错** 💦）

```java
byte n = 123; 
n = n + 1;					//编译错误，int → byte
n = (byte)(n + 1);	//编译通过

short s = 12; 
s = s - 9;					//编译错误，int → short
s = (short)(s - 9);	//编译通过

char c = 'a'; 
c = c + 1;					//编译错误，int → char
c = (char)(c + 1);  //编译通过
```



### 2. 强制类型转换

使用 **强制转换符**，将 **精度大的数据类型** 转换为 **精度小的数据类型**。但是这样会导致 **精度降低** 或 **溢出**，使用时要格外注意。

```java
type1 var1 = value1;				//定义 type1类型的变量var1
type2 var2 = (type2)var1;   //将var1强制转换为 type2类型的变量var2
```



🍉 **PS1**：强制转换符号只 **对于最近的操作数有效**

```java
int x = (int)10*3.5+6*1.5; 		//编译错误 double → int 
int x = (int)(10*3.5+6*1.5);	//编译通过 (int)44.0 → 44 
```



🍉 **PS2**：`char ` 类型 **可以保存 `int` 类型的常量值**，但 **不能保存 `int` 类型的变量值**。

```java
int n = 10;
char c1 = 10;   		//编译通过
char c2 = n;				//编译错误，int类型 无法自动转换为 char类型
char c2 = (char)n;  //编译通过，int类型 强制转换为 char类型
```



### 3. 基本数据类型和 String 类型的转换

**基本 → String**：`String s = var + ""`

```java
int n1 = 100; 
float f1 = 1.1F; 
double d1 = 4.5; 
boolean b1 = true; 

String s1 = n1 + ""; 
String s2 = f1 + ""; 
String s3 = d1 + ""; 
String s4 = b1 + ""; 

System.out.println(s1 + " " + s2 + " " + s3 + " " + s4);
```



**String → 基本**：`type var = Type.parseType(s)`

```java
public class conversion {
	public static void main(String[] args) {
		String s1 = "123";
		String s2 = "true";

		int n1 = Integer.parseInt(s1);           	//String → int
		double n2 = Double.parseDouble(s1);			  //String → double
		boolean flag = Boolean.parseBoolean(s2);	//String → boolean

		System.out.println(n1 + "\t" + n2 + "\t" + flag);
	}
}
```

在将 String 类型转成 基本数据类型时，要确保 String 类型能够 **转成有效的数据**，如不能把 "hello" 转成一个整数



## ✏️ 今日随记

学习 Java 的 **第 5 天**。⏰

今天算是比较空闲的一天，一天都宅在家里 ~~摸鱼~~ ，啊不，学习。

就成果而言，今天把前四天的内容做了一个 **小小的收尾**，把前三章的知识点都整理完了。

今天还把「**Java 学习日记**」系列博客的格式做了一个大的调整， **DIY** 了一下**文章的封面**，让博客看起来更加 **正式** 和 **美观** 了一些。虽然技术含量不高，但却带来了不错的视觉效果与满满的成就感，让博客撰写这件事有点「**步入正轨**」的意思，也带来了不少 **坚持创作的动力**。🧑🏻‍💻

在接下来的暑期学习中，博主打算采用 **`5 + 1 + 1`** 的形式，**以 7 天为一个学习周期**。

**`学 5 天 + 休 1 天 + X 1 天`**（X 看当周的心情决定）

最后给奋斗了5天的自己 **add some oil**⛽️

希望能够继续坚持，怀挺！✊

---

**相关博客**：

[【Java】学习日记 Day4](https://blog.csdn.net/qq_46025844/article/details/125567560?spm=1001.2014.3001.5501)

[【Java】学习日记 Day3](https://blog.csdn.net/qq_46025844/article/details/125543456?spm=1001.2014.3001.5502)

[【Java】学习日记 Day2](https://blog.csdn.net/qq_46025844/article/details/125531789?spm=1001.2014.3001.5502)




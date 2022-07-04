![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月5日



---

## 🌈 今日知识点总结

### 1. Java 运算符概述

运算符是一种特殊的符号，用以表示数据的运算、赋值和比较等。

![image-20220704152345495](https://tva1.sinaimg.cn/large/e6c9d24ely1h3ux9t0nmpj21iy0ngtdl.jpg)

<br/>

### 2. 算数运算符

**算术运算符** 用于 **数值类型变量的运算**，在 Java 程序中使用非常广泛。

![image-20220704154233946](https://tva1.sinaimg.cn/large/e6c9d24ely1h3uxtdjabbj20nm07gdgc.jpg)

<br/>

🍉 **PS1**：Java中， `%` 的本质是一个公式：`c = a % b = a - a / b * b` ，结果 **c 的符号与 a 的符号一致**。

```java
System.out.println(7 % 5)			//输出 2
System.out.println(7 % -5)		//输出 2
System.out.println(-7 % 5);		//输出 -2
System.out.println(-7 % -5);	//输出 -2
```

<br/>

🍉 **PS2**：Java中， `/` 在 **整数之间** 做除法时，结果 **只保留整数部分而舍弃小数部分**。

**示例**：`System.out.println(7 % 5)	//输出1，而不是1.4 `

<br/>

### 3. 关系（比较）运算符

![image-20220704154252568](https://tva1.sinaimg.cn/large/e6c9d24ely1h3uxtp2pxmj20ke07edgd.jpg)

🍉 **PS1**：关系运算符的结果都是 `boolean` 类型，只有 `true` 和 `false` 。

```java
System.out.println(7 > 5)			//输出 true
System.out.println(7 != -5)		//输出 true
System.out.println(-7 == 5);	//输出 false
System.out.println("Ricky" instanceof String);	//输出 true
```



🍉 **PS1**：关系运算符的结果都是 `boolean` 类型，只有 `true` 和 `false` 。

```java
System.out.println(7 > 5)			//输出 true
System.out.println(7 != -5)		//输出 true
System.out.println(-7 == 5);	//输出 false
System.out.println("Ricky" instanceof String);	//输出 true
```







### 4. 逻辑运算符

关系运算符的结果都是 boolean 型，也就是要么是 true， 要么是 false

![image-20220704154314838](https://tva1.sinaimg.cn/large/e6c9d24ely1h3uxu2psnbj20ey06iq38.jpg)















### 3. 



## ✏️ 今日随记

学习 Java 的 **第 6 天**。⏰

今天算是比较空闲的一天，一天都宅在家里 ~~摸鱼~~ ，啊不，学习。

就成果而言，今天把前四天的内容做了一个 **小小的收尾**，把前三章的知识点都整理完了。

今天还把「**Java 学习日记**」系列博客的格式做了一个大的调整， **DIY** 了一下**文章的封面**，让博客看起来更加 **正式** 和 **美观** 了一些。虽然技术含量不高，但却带来了不错的视觉效果与满满的成就感，让博客撰写这件事有点「**步入正轨**」的意思，也带来了不少 **坚持创作的动力**。🧑🏻‍💻

在接下来的暑期学习中，博主打算采用 **`5 + 1 + 1`** 的形式，**以 7 天为一个学习周期**。

**`学 5 天 + 休 1 天 + X 1 天`**（X 看当周的心情决定）

最后给奋斗了5天的自己 **add some oil**⛽️

希望能够继续坚持，怀挺！✊

---

**相关博客**：

[【Java】学习日记 Day5](https://blog.csdn.net/qq_46025844/article/details/125579422?spm=1001.2014.3001.5501)

[【Java】学习日记 Day4](https://blog.csdn.net/qq_46025844/article/details/125567560?spm=1001.2014.3001.5501)

[【Java】学习日记 Day3](https://blog.csdn.net/qq_46025844/article/details/125543456?spm=1001.2014.3001.5502)




![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月4日



---

## 🌈 今日知识点总结

### 1. Java 运算符概述

**运算符** 是一种特殊的符号，用以表示数据的运算、赋值和比较等。

![image-20220704152345495](https://tva1.sinaimg.cn/large/e6c9d24ely1h3ux9t0nmpj21iy0ngtdl.jpg)

<br/>

### 2. 算数运算符

**算术运算符** 用于 **数值类型变量的运算**，在 Java 程序中使用非常广泛。

![image-20220704162623917](https://tva1.sinaimg.cn/large/e6c9d24ely1h3uz2zya4fj215i0h60v0.jpg)

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

**示例**：`System.out.println(7 / 5)	//输出1，而不是1.4 `

<br/>

### 3. 关系（比较）运算符

![image-20220704162555113](https://tva1.sinaimg.cn/large/e6c9d24ely1h3uz2he8rbj21i40hiwhg.jpg)

🍉 **PS1**：关系运算符的结果都是 `boolean` 类型，只有 `true` 和 `false` 。

```java
System.out.println(7 > 5)			//输出 true
System.out.println(7 != -5)		//输出 true
System.out.println(-7 == 5);	//输出 false
System.out.println("Ricky" instanceof String);	//输出 true
```

<br/>

🍉 **PS2**：**赋值运算符** `=` 和 **关系运算符** `==` 需要注意区分。（开始极易搞错 💦）

```java
System.out.println(7 == 5)			//输出 true
System.out.println(i = 5)       //输出 5
```



<br/>

### 4. 逻辑运算符

![image-20220704162535331](https://tva1.sinaimg.cn/large/e6c9d24ely1h3uz24lp3hj219a0j8jtr.jpg)

|   a   |   b   | a & b | a \| b | a && b | a \|\| b |  ! a  | a ^ b |
| :---: | :---: | :---: | :----: | :----: | :------: | :---: | :---: |
| true  | true  | true  |  true  |  true  |   true   | false | false |
| true  | false | false |  true  | false  |   true   | false | true  |
| false | true  | false |  true  | false  |   true   | true  | true  |
| false | false | false | false  | false  |  false   | true  | false |

<br/>

🍉 **PS1**：其中，`&&` 和 `||` 为 **短路与/或** ， 相比 **逻辑与/或** 效率更高，在 **实际开发中使用频率更高**。

+ **短路与**： `[条件1] && [条件2]` ，当 `[条件1]` 为 `false` 时，**不会判断/执行**  `[条件2]` 
+ **短路或**： `[条件1] || [条件2]` ，当 `[条件1]` 为 `true` 时，**不会判断/执行**  `[条件2]` 

**示例：**

```java
int a = 10;
int b = 100;

//短路与 &&
if(a == 11 && b++ == 100)
	System.out.println("Conditions are satisfied");
System.out.println("a = " + a + "\tb = " + b);

//逻辑与 &
if(a == 11 & b++ == 100);
	System.out.println("Conditions are satisfied");
System.out.println("a = " + a + "\tb = " + b);
```

![image-20220704164542159](https://tva1.sinaimg.cn/large/e6c9d24ely1h3uznat1r2j213i02swew.jpg)

<br/>

🍉 **PS2**：**异或运算符** `^` 的运算规则非常容易搞错，以下为 **两种记忆方法**

+ 将「异或」分解为「异」 + 「或」
  + 「异」指该运算符 **侧重「不同」**，即 **左右两边的变量不同** 才符合条件
  + 「或」指该运算符 **侧重「或」的结果**，而「或」的结果有3个 `true`，1个 `false`，总体偏向 `true`
  + 由上面两点，得到**「不同 → true」**

+ 将「异或」两边的逻辑值 `false 和 true` 转换为 `0 和 1` ，进行 **加法运算**
  + `true ^ true` → `1 + 1 = 10` → `取末尾 0`
  + `true ^ false` → `1 + 0 = 1` → `取末尾 1`
  + `false ^ true` → `0 + 1 = 1` → `取末尾 1`
  + `false ^ false` → `0 + 0 = 0` → `取末尾 0`

<br/>

## ✏️ 今日随记

学习 Java 的 **第 6 天**。⏰

感觉「**运算符**」这一章的内容还是比较基础的。对于科班出身的博主来说，很多内容都可以倍速刷完。

虽然今天笔记的内容不算很多，但实际上花费的时间一点也不少，甚至快赶上看课的时间了。很多时候想要把笔记整理的有条理些，就需要花比较多的心思去筛选内容，构建出知识框架，用不同的方式进行归纳总结。

虽然这样的过程很繁琐，但这考验着自己的逻辑思考能力和总结能力，还是非常必要的。

「**路漫漫其修远兮，吾将上下而求索**」✊

---

**相关博客**：

[【Java】学习日记 Day5](https://blog.csdn.net/qq_46025844/article/details/125579422?spm=1001.2014.3001.5501)

[【Java】学习日记 Day4](https://blog.csdn.net/qq_46025844/article/details/125567560?spm=1001.2014.3001.5501)

[【Java】学习日记 Day3](https://blog.csdn.net/qq_46025844/article/details/125543456?spm=1001.2014.3001.5502)




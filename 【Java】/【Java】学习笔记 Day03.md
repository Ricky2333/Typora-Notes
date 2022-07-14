![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年6月30日

---



## 🌈 今日知识点总结

### 1.  Java 转义字符

#### 1.1 常用转义字符表

| 转义字符 |          意义          |
| :------: | :--------------------: |
|  **\n**  |          换行          |
|  **\t**  |       水平制表符       |
|  **\r**  | 光标回到当前所在行行首 |
| **\\\\** |         打印 \         |
| **\\'**  |         打印 '         |
| **\\"**  |         打印 "         |



#### 1.2 关于 `\r` 

**验证程序**

```java
public class HelloWorld {
	public static void main(String[] args) {
    //验证\r的作用
		System.out.println("Hello World\r123");
	}
}
```

**验证结果**

![image-20220630150334256](https://tva1.sinaimg.cn/large/e6c9d24ely1h3qa7onrwdj21dc04g74p.jpg)

**结果分析**

由程序的运行结果可知，转义字符 `\r` 使得当前光标 **回到了行首**，后面的字符串 “123” 替换了行首的 “Hel”



### 2. Java 注释

#### 2.1 单行注释、多行注释、文档注释

```java
// 这是一个单行注释

/*
	这是一个多行注释
	注释内容如下：
	1. ***
	2. ***
*/

//这是一个文档注释
/**
 * @author Ricky
 * @version 1.0
*/
```

#### 2.2 文档注释 与 javadoc命令

**文档注释** 可以被 **`javadoc`** 命令解析，生成 **网页文件 **显示的 **说明文档**。

**示例**：

1. 编写含有 **文档注释** 的源程序：

```java
/**
 * @author Ricky
 * @version 1.0
*/
public class HelloWorld {
	public static void main(String[] args) {
		System.out.println("Hello World\n");
	}
}
```

2. 使用 `javadoc` 命令解析

```bash
javadoc -d ~/desktop -author -version HelloWorld.java
```

![image-20220630153256350](https://tva1.sinaimg.cn/large/e6c9d24ely1h3qb24ijsaj21gc0eejum.jpg)

3. 查看目录中新生成的 **html 说明文档**

![image-20220630153647144](https://tva1.sinaimg.cn/large/e6c9d24ely1h3qb646cuhj20hk0e4abc.jpg)

![image-20220630152323958](https://tva1.sinaimg.cn/large/e6c9d24ely1h3qas7aymxj21q90u0juc.jpg)



### 3. Java 代码规范

[阿里巴巴 Java代码规范](https://blog.csdn.net/qq_36178727/article/details/94047230?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165657483116782391814915%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165657483116782391814915&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-1-94047230-null-null.142^v26^pc_rank_34,157^v15^new_3&utm_term=Java%E4%BB%A3%E7%A0%81%E8%A7%84%E8%8C%83+%E9%98%BF%E9%87%8C&spm=1018.2226.3001.4187)



### 4. Java 数据类型 🔴

![image-20220630160757347](https://tva1.sinaimg.cn/large/e6c9d24ely1h3qc2k3qihj21ga0u0gqe.jpg)

```java
public class DataType {
    public static void main(String[] args) {
        byte n1 = 1;       
        short n2 = -100;
        int n3 = 200;
        long n4 = -3000;

        float m1 = 12.29;
        double m2 = 23.333;

        char c = 'a';

        boolean flag = true;
    }
}
```



### 5. Java “+” 使用规则

+ “+” 两边 **都是数字**，执行 **相加** 操作
+ “+” 有 **一边是字符串**，执行 **拼接** 操作
+ **无括号 **的情况下，执行顺序 **从左到右**

```java
public class Plus {
    public static void main(String[] args){
        //两边都是数字，执行相加操作
        System.out.println(11 + 11);

        //一边都是字符串，执行拼接操作
        System.out.println("hello" + 11);

        System.out.println("hello" + "world");

        System.out.println(100 + 3 + "hello");

        System.out.println("hello" + 100 + 3);
    }
}
```

![image-20220630162907643](https://tva1.sinaimg.cn/large/e6c9d24ely1h3qcol2b8lj219405eaa4.jpg)



## ✏️ 今日随记

今天是学习 Java 的 **第 3 天**，也是在家休息的 **第 1 天**。

不得不说，家里的环境真是比学校宿舍舒服太多；爸妈做的饭菜也是学校食堂远远不能比的，有一对会做饭的爸妈真是人间一大幸福。🥰

言归正传，今天在学习方面也收获颇丰，学习节奏也从容了很多，进度从昨天的 EP20，一下子到了 EP42。

第三章 **Java 变量** 感觉有不少内容在 **C语言 **里就已经了解过了，学起来就格外轻松。😊

明天继续加油，争取把 **Java 变量** 这一章学完，早日进入 **面向对象** 这一块核心内容的学习，**奥利给** 💪 

---

**相关博客**：

[【Java】学习日记 Day2](https://blog.csdn.net/qq_46025844/article/details/125531789?spm=1001.2014.3001.5502)

[【Java】学习日记 Day1](https://blog.csdn.net/qq_46025844/article/details/125508842?spm=1001.2014.3001.5502)


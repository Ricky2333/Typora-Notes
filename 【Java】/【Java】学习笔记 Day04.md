![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月1日



---

## 🌈 今日知识点总结

### 1.  Java API 帮助文档

> This document is the **API specification** for the **Java™ Platform, Standard Edition**

[Java API 帮助文档—英文版](https://docs.oracle.com/javase/8/docs/api/index.html)（Java SE 8）

[Java API 帮助文档—中文版](https://www.matools.com/api/java8)（Java SE 8）

![image-20220701231845894](https://tva1.sinaimg.cn/large/e6c9d24ely1h3ru55pju9j21r20o4q7t.jpg)

### 2. Java 数据类型

本阶段需要掌握 **Java 8大基本数据类型**，即：**byte、short、int、long、float、double、char、boolean**

![image-20220630160757347](https://tva1.sinaimg.cn/large/e6c9d24ely1h3qc2k3qihj21ga0u0gqe.jpg)

#### 2.1 整数类型

| 数据类型 | 占用存储空间字节数 |                       数据范围                        |
| :------: | :----------------: | :---------------------------------------------------: |
|   byte   |         1          |         $-2^{7}\sim2^{7}-1$<br/>$-128\sim127$         |
|  short   |         2          |      $-2^{15}\sim2^{15}-1$<br/>$-32768\sim32767$      |
| **int**  |         4          | $-2^{31}\sim2^{31}-1$<br/>$-2147483648\sim2147483647$ |
|   long   |         8          |                 $-2^{63}\sim2^{63}-1$                 |

+ Java 中的整数类型默认为 **int**
+ 变量命名示例：`byte n1 = 10` 、`short n2 = 123` 、`int n3 = 1234` 、`long n4 = 1234L`



#### 2.2 浮点数类型

|  数据类型  | 占用存储空间字节数 |         数据范围          |
| :--------: | :----------------: | :-----------------------: |
|   float    |         4          |  $-3.403E38\sim3.403E38$  |
| **double** |         8          | $-1.798E308\sim1.798E308$ |

+ Java 中的浮点数类型 **默认** 为 **double**
+ 变量命名示例：`float n1 = 123.4F` 、`double n2 = 123.4`

+ ☘️ **知识拓展**：[浮点数在计算机中的存储方式—CSDN](https://blog.csdn.net/Romantic_wennuan/article/details/123769217?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165672861916780366575137%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165672861916780366575137&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduend~default-3-123769217-null-null.142^v30^pc_rank_34,185^v2^control&utm_term=%E6%B5%AE%E7%82%B9%E6%95%B0%E5%AD%98%E5%82%A8&spm=1018.2226.3001.4187)



🍉 **PS**：在 Java 编程中，要尽量 **避免** 浮点数变量值之间 **直接的相等判断**，而是采用 **差值比较法** 判断浮点数变量值是否相等。

**示例源程序：**

```java
public class IsEqual {
    public static void main(String[] args){
        double d1 = 2.7;
        double d2 = 8.1/3;

        //输出d1与d2，观察两者是否相等
        System.out.println("d1 = " + d1);
        System.out.println("d2 = " + d2);
        
        //方法1:直接比较法
        if (d1 == d2 )
            System.out.println("Method 1: d1 is equal to d2");
        //方法2:差值比较法
        if ( Math.abs(d1-d2) < 0.00001 )
            System.out.println("Method 2: d1 is equal to d2");
    }
}
```

**运行结果：**

![image-20220702104544790](https://tva1.sinaimg.cn/large/e6c9d24ely1h3sdzwxt29j20r80363yk.jpg)

**结果分析：**

从该程序运行结果来看，**d2 的值并不是`8.1/3 = 2.7`**，而是非常 **接近 2.7** 的一个浮点数。这就使得 直接比较法 中的 **相等条件无法满足**，因此需要采用 **差值比较法**。



#### 2.3 字符类型

+ Java 中的字符类型采用 **Unicode编码表**，一个字符占用 **2个字节**，数据范围是 $[0,65535]$
+ 变量命名示例：`char c = 'a'`

+ ☘️ **知识拓展**

  + [Unicode编码在线转换工具](https://c.runoob.com/front-end/3602/)
  + [Unicode编码表—CSDN](https://blog.csdn.net/hherima/article/details/9045861?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165673062316782184674581%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165673062316782184674581&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-9045861-null-null.142^v30^pc_rank_34,185^v2^control&utm_term=unicode%E7%BC%96%E7%A0%81%E8%A1%A8&spm=1018.2226.3001.4187)

  + [字符编码知识概述—CSDN](https://blog.csdn.net/sgy1993/article/details/114929342?ops_request_misc=&request_id=&biz_id=102&utm_term=%E7%BC%96%E7%A0%81&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-4-114929342.142^v30^pc_rank_34,185^v2^control&spm=1018.2226.3001.4187)
  + [字符编码那些事（详细版）—CSDN](https://blog.csdn.net/hherima/article/details/9045861?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165673062316782184674581%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165673062316782184674581&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-9045861-null-null.142^v30^pc_rank_34,185^v2^control&utm_term=unicode%E7%BC%96%E7%A0%81%E8%A1%A8&spm=1018.2226.3001.4187)



🍉 **PS1**：在 Java 编程中，在给 **char类型赋值** 时，要区分 **单/双引号** `''` 与  `""` ，使用双引号给 char类型赋值会报错。

+ ❌ 典型错误：**`char c = "a"`**

+ ✅ 正确形式：**`char c = 'a'`**

![image-20220702120452875](https://tva1.sinaimg.cn/large/e6c9d24ely1h3sga92g11j213q04c0ti.jpg)



🍉 **PS2**：在 Java 编程中，“ + ” 的功能会因为 `''` 和  `""` 而 **发生改变**。

**示例程序：**

```java
public class Quotes {
    public static void main(String[] args) {
        System.out.println('a' + 2);   //单引号，相加
        System.out.println("a" + 2);   //双引号，进行拼接
    }
}
```

**运行结果：**

![image-20220702142301006](https://tva1.sinaimg.cn/large/e6c9d24ely1h3sk9za938j20nk028a9u.jpg)



🍉 **PS3**：字符类型既可以用字符赋值，也可以用符合要求的整数赋值。

**示例程序：**

```java
public class Quotes {
    public static void main(String[] args) {
        char c1 = 'a';
        char c2 = '逸';
        char c3 = 97;
        char c4 = 36920;

        System.out.println("c1 = " + c1);
        System.out.println("c2 = " + c2);
        System.out.println("c3 = " + c3);
        System.out.println("c4 = " + c4);

    }
    
}
```

**运行结果：**

![image-20220702141552668](https://tva1.sinaimg.cn/large/e6c9d24ely1h3sk2jynlbj20vq044jra.jpg)



#### 2.4 boolean类型

+ Java 中的boolean类型占用 **1个字节**

+ Java 中 boolean类型的取值只能是 `true` 或 `false`（**必须小写，不可用 0 或 非0 替代**）

+ 变量命名示例：`boolean flag = true`



#### 2.5 Java数据类型综合判断题

**题目：**

判断以下语句是否符合 Java 编程语法

```java
1. int n1 = 123L;

2. long n2 = 1234;

3. float n3 = 123.4;

4. double n4 = 1234.5f;

5. char c1 = "b";

6. char c2 = 69999;

7. boolean flag = False；

8. byte n5 = 123;

9. short n6 = 123;

10. byte n5 = 123L;

11. byte n7 = 123L;
```

**答案与解析：**

1. ❌  `123L` 为 `long` 类型，不可以赋值给 ***精度更低*** 的 `int` 类型变量

2. ✅  `1234` 为 `int` 类型，可以赋值给 ***精度更高*** 的 `long` 类型变量
3. ❌  `123.4` 为 `double` 类型，不可以赋值给 ***精度更低*** 的 `float` 类型变量

4. ✅  `1234.5f` 为 `float` 类型，可以赋值给 ***精度更高*** 的 `double` 类型变量
5. ❌  `“b”` 为 `String` 类型，不可以赋值给 ***精度更低*** 的 `char` 类型变量
6. ❌  $69999 > 65535$，**超出** 了 `char` 类型的 **整数范围**
7. ❌  `boolean` 类型只能接收  `true` 或 `false` ， **无法接收大写开头的** `False`
8. ✅  `123` 为 `int` 类型，按照惯例，不可以赋值给 ***精度更低*** 的 `byte` 类型变量，但 `byte` 类型无专门的数字后缀，故只能用默认的 `int` 类型给其赋值
9. ✅  `123` 为 `int` 类型，按照惯例，不可以赋值给 ***精度更低*** 的 `short` 类型变量，但 `short` 类型无专门的数字后缀，故只能用默认的 `int` 类型给其赋值
10. ❌  `123L` 为 `long` 类型，不可以赋值给 ***精度更低*** 的 `byte` 类型变量
11. ❌  `123L` 为 `long` 类型，不可以赋值给 ***精度更低*** 的 `short` 类型变量

注：以上解析中的 「**不可以赋值给精度更低的数据类型**」，指的是 **不使用强制类型转换的情况下**，系统编译这条语句时 **会报错**。

![image-20220702145523471](https://tva1.sinaimg.cn/large/e6c9d24ely1h3sl7o3b0rj210g0480t1.jpg)



## ✏️ 今日随记

学习 Java 的 **第 4 天**。⏰

今天算是比较忙碌的一天，行程排的比较满，但也过的还算充实。上午去市区里的中医院看了一趟医生，打算趁暑假的时间喝点中药补补身体；下午和爸妈一起去了商场购物，添置了好多秋天的衣物；晚上又出门小跑了一会，锻炼锻炼身体。🏃

今天的行程虽然看着有点忙，但好在完成了昨天定下的指标，**把第三章的网课刷完了**。✅

目前对 Java 的数据类型、自动类型转换、强制类型转换也都有了一定的理解。但是知识点归纳的部分还是有些来不及了，还差一些内容需要明天来完善了。（现在是北京时间 23:56，准备润了💨）

希望自己继续加油，坚持坚持，再坚持。✊

---

**相关博客**：

[【Java】学习日记 Day3](https://blog.csdn.net/qq_46025844/article/details/125543456?spm=1001.2014.3001.5502)

[【Java】学习日记 Day2](https://blog.csdn.net/qq_46025844/article/details/125531789?spm=1001.2014.3001.5502)

[【Java】学习日记 Day1](https://blog.csdn.net/qq_46025844/article/details/125508842?spm=1001.2014.3001.5502)


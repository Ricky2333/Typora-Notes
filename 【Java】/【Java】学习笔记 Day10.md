![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月12日



---

## 🌈 今日知识点总结

###  Java 数组简介

#### 1. 数组的基本概念

+ **数组** 是一组数据，存放 **多个同一类型** 的数据
+ **数组** 也是一种数据类型，属于 **引用类型**
+ **数组** 采用 **引用赋值** 的方式（靠传递 **地址** 赋值）

<br/>

#### 2. 数组的初始化

##### 动态初始化：

数组的 **动态初始化** 常用于 **输入值未知** 的情况。

```java
//方式1:声明数组后直接 new 分配空间
int[] arr1 = new int[6];   
//int arr1[] = new int[6] 与 int[] arr1 = new int[6] 等价

//方式2:先声明数组，再 new 分配空间
int[] arr2;
arr2 = new int[6];

//循环赋值
for(int i = 0;i < arr2.length;i++){ //arr.length表示数组长度/大小
  arr2[i] = myScanner.nextInt();
}
```

<br/>

##### 静态初始化：

数组的 **静态初始化** 常用于 **输入值已知** 的情况。

```java
int [] arr3 = {1,2,3,4,5,6};
```

<br/>

🍉 **PS1**：创建数组后，不同类型的数组有 **不同的默认值**

| 数据类型  | 默认值 |
| :-------: | :----: |
|  `byte`   |   0    |
|  `short`  |   0    |
|  `int `   |   0    |
|  `long`   |   0    |
|  `float`  |  0.0f  |
| `double`  |  0.0   |
| `boolean` | false  |
|  `char`   | \u0000 |
| `String`  |  null  |

<br/>

🍉 **PS2**：数组的下标 **从 0 开始**，且必须在指定范围内使用，否则在 **运行时抛出「下标越界」异常**（编译时不会报错）💦

```java
int[] arr = new int[6];
System.out.println(arr[6]);  //arr数组的下标范围是 0-5
```

![image-20220712160717448](https://tva1.sinaimg.cn/large/e6c9d24ely1h447hll4yvj20xw02c0t0.jpg)

<br/>

#### 3. 数组的赋值机制

**基本数据类型**：采用 「**值传递**」 的方式，拷贝值是 **具体的数据**。

**数组**：采用 「**引用传递**」 的方式，拷贝值是 **地址**。

**示例程序**：

```java
int n1 = 10;
int n2 = n1;
n2 = 100;    //修改n2的值
System.out.println("n1 = " + n1); //查看n1是否有变化
  
int[] arr1 = {1,2,3,4,5,6};
int[] arr2 = arr1;
arr2[0] = 100;    //修改arr2[0]的值
System.out.println("arr1[0] = " + arr1[0]); //查看arr1[0]是否有变化
```

**运行结果**：

![image-20220712163840090](https://tva1.sinaimg.cn/large/e6c9d24ely1h448e7lo3xj20si024wep.jpg)

**JVM 内存分析**：

![image-20220712221945132](https://tva1.sinaimg.cn/large/e6c9d24ely1h44i95c7k1j21o00u0q6e.jpg)

由以上分析可知，在 Java 编程中如需 **拷贝数组**，需要 `new`一个新数组，**开辟新的内存空间**，通过编程实现。

<br/>

#### 4. 数组拷贝

**实现代码**：

```java
int[] arr1 = {1,2,3,4,5,6};
int[] arr2 = new int[arr1.length];   //创建相同长度的新数组 arr2，两者有不同的内存空间

for(int i = 0; i < arr1.length; i++){  //拷贝
  arr2[i] = arr1[i];
}
System.out.println("");                //修改arr2
for(int i = 0; i < arr1.length; i++){
    arr2[i] += 1;
}
for(int i = 0; i < arr1.length; i++){  //查看arr1是否被改变
    System.out.print(arr1[i] + " ");
}
System.out.println("");
```

**输出结果**：

```java
1 2 3 4 5 6
```

从输出结果来看，`arr1` 并没有因为 `arr2` 的修改而改变，说明拷贝成功，两个数组是互相独立的。✅ 

<br/>

## ✏️ 今日随记

学习 Java 的 **第 10 天**。⏰

今天主要整理了数组的基础知识，把一些需要注意的点给列了出来，方便以后复习。

今日金句摘录：

>  *「 **Think twice，Code once** 」*

---

**相关博客**：

[【Java】学习日记Day 9](https://blog.csdn.net/qq_46025844/article/details/125669124?spm=1001.2014.3001.5501)

[【Java】学习日记Day 8](https://blog.csdn.net/qq_46025844/article/details/125649393?spm=1001.2014.3001.5501)

[【Java】学习日记Day 7](https://blog.csdn.net/qq_46025844/article/details/125624935?spm=1001.2014.3001.5502)










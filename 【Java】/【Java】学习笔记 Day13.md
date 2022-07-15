![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月15日



---

## 🌈 今日知识点总结

### 1. 类与对象介绍

#### 1.1 面向对象的基本概念

+ 「**类**」：**类** 是 **抽象的**，代表一类事物，比如人类，猫类，**是程序员自己定义的数据类型**。

+ 「**对象**」：**对象** 是 **具体的**，代表一个具体事物，程序员 **通过「类」来 创建（实例化）一个 「对象」**。

+ **两者关系**：对象是类的实例，类是对象的模板。

<br/>

#### 1.2 面向对象的优点

+ 易维护
+ 易扩展
+ 模块化
+ 方便建模

<br/>

### 2. 类与对象的初始化

#### 2.1 类的定义

```java
class Person {    //定义一个 Person类
    String name;  //Person类 包含 String类型的name属性
    int age;
    String major;
}
```

<br/>

🍉 **PS1**：定义 **类** 时，**无需添加小括号** `()`，否则会报错。💦

![image-20220714222833398](https://tva1.sinaimg.cn/large/e6c9d24ely1h46tqvomb9j217k0ku0xq.jpg)

<br/>

#### 2.2 对象的创建

```java
public class ObjectInit {
    public static void main(String[] args){
        Person p1 = new Person();  //new 一个 Person类对象 p1
      
        p1.name = "Ricky";        //给 p1的属性赋值
        p1.age = 20;
        p1.major = "CS";
        System.out.println(p1.name);  //输出 p1的name属性值
    }
}
```

<br/>

### 3. 对象的内存布局

#### 3.1 **Java 内存的结构分析**：

「**栈**」： 一般存放 **基本数据类型**（局部变量）

「**堆**」： 存放 **对象、数组** 等

「**方法区**」：**常量池**（常量，比如字符串）、**类加载信息**

<br/>

#### 3.2 **Java 创建对象的流程简单分析**：

```java
Cat cat1 = new Cat();
cat1.name = "小白";
cat1.age = 12;
cat.color = "白色";
```

1) 先在「**方法区**」加载 Cat 类信息（属性和方法信息，**只会加载一次**）
2) 在「**堆**」中分配空间，进行默认初始化（若属性中有 `String` 类型，则在「**常量池**」中分配相应空间）
3) 在「**栈**」把地址赋给 `cat`，`cat` 指向创建的对象
4) 进行指定初始化， 比如 `cat.name = "小白"`、`cat.age = 12`、`cat.color = "白色"`

**内存分配图**：

![image-20220715094245466](https://tva1.sinaimg.cn/large/e6c9d24ely1h47d8dyd58j21ya0tyn4n.jpg)

>[【视频讲解】对象的内存布局—B站（韩顺平老师）](https://www.bilibili.com/video/BV1fh411y7R8?p=195&vd_source=796196124611740a485335e1a4b12c0f)

<br/>

#### 3.3 思考题

##### 📝 **思考题1**：

> 根据下面一段代码，求输出值，并且画出相应的内存分配图。

```java
Person p1 = new Person();
p1.age = 10；
pl.name = "小明";
Person p2 = p1; 
System.out.println(p2.age);
```

☘️ **参考答案与视频解析**：

第 5 行输出值为：`10`

![image-20220715094415984](https://tva1.sinaimg.cn/large/e6c9d24ely1h47d9ykrgvj221q0u0do6.jpg)

[【视频讲解】思考题1的内存图绘制过程—B站（韩顺平老师）](https://www.bilibili.com/video/BV1fh411y7R8?p=199&vd_source=796196124611740a485335e1a4b12c0f)

<br/>

##### 📝 **思考题2**：

> 根据下面一段代码，求输出值，并且画出相应的内存分配图。

```java
Person a = new PersonO;
a.age = 10;
a.name = "小明”;
Person b;
b = a;
System.out.println(b.name)；
b.age = 200;
b = null;
System.out.printin(a.age); 
System.out.println(b.age)；  //重点
```

☘️ **参考答案与视频解析**：

第 6 行输出值为：`小明` 

第 9 行输出值为：`200`

第 10 行输出值为：**抛出异常** ` Exception in thread "main" java.lang.NullPointerException`	

![image-20220715094559393](https://tva1.sinaimg.cn/large/e6c9d24ely1h47dbr5feyj220o0tg466.jpg)

[【视频讲解】思考题2的内存图绘制过程—B站（韩顺平老师）](https://www.bilibili.com/video/BV1fh411y7R8?p=201&vd_source=796196124611740a485335e1a4b12c0f)

<br/>

## ✏️ 今日随记

学习 Java 的 **第 13 天**。⏰

今天主要整理了 **面向对象** 的一些基本概念，重点是理清 **对象的内存布局**，收获颇丰。☘️

今日摘录：

>  「 ***It is a great thing to have a beginner's mind*** 」— *Steve Jobs*

---

**相关博客**：

[【Java】学习日记 Day12](https://blog.csdn.net/qq_46025844/article/details/125778713?spm=1001.2014.3001.5501)

[【Java】学习日记 Day11](https://blog.csdn.net/qq_46025844/article/details/125756960)

[【Java】学习日记 Day10](https://blog.csdn.net/qq_46025844/article/details/125747990?csdn_share_tail=%7B%22type%22%3A%22blog%22%2C%22rType%22%3A%22article%22%2C%22rId%22%3A%22125747990%22%2C%22source%22%3A%22qq_46025844%22%7D&ctrtid=c411e)
















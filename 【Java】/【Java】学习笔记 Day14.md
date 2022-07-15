![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月15日



---

## 🌈 今日知识点总结

### 1. 属性

「**属性**」是「**类**」的一个 **组成部分**，描述「类」的 **状态信息**。

表示「**属性**」的 **若干术语**：属性 = 「**成员变量**」 = 「**字段**」 = 「**field**」

#### 1.1 属性的定义：

属性的定义语法与变量相似，一般结构： `访问修饰符 属性类型 属性名`

```java
class Person{
	String name;   //name、age、major、scores[] 均为 Person类的属性
	int age;
  String major;
  double[] scores;  //属性既可以是基本数据类型，也可以是引用类型
}
```

<br/>

#### 1.2 属性的访问：

属性的访问语法：`对象名.属性名`

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

🍉 **PS1**：属性的 `访问修饰符` 有 4 种：`public` 、`protected`、`default`、`private`，之后会具体介绍。

<br/>

🍉 **PS2**：属性如果不进行赋值，则保留默认值，规则和数组一致。

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



## ✏️ 今日随记

学习 Java 的 **第 13 天**。⏰

今天主要整理了二维数组的相关内容，感觉二维数组相比一维数组，还是有不少需要注意的地方。☘️

明天正式开始学习 **面向对象**，继续加油 ✊

今日摘录：

>  「 ***It is a great thing to have a beginner's mind*** 」— *Steve Jobs*

---

**相关博客**：

[【Java】学习日记 Day11](https://blog.csdn.net/qq_46025844/article/details/125756960)

[【Java】学习日记 Day10](https://blog.csdn.net/qq_46025844/article/details/125747990?csdn_share_tail=%7B%22type%22%3A%22blog%22%2C%22rType%22%3A%22article%22%2C%22rId%22%3A%22125747990%22%2C%22source%22%3A%22qq_46025844%22%7D&ctrtid=c411e)

[【Java】学习日记Day 9](https://blog.csdn.net/qq_46025844/article/details/125669124?spm=1001.2014.3001.5501)














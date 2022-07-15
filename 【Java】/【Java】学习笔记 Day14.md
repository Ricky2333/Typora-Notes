![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月16日



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

🍉 **PS2**：属性如果不进行赋值，**则保留默认值**，规则和数组一致。

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

### 2. 方法

「**方法**」是「**类**」的一个 **组成部分**，描述「**类**」的 **行为信息**。

表示「**方法**」的 **若干术语**：「**方法**」 = 「**成员方法**」 = 「**method**」

#### 2.1 方法的定义：

方法名采用「**小驼峰命名法**」，一般结构： `访问修饰符 返回数据类型 方法名(形参列表)`

```java
class Person{    //定义一个 Person 类
    String name;  //定义若干属性
    int age;
  
		//定义 greeting() 方法，无返回值
    public void greeting(){   
        System.out.println("x");
    }
  
		//定义 doAddCal() 方法，返回一个整数
    public int doAddCal(int n1,int n2){
        return n1 + n2;
    }
}
```

<br/>

#### 2.2 方法的调用：

**对象** 中调用方法：`对象名.方法名(实参列表)`

```java
public class ObjectInit {
    public static void main(String[] args){
        Person p1 = new Person();   //创建 p1 对象
        p1.greeting();              //调用 p1 的 greeting() 方法
        int res = p1.doAddCal(10,20);  //调用 p1 的 doAddCal() 方法
        System.out.println("res = " + res);
    }
}
```

**同一类中** 调用其他方法：`方法名（实参列表）` （**无需** 添加对象名）

```java
class Person{    
    public void greeting(){   
        System.out.println("hi");
    }
  
    public void selfIntro(){
				greeting();            //同一个类中，调用该类中的其他方法
      	System.out.println("My name is Ricky.");
    }
}
```

**跨类中** 的方法调用（如 A类 中的 a方法 想要调用 B类 中的 b方法 ）：需要创建对象后调用

```java
class A{
    public void a(){   //A类 中定义 a方法
        System.out.println("Hi,I'm from class A");
    }
}

class B{
    public void b(){    //想要在 B类 中调用 a方法
        A a1  = new A();   //首先创建一个 A类 对象a1
        a1.a(); 					 //通过对象a1 调用 a方法
        System.out.println("Hi,I'm from class B");
    }
}
```

<br/>

🍉 **PS1**：**实参** 和 **形参**的类型要一致或兼容、个数、顺序必须一致，否组会编译错误。

![image-20220715142216997](https://tva1.sinaimg.cn/large/e6c9d24ely1h47lb8bdzwj21is02y3zk.jpg)

<br/>

🍉 **PS2**：方法 **不能** 嵌套定义。

```java
class Person {
	public void greeting(){
		public int doAddCal(int n){	//在 greeting() 方法中又定义 doAddCal方法，属于嵌套定义
			...
		}
	}
}
```

<br/>

🍉 **PS3**：一个方法 **最多** 有一个返回值（但是可以通过 **返回一个数组的方式** 达到返回多个值的效果）

**程序示例**：

```java
class Test{
	public int[] multiReturn(){   //在方法中创建一个数组，并将其返回
		int[] arr = new int[2];
    arr[0] = 100;
    arr[1] = 200;
    return arr;
	}
}

public class MultiReturn {
    public static void main(String[] args){
			Test test = new Test();   //在main方法中创建Test实例
      int[] res = new int[2];
      res = test.multiReturn(); //调用multiReturn方法，返回一个数组
      System.out.println(res[0] + " " + res[1]);
    }
}
```

**运行结果**：

![image-20220715143425357](https://tva1.sinaimg.cn/large/e6c9d24ely1h47lnuznwxj21mu04kjsw.jpg)

<br/>



#### 2.3 方法的调用机制（重点掌握❗️）

1. 当程序执行到方法时，就会开辟一个独立的空间（**栈空间**）
2. 当方法执行完毕，或者执行到 `return` 语句时，就会返回到调用方法的地方
4. 返回后，继续执行方法后面的代码
5. 当 `main` 方法(栈) 执行完毕，整个程序退出

**内存分配图**：

![image-20220715114454123](https://tva1.sinaimg.cn/large/e6c9d24ely1h47grhem4ej21yh0u07d8.jpg)

> [【视频讲解】方法的调用机制—B站（韩顺平老师）](https://www.bilibili.com/video/BV1fh411y7R8?p=204&vd_source=796196124611740a485335e1a4b12c0f)



<br/>

## ✏️ 今日随记

学习 Java 的 **第 14 天**。⏰

今天主要整理了Java 面向对象中的「**属性**」与「**方法**」，虽然整体难度不大，但是需要注意的细节还是不少。

明天博主将开始暑期的「厦门之旅」🌊，打算去这座美丽的海滨城市好好玩耍休息一番。😃

所以博主这两天稍微多学习了一些， 把明天的学习日记也写完了，明天也能顺利更新，给第 3 个「5 + 1 +1」的学习周期划上完美的句号。

等旅游回来后再开启第 4 个「5 + 1 +1」的学习周期✊

今日摘录：

>  「 ***I think, therefore I am*** 」— *Descartes*

---

**相关博客**：

[【Java】学习日记 Day13](https://blog.csdn.net/qq_46025844/article/details/125798214?spm=1001.2014.3001.5502)

[【Java】学习日记 Day12](https://blog.csdn.net/qq_46025844/article/details/125778713?spm=1001.2014.3001.5501)

[【Java】学习日记 Day11](https://blog.csdn.net/qq_46025844/article/details/125756960)










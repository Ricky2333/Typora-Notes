![image-20220702163210840](https://img-blog.csdnimg.cn/img_convert/1a0b6d3652dc36ca62aa7729e89b4827.jpeg)

作者｜Rickyの水果摊

时间｜2022年7月25日

---

## 🌈 今日知识点总结

#### 1. 构造器的概念

之前在创建对象时，都是通过 `Person p = new Person()` 的方式来创建对象 `p` ，然后通过 `p.name = "Ricky"` 的方式来为对象的属性赋值。

这样传统的方式效率并不是很高，通过引入 「**构造器**」，我们就可以在创建对象 `p` 时，用  `Person p = new Person("Ricky")`  的方式直接为对象的属性赋值。

<br/>

#### 2. 构造器的特点

+ 构造器的名称和 **类名相同**
+ 构造器 **没有返回值**，但是在创建时 **无需添加** `void`
+ 在创建对象时，系统会 **自动调用** 该类的构造器完成对象的初始化。

<br/>

#### 3. 构造器的创建方式（未优化前）

**定义代码**：

```java
//定义构造器
public Person(String pname, int page) {
    name = pname;
    age = page;
}
```

构造器在创建后，系统会在创建对象时 **自动调用该构造器**。

**完整测试代码**：

```java
public class Constructor {
    public static void main(String[] args) {
				//创建对象时赋值
        Person p = new Person("Ricky", 20);
    		//显示对象信息
        p.info();
    }
}

class Person {
		//定义属性
    String name;
    int age;
		//定义构造器
    public Person(String pname, int page) {
        name = pname;
        age = page;
    }
		//定义方法
    public void info(){
        System.out.println("name is " + name + "\nage is " +  age);
    }
}
```

**测试结果**：

![image-20220724164546478](https://tva1.sinaimg.cn/large/e6c9d24ely1h4i41awah0j21mq060go6.jpg)

<br/>

#### 4. 构造器创建方式的优化（通过 this 关键字）

**优化前** 的创建方式：

```java
//优化前的构造器创建方式
public Person(String pname, int page) {
    name = pname;
    age = page;
}
```

在上面这段代码中，我们定义了两个局部变量 `pname` 、`page` 来给属性 `name` 和 `age` 赋值。

但是 **在实际开发** 中，程序员 **为了命名方便**，通常 **不会给构造器的局部变量再次取名**，而是沿用属性名 `name` 和 `age` 给局部变量，如以下程序所示：

```java
//优化未完成的构造器创建方式
public Person(String name, int age) {
    name = name;
    age = age;
}
```

我们 **实际想要实现的效果** 是：`属性中的 name = 局部变量中的 name` ，但是上面 `name = name `的方式，根据 **就近原则**，实现的效果却是：`局部变量中的 name = 局部变量中的 name` ，**存在巨大的 bug**。

因此我们通过 **引入 `this` 关键字**，来达到前者 `属性中的 name = 局部变量中的 name` 的效果。

**优化后** 的代码：

```java
//优化后的构造器创建方式
public Person(String name, int age) {
    this.name = name;
    this.age = age;
}
```

> `this` 关键字的具体介绍详见。

 <br/>

#### 5. 构造器的默认状态

其实，在我们之前定义类时，类中均有一个我们 **看不见的，已经提前定义好的构造器**，如下面的代码所示：

```java
class Person {
		//默认构造器
		public Person(){
    }
}
```

正是因为 **默认构造器的存在**，才使得之前 `new Person()` 时，必须添加 `()` ，并且括号中无参数传入。

 <br/>

#### 6. 构造器默认状态的覆盖

在我们定义了新的构造器后，默认构造器 **会被覆盖**。

```java
class Person {
    String name;
    int age;
    //public Person(){}
    //创建了新的构造器后，上面这一行默认的构造器会被覆盖
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

也就是说，我们 **没有办法** 再次通过 `new Person()` 来创建对象，而必须以 `new Person("name",age)` 的方式创建对象。

![image-20220724170114658](https://tva1.sinaimg.cn/large/e6c9d24ely1h4i4heja1rj21180aytav.jpg)

<br/>

但是很多时候，我们希望能够 **同时用两者方式来创建对象**，这就需要我们用到「**方法重载**」的知识，即在类中 **显性的定义一次默认构造器**，就可以实现该需求了。

**优化方案**：

```java
class Person {
    String name;
    int age;
    //显性定义默认构造器，就不会出现覆盖的情况
    public Person(){
    }
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

**测试结果**：

![image-20220724170334475](https://tva1.sinaimg.cn/large/e6c9d24ely1h4i4jtq714j20vg0by76v.jpg)

 <br/>

同理，我们可以 **定义多个构造器**，使得我们有 **更多的方式创建对象**。

```java
class Person {
    String name;
    int age;
		//构造器1
    public Person(){
    }
		//构造器2
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
		//构造器3
    public Person(String name) {
        this.name = name;
    }
		//构造器4
    public Person(int age) {
        this.age = age;
    }
}
```

**测试结果**：

![image-20220724171556542](https://tva1.sinaimg.cn/large/e6c9d24ely1h4i4woqdnpj20yi0fagof.jpg)

<br/>

#### 7. 构造器创建的快捷键（拓展☘️）

系统：MacOS

编辑器：VS Code

##### 1. 键盘快捷键 `⌘` + `.` 调出 Generator，`Enter ` 进入下一个操作

![image-20220724173653547](https://tva1.sinaimg.cn/large/e6c9d24ely1h4i5ihhlksj210c0f476c.jpg)

##### 2. 在顶部方框勾选想要在构造器中初始化的参数，`Enter ` 进入下一个操作

![image-20220724174054706](https://tva1.sinaimg.cn/large/e6c9d24ely1h4i5mo9m5vj21qm0ta442.jpg)

##### 3. 查看类中代码，VS Code 顺利生成构造器代码

![image-20220724174332939](https://tva1.sinaimg.cn/large/e6c9d24ely1h4i5pez5q7j21380icac9.jpg)



## ✏️ 今日随记

学习 Java 的 **第 19 天**。⏰

今天主要整理了Java 中的「**构造器**」的相关内容，内容较为繁杂，难度适中。

明天会更新第 4 个学习周期的最后一篇博客，之后会博主将规划新的学习周期模式，更好的平衡看网课与写博客的时间。

继续加油。✊

今日摘录：

>  *「**劝君莫惜金缕衣，劝君惜取少年时**」*— *杜秋娘《金缕衣》*

---

**相关博客**：

[【Java】学习日记 Day18](https://blog.csdn.net/qq_46025844/article/details/125962423?spm=1001.2014.3001.5501)

[【Java】学习日记 Day17](https://blog.csdn.net/qq_46025844/article/details/125954156?spm=1001.2014.3001.5502)

[【Java】学习日记 Day16](https://blog.csdn.net/qq_46025844/article/details/125920143?spm=1001.2014.3001.5502)


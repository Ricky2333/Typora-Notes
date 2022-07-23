![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月17日



---

## 🌈 今日知识点总结

### 1. 方法传参机制（非常重要❗️）

#### 1.1 形参与实参

+ 「**实参**」：对象调用方法时，向方法中传递的参数称为「**实参**」（Parameter）

+ 「**形参**」：在类中定义方法时，该方法指明的参数称为「**形参**」（Argument）

```java
public class Test {
    public static void main(String[] args){
      	int n1 = 100;
      	int n2 = 200;
				Tools t = new Tools();
      
        t.getSum(n1,n2);     //此处的n1、n2、1000、2000均为「实参」
      	t.getSum(1000,2000);
    }
}

class Tools{
		public int getSum(int n1,int n2){ //此处的n1、n2均为「形参」
    		...
  	}
}
```

<br/>

#### 1.2 方法传参机制

**方法传参机制** 主要根据 **形参的数据类型不同**，分为 2 种情况：

+ **形参** 是 「**基本数据类型**」，采用「**值传递**」的方式。

+ **形参** 是 「**引用数据类型**」，采用「**引用传递**」的方式。

关于「**值传递**」与「**引用传递**」的内容，详见 「**Java 学习日记**」系列博客 和 「**韩顺平老师**」B站视频讲解：

> [【Java】学习日记 Day10](https://blog.csdn.net/qq_46025844/article/details/125747990?csdn_share_tail=%7B%22type%22%3A%22blog%22%2C%22rType%22%3A%22article%22%2C%22rId%22%3A%22125747990%22%2C%22source%22%3A%22qq_46025844%22%7D&ctrtid=c411e)
>
> [【视频讲解】值传递与引用传递—B站（韩顺平老师）](https://www.bilibili.com/video/BV1fh411y7R8?p=164&vd_source=796196124611740a485335e1a4b12c0f)
>
> [【视频讲解】方法传参机制—B站（韩顺平老师）](https://www.bilibili.com/video/BV1fh411y7R8?p=212&vd_source=796196124611740a485335e1a4b12c0f)

<br/>

📝 **示例 1**：形参是 **基本数据类型**

> 查看代码第 9 行输出结果，`n1`，`n2` 的值是否因为方法的调用而发生改变？

```java
public class Example {
    public static void main(String[] args){
      	int n1 = 100;
      	int n2 = 200;
      
				Tools t = new Tools();
        t.modifyNum(n1,n2);  
      	//查看n1，n2的值是否因为方法的调用而发生改变
      	System.out.println("n1 = " + n1 + "\tn2 = " + n2);
    }
}

class Tools{
		public void modifyNum(int n1,int n2){ 
    		n1 = n1 + 10;   //在方法中修改 形参n1，n2的值
      	n2 = n2 - 10;
  	}
}
```

**输出结果**：

输出 `n1 = 100	n2 = 200` ，即 `n1`、`n2` 的值并 **没有因为方法的调用而改变**。

<br/>

📝 **示例 2**：形参是 **引用数据类型（数组）**

> 查看代码第 14 行输出结果，`arr` 的值是否因为方法的调用而发生改变？

```java
public class Example {
    public static void main(String[] args){
      	int[] arr = new int[6];
				for(int i = 0;i < arr.length;i++){
          arr[i] = i;   //在方法中修改 形参arr的值
        }
      
				Tools t = new Tools();
        t.modifyArr(arr);  //调用方法
      
      	//查看arr的值是否因为方法的调用而发生改变
				for(int i = 0;i < arr.length;i++){
          System.out.print(arr[i] + " ");
        }
    }
}

class Tools{
		public void modifyArr(int[] arr){ 
				for(int i = 0;i < arr.length;i++){
          arr[i] += 10;   //在方法中修改 形参arr的值
        }
  	}
}
```

**输出结果与分析**：

输出 `10 11 12 13 14 15 ` ，即 `arr` 的值因为方法的调用而 **发生改变**。

<br/>

📝 **示例 3**：形参是 **引用数据类型（对象）**

> 查看代码第 8 行输出结果，`p.age` 的值是否因为方法的调用而发生改变？

```java
public class Example {
    public static void main(String[] args){
      	Person p = new Person();
				p.age = 18;
        p.modifyObj(p);  //调用方法
      
      	//查看p.age的值是否因为方法的调用而发生改变
				System.out.println(p.age);
    }
}

class Person{
		int age;
		public void modifyObj(Person p){ 
				p.age += 10;
  	}
}
```

**输出结果与分析**：

输出 `28` ，即 `p.age` 的值因为方法的调用而 **发生改变**。

<br/>

🧐 **思考题**（重要，必需掌握❗️）

> 在 **示例 3** 的基础上，如果将 Person 类的代码修改为以下两种方式，输出结果会有什么变化？

```java
//第一种修改方式
class Person{
		int age;
		public void modifyObj(Person p){ 
        p = null;   //将 p 设置为空指针
  	}
}

//第二种修改方式
class Person{
		int age;
		public void modifyObj(Person p){ 
        p = new Person();     //新建一个对象p
      	p.age = 28;
  	}
}
```

**输出结果与分析**：

第一种修改方式：输出保持不变，仍为 `18`	

第二种修改方式：输出保持不变，仍为 `18`	

> [【视频讲解】思考题输出分析—B站（韩顺平老师）](https://www.bilibili.com/video/BV1fh411y7R8?p=213&vd_source=796196124611740a485335e1a4b12c0f)

<br/>

## ✏️ 今日随记

学习 Java 的 **第 15 天**。⏰

今天主要整理了Java 面向对象中的 「**方法传参机制**」，理清形参与实参的联系与区别。

这是一篇提前写好定时发布的博客，这篇博客更新的时候，博主已经在「厦门」玩耍啦。🏄🏻

估计未来几天都不会更新，等旅游回来后再开启第 4 个「5 + 1 +1」的学习周期，恢复更新 ✊

今日摘录：

> 「 ***The reason for time is so that everything doesn't happen at once*** 」— *Albert Einstein*

---

**相关博客**：

[【Java】学习日记 Day14](https://blog.csdn.net/qq_46025844/article/details/125805093)

[【Java】学习日记 Day13](https://blog.csdn.net/qq_46025844/article/details/125798214?spm=1001.2014.3001.5502)

[【Java】学习日记 Day12](https://blog.csdn.net/qq_46025844/article/details/125778713?spm=1001.2014.3001.5501)












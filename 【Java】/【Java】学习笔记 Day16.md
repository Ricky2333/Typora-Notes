![image-20220702163210840](https://img-blog.csdnimg.cn/img_convert/1a0b6d3652dc36ca62aa7729e89b4827.jpeg)

作者｜Rickyの水果摊

时间｜2022年7月21日

---

## 🌈 今日知识点总结

### 方法重载（Overload）

#### 1. 方法重载的定义

「**方法重载**」是指 Java 允许在同一个类中，定义多个 **方法名相同**，但是 **形参列表不同** 的方法。

<br/>

#### 2. 方法重载的优点

+ 减少方法的取名压力
+ 减少方法的记名压力

<br/>

#### 3. 方法重载的实例

在「**方法重载**」中，各方法之间的 **形参列表不同** **至少包括** 以下 3 种情况的 1 种：

+ 形参 **个数不同**
+ 形参 **类型不同**
+ 形参 **顺序不同**

##### 1. 形参 「个数不同」：

```java
class Tool{
	public int getSum(int n1,int n2){       //int  int
		return n1 + n2;
	}
  public int getSum(int n1,int n2,int n3){//int  int  int
		return n1 + n2 + n3;   //第2个getSum方法 与 第1个getSum方法的 形参个数不同，构成方法重载
	}
}
```

##### 2. 形参 「类型不同」：

```java
class Tool{
	public int getSum(int n1,int n2){         //int  int
		return n1 + n2;
	}
  	public double getSum(double n1,double n2){//double  double
		return n1 + n2;             //第2个getSum方法 与 第1个getSum方法的 参数类型不同，构成方法重载
	}
}
```

##### 3. 形参 「顺序不同」：

```java
class Tool{
  	public double getSum(int n1,double n2){ //int  double
  		return n1 + n2;
	}
 	public double getSum(double n1,int n2){ //double  int
		return n1 + n2;            //第2个getSum方法 与 第1个getSum方法的 形参顺序不同，构成方法重载
	}
}
```

在 **主类中** 调用以上方法：

```java
public MyTools {
	public void main(String[] args) {
		Tool tool = new Tool();
    res1 = tool.getSum(10,20);      //int int
    res2 = tool.getSum(10,20,30);   //int int int
    res3 = tool.getSum(11.1,22.2);  //double double
    res4 = tool.getSum(33.3,10);    //double int 
    res4 = tool.getSum(10,33.3);    //int double
	}
}
```

<br/>

#### 4. 方法重载的判断技巧

本质：在主类中调用重载方法时，系统需要 **清楚的知道** 调用哪一个重载的方法。

+ **方法名相同**：首先看 2 个方法的方法名是否相同，方法名不同，就不构成重载。

+ **形参列表不同**：在方法名一致的前提下，按照定义对比形参列表。
+ **形参名**：没有要求。
+ **返回类型**：没有要求。



🤔 思考题（重要，必须掌握❗️）

> 判断下列方法是否构成「方法重载」

```java
//题目1:
public int getSum(int n1,int n2){ ... }
public int getSun(int a,int b){ ... }

//题目2:
public int getSum(int n1,int n2){ ... }
public void getSum(int n1,int n2){ ... }

//题目3:
public double getSum(double n1,int n2){ ... }
public double getSum(int n2,double n1){ ... }

//题目4:
public double getSum(double n1,double n2){ ... }
public double getSum(double n2,double n1){ ... }

//题目5:
public int getSum(int n1,int n2,int n3){ ... }
public void getSum(int n1,int n2){ ... }
```

1. ❌ 首先看方法名是否相同，不相同，不构成重载。

2. ❌ 首先看方法名是否相同，相同；再看形参列表是否相同，相同（与 **返回类型无关**），不构成重载。

3. ✅ 首先看方法名是否相同，相同；再看形参列表是否相同，不相同（形参 **顺序不同**），构成重载。

4. ❌ 首先看方法名是否相同，相同；再看形参列表是否相同，相同（与 **形参名无关**），不构成重载。

5. ✅ 首先看方法名是否相同，相同；再看形参列表是否相同，不相同（形参 **个数不同**），构成重载。

<br/>

## ✏️ 今日随记

学习 Java 的 **第 16 天**。⏰

今天主要整理了Java 面向对象中的「**方法重载**」的相关内容，难度并不是很大。

今天也是第 4 个「5 + 1 +1」的学习周期的第 1 天，接下来继续加油✊

今日摘录：

>  「 ***I could either watch it happen or be part of it*** 」— *Elon Musk*

---

**相关博客**：

[【Java】学习日记 Day15](https://blog.csdn.net/qq_46025844/article/details/125814016)

[【Java】学习日记 Day14](https://blog.csdn.net/qq_46025844/article/details/125805093)

[【Java】学习日记 Day13](https://blog.csdn.net/qq_46025844/article/details/125798214?spm=1001.2014.3001.5502)
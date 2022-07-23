![image-20220702163210840](https://img-blog.csdnimg.cn/img_convert/1a0b6d3652dc36ca62aa7729e89b4827.jpeg)

作者｜Rickyの水果摊

时间｜2022年7月23日

---

## 🌈 今日知识点总结

### 可变参数

#### 1. 可变参数的定义

「**可变参数**」是指 Java 允许以 `[DataType]... [arg_name]` 的方式定义形参，之后可以向该方法中传入 **任意数量（> 0）** 的 `DataType` 类型参数。

**实例**：`public void sum(int... arr)` 、`public void test(int,String,double... nums)` 

<br/>

#### 2. 可变参数的优点

「**可变参数**」将同一个类中 **多个同名同功能但参数个数不同** 的方法，**封装成了一个方法**，提高了 **代码的复用性**。

<br/>

#### 3. 可变参数的示例程序

定义 `getSum` 方法，使其能够输出 **任意个数** 的传入参数之和。

```java
class Tool {
    public void getSum(int... arr) {   //int... arr 就是 int 类型的可变参数
        int sum = 0;
        for (int i = 0; i < arr.length; i++) {
            sum += arr[i];
        }
        System.out.println(sum);
    }
}
```

在 **主类中** 调用该方法：

```java
public class Test {
    public static void main(String[] args) {
        Tool tool = new Tool();
        tool.getSum();  //传入任意数量的参数
        tool.getSum(10);
        tool.getSum(10, 20, 30);
        tool.getSum(10, 20, 30, 40);
    }
}
```

**测试结果**：

![image-20220723202826749](https://tva1.sinaimg.cn/large/e6c9d24ely1h4h4uq6f03j20y0046mxu.jpg)

<br/>

#### 4. 可变参数的注意事项

🍉 **PS1**：可变参数的实参可以为 **0 个或多个**。

在上面的示例中，在主类中调用 `getSum` 方法时，无论传入的参数是 **0 个还是多个**，结果均正确。

<br/>

🍉 **PS2**：可变参数的实参可以为 **数组**，但是当形参只有可变参数时，不能同时传入数组和其他实参。

```java
public class Test {
    public static void main(String[] args) {
      	int[] nums = {1,2,3,4,5};  //定义一个整数数组 nums
        Tool tool = new Tool();
    		tool.getSum(nums);    //正确，结果输出该数组之和
      	tool.getSum(10,nums); //错误，无法计算 10 与该数组之和
    }
}
```

<br/>

🍉 **PS3**：可变参数的**本质为数组**。

```java
class Tool {
    public void getSum(int... arr) {   //int... arr 就是 int 类型的可变参数
        int sum = 0;
        for (int i = 0; i < arr.length; i++) {
            sum += arr[i];
        }
        System.out.println(sum);
    }
}
```

在上面的示例中，可变参数均存储在名为 `arr` 的数组中，也是通过调用 `arr` 数组，来计算总和。

<br/>

🍉 **PS4**：在 **定义形参列表时**，可变参数可以和其他形参同时存在，但必须保证 **可变参数在形参列表最后**，且 1 个形参列表中 **最多只能有 1 个可变参数**。

> 判断下列方法的定义是否符合 Java 语法要求

```java
1. public int getSum(int... nums,double d){ ... }
2. public int getSum(int n1,int n2,int... nums){ ... }
3. public int getSum(int,int... nums,double... arr){ ... }
```

1. ❌ 可变参数必须定义在形参列表的最后。
2. ✅ 该定义符合 Java 语法要求。
3. ❌ 1 个形参列表最多只能有 1 个可变参数。

<br/>

## ✏️ 今日随记

学习 Java 的 **第 17 天**。⏰

今天主要整理了Java 面向对象中的「**可变参数**」的相关内容，较为简单。

接下来继续加油✊

今日摘录：

>  「 ***Nothing is impossible to a willing heart*** 」

---

**相关博客**：

[【Java】学习日记 Day16](https://blog.csdn.net/qq_46025844/article/details/125920143?spm=1001.2014.3001.5502)

[【Java】学习日记 Day15](https://blog.csdn.net/qq_46025844/article/details/125814016)

[【Java】学习日记 Day14](https://blog.csdn.net/qq_46025844/article/details/125805093)


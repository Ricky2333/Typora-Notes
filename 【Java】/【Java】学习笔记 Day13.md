![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月15日



---

## 🌈 今日知识点总结

### Java 面向对象基础

#### 1. 为什么要引入类与对象？



#### 2. 二维数组的内存布局

![image-20220713225857814](https://tva1.sinaimg.cn/large/e6c9d24ely1h45p07zvmbj21ja0j8jww.jpg)

[【视频讲解】二维数组的内存布局—B站（韩顺平老师）](https://www.bilibili.com/video/BV1fh411y7R8?p=177&vd_source=796196124611740a485335e1a4b12c0f)

<br/>

#### 3. 二维数组注意点

🍉 **PS1**：二维数组有 **三种定义方式**，三者均等价。

<br>

🍉 **PS2**：二维数组 **由多个一维数组构成**，数组名后的 **方括号数量不同**，代表的内容也完全不同。

+ `arr` 表示二维数组 **本身**，是 `int[][]` 类型。

+ `arr[n] ` 表示二维数组中的 **某一个一维数组**，是 `int[]` 类型。
+ `arr[n][m]` 表示二维数组中的 **某一个具体元素**，是 `int` 类型。

**示例程序**：

```java
int[][] arr = new int[3][5];
arr        //是int[][]类型，即为二维数组
arr[1]     //是int[]类型，即为一维数组
arr[1][1]  //是int 类型，即一个具体的元素
```

**判断题**：

6. 

<br/>





#### 4. 二维数组编程练习

#### 🟢 1. 输出二维数组的元素总和

📝 **题目描述**：

> 随机生成 2*5 的二维数组，元素范围是 [1,10] 的整数，并且输出该二维数组的元素总和。

🧑🏻‍💻 **源代码**：

```java
public class TwoDimSum {
    public static void main(String[] args){
        int[][] arr = new int[2][5];
        int sum = 0;
        for(int i = 0;i < arr.length;i++){
            for(int j = 0;j < arr[i].length;j++){
                arr[i][j] =(int)(Math.random()*10 + 1);  //随机生成范围为[1,10]的整数
                sum += arr[i][j];
            }
        }
        for(int i = 0;i < arr.length;i++){   //输出生成的二维数组
            for(int j = 0;j < arr[i].length;j++){
                System.out.print(arr[i][j] + " ");
            }
            System.out.println("");
        }
        System.out.println("sum = " + sum);
    }
}
```

<br/>

#### 🟡 2. 杨辉三角

📝 **题目描述**：

> 输出一个 6 行的杨辉三角。效果图如下：

```java
1 
1 1 
1 2 1 
1 3 3 1 
1 4 6 4 1 
1 5 10 10 5 1
```



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














![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月14日



---

## 🌈 今日知识点总结

### Java 二维数组

#### 1. 二维数组的初始化

##### 动态初始化：

```java
//方式1:声明数组后直接 new 分配空间
int[][] arr0 = new int[3][5]; 

int[][] arr1 = new int[3][]; //二维数组每行的元素个数可以不等，第二个方括号内不指定数字即可
arr1[0] = new int[1];    //这种情况需要new两次，原因见下文「二维数组的内存布局」
arr1[0] = new int[2];
arr1[0] = new int[3];

//方式2:先声明数组，再 new 分配空间
int[][] arr2;
arr2 = new int[3][5];

//二维数组的循环赋值
for(int i = 0;i < arr2.length;i++){   //arr2.length表示二维数组包含的一维数组个数
  for(int j = 0;j < arr2[i].length;j++){ //arr2[i].length表示每个一维数组包含的元素个数
  	arr2[i][j] = myScanner.nextInt();
  }
}
```

<br/>

##### 静态初始化：

```java
int[][] arr = {{1,2,3,4},{1,2,3,4,5},{1,2,3,4,5,6}}
```

<br/>

#### 2. 二维数组的内存布局

![image-20220713225857814](https://tva1.sinaimg.cn/large/e6c9d24ely1h45p07zvmbj21ja0j8jww.jpg)

[【视频讲解】二维数组的内存布局—B站（韩顺平老师）](https://www.bilibili.com/video/BV1fh411y7R8?p=177&vd_source=796196124611740a485335e1a4b12c0f)

<br/>

#### 3. 二维数组注意点

🍉 **PS1**：二维数组有 **三种定义方式**，三者均等价。

+ `int[][] arr ` 
+ `int[] arr[] `
+ `int arr[][] `  

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

声明 `int[] x,y[]`，判断以下语句是否能够通过编译。

```java
1. x[0] = y;

2. y[0] = x;

3. y[0][0] = x;

4. x[0][0] = y;

5. y[0][0] = x[0];

6. x = y;
```

1. ❌  `y` 为 `int[][]` 类型，`x[0]` 为 `int` 类型，`int[][]` 不可以赋值给 `int` 类型。
2. ✅  `x` 为 `int[]` 类型，`y[0]` 为 `int[]` 类型，相同类型可以赋值。
3. ❌  `x` 为 `int[]` 类型，`y[0][0]` 为 `int` 类型，`int[]` 不可以赋值给 `int` 类型。
4. ❌  `x` 为一维数组，没有第二个下标。
5. ✅  `x[0]` 为 `int` 类型，`y[0][0]` 为 `int` 类型，相同类型可以赋值。
6. ❌   `y` 为 `int[][]` 类型，`x` 为 `int[]` 类型，`int[][]` 不可以赋值给 `int[]` 类型。

<br/>

🍉 **PS3**：二维数组中的一维数组元素个数可以相等，**也可以不相等**，后者称为「**列数不等的二维数组**」。

```java
int[][] arr1 = new int[3][]   //动态初始化「列数不等的二维数组」

int[][] arr = {{1},{1,2},{1,2,3},{1,2,3,4}} //静态初始化「列数不等的二维数组」
//arr[0] 包含1个元素
//arr[1] 包含2个元素
//arr[2] 包含3个元素
//arr[4] 包含4个元素
```

<br/>

🍉 **PS4**：二维数组若列数不确定，且采用动态初始化方式，需 `new` 两次创建。（结合内存图分析）。

```java
int[][] arr1 = new int[2][3];   //列数确定，一步到位

int [][] arr2 = new int[2][];   //列数不确定，此步仅创建了1个二维数组，包含了2个一维数组名
arr2[0] = new int[3];     //为arr2[0] 分配内存空间
arr2[0] = new int[2];     //为arr2[1] 分配内存空间
```

<br/>

🍉 **PS5**：二维数组中，若某行只有 **单个元素**，这个元素 **也应当由方括号括起来**，否则会报错。

❌  `int[][] arr = {1,{1,2},{1,2,3},{1,2,3,4}} //元素1未添加方括号`

✅  `int[][] arr = {{1},{1,2},{1,2,3},{1,2,3,4}}////元素1添加方括号后，由 int 变为 int[] `

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

☘️ **提示**：需注意 **列数不等的二维数组** 创建时的 **内存分配问题**。

🧑🏻‍💻 **源代码**：

```java
public class PascalTriangle {
    public static void main(String[] args){
        int[][] arr = new int[6][];
      
        //生成杨辉三角
        for(int i = 0;i < arr.length;i++){
            arr[i] = new int[i + 1];    //非常容易遗忘的一步
            for(int j = 0;j < arr[i].length;j++){
                if(j == 0 || j == arr[i].length - 1 ){
                    arr[i][j] = 1;
                }else{       //杨辉三角的数量关系
                    arr[i][j] = arr[i - 1][j] + arr[i - 1][j - 1];
                }
            }
        }
      
        //输出杨辉三角
        for(int i = 0;i < arr.length;i++){
            for(int j = 0;j < arr[i].length;j++){
                System.out.print(arr[i][j] + " ");
            }
            System.out.println("");
        }
    }
}
```

<br/>

## ✏️ 今日随记

学习 Java 的 **第 12 天**。⏰

今天主要整理了二维数组的相关内容，感觉二维数组相比一维数组，还是有不少需要注意的地方。☘️

明天正式开始学习 **面向对象**，继续加油 ✊

今日摘录：

>  *「 **Talk is cheap.Show me the code** 」— Linus Torvalds*

---

**相关博客**：

[【Java】学习日记 Day11](https://blog.csdn.net/qq_46025844/article/details/125756960)

[【Java】学习日记 Day10](https://blog.csdn.net/qq_46025844/article/details/125747990?csdn_share_tail=%7B%22type%22%3A%22blog%22%2C%22rType%22%3A%22article%22%2C%22rId%22%3A%22125747990%22%2C%22source%22%3A%22qq_46025844%22%7D&ctrtid=c411e)

[【Java】学习日记Day 9](https://blog.csdn.net/qq_46025844/article/details/125669124?spm=1001.2014.3001.5501)














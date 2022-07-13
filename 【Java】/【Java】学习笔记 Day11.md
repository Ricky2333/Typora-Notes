![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年7月13日



---

## 🌈 今日知识点总结

### Java 数组编程练习

#### 1. 打印大写字母表

📝 **题目描述**：

> 打印大写字母表。

🧑🏻‍💻 **源代码**：

```java
public class ArrChar {
	public static void main(String[] args) {
        char[] c = new char[26];
        for (int i = 0;i < c.length;i++){
            c[i] = (char)('A' + i);   //注意此步强制转换，非常容易遗漏
        }
        for (int i = 0;i < c.length;i++){
            System.out.println(c[i]);
        }
	}
}
```

<br/>

#### 2. 数组拷贝

📝 **题目描述**：

> 拷贝数组 arr1 的值，存储到新的数组 arr2 中。（两个数组需要有不同的内存空间）

🧑🏻‍💻 **源代码**：

```java
public class ArrayCopy {
    public static void main(String[] args){
        int[] arr1 = {1,2,3,4,5,6};
        int[] arr2 = new int[arr1.length];   //创建相同长度的新数组 arr2
        
        for(int i = 0; i < arr1.length; i++){  //拷贝
          arr2[i] = arr1[i];
        }
    }
}
```

<br/>

#### 3. 数组逆序

📝 **题目描述**：

> 将 数组arr 中的元素 逆序存储（还是存储在 arr 中）

🧑🏻‍💻 **源代码**：

```java
public class ArrayReverse {
    public static void main(String[] args){
        int[] arr = {1,2,3,4,5,6};
        int tmp;
        for(int i = 0; i < arr.length / 2; i++){  
          tmp = arr[i];                       //当前首尾元素交换
          arr[i] = arr[arr.length - i -1];   
          arr[arr.length - i -1] = tmp;
        }
        for (int i = 0;i < arr.length;i++){   //打印逆序结果
            System.out.print(arr[i] + " ");
        }
    }
}
```

<br/>

#### 4. 冒泡排序

📝 **题目描述**：

> 冒泡排序，升序。

🧑🏻‍💻 **源代码**：

```java
public class BubbleSort {
    public static void main(String[] args) {
        int[] arr = {4,8,3,2,1,0,9};
        int tmp;

        for(int i = 0;i < arr.length - 1;i++){   //冒泡排序共需 arr.length - 1 趟
            for(int j = 0; j < arr.length - i - 1;j++){ 
                if(arr[j] > arr[j+1]){   //交换
                    tmp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = tmp;
                }
            }
        }
        for(int i = 0;i < arr.length;i++) {   //输出排序结果
            System.out.print(arr[i] + " ");
        }
    }
}
```

<br/>

#### 5. 选择排序

📝 **题目描述**：

> 选择排序，升序。

🧑🏻‍💻 **源代码**：

```java
public static void main(String[] args) {
    int[] arr = {3,1,8,6,2,9,4,5};
    int tmp;
  
    for(int i = 0;i < arr.length - 1;i++){
        int minIndex = i;
        for(int j = i + 1;j < arr.length;j++){
            if(arr[j] < arr[minIndex])
                minIndex = j;
        }
        if(minIndex != i){
            tmp = arr[i];
            arr[i] = arr[minIndex];
            arr[minIndex] = tmp; 
        }
    }
  
    for(int i = 0;i < arr.length;i++){      //输出排序结果
        System.out.print(arr[i] + " ");
    }
}
}
```

<br/>

#### 6. 二分查找

📝 **题目描述**：

> 二分查找

🧑🏻‍💻 **源代码**：

```java
public class BinarySearch {
    public static void main(String[] args) {
        int[] arr = {10,20,30,40,50,60,70};
        int i = 0;
        int j = arr.length -1 ;
				int key = 11;           //key为想要查找的值

        while(i <= j){
            int mid = (i + j) / 2;   //mid为每轮循环中间值下标
            if(arr[mid] == key){
                System.out.println("Success");
                break;
            }else if(key < arr[mid])
                j = mid -1;
             else
                i = mid + 1;
        }

        if(i > j)
          System.out.println("Fail");

    }
}
```



<br/>

## ✏️ 今日随记

学习 Java 的 **第 11 天**。⏰

今天主要整理了本章的编程习题，同时回顾了一些经典的算法，如冒泡排序、选择排序、二分查找等，梦回高中。😂

今日摘录：

>  *「 **Extract the eternal from the ephemeral** 」— Baudelaire*

---

**相关博客**：

[【Java】学习日记 Day10](https://blog.csdn.net/qq_46025844/article/details/125747990?csdn_share_tail=%7B%22type%22%3A%22blog%22%2C%22rType%22%3A%22article%22%2C%22rId%22%3A%22125747990%22%2C%22source%22%3A%22qq_46025844%22%7D&ctrtid=c411e)

[【Java】学习日记Day 9](https://blog.csdn.net/qq_46025844/article/details/125669124?spm=1001.2014.3001.5501)

[【Java】学习日记Day 8](https://blog.csdn.net/qq_46025844/article/details/125649393?spm=1001.2014.3001.5501)












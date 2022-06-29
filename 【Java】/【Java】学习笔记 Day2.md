# 【Java】学习日记 Day2



## 🌟今日知识点总结

### 1.  Java 运行机制

+ Java 源程序通过 **`javac [filename.Java]`** 编译，生成 `filename.class` 的字节码文件。
+ 字节码文件通过 **`java [filename]`** 命令，借助不同平台的 **JVM** 在主机上运行。（注：`java 命令` 的文件名无需加 .class 后缀）

![image-20220629171658988](https://tva1.sinaimg.cn/large/e6c9d24ely1h3p8g3xfsmj21au0k2tbl.jpg)



### 2. JDK、JRE、JVM 的联系与区别

**JDK**

> **JDK** 的全称是 **Java Developent Kit**，是 Java 语言的 **软件开发工具包**，主要用于移动设备、嵌入式设备上的 Java 应用程序，是整个 **Java 开发的核心**。

**JRE**

> **JRE** 的全称是 **Java Runtime Environment**，是 Java 程序运行所需要的软件环境，用于解释执行 Java 的字节码文件 。普通用户只需要安装 JRE 来运行 Java 程序即可；而程序员则必须安装 JDK ，来编译、调试 Java 程序。

**JVM**

> **JVM** 的全称是 **Java Virtual Machine**，即 Java 虚拟机。 **它是整个** **Java** **实现跨平台的核心** ，负责解释执行字节码文件，是可运行 Java 字节码文件的虚拟计算机。



**三者的关系**
$$
JDK \supset JRE \supset JVM
$$
![image-20220629173245564](https://tva1.sinaimg.cn/large/e6c9d24ely1h3p8whr0g7j21b20iwn0a.jpg)



### 3. Java HelloWorld 程序编写

**HelloWorld.java 源程序**

```java
public class HelloWorld {
  public static void main() {
    System.out.println("Hello world\n");
  }
}
```

**编译**

```bash
javac HelloWorld.java  #编译 HelloWorld.java，生成 HelloWorld.class 文件
```

![image-20220629234647653](https://tva1.sinaimg.cn/large/e6c9d24ely1h3pjpnz2pgj21h6094mzf.jpg)



**运行**

```bash
java HelloWorld
```

![image-20220629232241483](https://tva1.sinaimg.cn/large/e6c9d24ely1h3pj0mem1vj22by054gn4.jpg)





## ✏️今日随记

今天是学习 Java 的 **第 2 天**，也是格外忙碌的一天，还好还是赶在 24点的 **DDL** 之前写完了这篇学习笔记✅，没有让自己昨天立下的 Flag 还没插稳就倒下了。🙈（当前时间：2022年 6月 29日 23：25）

由于今天要 **收拾行李**，**坐高铁回家**（学校去往高铁站的路上还下起了大雨，我真的会谢🥀），学习 Java 的时间就被大大压缩，仅仅在高铁上学习了一会韩顺平老师的 Java 网课，看到 EP20。（好吧，其实还有很大一部分时间是在二刷 「**四谎**」摸鱼。😂 四谎真的太好看了，虽然内心疯狂想给作者寄刀片。。。小薰真的。。。我哭死😭 ）

回家后匆匆回顾了一下今天所学，敲完这篇学习日记就准备休息了（ **润了润了**💨）

希望明天能够继续 **坚持**，争取 **不咕咕**🐦，**奥利给**✊

（PS：我觉得我有必要花点时间去看看 MD格式的日记怎么写，感觉心理描写啥的用一个括号来排版也太不美观了，容我明天研究研究🧐）


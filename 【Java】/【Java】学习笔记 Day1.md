![image-20220702163210840](https://tva1.sinaimg.cn/large/e6c9d24ely1h3so0dh978j21du0l80vm.jpg)

作者｜Rickyの水果摊

时间｜2022年6月28日

---



## ✍️ 写在最前

本系列博客主要记录博主学习 Java 的历程，帮助博主更好的总结每天学到的知识点，同时便于日后的复习。



### 个人介绍

博主目前就读于某双非 CS 专业，是一名即将成为大三狗的学生。



### 学习动机

+ 由于某些特殊原因，博主虽然是 CS 专业，但学校专业核心课却不包含 Java 的内容（此处博主想借用汤家凤老师的名言来吐槽「这学校课程安排，真是让人匪夷所思啊」），而是以 Python 为主。但博主认为，不学 Java 的 大学生活是不完整的，没有灵魂的，博主也不想在未来遇到同行或老师时，被调侃「你这 CS 专业连 Java 都不学，还能叫 CS 专业吗？」

+ 经过了解，大三的部分专业拓展课需要有 Java 基础。在没有 Java 的基础下去学习这些课程，会比较吃力。
+ Java 语言在企业中应用比较广泛，就业前景较为不错。
+ 不想浪费暑假，把时间全花在娱乐休闲上。



### 学习材料

经过一系列学习路线的查询后，博主确定了一些基本的学习材料，决定先从 **韩顺平老师的零基础学 Java 网课** 开始学习。

**视频资料：**

+ [韩顺平零基础学 Java — B站（UP主：韩顺平）](https://www.bilibili.com/video/BV1fh411y7R8?spm_id_from=333.999.0.0)

+  [Java 学习路线 — B站（UP主：鱼皮程序员）](https://www.bilibili.com/video/BV1Qf4y1K7ff/?spm_id_from=333.788&vd_source=796196124611740a485335e1a4b12c0f)

**书籍资料：**

+ [Java核心技术·卷 I（原书第11版）](https://book.douban.com/subject/34898994/)

+ [Head First Java](https://book.douban.com/subject/2000732/)

**在线编程网站：**

+ [Java 在线编程网站](https://c.runoob.com/compile/10/)



### 开发环境

设备：MacBook Pro 2021 （M1 Pro芯片）

系统：MacOS

常用开发环境：Sublime Text、VS Code、IntelliJ IDEA

JDK版本：JDK 8 



## 🌈 今日知识点总结

### 1.  Java 概述

#### Java 特点

+ **面向对象编程**（Object-Oriented Programming）
+ **跨平台性**（一个编译好的 **.class文件 **可以在多个系统下运行）
+ **健壮性**（Java 的强类型机制、异常处理、垃圾的自动收集等是 Java 健壮性的重要保证）
+ **解释性语言**（解释性语言，编译后的代码，不能直接被机器执行,需要解释器来执行）



#### Java 应用场景

+ 企业级应用

+ Android 平台应用
+ 移动领域应用



#### Java 历史

+ 1991年，**Sun 公司** 成立了一个由 **James Gosling** 领导的 **Green Project**

+ 1995年，Sun 公司正式在 Sun World 大会上正式发布 **Java 1.0** 版本
+ 1996年，**JDK1.0** 正式发布

**Java 之父**：James Gosling

<img src="https://tva1.sinaimg.cn/large/e6c9d24ely1h3o2kkvwdtj20rq0kkjtu.jpg" alt="image-20220628170809416" style="zoom:50%;" />

[Java 发展史](https://www.bilibili.com/read/cv10243683/)

[Java 发展史—漫画版](https://baijiahao.baidu.com/s?id=1695678076341107704&wfr=spider&for=pc)



#### Java 技术体系平台

**Java SE**（Java Standard Edition）— 标准版

**Java EE**（Java Enterprising Edition）— 企业版

**Java ME**（Java Micro Edition）— 微型版



### 2. Java 开发环境配置

博主使用的设备是M1 Pro芯片的MacBook Pro，M系列芯片为ARM架构。截止目前（2022.6.28），Java 的常用工具均已适配 M系列芯片，且性能相比于 intel芯片的 MacBook 均有大幅提升。以下环境配置均基于此设备。

[M系列芯片的 Java开发测试—B站（UP：CodeSheep）](https://www.bilibili.com/video/BV14f4y1e7MU?spm_id_from=333.999.0.0&vd_source=796196124611740a485335e1a4b12c0f)



#### JDK配置

经过了解与学习，目前企业中主要使用的 JDK 版本为 **JDK8** 与 **JDK11**，且这两个版本均为 「**Long Term Supprot**」的 LTS 版本，故博主选择安装 JDK8 。

[Mac M系列芯片的 JDK 安装教程—B站（UP主：小新不吃蔬菜）](https://www.bilibili.com/video/BV16L4y1b75R?p=1&vd_source=796196124611740a485335e1a4b12c0f)



#### 开发环境配置

**Sublime Text**

[Sublime Text 的安装视频教程—B站（UP主：小新不吃蔬菜）](https://www.bilibili.com/video/BV16L4y1b75R?p=2&vd_source=796196124611740a485335e1a4b12c0f)



**VSCode**

[VSCode 官网下载链接](https://code.visualstudio.com/Download)

[VSCode 配置 Java环境—B站（搬运）](https://www.bilibili.com/video/BV1Vq4y1P7vJ?spm_id_from=333.337.search-card.all.click&vd_source=796196124611740a485335e1a4b12c0f)



**IDEA**

[IDEA 官网下载链接](https://www.jetbrains.com/idea/download/#section=mac)

[IDEA 学生账号认证方式—CSDN](https://blog.csdn.net/m0_52387040/article/details/123966458?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522165641252716782246421464%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=165641252716782246421464&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_click~default-2-123966458-null-null.142^v24^huaweicloudv2,157^v15^new_3&utm_term=IDEA%E5%AD%A6%E7%94%9F%E8%AE%A4%E8%AF%81&spm=1018.2226.3001.4187)



## ✏️ 今日随记

今天是学习 Java 的第一天，也是撰写这个「**学习日记**」系列的第一天。总有一种「**新官上任三把火**」的感觉，表现方式为学习时特别有 **动力和干劲**，热情满满。

希望自己能够坚持下去，等暑假结束回过头来，再看这第一篇博文时，能够骄傲的对自己说：**你，做到了**。

---


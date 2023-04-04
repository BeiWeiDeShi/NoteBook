1. Java的集合容器
   
   1. List，Set（继承Collection接口）
      
      - List有序，插入元素的顺序，可以存放重复的值和null值
      
      - Set无序，值各不相同，只能存放一个null值
   
   2. Map（单独的接口，与上面的不同）
      
      - 存放键值对
      
      - 键必须是唯一的，只能存放一个键为null的值，但是值为null可以多个

2. HashMap
   
   1. Key通过HashCode来存储
   
   2. 内部结构：
      
      1. 数组
      
      2. 链表
      
      3. JDK8中提升查询速度的红黑树

---

---

JVM，即JAVA虚拟机:

- Java Virtual Machine的缩写，是用来**运行**Java<mark>**字节码**</mark>程序的一个虚拟计算机。负责将Java<mark>**字节码**转换成底层**机器指令**</mark>，然后执行;

- 我们编写的Java代码，都运行在`JVM`之上

- 任何软件的运行，都必须要运行在操作系统之上，而我们用Java编写的软件可以运行在任何的操作系统上，这个特性称为**Java语言的跨平台性**。该特性是由JVM实现的，我们编写的程序运行在JVM上，而JVM运行在操作系统上。

- <font color="red">**注意：**</font>**Java的虚拟机本身不具备跨平台功能**，每个操作系统下都有不同版本的虚拟机。

---

JRE，JAVA运行环境:
英文全称是Java Runtime Environment，是一个软件包，提供了运行一个Java程序所需的各种组件(环境)

---

JDK，JAVA开发工具箱:
Java Development Kit，它是面向Java开发人员的工具包，提供了开发Java程序所需的各种开发工具(编译器，调试器)，以及运行Java程序的JRE。

---

1. 要开发Java程序，请使用JDK

2. 只想运行Java程序，那JRE就足够了

3. JVM，它是Java体系的<mark>**核心基础组件**</mark>，是Java程序运行的载体

---

<img title="" src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/Java.6wxir1rmiqw0.webp" alt="Java" width="397">

---

字节码，使用JDK**编译器**，得到的byte code，即以<mark>**.class为后缀**</mark>的类文件；

字节码即位“<mark><font color="red">**为虚拟机JVM生成的代码**</font></mark>”，与平台无关；

别的语言也可以编译为字节码，然后在JVM上运行

---

为什么Java跨平台：

<img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/Java.7g16yqubmy80.webp" title="" alt="Java" width="586">

Java语言是平台无关：

1. <mark><font color="red">**字节码与平台无关**</font></mark>

2. JDK、JRE、JVM的具体实现与平台相关

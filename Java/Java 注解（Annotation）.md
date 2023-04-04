# Java 注解（Annotation）

Java 注解（Annotation）又称 Java 标注，是 JDK5.0 引入的一种注释机制。

        Java 语言中的类、方法、变量、参数和包等都可以被标注。和 Javadoc 不同，Java 标注可以通过**反射**获取标注内容。在编辑器生成类文件时，**标注可以被嵌入到字节码中**。Java 虚拟机可以保持标注内容，在运行时可以获取到标注内容。当然它也支持自定义 Java 内容。

> 用来说明程序的，给计算机看的

        理解 Annotation 的关键，是理解 Annotation 的关键，是理解　Annotation　的语法和用法，在理解这些之后，再看 Annotation 的框架图，可以又更深刻体会。

---

##### 内置的注解

Java 定义了一套注解，共有7个，3个在 java.lang 中，剩下 4 个在 java.lang.annotation 中。

###### 作用在代码中的注解是：

| @Override             | 检查该方法是否是重写方法。如果发现其父类，或是引用的接口中并没有该方法时，会报编译错误。 |
| --------------------- | -------------------------------------------- |
| **@Deprecated**       | **标记过时方法。如果使用该方法，会编译报错。**                    |
| **@SuppressWarnings** | **指示编译器去忽略注解中声明的警告。**                        |

###### 作用在其他注解的注解（或者说 元注解）是：

| @Retention      | 标识这个注解怎么保存，是只在代码中，还是编入 class 文件中，或者是在运行时可以通过反射访问。 |
| --------------- | ------------------------------------------------- |
| **@Documented** | **标记这些注解是否包含在用户文档中。**                             |
| **@Target**     | **标记这个注解应该是哪种 Java 成员。**                          |
| **@Inherited**  | **标记这个注解是继承于哪个注解类（默认，注解没有继承于任何子类）**               |

###### 从 Java8 开始，额外添加了 3 个注解：

| @SafeVarargs             | Java7 开始支持，忽略任何使用参数为泛型变量的方法或构造函数调用产生的警告。 |
| ------------------------ | ---------------------------------------- |
| **@FuncitonalInterface** | **Java8 开始支持，标识一个匿名函数或函数式接口**            |
| **@Repeatable**          | **Java8 开始支持，标识某注解可以在同一个声明上使用多次**        |

---

### 1. Annotation 架构

<img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/Annotation.2j6eup94jm00.webp" title="" alt="Annotation" width="537">

从中，我们可以看出：

**(01) 1 个 Annotation 和 1 个 RetentionPolicy 关联。**

可以理解为：每1个Annotation对象，都会有唯一的RetentionPolicy属性。

**(02) 1 个 Annotation 和 1~n 个 ElementType 关联。**

可以理解为：对于每 1 个 Annotation 对象，可以有若干个 ElementType 属性。

**(03) Annotation 有许多实现类，包括：Deprecated, Documented, Inherited, Override 等等。**

Annotation 的每一个实现类，都 "和 1 个 RetentionPolicy 关联" 并且 " 和 1~n 个 ElementType 关联"。

下面，我先介绍框架图的左半边(如下图)，即 Annotation, RetentionPolicy, ElementType；然后在就 Annotation 的实现类进行举例说明。

<img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/Annotation.an51enmcisk.webp" title="" alt="Annotation" width="329">

---

### 2. Annotation 组成部分

Java Annotation 的组成中，有 3 个非常重要的主干类。它们分别是：

```java
// Annotation.java
package java.lang.annotation;

public interface Annotation {

    boolean equals(Object obj);

    int hashCode():

    String toString();

    Class<? extends Annotation> annotationType();
}
```

```java
// ElementType.java
package java.lang.annotation;

public enum ElementType {
    TYPTE,            /* 类、接口（包括注释类型）或枚举声明 */

    FIELD,            /* 字段声明（包括枚举常量） */

    METHOD,           /* 方法声明 */

    PARAMETER,        /* 参数声明 */

    CONSTRUCTOR,      /* 构造方法声明 */

    LOCAL_VARIABLE,   /* 局部变量声明 */

    ANNOTATION_TYPE,  /* 注释类型声明 */

    PACKAGE           /* 包声明 */
}
```

```java
// RetentionPolicy.java
package java.lang.annotation;

public enum RententionPolicy {
    SOURCE,    /* Annotation 信息仅存在与编译器处理期间，
                  编译器处理完之后就没有该 Annotation 信息了 */

    CLASS,

    RUNTIME
}
```





---

### 小结 ：

- 大多数时候，我们会使用注解而不是自定义注解
- 注解给编译器和解析程序用
- 注解不是程序的一部分，可以理解为标签











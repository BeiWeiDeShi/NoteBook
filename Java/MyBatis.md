Tomcat系统各个文件夹目录是什么意义：

1. bin：放置的是Tomcat一些相关的命令，启动的命令（startup）和关闭的命令（shutdown）等等；

2. conf：（configure）配置文件；

3. lib：（library）库，依赖的 jar 包；

4. webapps：可执行的项目。默认作为存放开发项目的目录；

5. work：存放由 jsp 翻译成的 .java 源文件以及编译的 .class 字节码文件 （jsp → java → class）



---



        MyBatis 是一个基于 Java 的支持普通 SQL 查询，存储过程 和 高级映射 的优秀持久层框架，其几乎消除了所有的 JDBC 代码和参数的手工设置以及结果集的检索。MyBatis 基于 SQL 面向结果集，因此其效率更高。

        MyBatis 使用简单的 XML 或 注解 用于**配置**和**原始映射**，将接口和 Java 的 POJOs（Plain Old Java Objects，普通的 Java 对象）映射成数据库中的记录。MyBatis 应用程序大都使用 SqlSessionFactory 实例，SqlSessionFactory 实例可以通过 SqlSessionFactoryBuilder 获得，而 SqlSessionFactoryBuilder 则可以从一个 XML 配置文件 或者 一个预定义的配置类的实例获得。Mybatis 是一个半自动的ORM（Object Relation  Mapping）框架



---



构建 MyBatis 框架的详细步骤：

1. 创建一个 Java Web 项目；
2. 导入 MyBatis 框架的 jar 包；
3. 创建核心配置文件 sqlMapConfig.xml；
4. 创建映射文件 UserMapper.xml；
5. 创建测试类



## SpringBoot

#### SpringBoot 部署-jar 方式

> `Springboot` 和我们之前学习的 `web` 应用程序不一样，其本质上是一个 Java 应用程序，那么又如何部署呢？ 通常来说，`Springboot` 部署会采用两种方式：全部打包成一个 `jar`，或者打包成一个 `war`。 本知识点讲解 `jar` 的方式。

  在项目文件夹中打开终端，输入 `mvn install`，这将会在目录下生成一个 `jar` 文件;

  接着输入命令 `java -jar target/springboot-0.0.1-SNAPSHOT.jar` 就启动这个 jar 了，通过这种方式，把此jar上传到服务器并运行，就可达到部署的效果了。

#### SpringBoot 热部署

> 目前的 `SpringBoot`，当发生了任何修改之后，必须关闭后在启动 `Application` 类才能够生效，显得略微麻烦。
> 
> `SpringBoot` 提供了热部署的方式，当发现任何类发生了改变，马上通过 `JVM` 类加载的方式，加载最新的类到虚拟机中。这样就不需要重新启动就能看到修改后的效果了。

#### DAO 层

`jdbc.properties` 中 `allowPublicKeyRetrieval` 可以实现主键`id`回传的功能（主键是自动递增的）

----

#### SpringBoot 特点

- 遵循 "约定优于配置原则"，只需要很少的配置或使用默认的配置。

- 能够使用内嵌的 Tomcat、Jetty 服务器，不需要部署 war 文件。

- 提供定制化的启动器 Starters，简化 Maven 配置，开箱即用。

- 纯 Java 配置，没有代码生成，也不需要 XML 配置。

- 提供了生产级的服务监控方案，如安全监控，应用监控，健康检测等。

---

```undefined
Spring分为
  1. 狭义
    Spring Framework（本篇文章介绍）
      2个核心功能：Ioc、AOP。
  2. 广义（以Spring Framework框架为核心的Spring技术栈）
    1. Spring Framework
    2. Spring MVC
    3. Spring Boot（Spring团队提供的全新框架，用来简化Spring项目的搭建和开发）
      以Spring为基础，提供了大量开箱即用的依赖包（自动管理依赖包中的依赖、提供了大量默认配置）使开发者更专注于业务逻辑。
    4. Spring Cloud（一款基于Spring Boot实现的微服务框架）
      用来开发高度可扩展、高性能、简单易懂、易部署、易维护的分布式微服务系统。
      它并不是某一门技术，而是一系列微服务解决方案或框架的集合。它将市面上成熟的、经过验证的微服务框架整合后通过Spring Boot的思想进行再封装（屏蔽掉其中复杂的配置和实现原理）。
    5. Spring Mobile（对Spring MVC进行了扩展，用来简化移动端Web应用的开发）
    6. Spring Data
      数据库访问模块。
      通过它，开发人员可以使用一种相对统一的方式，来访问位于不同类型数据库中的数据。
    7. Spring Security（前身为Acegi）
      一款可以定制化的身份验证和访问控制框架。
    8. Spring Batch（批处理）
     一款专门针对企业级系统中的日常批处理任务的轻量级框架，能够帮助开发人员方便的开发出健壮、高效的批处理应用程序。
```

---

##### IOC

1. 对象地方"自然经济"模式
   
   <img title="" src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.1mssn8m79ezk.webp" alt="spring" width="286">

2. 对象的"商品经济"模式
   
   <img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.1mssn8m79ezk.webp" title="" alt="spring" width="284">

3. 对象进一步抽象
   <img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.5zmbswd6x9w0.webp" title="" alt="spring" width="325"><img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.hmio3cb5lqo.webp" title="" alt="spring" width="437">

---

#### Controller

<img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.6bfsgwbwusw0.webp" title="" alt="" width="453">

---

<img title="" src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.166x79pesyww.webp" alt="" width="467">

> 这个时候前后端分离很难实现 @Controller，返回 html数据

---

<img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.65mnin19uq40.webp" title="" alt="" width="446">

---

1. web 入门
   
   <img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.6as271m4xr80.webp" title="" alt="" width="428">

2. 路由映射
   
   <img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.2wan95ovj5m0.webp" title="" alt="" width="415">

3. 参数传递
   ![](https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.z1fstjt0yy8.webp)
   如果接收 `json` 数据，需要加一个注解 `RequestBody`

4. 数据相应

---

<img title="" src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.730lpyvefsw0.webp" alt="" width="428">

---

<img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.1n2chch19rkw.webp" title="" alt="" width="491">

---

**p15** 这走了很多弯路，你可以试一下：先把node版本降到16，然后修改老师所说的false，之后npm intall，会提示有vulnerability但不管，继续npm run dev（很奇怪的就可以……我前面试了一大堆）

**p15** 登录出错 1、vue-admin-template\env.development 文件该为VUE_APP_BASE_API = 'dev-api'2、vue-admin-template\src\api\user.js 文件url: '/user/login',要改为 url: '/vue-admin-template/user/login', getInfo和logout同样要改

---

**p5** 没有配置properties 
在application.properties输入 
spring.mvc.pathmatch.matching-strategy=ant_path_matcher 
就可以正常运行了

**p5** 问题：Swagger2启动后，显示 127.0.0.1拒绝连接  
解决方法：将 @EnableSwagger2加到主启动类（HelloworldApplication）上即可

**p5** swagger有坑，个人已解决，先在pom文件里将springboot版本改成2.2.6.RELEASE，然后去参考这篇文章https://blog.csdn.net/hjjjjjjj_/article/details/120537261进行配置即可，亲测完美运行。

---

**P6** 里面的2个坑： 
1、pom.xml的修改：  

```
<!--mysql依赖-->
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <scope>runtime</scope>
            <version>5.1.6</version>  //这里的驱动版本需要从原来的5.1.47改成5.1.6
        </dependency>
```

2、settings.xml需要加入&useUnicode=true&characterEncoding=utf8，成为： 
spring.datasource.url=jdbc:mysql://localhost:3306/mydb?useSSL=false&useUnicode=true&characterEncoding=utf8

mysql-connector-java驱动一般用最新就行了，数据库版本5.0不影响我使用8.0版本的驱动，url后面加的是防止出现乱码，一般不加也行

第六节：连接数据库应该加上字符设置  
spring.datasource.url=jdbc:mysql://localhost:3306/mydb?useSSL=false&characterEncoding=utf8

IntelliJ IDEA 2021.2之后的版本compiler.automake.allow.when.app.running 需要在File->Settings->Advanced Settings下找到Compiler块，勾选后点击Apply按钮和OK即可

---

###### GET and POST

GET和POST是HTTP请求的两种基本方法，最直观的区别就是GET把参数包含在URL中，POST通过request body传递参数。

---

<img title="" src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.3pa9knj97940.webp" alt="" width="453">

<img title="" src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.1p6czrjgfm1s.webp" alt="" width="488">

```java
public class LoginInterceptor extends HandlerInterceptor {
    // 在请求处理之前进行调用 (Controller 方法)
    @Override
    public boolean preHandle(HttpServletRequest request, HttpServletResponse response,
                             Object handler) throws Exception {
        if(condition) {
            System.out.println("通过");
            return true;
        } else {
            System.out.println("不通过");
            return false;
        }
    }
}
```

---

#### RESTful 服务+Swagger

<img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.2bjeht0oo2qs.webp" title="" alt="spring" width="262">

<img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.3wot35uvkw40.webp" title="" alt="spring" width="392">

<img title="" src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.4cwejryu1vo0.webp" alt="spring" width="425">

<img src="assets/2023-04-04-17-36-23-image.png" title="" alt="" width="550">

<img src="assets/2023-04-04-17-37-50-image.png" title="" alt="" width="531">

<img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.okio8cver2o.webp" title="" alt="spring" width="505">

<img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.d7w5fjtog9s.webp" title="" alt="spring" width="479">

---

#### MyBatis-Plus

<img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.jqxcy62g9cg.webp" title="" alt="spring" width="437">

<img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.66rm44ov2c80.webp" title="" alt="spring" width="440">

<img src="https://cdn.staticaly.com/gh/BeiWeiDeShi/image@main/typora_img/spring.6k2n3m5ju300.webp" title="" alt="spring" width="446">

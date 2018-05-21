# SSM整合

## 项目介绍

前段时间准备自学ssm框架的时候，在网上百度了很多整合方式，但是结果差强人意。要么就是jar包不全，要么就是整合的结构很乱，或者直接就是把别人的抄过来，甚至连pom.xml里的名字都没去改。总之，我是花了好几天才配出了一个能跑的ssm框架。这个项目是一个直接能用的配置方法，jar包那些我都自己试过，希望想学ssm的同学根据这个项目第一次配置就能让框架跑起来。

## 步骤

- 创建和图一样的文件结构 (.idea README.md ssm.iml是IEAD生成的，其他的如果没有请手动创建和图上保持一致)

![](https://github.com/NicXia970112/ssm-config/blob/master/src/main/webapp/resources/Screenshot%20from%202018-05-21%2015-05-34.png)  

![](https://github.com/NicXia970112/ssm-config/blob/master/src/main/webapp/resources/Screenshot%20from%202018-05-21%2015-14-17.png) 
 
![](https://github.com/NicXia970112/ssm-config/blob/master/src/main/webapp/resources/Screenshot%20from%202018-05-21%2015-14-53.png)

- 编写pom.xml（maven会根据这个配置文件来管理整个项目所需要的第三方jar包，我整理了一些项目常用的jar包，包括支持json的包，对于入门ssm已经足够了。当然肯定是不全的，如果你需要更多的第三方包，可以去maven仓库搜索并填写到这个配置文件中就可以了）

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>space.nicxia</groupId>
    <artifactId>ssm</artifactId>
    <version>1.0-SNAPSHOT</version>
    <name>ssm</name>
    <url>nicxia.space</url>
    <dependencies>
        <!-- 单元测试 -->
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.11</version>
        </dependency>

        <!-- 1.日志 -->
        <!-- 实现slf4j接口并整合 -->
        <dependency>
            <groupId>ch.qos.logback</groupId>
            <artifactId>logback-classic</artifactId>
            <version>1.1.1</version>
        </dependency>

        <!-- 2.数据库 -->
        <dependency>
            <groupId>mysql</groupId>
            <artifactId>mysql-connector-java</artifactId>
            <version>5.1.37</version>
            <scope>runtime</scope>
        </dependency>
        <dependency>
            <groupId>c3p0</groupId>
            <artifactId>c3p0</artifactId>
            <version>0.9.1.2</version>
        </dependency>

        <!-- DAO: MyBatis -->
        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis</artifactId>
            <version>3.3.0</version>
        </dependency>
        <dependency>
            <groupId>org.mybatis</groupId>
            <artifactId>mybatis-spring</artifactId>
            <version>1.2.3</version>
        </dependency>

        <!-- 3.Servlet web -->
        <dependency>
            <groupId>taglibs</groupId>
            <artifactId>standard</artifactId>
            <version>1.1.2</version>
        </dependency>
        <dependency>
            <groupId>jstl</groupId>
            <artifactId>jstl</artifactId>
            <version>1.2</version>
        </dependency>
        <dependency>
            <groupId>com.fasterxml.jackson.core</groupId>
            <artifactId>jackson-databind</artifactId>
            <version>2.5.4</version>
        </dependency>
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>javax.servlet-api</artifactId>
            <version>3.1.0</version>
        </dependency>

        <!-- 4.Spring -->
        <!-- 1)Spring核心 -->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-core</artifactId>
            <version>4.1.7.RELEASE</version>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-beans</artifactId>
            <version>4.1.7.RELEASE</version>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-context</artifactId>
            <version>4.1.7.RELEASE</version>
        </dependency>
        <!-- 2)Spring DAO层 -->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-jdbc</artifactId>
            <version>4.1.7.RELEASE</version>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-tx</artifactId>
            <version>4.1.7.RELEASE</version>
        </dependency>
        <!-- 3)Spring web -->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-web</artifactId>
            <version>4.1.7.RELEASE</version>
        </dependency>
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-webmvc</artifactId>
            <version>4.1.7.RELEASE</version>
        </dependency>
        <!-- 4)Spring test -->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-test</artifactId>
            <version>4.1.7.RELEASE</version>
        </dependency>

        <!-- redis客户端:Jedis -->
        <dependency>
            <groupId>redis.clients</groupId>
            <artifactId>jedis</artifactId>
            <version>2.7.3</version>
        </dependency>
        <dependency>
            <groupId>com.dyuproject.protostuff</groupId>
            <artifactId>protostuff-core</artifactId>
            <version>1.0.8</version>
        </dependency>
        <dependency>
            <groupId>com.dyuproject.protostuff</groupId>
            <artifactId>protostuff-runtime</artifactId>
            <version>1.0.8</version>
        </dependency>

        <!-- Map工具类 -->
        <dependency>
            <groupId>commons-collections</groupId>
            <artifactId>commons-collections</artifactId>
            <version>3.2</version>
        </dependency>


        <!-- SpringMvc Json格式支持 -->
        <dependency>
            <groupId>org.codehaus.jackson</groupId>
            <artifactId>jackson-core-asl</artifactId>
            <version>1.9.11</version>
        </dependency>

        <dependency>
            <groupId>org.codehaus.jackson</groupId>
            <artifactId>jackson-mapper-asl</artifactId>
            <version>1.9.11</version>
        </dependency>
    </dependencies>
    <build>
        <finalName>ssm</finalName>
    </build>

</project>
```

多说一点，每一个dependency节点就是一个jar包，如果你去maven仓库搜一个jar包，会是这样的 net.sf.spring-json:spring-json:1.3.1 ,你只需要把:号隔开的三部分依次输入<dependency>下的每一个节点就好了。当然由于那道伟大的墙，这个过程可能是一万年。

- 编写数据库信息 /src/main/resources/jdbc.properties

```properties
jdbc.driver = com.mysql.jdbc.Driver
jdbc.url = jdbc:mysql://localhost:3306/Contact?useUnicode=true&characterEncoding=utf8
jdbc.username = your name
jdbc.password = your password
```

很好理解，就是你要连接的数据库服务器的驱动，服务器的哪个数据库，用户名和密码。为了减少硬编码，让项目耦合低一点，我们单独把它写出来。

- 编写日志信息 /src/main/resources/logback.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration debug="true">
    <appender name="STDOUT" class="ch.qos.logback.core.ConsoleAppender">
        <!-- encoders are by default assigned the type ch.qos.logback.classic.encoder.PatternLayoutEncoder -->
        <encoder>
            <pattern>%d{HH:mm:ss.SSS} [%thread] %-5level %logger{36} - %msg%n</pattern>
        </encoder>
    </appender>

    <root level="debug">
        <appender-ref ref="STDOUT" />
    </root>
</configuration>
``` 

我们可能会要用到logback这个日志功能，所以就要配置它。

- 编写mybatis框架的信息 /src/main/resources/mybatis-config.xml
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE configuration
        PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-config.dtd">
<configuration>
    <!-- 配置全局属性 -->
    <settings>
        <!-- 使用jdbc的getGeneratedKeys获取数据库自增主键值 -->
        <setting name="useGeneratedKeys" value="true" />

        <!-- 使用列别名替换列名 默认:true -->
        <setting name="useColumnLabel" value="true" />

        <!-- 开启驼峰命名转换:Table{create_time} -> Entity{createTime} -->
        <setting name="mapUnderscoreToCamelCase" value="true" />
    </settings>
</configuration>
```
这里我们配置mybatis框架要开启的功能，如果你要开启更多的功能也写在这里。

### 进入正题，配置spring
我们采取从最底层（存取数据库）开始往上配置。

> 配置/src/main/resources/spring/spring-dao.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:context="http://www.springframework.org/schema/context"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
	http://www.springframework.org/schema/beans/spring-beans.xsd
	http://www.springframework.org/schema/context
	http://www.springframework.org/schema/context/spring-context.xsd">

    <context:property-placeholder location="classpath:jdbc.properties"></context:property-placeholder>

    <bean id="dataSource" class="com.mchange.v2.c3p0.ComboPooledDataSource" >
        <property name="driverClass" value="${jdbc.driver}"/>
        <property name="jdbcUrl" value="${jdbc.url}"/>
        <property name="user" value="${jdbc.username}"/>
        <property name="password" value="${jdbc.password}"/>
    </bean>

    <bean id = "sqlSessionFactory" class="org.mybatis.spring.SqlSessionFactoryBean">
        <property name="dataSource" ref="dataSource"/>
        <property name="typeAliasesPackage" value="space.nicxia.entity, space.nicxia.dto"/>
        <property name="configLocation" value="classpath:mybatis-config.xml"/>
        <property name="mapperLocations" value="classpath:mapper/*.xml"/>
    </bean>

    <bean class="org.mybatis.spring.mapper.MapperScannerConfigurer">
        <property name="sqlSessionFactoryBeanName" value="sqlSessionFactory"></property>
        <property name="basePackage" value="space.nicxia.dao"/>
    </bean>
    
</beans>
```
- dao(data to access),就是把数据库的数据注入到对象中，这一层我们利用mybatis的代理对象方式（只写接口，让mybatis框架帮我们代理生成对应的实现类）。

- 看 context:property-placeholder ,我们就是从这里引入数据库的信息。引入之后，我们向Spring容器中注入dataSource对象（数据源），然后，我们用引入的信息配置好数据源的属性。这样，我们就配置好了数据源，从而通过操作这个数据源操作数据库。有了数据源，我们就可以整合spring和mybatis框架了，我们通过配置的方式向spring中注入SqlSessionFactory对象（学了mybatis后你就知道，mybatis对数据库的操作是通过它得到SqlSession对象，然后通过SqlSession的getMapper方法获得代理对象），同时向这个对象中注入相应的属性。


- 最后，我们向spring容器中注入 org.mybatis.spring.mapper.MapperScannerConfigurer ，并把sqlSessionFactory和dao包的绝对路径注入到它的属性中，这个对象会扫描dao包，并把包内dao接口的代理对象自动注入到spring容器中。

- 你可能好奇既然要生成dao接口对应的代理对象，怎么把他们对应起来？要实现对应，我们编写dao接口和dao接口对应的mapper.xml时要遵循开发规范。mapper.xml的namespace必需是对应的dao接口的绝对路径。我们在SqlSessionFactory中配置了mapperLocations,这个路径下的每一个mapper.xml就对应一个dao接口。

> 配置spring-service.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:tx="http://www.springframework.org/schema/tx"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
	http://www.springframework.org/schema/beans/spring-beans.xsd
	http://www.springframework.org/schema/context
	http://www.springframework.org/schema/context/spring-context.xsd
	http://www.springframework.org/schema/tx
	http://www.springframework.org/schema/tx/spring-tx.xsd">

    <bean id="transactionManager" class="org.springframework.jdbc.datasource.DataSourceTransactionManager">
        <property name="dataSource" ref="dataSource"/>
    </bean>

    <tx:annotation-driven transaction-manager="transactionManager"/>

    <context:component-scan base-package="space.nicxia.serviceImpl"/>
</beans>

```

- 将事物管理器（transactionManager）注入到spring容器中，同时在属性中注入事务管理对应的数据源

- 通过注解驱动的方式开启事物管理（transactionManager）

- 扫描service包，将@Service注解的类导入到spring容器中

> 配置spring-web.xml

```xml

<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:mvc="http://www.springframework.org/schema/mvc"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
	http://www.springframework.org/schema/beans/spring-beans.xsd
	http://www.springframework.org/schema/context
	http://www.springframework.org/schema/context/spring-context.xsd
	http://www.springframework.org/schema/mvc
	http://www.springframework.org/schema/mvc/spring-mvc-3.0.xsd">

    <mvc:annotation-driven/>

    <mvc:default-servlet-handler/>

    <bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
        <property name="viewClass" value="org.springframework.web.servlet.view.JstlView" />
        <property name="prefix" value="/WEB-INF/jsp/" />
        <property name="suffix" value=".jsp" />
    </bean>

    <context:component-scan base-package="space.nicxia.web"/>
</beans>
```

- 开启注解驱动

- 开启静态文件解析

- 将视图解析器注入到spring容器中

- 扫描web包，将@Controller注解的类注入容器中

> 配置web.xml

- 这里首先说一下按照j2ee规范，一个部署在web容器的webapp必须是这样的结构

![](https://github.com/NicXia970112/ssm-config/blob/master/src/main/webapp/resources/Screenshot%20from%202018-05-21%2021-03-48.png)

![](https://github.com/NicXia970112/ssm-config/blob/master/src/main/webapp/resources/Screenshot%20from%202018-05-21%2021-04-11.png)

图不是这个项目的，是一个已经部署到tomcat的应用。所以只讲一下图中重要的，一个webapp文件夹必须包含一个WEB-INF文件夹，名字大小写必须一样；WEB-INF文件夹中必须包含一个web.xml。tomcat启动时就会去读这个web.xml，从而获取你这个应用的配置信息。我们之前在spring-dao.xml.spring-service.xml,spring-web.xml中将mybatis,事物管理,spring-mvc分别和spring容器整合在了一起，那么怎样把这三部分再整合在一个应用程序中呢？就在这个web.xml中。

```xml
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee
                      http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd"
         version="3.1" metadata-complete="true">

    <context-param>
        <param-name>contextConfigLocation</param-name>
        <param-value>classpath:spring/spring-dao.xml,classpath:spring/spring-service.xml</param-value>
    </context-param>
    <listener>
        <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
    </listener>



    <!-- 匹配请求 -->
    <servlet>
        <servlet-name>Dispacher</servlet-name>
        <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
        <init-param>
            <param-name>contextConfigLocation</param-name>
            <param-value>classpath:spring/spring-web.xml</param-value>
        </init-param>
    </servlet>

    <servlet-mapping>
        <servlet-name>Dispacher</servlet-name>
        <url-pattern>/</url-pattern>
    </servlet-mapping>

</web-app>
```
通过这个url-pattern把所有的请求都匹配到这个servlet中，context-param是这个应用在响应请求之前就会去读取的配置（其配置供所有servlet使用），init-param是这个servlet第一次响应请求之前会去读取的配置（其配置只有自己能够使用）。照理说我可以在init-param中导入所有的配置文件，因为一个webapp可能需要配置多个servlet，所以把对这些servlet来说都一样(spring-dao.xml.spring-service.xml)的配置写在context-param里面，把不一样的配置（spring-web.xml）写在每个servlet的init-param里面。

## 结束
当你照着做到这里，一个整合好的ssm框架就等着你coding了。如果你想看一个ssm项目是怎样写的，这里有一个我写的[迷你demo](https://github.com/NicXia970112/SSM-demo)。

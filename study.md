## 入门

添加依赖

```xml
<dependency>
  <groupId>org.mybatis</groupId>
  <artifactId>mybatis</artifactId>
  <version>x.x.x</version>
</dependency>
```

 
`SqlSessionFactoryBuilder`通过读取xml配置文件或者一个预先配置的Configuration实例来构建出`SqlSessionFactory`实例，
然后`SqlSessionFactory`实例创建一个`SqlSession`实例，要想用mybatis应用，就要创建这么一个`SqlSession`实例。其实mybatis中我们和数据库打交道主要还是通过sqlSession来完成，我们可以使用这个接口来执行命令、获取映射器和事务管理器等等

### 从 XML 中构建 SqlSessionFactory

SqlSessionFactory本身又是SqlSessionFactoryBuilder创建的，它可以通过XML配置文件、注解或者手动配置来完成创建SqlSessionFactory实例的工作。

1. 建议使用类路径下的资源文件进行配置
2. 但也可以使用任意的输入流（InputStream）实例

MyBatis 包含一个名叫 Resources 的工具类，它包含一些实用方法，使得从类路径或其它位置加载资源文件更加容易。

```java
String resource = "org/mybatis/example/mybatis-config.xml";
InputStream inputStream = Resources.getResourceAsStream(resource);
SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);
```

先简要认识SqlSessionFactoryBuilder类，它是可以被直接new的类。其中有9个重载的build()方法，每一个build()方法都可以从不通的资源创建一个SqlSessionFactory接口的实例。

[mybatis中获取SqlSessionFactory的几种方法及其相关使用](https://blog.csdn.net/uhgagnu/article/details/53446501)


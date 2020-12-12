







<!-- TOC -->

- [帖子](#帖子)
- [检查对象是否相等](#检查对象是否相等)
- [初始化和类装载](#初始化和类装载)
- [从控制台读取数据](#从控制台读取数据)
- [文件的输入和输出](#文件的输入和输出)
- [随机数的产生](#随机数的产生)
    - [System.currentTimeMilli()](#systemcurrenttimemilli)
    - [random方法](#random方法)
    - [java.util.Random类](#javautilrandom类)
- [常用API](#常用api)
    - [Object类](#object类)
        - [toString()方法](#tostring方法)
        - [hashCode()方法](#hashcode方法)
        - [equals()方法](#equals方法)
        - [equals方法与hashCode方法比较](#equals方法与hashcode方法比较)
        - [Equals和“==”的比较](#equals和的比较)
    - [Arrays类](#arrays类)
        - [binarySearch方法](#binarysearch方法)
        - [copyOf方法](#copyof方法)
        - [fill方法](#fill方法)
        - [hashCode方法](#hashcode方法)
        - [sort方法](#sort方法)
        - [toString 方法](#tostring-方法)
    - [String类](#string类)
- [其他](#其他)
    - [可变参数](#可变参数)
    - [运算符和表达式](#运算符和表达式)
    - [命令和参数](#命令和参数)
    - [数据存储位置](#数据存储位置)
    - [基本数据类型和引用数据类型的存储位置](#基本数据类型和引用数据类型的存储位置)
    - [作用域](#作用域)
    - [代码重构](#代码重构)
    - [重定向和管道](#重定向和管道)

<!-- /TOC -->

# 参考帖子

**好贴**

已看：

[java中system.out.printf()所支持的格式化字符串汇总](https://blog.csdn.net/xhw035/article/details/52433903)

未看：

[重新认识java --- java提高篇](https://blog.csdn.net/qq_31655965/article/category/9267458)



# 加载配置文件的方法

假设配置文件（.properties形式的文件）中的内容是：

> user=zhangsan
>
> password=123

**方法一**：使用类加载器加载配置文件

```java
//1.获取类加载器
ClassLoader cl = 类名.class.getClassLoader（）；
//或 ClassLoader cl=this.getClass().getClassLoader(); 

//2.使用类装载器读取配置文件
InputStream is= cl.getResourceAsStream("配置文件全名");
Properties prop = new Properties();
prop.load(is); 

//以下代码输出为 zhangsan 123
String user = prop.getProperty("user");
String password = prop.getProperty("password");
System.out.println(user+" "+password);
```

**方法二**：使用ServletContext加载文件

```java
//1.使用ServletContext加载配置文件
//加载位于WebRoot目录下的配置文件
InputStream in =this.getServletContext().getResourceAsStream("/配置文件名（.properties形式的文件）");
Properties prop = new Properties();
prop.load(in)

//以下代码输出为 zhangsan 123
String user = prop.getProperty("user");
String password = prop.getProperty("password");
System.out.println(user+" "+password);
```

**方法三：**通过数据流来读取

```java
//1.获取类加载器
ClassLoader cl = 类名.class.getClassLoader（）；
//或 ClassLoader cl=this.getClass().getClassLoader(); 

//2.使用类装载器读取配置文件
FileInputStream fis = new FileLoaderStream("配置文件全名")
Properties prop = new Properties();
prop.load(fis); 

//以下代码输出为 zhangsan 123
String user = prop.getProperty("user");
String password = prop.getProperty("password");
System.out.println(user+" "+password);
```



## getResourceAsStream的用法

> 摘自：<https://www.cnblogs.com/macwhirr/p/8116583.html>

**首先，Java中的getResourceAsStream有以下几种：**&nbsp;

1. `Class.getResourceAsStream(String path) `： path 不以&rsquo;/'开头时默认是从此类所在的包下取资源，以&rsquo;/'开头则是从ClassPath根下获取。其只是通过path构造一个绝对路径，最终还是由ClassLoader获取资源。&nbsp;
2. `Class.getClassLoader.getResourceAsStream(String path)` ：默认则是从ClassPath根下获取，**path不能以&rsquo;/'开头**，最终是由ClassLoader获取资源。&nbsp;
3. `ServletContext. getResourceAsStream(String path)`：默认从WebAPP根目录下取资源，Tomcat下path是否以&rsquo;/'开头无所谓，当然这和具体的容器实现有关。&nbsp;
4. Jsp下的application内置对象就是上面的ServletContext的一种实现。&nbsp;

**其次，getResourceAsStream 用法大致有以下几种：**&nbsp;

1. 要加载的文件和.class文件在同一目录下，例如：com.x.y 下有类me.class ,同时有资源文件myfile.xml&nbsp;

那么，应该有如下代码：`me.class.getResourceAsStream("myfile.xml")`;

2. 在me.class目录的子目录下，例如：com.x.y 下有类me.class ,同时在 com.x.y.file 目录下有资源文myfile.xml&nbsp;

那么，应该有如下代码：&nbsp;`me.class.getResourceAsStream("file/myfile.xml")`;&nbsp;

3. 不在me.class目录下，也不在子目录下，例如：com.x.y 下有类me.class ,同时在 com.x.file 目录下有资源myfile.xml，那么，应该有如下代码：`me.class.getResourceAsStream("/com/x/file/myfile.xml")`;&nbsp;

**最后，自己的理解：**&nbsp;
getResourceAsStream读取的文件路径只局限与工程的源文件夹中，包括在工程src根目录下，以及类包里面任何位置，但是如果配置文件路径是在除了源文件夹之外的其他文件夹中时，该方法是用不了的。



# 动态代理

![](https://gitee.com/aduncmj/PictureBed/raw/master/images/2020-02-13_165539.png)

![](https://gitee.com/aduncmj/PictureBed/raw/master/images/2020-02-13_163054.png)





# 检查对象是否相等
---
![](https://upload-images.jianshu.io/upload_images/1732196-61de5362c99953f0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-00f595897e2cc9d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-566ebc5412a7ba91.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-7260f24182dcfac5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


# 对象初始化
---
> 参考：[java类的初始化顺序](http://blog.sina.com.cn/s/blog_4cc16fc50100bjjp.html)

对于静态变量、静态初始化块、变量、初始化块、构造器，它们的初始化顺序依次是**（静态变量、静态初始化块）>（变量、初始化块）>构造器**。我们也可以通过下面的测试代码来验证这一点：

```java
public class InitialOrderTest {
// 静态变量
public static String staticField = "静态变量";
// 变量
public String field = "变量";
// 静态初始化块
static {
System.out.println(staticField);
System.out.println("静态初始化块");
}
// 初始化块
{
System.out.println(field);
System.out.println("初始化块");
}
// 构造器
public InitialOrderTest() {
System.out.println("构造器");
}
public static void main(String[] args) {
new InitialOrderTest();
}
}
```

运行以上代码，我们会得到如下的输出结果：

> 静态变量
> 静态初始化块
> 变量
> 初始化块
> 构造器

这与上文中说的完全符合。那么对于继承情况下又会怎样呢？我们仍然以一段测试代码来获取最终结果：

```java
class Parent {
 // 静态变量
 public static String p_StaticField = "父类--静态变量";
 // 变量
 public String p_Field = "父类--变量";
 protected int i = 9;
 protected int j = 0;
 // 静态初始化块
 static {
  System.out.println(p_StaticField);
  System.out.println("父类--静态初始化块");
 }
 // 初始化块
 {
  System.out.println(p_Field);
  System.out.println("父类--初始化块");
 }
// 构造器
 public Parent() {
  System.out.println("父类--构造器");
  System.out.println("i=" + i + ", j=" + j);
  j = 20;
 }
}

public class SubClass extends Parent {
 // 静态变量
 public static String s_StaticField = "子类--静态变量";
 // 变量
 public String s_Field = "子类--变量";
 // 静态初始化块
 static {
  System.out.println(s_StaticField);
  System.out.println("子类--静态初始化块");
 }
 // 初始化块
 {
  System.out.println(s_Field);
  System.out.println("子类--初始化块");
 }
// 构造器
 public SubClass() {
  System.out.println("子类--构造器");
  System.out.println("i=" + i + ",j=" + j);
 }
// 程序入口
 public static void main(String[] args) {
  System.out.println("子类main方法");
  new SubClass();
 }
}
```

运行一下上面的代码，结果马上呈现在我们的眼前：

> 父类--静态变量
> 父类--静态初始化块
> 子类--静态变量
> 子类--静态初始化块
> 子类main方法
> 父类--变量
> 父类--初始化块
> 父类--构造器
> i=9, j=0
> 子类--变量
> 子类--初始化块
> 子类--构造器
> i=9,j=20

 现在，结果已经不言自明了。子类的静态变量和静态初始化块的初始化是在父类的变量、初始化块和构造器初始化之前就完成了。

**静态变量、静态初始化块，变量、初始化块初始化的顺序取决于它们在类中出现的先后顺序。**

**执行过程分析**

(1)访问SubClass.main(),(这是一个static方法)，于是装载器就会为你寻找已经编译的SubClass类的代码（也就是SubClass.class文件）。在装载的过程中，装载器注意到它有一个基类（也就是extends所要表示的意思），于是它再装载基类。不管你创不创建基类对象，这个过程总会发生。如果基类还有基类，那么第二个基类也会被装载，依此类推。

(2)执行根基类的**static初始化**，然后是下一个派生类的static初始化，依此类推。这个顺序非常重要，因为派生类的“static初始化”有可能要依赖基类成员的正确初始化。

(3)当所有必要的类都已经装载结束，就能够创建对象。首先，这个对象中的所有**基本数据类型**都会设成它们的默认值，而将对象句柄设为null，随后会调用**基础类构建器**。**用new SubClass（）创建对象之前，先执行main()方法体。**

(4)类SubClass存在父类，则调用父类的构造函数，你可以使用super来指定调用哪个构造函数（也就是Beetle（）构造函数所做的第一件事）。

(5)基类的构造过程以及构造顺序，同派生类的相同。首先基类中各个变量按照字面顺序进行初始化，然后执行基类的构造函数的其余部分。对子类成员数据按照它们声明的顺序初始化，执行子类构造函数的其余部分。

**总结**

 1．父类静态变量和静态代码块（静态初始化块） ，按在代码中出现的顺序依次执行
 2．子类静态变量和静态代码块 （静态初始化块），按在代码中出现的顺序依次执行
 3．父类非静态变量和代码块（初始化块） ，按在代码中出现的顺序依次执行
 4．父类构造方法
 5．子类非静态变量和代码块（初始化块） ，按在代码中出现的顺序依次执行
 6．子类构造方法 	

> 除构造方法外的方法如果不调用就不会初始化

**PS:**如果类已经被加载： 则静态代码块和静态变量就不用重复执行，再创建类对象时，只执行与实例相关的变量初始化和构造方法。也就是说类再被ClassLoader第一次加载时才会执行静态代码块和静态变量。

案例：

```java
public class Test {
    public static Test t1 = new Test();
    {
        System.out.println("A");
    }
    static{
        System.out.println("B");
    }
    public static void main(String[] args) {
        Test t2 = new Test();
    }
}

输出：
    A
    B
    A
```



# 类装载

> 参考：[java类的加载机制](https://www.cnblogs.com/ityouknow/p/5603287.html)

## 什么是类的加载

类的加载指的是将类的.class文件中的二进制数据读入到内存中，将其放在运行时数据区的**方法区**内，然后在**堆区**创建一个java.lang.Class对象，用来封装类在方法区内的数据结构。类的加载的最终产品是位于堆区中的Class对象，Class对象封装了类在方法区内的数据结构，并且向Java程序员提供了访问方法区内的数据结构的接口。



## 类的生命周期

![](https://gitee.com/aduncmj/PictureBed/raw/master/images/QQ图片20191020203944.jpg)



## 类加载器

请注意，虚拟机只加载程序执行时所需要的类文件。例如，假设程序从MyProgram.class开始运行，下面是虚拟机执行的步骤：
1）虚拟机有一个用于加载类文件的机制，例如，从磁盘上读取文件或者请求Web上的文件；它使用该机制来加载MyProgram类文件中的内容。
2）如果MyProgram类拥有类型为另一个类的域，或者是拥有超类，那么这些类文件也会被加载。（加载某个类所依赖的所有类的过程称为类的解析。）
3）接着，虚拟机执行MyProgram中的main方法（它是静态的，无需创建类的实例）。
4）如果main方法或者main调用的方法要用到更多的类，那么接下来就会加载这些类。
以上是**类加载过程**。

然而，类加载机制并非只使用单个的类加载器。每个Java程序至少拥有三个类加载器：

- **引导类加载器**
- **扩展类加载器**
- **系统类加载器（有时也称为应用类加载器）**

引导类加载器负责加载系统类（通常从JAR文件rt.jar中进行加载）。它是虚拟机不可分割的一部分，而且通常是用C语言来实现的。引导类加载器没有对应的ClassLoader对象，例如，该方法：String.class.getClassLoader()
将返回null。

扩展类加载器用于从jre/lib/ext目录加载“标准的扩展”。可以将JAR文件放入该目录，这样即使没有任何类路径，扩展类加载器也可以找到其中的各个类。

系统类加载器用于加载应用类。它负责加载用户类路径（ClassPath）所指定的类，开发者可以直接使用该类加载器，如果应用程序中没有自定义过自己的类加载器，一般情况下这个就是程序中默认的类加载器。

在Oracle的Java语言实现中，扩展类加载器和系统类加载器都是用Java来实现的。它们都是URLClassLoader类的实例。

应用程序都是由以上这三种类加载器互相配合进行加载的，如果有必要，我们还可以加入自定义的类加载器。因为JVM自带的ClassLoader只是懂得从本地文件系统加载标准的java class文件，因此如果编写了自己ClassLoader，便可以做到如下几点：

1）在执行非置信代码之前，自动验证数字签名。

2）动态地创建符合用户特定需要的定制化构建类。

3）从特定的场所取得java class，例如数据库中和网络中。

PS:**类加载的缓存机制**将会保证所有加载过的Class都会被缓存，当程序中需要使用某个Class时，类加载器先从缓存区寻找该Class，只有缓存区不存在，系统才会读取该类对应的二进制数据，并将其转换成Class对象，存入缓存区。

**寻找类加载器，**先来一个小例子

```java
package com.neo.classloader;
public class ClassLoaderTest {
     public static void main(String[] args) {
        ClassLoader loader = Thread.currentThread().getContextClassLoader();
        System.out.println(loader);
        System.out.println(loader.getParent());
        System.out.println(loader.getParent().getParent());
    }
}
```

运行后，输出结果：

> ```
> sun.misc.Launcher$AppClassLoader@64fef26a
> sun.misc.Launcher$ExtClassLoader@1ddd40f3
> null
> ```

从上面的结果可以看出，并没有获取到ExtClassLoader的父Loader，原因是Bootstrap Loader（引导类加载器）是用C语言实现的，找不到一个确定的返回父Loader的方式，于是就返回null。

这几种类加载器的层次关系如下图所示：

![](https://gitee.com/aduncmj/PictureBed/raw/master/images/QQ图片20191020203650.jpg)

**注意：这里父类加载器并不是通过继承关系来实现的，而是采用组合实现的。**



## 类加载的三种方式

1、命令行启动应用时候由JVM初始化加载

2、通过Class.forName()方法动态加载

3、通过ClassLoader.loadClass()方法动态加载







![](https://gitee.com/aduncmj/PictureBed/raw/master/images/QQ图片20191020203445.jpg)

![](https://gitee.com/aduncmj/PictureBed/raw/master/images/QQ图片20191020203905.jpg)

![](https://gitee.com/aduncmj/PictureBed/raw/master/images/QQ图片20191020203759.jpg)



# 向上转型和向下转型

[Java向下转型的意义](https://blog.csdn.net/xyh269/article/details/52231944)

[Java向上转型和向下转型（附详细例子）](https://blog.csdn.net/sheepmu/article/details/38327205)



# Java方法参数的值调用

先阅读：[C语言函数调用三种方式：传值调用，引用调用和传地址调用](<https://blog.csdn.net/xiaosong2008/article/details/25430261>)



![Java核心技术+卷1+基础知识+原书第10版](https://gitee.com/aduncmj/PictureBed/raw/master/images/2019-10-27_141049.png)

# 深入理解Java的接口和抽象类

[深入理解Java的接口和抽象类](https://www.cnblogs.com/dolphin0520/p/3811437.html)



# 从控制台读取数据

---
![](https://upload-images.jianshu.io/upload_images/1732196-91e080f89ca3d871.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-7cee12831170e76e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-bb8296b3f5b05ff1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-fbce487e6dd45daf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-9d64b43b8004b1a1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-e4b8c5f4af7190d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-41dc8603ab9c78e5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-ad64256bf5e722eb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 文件的输入和输出
---
![](https://upload-images.jianshu.io/upload_images/1732196-b6ec7ade6683b17d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-bd30973e3d0d27d7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-086f3d5c67519773.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-51b449f1a41efdfd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-b360c0d08eb88453.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-1cc76cb79ecffdd3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-8d865137d6e124fe.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-03e39296cadff936.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-65c18ae57413cf33.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-37b4a451a4dd30ec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



# 基本类型与字符串之间的转换

**基本类型转换为String**

   基本类型转换String总共有三种方式，这里只讲最简单的一种方式： 

```
基本类型直接与””相连接即可；如：34+""
```

**String转换成对应的基本类型** 

**除了Character类之外，其他所有包装类都具有parseXxx静态方法**可以将字符串参数转换为对应的基本类型：

- `public static byte parseByte(String s)`：将字符串参数转换为对应的byte基本类型。
- `public static short parseShort(String s)`：将字符串参数转换为对应的short基本类型。
- `public static int parseInt(String s)`：将字符串参数转换为对应的int基本类型。
- `public static long parseLong(String s)`：将字符串参数转换为对应的long基本类型。
- `public static float parseFloat(String s)`：将字符串参数转换为对应的float基本类型。
- `public static double parseDouble(String s)`：将字符串参数转换为对应的double基本类型。
- `public static boolean parseBoolean(String s)`：将字符串参数转换为对应的boolean基本类型。

代码使用（仅以Integer类的静态方法parseXxx为例）如：

```java
public class Demo18WrapperParse {
    public static void main(String[] args) {
        int num = Integer.parseInt("100");
    }
}
```

> 注意:如果字符串参数的内容无法正确转换为对应的基本类型，则会抛出`java.lang.NumberFormatException`异常。



# 随机数的产生

---
> Java产生随机数的方法主要有三种System.currentTimeMilli()、random方法、Random类。

## System.currentTimeMilli()

currentTimeMilli()方法返回从1970年1月1日0时0分0秒到现在的一个long型的毫秒数，将其返回值取余后可得到所需范围内的随机数。

## random方法

random方法是Math类里的一个方法，通过Math.random()可以获得0.0到1.0间的double型随机数，但不包括1.0。

尽管random方法产生的随机数范围比较小，但我们可以将产生的随机值乘以一个数，这样我们既可以获得更大范围的随机数。

**我们还可以结合造型来获得所需范围的随机整数**。

![](https://gitee.com/aduncmj/PictureBed/raw/master/images/2019-10-27_202014.png)

## java.util.Random类

![](https://upload-images.jianshu.io/upload_images/1732196-0604c1f6bd997998.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

利用这种方法其比较方便。如可以利用提供的关键字，让程序返回一个随机的整数(采用int nextInt(10))等等。不过其返回控制要比Random方法困难一点。如现在需要系统提供一个10到50之间的随机奇数， 利用这个Random类就无法完成。也就是说，利用这个Random类来生成随机数，其只能够控制上限，而不能够控制下限。换一句话说，其可以指定最大的随机数范围，而不能够指定最小的随机数范围。所以，在灵活性上，其比Random方法要稍微差一点。



# 常用API



## Object类 √

---
> `Java.lang.Object`类为类层次结构的根，是所有类的父类。所有对象，包括数组，都实现这个类的方法。

### toString()方法

    public String toString()

 Object 类的 toString（） 方法返回一个字符串，该字符串由类名（对象是该类的一个实例）、at 标记符“@”和此对象哈希码（对象在JVM虚拟出来的内存地址，为整数。不是实际物理内存地址。）的无符号十六进制表示组成。如：**java.lang.Object@1b6d3586**。

由于toString方法返回的结果是内存地址，而在开发中，经常需要按照对象的属性得到相应的字符串表现形式，因此也需要重写它。

toString 方法是一种非常有用的调试工具 。 在标准类库中 ， 许多类都定义了 toString 方法 ， 以便用户能够获得一些有关对象状态的必要信息 。


> 扩展：**哈希吗（HashCode）**
> 哈希码产生的依据：哈希码并不是完全唯一的，它是一种算法，让同一个类的对象按照自己不同的特征尽量的有不同的哈希码，但不表示不同的对象哈希码完全不同。也有相同的情况，看程序员如何写哈希码的算法。
> ![](https://upload-images.jianshu.io/upload_images/1732196-65f908643c50f421.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 
> ![](https://upload-images.jianshu.io/upload_images/1732196-238d17758b4132ce.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)




### hashCode()方法
    public native int hashCode()

散列码 （ hash code ) 是由对象导出的一个整型值。 散列码是没有规律的 。

  该方法返回对象的哈希值（十进制）。

每个对象都有一个默认的散列码 ， 其值为对象的存储地址。

### equals()方法
    public boolean equals(Object obj)

  默认情况下，该方法比较当前对象是否和目标对象拥有相同的内存地址，返回值为布尔类型。但这方法使用的时候通常也需要重写。

### equals方法与hashCode方法比较

  如果两个对象使用equals比较返回true,那么它们的hashCode值一定要相同，所以，重写了equals方法一般都要重写hashCode方法。

![对比](https://upload-images.jianshu.io/upload_images/1732196-e960cc67dba35066.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


hashCode()相等的两个对象他们的equal()不一定相等，也就是hashCode()不是绝对可靠的。

因为重写的equal（）里一般比较的比较全面比较复杂，这样效率就比较低，而利用hashCode()进行对比，则只要生成一个hash值进行比较就可以了，效率很高，那么hashCode()既然效率这么高为什么还要equal()呢？因为hashCode()并不是完全可靠，有时候不同的对象他们生成的hashcode也会一样（生成hash值得公式可能存在的问题），所以hashCode()只能说是大部分时候可靠，并不是绝对可靠。

hashcode方法一般只有在集合中用到

> 将对象放入到集合中时，首先判断要放入对象的hashcode值与集合中的任意一个元素的hashcode值是否相等，如果不相等直接将该对象放入集合中。如果hashcode值相等，然后再通过equals方法判断要放入对象与集合中的任意一个对象是否相等，如果equals判断不相等，直接将该元素放入到集合中，否则不放入。

### Equals和“==”的比较

**== 的作用：**

　　基本类型：比较的就是值是否相同

　　引用类型：比较的就是地址值是否相同

**equals 的作用:**

　　引用类型：默认情况下，比较的是地址值。

> 注：不过，我们可以根据情况自己重写该方法。一般重写都是自动生成，比较对象的成员变量值是否相同。对于复合数据类型之间进行equals比较，在没有覆写equals方法的情况下，他们之间的比较还是内存中的存放位置的地址值，跟双等号（==）的结果相同。


## Arrays类 √
---
> `java.util.Arrays`类包含了许多用于操作数组（比如排序和搜索）的静态方法，是JDK提供的专门用于操作数组的工具类，位于java.util包中，它继承于Object类。

### toString 方法

```
public static String toString(type[] a)
```

  返回指定的type数组内容的字符串表示形式。该字符串表示形式由数组的元素，括在方括号(“[]”)的列表。相邻元素由字符分隔“，”(逗号后面有一个空格)。

```java
public static void main(String[] args) {
  // 定义int 数组
  int[] arr  =  {2,34,35,4,657,8,69,9};
  // 打印数组,输出地址值
  System.out.println(arr); // [I@2ac1fdc4
  // 数组内容转为字符串
  String s = Arrays.toString(arr);
  // 打印字符串,输出内容
  System.out.println(s); // [2, 34, 35, 4, 657, 8, 69, 9]
}
```

### hashCode方法

    public static int hashCode(type[] a)

  返回**基于指定数组的内容**的哈希码。

### sort方法
    public static void sort(type[] a)

  指定的int型数组排序按数字升序顺序。

### binarySearch方法

```
public static int binarySearch(type[] array ,type key)
```

通过binarySearch方法能对排序好的各种类型的数组进行二分查找法操作。注意必须事先对数组array进行排序，否则结果不确定。该方法返回待搜索值的索引。



## String类 √

**概述**

java.lang.String` 类代表字符串。Java程序中所有的字符串文字（例如 "abc" ）都可以被看作是实现此类的实例。

类 String 中包括用于检查各个字符串的方法，比如用于比较字符串，搜索字符串，提取子字符串以及创建具有翻译为大写或小写的所有字符的字符串的副本。

**特点**

1. 字符串不变：字符串的值在创建后不能被更改。

```java
String s1 = "abc";
s1 += "d";
System.out.println(s1); // "abcd"
// 内存中有"abc"，"abcd"两个对象，s1从指向"abc"，改变指向，指向了"abcd"。
```

2. 因为String对象是不可变的，所以它们可以被共享。

```java
String s1 = "abc";
String s2 = "abc";
// 内存中只有一个"abc"对象被创建，同时被s1和s2共享。
```

3. "abc" 等效于 char[] data={ 'a' , 'b' , 'c' } 。

```java
例如：
String str = "abc";
相当于：
char data[] = {'a', 'b', 'c'};    
String str = new String(data);
// String底层是靠字符数组实现的。
```

**使用**

- 查看类

  - java.lang.String ：此类不需要导入。

- 查看构造方法

  - public String() ：初始化新创建的 String对象，以使其表示空字符序列

  - public String(char[] value) ：通过当前参数中的字符数组来构造新的String。

  - public String(byte[] bytes) ：**通过使用平台的默认字符集解码当前参数中的字节数组来构造新的String**。

  构造举例，代码如下：

```java
// 无参构造
String str = new String（）；
// 通过字符数组构造
char chars[] = {'a', 'b', 'c'};    
String str2 = new String(chars);
// 通过字节数组构造
byte bytes[] = { 97, 98, 99 };    
String str3 = new String(bytes);
```

**常用方法**

**判断功能的方法：**

`public boolean equals (Object anObject) `：将此字符串与指定对象进行比较。
`public boolean equalsIgnoreCase (String anotherString) `：将此字符串与指定对象进行比较，忽略大小写。



**获取功能的方法**:

`public int length () `：返回此字符串的长度。
`public String concat (String str)` ：将指定的字符串连接到该字符串的末尾。
`public char charAt (int index) `：返回指定索引处的 char值。
`public int indexOf (String str)` ：返回指定子字符串第一次出现在该字符串内的索引。
`public String substring (int beginIndex) `：返回一个子字符串，从beginIndex开始截取字符串到字符串结尾。
`public String substring (int beginIndex, int endIndex) `：返回一个子字符串，从beginIndex到endIndex截取字符串。**含beginIndex，不含endIndex。**

**转换功能的方法**

`public char[] toCharArray () `：将此字符串转换为新的字符数组。
`public byte[] getBytes () `：使用平台的默认字符集将该 String编码转换为新的字节数组。**特殊**：字符串和字节数组在转换过程中，是可以指定编码表的。
`public String replace (CharSequence target, CharSequence replacement) `：将与target匹配的字符串使用replacement字符串替换。

**分割功能的方法**

`public String[] split(String regex)` ：将此字符串按照给定的regex（规则）拆分为字符串数组。

## StringBuilder类 √

**字符串拼接问题**

由于String类的对象内容不可改变，所以每当进行字符串拼接时，总是会在内存中创建一个新的对象。例如：

```java
public class StringDemo {
    public static void main(String[] args) {
        String s = "Hello";
        s += "World";
        System.out.println(s);
    }
}
```

在API中对String类有这样的描述：字符串是常量，它们的值在创建后不能被更改。

根据这句话分析我们的代码，其实总共产生了三个字符串，即`"Hello"`、`"World"`和`"HelloWorld"`。引用变量s首先指向`Hello`对象，最终指向拼接出来的新字符串对象，即`HelloWord` 。

由此可知，如果对字符串进行拼接操作，每次拼接，都会构建一个新的String对象，既耗时，又浪费空间。为了解决这一问题，可以使用`java.lang.StringBuilder`类。

**StringBuilder概述**

查阅`java.lang.StringBuilder`的API，StringBuilder又称为可变字符序列，它是一个类似于 String 的字符串缓冲区，通过某些方法调用可以改变该序列的长度和内容。

原来StringBuilder是个字符串的缓冲区，即它是一个容器，容器中可以装很多字符串。并且能够对其中的字符串进行各种操作。

它的内部拥有一个数组用来存放字符串内容，进行字符串拼接时，直接在数组中加入新内容。StringBuilder会自动维护数组的扩容。原理如下图所示：(默认16字符空间，超过自动扩充)

![06-StringBuilder的原理](https://gitee.com/aduncmj/PictureBed/raw/master/images/print.png)

**构造方法**

根据StringBuilder的API文档，常用构造方法有2个：

- `public StringBuilder()`：构造一个空的StringBuilder容器。
- `public StringBuilder(String str)`：构造一个StringBuilder容器，并将字符串添加进去。

```java
public class StringBuilderDemo {
    public static void main(String[] args) {
        StringBuilder sb1 = new StringBuilder();
        System.out.println(sb1); // (空白)
        // 使用带参构造
        StringBuilder sb2 = new StringBuilder("itcast");
        System.out.println(sb2); // itcast
    }
}
```

**常用方法**

StringBuilder常用的方法有2个：

- `public StringBuilder append(...)`：添加任意类型数据的字符串形式，并返回当前对象自身。
- `public String toString()`：将当前StringBuilder对象转换为String对象。

**append方法**

**append方法具有多种重载形式**，可以接收任意类型的参数。任何数据作为参数都会将对应的字符串内容添加到StringBuilder中。例如：

```java
public class Demo02StringBuilder {
	public static void main(String[] args) {
		//创建对象
		StringBuilder builder = new StringBuilder();
		//public StringBuilder append(任意类型)
		StringBuilder builder2 = builder.append("hello");
		//对比一下
		System.out.println("builder:"+builder);
		System.out.println("builder2:"+builder2);
		System.out.println(builder == builder2); //true
	    // 可以添加 任何类型
		builder.append("hello");
		builder.append("world");
		builder.append(true);
		builder.append(100);
		// 在我们开发中，会遇到调用一个方法后，返回一个对象的情况。然后使用返回的对象继续调用方法。
        // 这种时候，我们就可以把代码现在一起，如append方法一样，代码如下
		//链式编程
		builder.append("hello").append("world").append(true).append(100);
		System.out.println("builder:"+builder);
	}
}
```

> 备注：StringBuilder已经覆盖重写了Object当中的toString方法。

**toString方法**

通过toString方法，StringBuilder对象将会转换为不可变的String对象。如：

```java
public class Demo16StringBuilder {
    public static void main(String[] args) {
        // 链式创建
        StringBuilder sb = new StringBuilder("Hello").append("World").append("Java");
        // 调用方法
        String str = sb.toString();
        System.out.println(str); // HelloWorldJava
    }
}
```



## System类

`java.lang.System`类中提供了大量的静态方法，可以获取与系统相关的信息或系统级操作，在System类的API文档中，常用的方法有：

- `public static long currentTimeMillis()`：返回以毫秒为单位的当前时间。
- `public static void arraycopy(Object src, int srcPos, Object dest, int destPos, int length)`：将数组中指定的数据拷贝到另一个数组中。

### currentTimeMillis方法

实际上，currentTimeMillis方法就是 获取当前系统时间与1970年01月01日00:00点之间的毫秒差值

```java
import java.util.Date;

public class SystemDemo {
    public static void main(String[] args) {
       	//获取当前时间毫秒值
        System.out.println(System.currentTimeMillis()); // 1516090531144
    }
}
```

### arraycopy方法

- `public static void arraycopy(Object src, int srcPos, Object dest, int destPos, int length)`：将数组中指定的数据拷贝到另一个数组中。

数组的拷贝动作是系统级的，性能很高。System.arraycopy方法具有5个参数，含义分别为：

| 参数序号 | 参数名称 | 参数类型 | 参数含义             |
| -------- | -------- | -------- | -------------------- |
| 1        | src      | Object   | 源数组               |
| 2        | srcPos   | int      | 源数组索引起始位置   |
| 3        | dest     | Object   | 目标数组             |
| 4        | destPos  | int      | 目标数组索引起始位置 |
| 5        | length   | int      | 复制元素个数         |

## 日期时间类

### Date类

**概述**

` java.util.Date`类 表示特定的瞬间，精确到毫秒。

继续查阅Date类的描述，发现Date拥有多个构造函数，只是部分已经过时，但是其中有未过时的构造函数可以把毫秒值转成日期对象。

- `public Date()`：分配Date对象并初始化此对象，以表示分配它的时间（精确到毫秒）。
- `public Date(long date)`：分配Date对象并初始化此对象，以表示自从标准基准时间（称为“历元（epoch）”，即1970年1月1日00:00:00 GMT）以来的指定毫秒数。

> tips: 由于我们处于东八区，所以我们的基准时间为1970年1月1日8时0分0秒。

简单来说：使用无参构造，可以自动设置当前系统时间的毫秒时刻；指定long类型的构造参数，可以自定义毫秒时刻。例如：

```java
import java.util.Date;

public class Demo01Date {
    public static void main(String[] args) {
        // 创建日期对象，把当前的时间
        System.out.println(new Date()); // Tue Jan 16 14:37:35 CST 2018
        // 创建日期对象，把当前的毫秒值转成日期对象
        System.out.println(new Date(0L)); // Thu Jan 01 08:00:00 CST 1970
    }
}
```

> tips:在使用println方法时，会自动调用Date类中的toString方法。Date类对Object类中的toString方法进行了覆盖重写，所以结果为指定格式的字符串。

**常用方法**

Date类中的多数方法已经过时，常用的方法有：

- `public long getTime()`：返回自1970年1月1日以来，由此 `Date`对象表示的00:00:00 GMT的毫秒 `数` 
- `public String toString()`:  将此`Date`对象转换为`String`的形式：dow mon dd hh:mm:ss zzz yyyy(Thu Jan 01 08:00:00 CST 1970)

### DateFormat抽象类

`java.text.DateFormat` 是日期/时间格式化子类的抽象类，我们通过这个类可以帮我们完成日期和文本之间的转换,也就是可以在Date对象与String对象之间进行来回转换。

- **格式化**：按照指定的格式，从Date对象转换为String对象。
- **解析**：按照指定的格式，从String对象转换为Date对象。

**构造方法**

由于DateFormat为抽象类，不能直接使用，所以需要常用的子类`java.text.SimpleDateFormat`。这个类需要一个模式（格式）来指定格式化或解析的标准。构造方法为：

- `public SimpleDateFormat(String pattern)`：用给定的模式和默认语言环境的日期格式符号构造SimpleDateFormat。

参数pattern是一个字符串，代表日期时间的自定义格式。

**格式规则**

常用的格式规则为：

| 标识字母（区分大小写） | 含义 |
| ---------------------- | ---- |
| y                      | 年   |
| M                      | 月   |
| d                      | 日   |
| H                      | 时   |
| m                      | 分   |
| s                      | 秒   |

> 备注：更详细的格式规则，可以参考SimpleDateFormat类的API文档0。

创建SimpleDateFormat对象的代码如：

```java
import java.text.DateFormat;
import java.text.SimpleDateFormat;

public class Demo02SimpleDateFormat {
    public static void main(String[] args) {
        // 对应的日期格式如：2018-01-16 15:06:38
        DateFormat format = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss");
    }    
}
```

**常用方法**

DateFormat类的常用方法有：

- `public String format(Date date)`：将Date对象格式化为字符串。
- `public Date parse(String source)`：将字符串解析为Date对象。

**format方法**

使用format方法的代码为：

```java
import java.text.DateFormat;
import java.text.SimpleDateFormat;
import java.util.Date;
/*
 把Date对象转换成String
*/
public class Demo03DateFormatMethod {
    public static void main(String[] args) {
        Date date = new Date();
        // 创建日期格式化对象,在获取格式化对象时可以指定风格
        DateFormat df = new SimpleDateFormat("yyyy年MM月dd日");
        String str = df.format(date);
        System.out.println(str); // 2008年1月23日
    }
}
```

**parse方法**

使用parse方法的代码为：

```java
import java.text.DateFormat;
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;
/*
 把String转换成Date对象
*/
public class Demo04DateFormatMethod {
    public static void main(String[] args) throws ParseException {
        DateFormat df = new SimpleDateFormat("yyyy年MM月dd日");
        String str = "2018年12月11日";
        Date date = df.parse(str);
        System.out.println(date); // Tue Dec 11 00:00:00 CST 2018
    }
}
```

### Calendar抽象类

**概念**

`java.util.Calendar`是日历类，在Date后出现，替换掉了许多Date的方法。该类将所有可能用到的时间信息封装为静态成员变量，方便获取。日历类就是方便获取各个时间属性的。

**获取方式**

Calendar为抽象类，由于语言敏感性，Calendar类在创建对象时并非直接创建，而是通过静态方法创建，返回子类对象，如下：

Calendar静态方法

- `public static Calendar getInstance()`：使用默认时区和语言环境获得一个日历

例如：

```java
import java.util.Calendar;

public class Demo06CalendarInit {
    public static void main(String[] args) {
        Calendar cal = Calendar.getInstance();
    }    
}
```

**常用方法**

根据Calendar类的API文档，常用方法有：

- `public int get(int field)`：返回给定日历字段的值。
- `public void set(int field, int value)`：将给定的日历字段设置为给定值。
- `public abstract void add(int field, int amount)`：根据日历的规则，为给定的日历字段添加或减去指定的时间量。
- `public Date getTime()`：返回一个表示此Calendar时间值（从历元到现在的毫秒偏移量）的Date对象。

Calendar类中提供很多成员常量，代表给定的日历字段：

| 字段值       | 含义                                  |
| ------------ | ------------------------------------- |
| YEAR         | 年                                    |
| MONTH        | 月（从0开始，可以+1使用）             |
| DAY_OF_MONTH | 月中的天（几号）                      |
| HOUR         | 时（12小时制）                        |
| HOUR_OF_DAY  | 时（24小时制）                        |
| MINUTE       | 分                                    |
| SECOND       | 秒                                    |
| DAY_OF_WEEK  | 周中的天（周几，周日为1，可以-1使用） |

**get/set方法**

get方法用来获取指定字段的值，set方法用来设置指定字段的值，代码使用演示：

```java
import java.util.Calendar;

public class CalendarUtil {
    public static void main(String[] args) {
        // 创建Calendar对象
        Calendar cal = Calendar.getInstance();
        // 设置年 
        int year = cal.get(Calendar.YEAR);
        // 设置月
        int month = cal.get(Calendar.MONTH) + 1;
        // 设置日
        int dayOfMonth = cal.get(Calendar.DAY_OF_MONTH);
        System.out.print(year + "年" + month + "月" + dayOfMonth + "日");
    }    
}
```

```java
import java.util.Calendar;

public class Demo07CalendarMethod {
    public static void main(String[] args) {
        Calendar cal = Calendar.getInstance();
        cal.set(Calendar.YEAR, 2020);
        System.out.print(year + "年" + month + "月" + dayOfMonth + "日"); // 2020年1月17日
    }
}
```

**add方法**

add方法可以对指定日历字段的值进行加减操作，如果第二个参数为正数则加上偏移量，如果为负数则减去偏移量。代码如：

```java
import java.util.Calendar;

public class Demo08CalendarMethod {
    public static void main(String[] args) {
        Calendar cal = Calendar.getInstance();
        System.out.print(year + "年" + month + "月" + dayOfMonth + "日"); // 2018年1月17日
        // 使用add方法
        cal.add(Calendar.DAY_OF_MONTH, 2); // 加2天
        cal.add(Calendar.YEAR, -3); // 减3年
        System.out.print(year + "年" + month + "月" + dayOfMonth + "日"); // 2015年1月18日; 
    }
}
```

**getTime方法**

Calendar中的getTime方法并不是获取毫秒时刻，而是拿到对应的Date对象。

```java
import java.util.Calendar;
import java.util.Date;

public class Demo09CalendarMethod {
    public static void main(String[] args) {
        Calendar cal = Calendar.getInstance();
        Date date = cal.getTime();
        System.out.println(date); // Tue Jan 16 16:03:09 CST 2018
    }
}
```

> 小贴士：
>
> ​     西方星期的开始为周日，中国为周一。
>
> ​     在Calendar类中，月份的表示是以0-11代表1-12月。
>
> ​     日期是有大小关系的，时间靠后，时间越大。






















# 其他
---



## Java并发编程：进程和线程之由来





## 可变参数

在**JDK1.5**之后，如果我们定义一个方法需要接受多个参数，并且多个参数类型一致，我们可以对其简化成如下格式：

```
修饰符 返回值类型 方法名(参数类型... 形参名){  }
```

其实这个书写完全等价与

```
修饰符 返回值类型 方法名(参数类型[] 形参名){  }
```

只是后面这种定义，在调用时必须传递数组，而前者可以直接传递数据即可。

**JDK1.5**以后。出现了简化操作。**...** 用在参数上，称之为可变参数。

同样是代表数组，但是在调用这个带有可变参数的方法时，不用创建数组(这就是简单之处)，直接将数组中的元素作为实际参数进行传递，其实编译成的class文件，将这些元素先封装到一个数组中，在进行传递。这些动作都在编译.class文件时，自动完成了。

代码演示：    

```java
public class ChangeArgs {
    public static void main(String[] args) {
        int[] arr = { 1, 4, 62, 431, 2 };
        int sum = getSum(arr);
        System.out.println(sum);
        //  6  7  2 12 2121
        // 求 这几个元素和 6  7  2 12 2121
        int sum2 = getSum(6, 7, 2, 12, 2121);
        System.out.println(sum2);
    }

    /*
     * 完成数组  所有元素的求和 原始写法
     
      public static int getSum(int[] arr){
        int sum = 0;
        for(int a : arr){
            sum += a;
        }
        
        return sum;
      }
    */
    //可变参数写法
    public static int getSum(int... arr) {
        int sum = 0;
        for (int a : arr) {
            sum += a;
        }
        return sum;
    }
}
```

> tips: 上述add方法在同一个类中，只能存在一个。因为会发生调用的不确定性
>
> 注意：如果在方法书写时，这个方法拥有多参数，参数中包含可变参数，可变参数一定要写在参数列表的末尾位置。



## main()方法参数的含义 √

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-e9598dd5305990e2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-af5f52792f99147d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



## 逻辑运算符的区别 √

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-4d4aad5ee066428f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
**&（逻辑与）和&&（短路与）的区别:**
相同点：&与&&两边的算子都为boolean型，且结果也为boolean; 
不同点：&两边的算子都必须执行；&&若左边为false，则右边短路不予执行，若左边为true,右边还要执行。

**|（逻辑或）和 ||（短路或）的区别：**
相同点：两边的算子都为boolean型，且结果也为boolean; 
不同点：|两边的算子都必须执行；||若左边为true，则右边短路不予执行，若左边为false,右边还要执行。

## 内存堆和栈的区别

[内存堆和栈的区别](https://www.cnblogs.com/lln7777/archive/2012/03/14/2396164.html)




## 数据存储位置 √

程序运行时，我们最好对数据保存到什么地方做到心中有数。特别要注意的是内存的分配。有六个地方都可以保存数据： 
(1) **寄存器**。这是最快的保存区域，因为它位于和其他所有保存方式不同的地方：**处理器内部**。然而，寄存器的数量十分有限，所以寄存器是根据需要由编译器分配。我们对此没有直接的控制权，也不可能在自己的程序里找到寄存器存在的任何踪迹。 

(2) **栈**。驻留于**常规RAM**（随机访问存储器）区域，但可通过它的“堆栈指针”获得处理的直接支持。堆栈指针若向下移，会创建新的内存；若向上移，则会释放那些内存。这是一种**特别快、特别有效**的数据保存方式，仅次于寄存器。创建程序时，Java编译器必须准确地知道堆栈内保存的所有数据的“长度”以及“存在时间”。这是由于它必须生成相应的代码，以便向上和向下移动指针。这一限制无疑影响了程序的灵活性，所以尽管有些Java数据要保存在堆栈里——特别是对象句柄，但Java对象并不放到其中。 

(3) **堆**。一种常规用途的内存池（**也在RAM区域**），其中保存了Java对象。和堆栈不同，“内存堆”或“堆”（Heap）最吸引人的地方在于编译器不必知道要从堆里分配多少存储空间，也不必知道存储的数据要在堆里停留多长的时间。因此，用堆保存数据时会得到更大的灵活性。要求创建一个对象时，只需用new命令编制相关的代码即可。执行这些代码时，会在堆里自动进行数据的保存。当然，为达到这种灵活性，必然会付出一定的代价：在堆里分配存储空间时会花掉更长的时间！ 

(4) **静态存储**。这儿的“静态”（Static）是指“位于固定位置”（**尽管也在RAM里**）。程序运行期间，静态存储的数据将随时等候调用。可用static关键字指出一个对象的特定元素是静态的。但Java对象本身永远都不会置入静态存储空间。 

(5) **常数存储**。常数值通常直接置于程序代码内部。这样做是安全的，因为它们永远都不会改变。有的常数需要严格地保护，所以可考虑将它们置入只读存储器**（ROM）**。 

(6) **非RAM存储**。若数据完全独立于一个程序之外，则程序不运行时仍可存在，并在程序的控制范围之外。其中两个最主要的例子便是“流式对象”和“固定对象”。对于流式对象，对象会变成字节流，通常会发给另一台机器。而对于固定对象，对象保存在磁盘中。即使程序中止运行，它们仍可保持自己的状态不变。对于这些类型的数据存储，一个特别有用的技巧就是它们能存在于其他媒体中。一旦需要，甚至能将它们恢复成普通的、基于RAM的对象。Java 1.1提供了对Lightweight persistence的支持。未来的版本甚至可能提供更完整的方案。

## 基本数据类型和引用数据类型的存储位置
> 参考：[java中基本数据类型和引用数据类型的存储位置](https://blog.csdn.net/qq_36596145/article/details/76300922)

基本数据类型是放在栈中还是放在堆中，这取决于基本类型声明的位置。

一：在方法中声明的变量，即使变量是局部变量，每当程序调用方法时，系统都会为该方法建立一个方法栈，其所在方法中声明的变量就放在方法栈中，当方法结束系统会释放方法栈，其对应在该方法中声明的变量随着栈的销毁而结束，这就局部变量只能在方法中有效的原因。 
在方法中声明的变量可以是基本类型的变量，也可以是引用类型的变量。 
（1）当声明是基本类型的变量的时，其变量名及值（变量名及值是两个概念）是放在方法栈中 
（2）当声明的是引用变量时，所声明的变量（该变量实际上是在方法中存储的是内存地址值）是放在方法的栈中，该变量所指向的对象是放在堆类存中的。

二：在类中声明的变量是成员变量，也叫全局变量，放在堆中的（因为全局变量不会随着某个方法执行结束而销毁）。 
同样在类中声明的变量即可是基本类型的变量 也可是引用类型的变量 
（1）当声明的是基本类型的变量其变量名及其值放在堆内存中的 
（2）引用类型时，其声明的变量仍然会存储一个内存地址值，该内存地址值指向所引用的对象。引用变量名和对应的对象仍然存储在相应的堆中.

总结：
![](https://upload-images.jianshu.io/upload_images/1732196-27eba91a3e52b1d0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



## 作用域

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-17f8beb2556fa04a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-8a2052ba0a1604cd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 代码重构

![](https://upload-images.jianshu.io/upload_images/1732196-89d76f9fafe47b77.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 重命名、移动、方法名称修改、pull up和pull down、抽取重复代码成函数等

## 重定向和管道

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-de8df2b853951cd6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



## 序列化和反序列化

[序列化/反序列化，我忍你很久了，淦！](https://mp.weixin.qq.com/s/0EfIUB9E-0Oh_Clwuxswuw)



## 理解ORM和数据持久化

[理解ORM和数据持久化](<https://blog.csdn.net/u012585964/article/details/52412520>)



# 边角细节

for(int i=scores.length-1;**i>=0&&count<3**;i--)

在一个源文件中，只能有一个公有类，但可以有任意数目的非公有类。

一个方法可以访问所属类的所有对象的私有数据。在实现一个类时，由于公有数据非常危险，所以应该将所有的数据域都设置为私有的 。

**构造对象数组**

![](https://gitee.com/aduncmj/PictureBed/raw/master/images/foreach.png)



![](https://gitee.com/aduncmj/PictureBed/raw/master/images/2019-10-27_201136.png)



![](https://gitee.com/aduncmj/PictureBed/raw/master/images/sizeof.png)



![](https://gitee.com/aduncmj/PictureBed/raw/master/images/2019-10-27_201431.png)



![](https://gitee.com/aduncmj/PictureBed/raw/master/images/2019-10-27_201230.png)



![](https://gitee.com/aduncmj/PictureBed/raw/master/images/2019-10-27_201857.png)



![](https://gitee.com/aduncmj/PictureBed/raw/master/images/01_StringBuilder的原理.bmp)



![](https://gitee.com/aduncmj/PictureBed/raw/master/images/FastStoneEditor1.bmp)













 



 
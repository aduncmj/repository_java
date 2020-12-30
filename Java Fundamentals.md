<!-- TOC -->

- [java基本概念](#java基本概念)
    - [什么是环境变量？path、classPath](#什么是环境变量pathclasspath)
    - [JDK（Java Development Kit)里面有什么？](#jdkjava-development-kit里面有什么)
    - [什么是JRE（Java Runtime Environment : java运行环境）?](#什么是jrejava-runtime-environment--java运行环境)
    - [什么是JVM（Java Virtual Machine:java虚拟机）？](#什么是jvmjava-virtual-machinejava虚拟机)
- [java变量](#java变量)
    - [变量](#变量)
    - [布尔类型](#布尔类型)
    - [字符类型](#字符类型)
    - [数值类型](#数值类型)
- [类和对象](#类和对象)
    - [构造函数（构建器）](#构造函数构建器)
    - [this关键字](#this关键字)
    - [super关键字](#super关键字)
    - [static关键字](#static关键字)
    - [访问权限（default、public、private、protected）](#访问权限defaultpublicprivateprotected)
    - [面向对象基础](#面向对象基础)
    - [main函数](#main函数)
    - [包](#包)
    - [单例设计模式](#单例设计模式)
    - [继承](#继承)
    - [final](#final)
    - [强制类型转换](#强制类型转换)
    - [抽象类](#抽象类)
    - [模板方法设计模式](#模板方法设计模式)
    - [对象包装器和自动装箱](#对象包装器和自动装箱)
    - [反射：框架设计的灵魂](#反射框架设计的灵魂)
    - [接口](#接口)
    - [多态](#多态)
    - [内部类](#内部类)
        - [匿名内部类](#匿名内部类)
    - [异常](#异常)
    - [集合](#集合)
        - [集合概述](#集合概述)
        - [集合框架](#集合框架)
        - [Collection 接口常用方法](#collection-接口常用方法)
        - [Iterator迭代器](#iterator迭代器)
            - [Iterator接口](#iterator接口)
            - [迭代器的实现原理](#迭代器的实现原理)
            - [增强for](#增强for)
        - [泛型](#泛型)
            - [泛型概述](#泛型概述)
            - [使用泛型的好处](#使用泛型的好处)
            - [泛型的定义与使用](#泛型的定义与使用)
                - [定义和使用含有泛型的类](#定义和使用含有泛型的类)
                - [含有泛型的方法](#含有泛型的方法)
                - [含有泛型的接口](#含有泛型的接口)
            - [泛型通配符](#泛型通配符)
                - [通配符基本使用](#通配符基本使用)
                - [通配符高级使用----受限泛型](#通配符高级使用----受限泛型)
        - [List集合（接口）](#list集合接口)
            - [List接口介绍](#list接口介绍)
            - [List接口中常用方法](#list接口中常用方法)
            - [List的子类](#list的子类)
                - [ArrayList集合](#arraylist集合)
                - [LinkedList集合](#linkedlist集合)
        - [Set集合（接口）](#set集合接口)
            - [HashSet集合](#hashset集合)
                - [??HashSet集合存储数据的结构（哈希表）](#hashset集合存储数据的结构哈希表)
                - [LinkedHashSet](#linkedhashset)
            - [TreeSet集合](#treeset集合)
        - [Collections](#collections)
            - [常用功能](#常用功能)
            - [Comparator比较器](#comparator比较器)
            - [简述Comparable和Comparator两个接口的区别。](#简述comparable和comparator两个接口的区别)
        - [Map集合（接口）](#map集合接口)
            - [概述](#概述)
            - [Map常用子类](#map常用子类)
            - [Map接口中的常用方法](#map接口中的常用方法)
                - [**Hashmap**：](#hashmap)
                - [遍历键找值方式](#遍历键找值方式)
                - [遍历键值对方式](#遍历键值对方式)
                - [存储自定义类型键值](#存储自定义类型键值)
                - [LinkedHashMap](#linkedhashmap)
                - [TreeMap：](#treemap)
    - [多线程](#多线程)
        - [并发与并行](#并发与并行)
        - [线程与进程](#线程与进程)
        - [创建线程类方式一](#创建线程类方式一)
        - [多线程原理](#多线程原理)
        - [创建线程方式二](#创建线程方式二)
        - [Thread和Runnable的区别](#thread和runnable的区别)
        - [匿名内部类方式实现线程的创建](#匿名内部类方式实现线程的创建)
        - [线程安全](#线程安全)
            - [线程安全](#线程安全)
            - [线程同步](#线程同步)
                - [同步代码块](#同步代码块)
                - [同步方法](#同步方法)
                - [Lock锁](#lock锁)
        - [线程状态](#线程状态)
            - [线程状态概述](#线程状态概述)
            - [Timed Waiting（计时等待）](#timed-waiting计时等待)
            - [BLOCKED（锁阻塞）](#blocked锁阻塞)
            - [Waiting（无限等待）](#waiting无限等待)
            - [补充知识点](#补充知识点)
        - [等待唤醒机制](#等待唤醒机制)
            - [线程间通信](#线程间通信)
            - [等待唤醒机制](#等待唤醒机制)
            - [生产者与消费者问题](#生产者与消费者问题)
        - [线程池](#线程池)
            - [线程池思想概述](#线程池思想概述)
            - [线程池概念](#线程池概念)
            - [线程池的使用](#线程池的使用)

<!-- /TOC -->


# java基本概念
---

> Java分三个版本：Java SE（标准版）、Java EE（企业版）、Java ME（微型版）。其中SE就是大家学的Java基础，EE是公司最常用的用于网站开发（PC端），ME用于移动端开发（像以前诺基亚的塞班系统中Java，现在随着安卓的崛起，ME跟塞班一起没落了，没人用）

![](https://upload-images.jianshu.io/upload_images/1732196-1e511e658a62804c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


## 1.什么是环境变量？path、classPath

- path环境变量：操作系统外部**命令**搜索路径

- classpath环境变量：**类文件**搜索路径

## 2.JDK（Java Development Kit)里面有什么？

- JDK是由一套独立程序构成的集合，每个程序都是从命令行调用的，用于开发和测试Java程序。

- JDK简单易学，可以通过任何文本编辑器（如：Windows记事本、UltrEdit、Editplus、FrontPage以及dreamweaver等）编写Java源文件，然后在DOS状况下通过javac命令将Java源程序编译成字节码，通过Java命令来执行编译后的Java文件。

- 除了JDK,还可以使用某种Java开发工具（例如，NetBeans、Eclipse和TextPad)———为了快速开发Java程序而提供集成开发环境（IntegratedDevelopmentEnvironment,IDE)的软件。编辑、编译、链接、调试和在线帮助都集成在一个图形用户界面中，这样，只需在一个窗口中输入源代码或在窗口中打开已有的文件，然后单击按钮、菜单选项或者使用功能键就可以编译和运行源代码。

- Java初学者一般都采用这种开发工具。从初学者角度来看，采用JDK开发Java程序能够很快理解程序中各部分代码之间的关系，有利于理解Java面向对象的设计思想。JDK的另一个显著特点是随着Java
  （J2EE、J2SE以及J2ME）版本的升级而升级。但它的缺点也是非常明显的就是从事大规模企业级Java应用开发非常困难，不能进行复杂的Java软件开发，也不利于团体协同开发。

- JDK包含了一批用于Java开发的组件，其中包括：

  - javac：编译器，将后缀名为.java的源代码编译成后缀名为“.class”的字节码

  - java：运行工具，运行.class的字节码

等

- **JDK中还包括完整的JRE**（Java Runtime Environment）

## 3.什么是JRE（Java Runtime Environment : java运行环境）?

- Java运行环境（Java Runtime Environment，简称JRE）是一个软件，由太阳微系统所研发，JRE可以让计算机系统运行Java应用程序（JavaApplication）。

- **JRE的内部有一个Java虚拟机（Java Virtual Machine，JVM）**以及一些标准的类别函数库（Class Library）

## 4.什么是JVM（Java Virtual Machine:java虚拟机）？

- 一种能够运行java字节码的虚拟机

> Add：win+R-\>输入cmd,回车-\>命令行窗口


# java变量
---

## 变量

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-2e45441e4b5a3ed9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-3ff4b7738e0132e8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-1de60e111307f034.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 布尔类型

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-d2585576fcda7b8e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 字符类型

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-cf887c1121ad3ab9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-adcd2e43269f67f6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-d08697d7a2e8b786.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-5d5e6f9246848d8a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 数值类型
![图片.png](https://upload-images.jianshu.io/upload_images/1732196-e9e09567b8a70912.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-138592984283f3ae.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-18d3e7c85ff9367a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-3d34f076e975e9ab.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-87546bc41b926114.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-754f237f499296fa.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> j=i++; 等价于 j=i; i=i+1;
> j=++i; 等价于 j=i+1; i=i+1;


# 类和对象
---

![](https://upload-images.jianshu.io/upload_images/1732196-4258340f23afedf0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-d55c8167a9ed1968.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


## 构造函数（构建器）

![](https://upload-images.jianshu.io/upload_images/1732196-bae0cc89884233f7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-4006962405e653af.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

编译器不让我们从除了一个构建器之外的其他任何方法内部调用一个构建器。

## this关键字

![](https://upload-images.jianshu.io/upload_images/1732196-ae511ec29f8e9be4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

this 关键字用于那些特殊的类——需明确使用当前对象的句柄。例如，假若您希望将句柄返回给当前对象，那么它经常在return 语句中使用。通过 this 关键字返回当前对象的句柄，所以可以方便地对同一个对象执行多项操作。

若为一个类写了多个构建器，那么经常都需要在一个构建器里调用另一个构建器，**以避免写重复的代码**。可用this 关键字做到这一点。
尽管可用this 调用一个构建器，但不可调用两个。
除此以外，构建器调用必须是我们做的第一件事情，否则会收到编译程序的报错信息。

由于自变量s 的名字以及成员数据s 的名字是相同的，所以会出现混淆。为解决这个问题，可用 this.s来引用成员数据。

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-03766003412fc5f0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


## super关键字

我们通常想要在新类中调用基础类的成分，但又不想只是简单地调用，那样会造成递归调用。为解决这个问题，java提供了一个super关键字，通过它可直接调用基础类的成分。

对于衍生类，其构造函数里做的第一件事必须是给基础类进行初始化（用super关键字），但当基础类的构造函数没有参数时，可省略此步，当然系统亦会自动对其初始化。

> ![](https://upload-images.jianshu.io/upload_images/1732196-cce5e074e5f08241.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

使用super 调用构造器的语句必须是子类构造器的第一条语句 。


## static关键字

![](https://upload-images.jianshu.io/upload_images/1732196-89a78acbeac86963.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-7a6cb8d1f82b24de.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-0332ca3157de7157.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-b7d105eb88879042.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-56919111b1739e3f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 访问权限（default、public、private、protected）

**default：“友好的”**
当前包内的其他所有类都能访问“友好的”成员，但对包外来说，这些成员是“私有的”，外界无法访问。

**public**
可以修饰类、成员变量、成员函数；任何皆可访问public成员

**private**
可以修饰成员变量、成员函数；只能在类内访问。

**protected：友好的一种**
protected的意思是“它本身是私有的，但可由从这个类继承的任何东西或者同一个包内的其他任何东西访问”。也就是说，Java 中的protected 会成为进入“友好”状态。

## 面向对象基础

所有东西都是对象。可将对象想象成一种新型变量；它保存着数据，但可要求它对自身进行操作。理论上讲，可从要解决的问题身上提出所有概念性的组件，然后在程序中将其表达为一个对象。

每个对象都有自己的存储空间，可容纳其他对象。或者说，通过封装现有对象，可制作出新型对象。所以，尽管对象的概念非常简单，但在程序中却可达到任意高的复杂程度。

当您看到“type”这个字的时候，请同时想到“class”；反之亦然。

一旦向对象发出一个特定的请求，就会调用那个函数。我们通常将这个过程总结为向对象“发送一条消息”（提出一个请求）。

## main函数
    public static void main(String[] args) 

主函数：是一个特殊的函数。作为程序的入口，可以被jvm调用。

主函数的定义：
- public：代表着该函数访问权限是最大的。
- static：代表主函数随着类的加载就已经存在了。
- void：主函数没有具体的返回值。
- main：不是关键字，但是是一个特殊的单词，可以被jvm识别。
- （String[] arr）:函数的参数，参数类型是一个数组，该数组中的元素是字符串。字符串类型的数组。

主函数是固定格式的：jvm识别。

jvm在调用主函数时，传入的是new String[0];

## 包
访问包中的有两种方式，一种是在类名前加完整包名，另一种是使用一个关键字，import，导入的是包中的类。

一个类可以使用所属包中的所有类 ， 以及其他包中的公有类 （ public class )

建议，不要写通配符 * ，需要用到包中的哪个类，就导入哪个类。

> c:\myclass\packb\DemoA.class
> c:\myclass\packb\haha\DemoZ.class 
> import packb.*;
> import packb.haha.*;

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-495a12f49feba85a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


总结：
	包与包之间进行访问，被访问的包中的类以及类中的成员，需要public修饰。
	不同包中的子类还可以直接访问父类中被protected权限修饰的成员。

包与包之间可以使用的权限只有两种，public  protected。

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-e43174ad0cda8848.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)






java.lang : java的核心包 jdk1.2版本以后，该包中的类自动导入。
java.awt: 用于制作图形界面。
java.io:input output  用于操作设备上的数据。
java.util : 这里定义是java的工具类。集合，日期。
java.net:用于网络通讯的。
java.applet:  application  let        server  let    servlet      java server page   jsp

建立定包名不要重复，可以使用url来完成定义，url是唯一的。
www.itcast.cn

**将类放入包**
方式：在定义类的代码之前加上package语句
如：
package cn.itcast.demo
package cn.itcast.test

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-84226b3bb10e6e4e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


## 单例设计模式
> 设计模式：解决某一类问题最行之有效的方法。

java中有23种设计模式

单例设计模式：解决一个类在内存只存在一个对象。

想要保证对象唯一，需保证：
- 为了避免其他程序过多建立该类对象。先禁止其他程序建立该类对象
- 还为了让其他程序可以访问到该类对象，只好在本类中，自定义一个对象。
- 为了方便其他程序对自定义对象的访问，可以对外提供一些访问方式。

这三部怎么用代码体现呢？
- 将构造函数私有化。
- 在类中创建一个本类对象。
- 提供一个方法可以获取到该对象。

对于事物该怎么描述，还怎么描述。
当需要将该事物的对象保证在内存中唯一时，就将以上的三步加上即可。

单例设计模式有以下两种表现方式：
```
/*
这个是先初始化对象。
称为：饿汉式。

Single类一进内存，就已经创建好了对象。
class Single
{
	private static Single s = new Single();
	private Single(){}
	public static Single getInstance()
	{
		return s;
	}
}
*/
//对象是方法被调用时，才初始化，也叫做对象的延时加载。成为：懒汉式。
//Single类进内存，对象还没有存在，只有调用了getInstance方法时，才建立对象。
class Single
{
	private static Single s = null;
	private Single(){}
	public static Single getInstance()
	{
		if(s==null)
		{
			synchronized(Single.class)
			{				
				if(s==null)
					s = new Single();
			}
		}
		return s;
	}
}

//记录原则：定义单例，建议使用饿汉式。

class  
{
	public static void main(String[] args) 
	{
		System.out.println("Hello World!");
	}
}
```

## 继承
将学生和工人的共性描述提取出来，单独进行描述，只要让学生和工人与单独描述的这个类有关系，就可以了。

继承的好处：
- 提高了代码的复用性。
- 让类与类之间产生了关系。有了这个关系，才有了多态的特性。

**注意：**千万不要为了获取其他类的功能，简化代码而继承。必须是类与类之间有所属关系才可以继承。所属关系 is a。

Java语言中：java只支持单继承，不支持多继承。接口除外。
因为多继承容易带来安全隐患:当多个父类中定义了相同功能，当功能内容不同时，子类对象不确定要运行哪一个。但是java保留这种机制。并用另一种体现形式来完成表示。多实现（implements）。

java支持多层继承。也就是一个继承体系

> 如何使用一个继承体系中的功能呢？
> 想要使用体系，先查阅体系父类的描述，因为父类中定义的是该体系中共性功能。通过了解共性功能，就可以知道该体系的基本功能。那么这个体系已经可以基本使用了。
> 但在具体调用时，要创建最子类的对象，为什么呢？
> 一是因为有可能父类不能创建对象，
> 二是创建子类对象可以使用更多的功能，包括基本的也包括特有的。
> <br/>**简单一句话：查阅父类功能，创建子类对象使用功能。**

---
**子父类出现后，类成员的特点：**

> 类中成员：
> 1，变量。
> 2，函数。
> 3，构造函数。

1,变量
如果子类中出现非私有的同名成员变量时，
子类要访问本类中的变量，用this
子类要访问父类中的同名变量，用super。

super的使用和this的使用几乎一致。
this代表的是本类对象的引用。
super代表的是父类对象的引用。

![super和this](https://upload-images.jianshu.io/upload_images/1732196-dd44b8b21dabd7cb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


2,子父类中的函数。

当子类出现和父类一模一样的函数时，子类对象调用该函数，会运行子类函数的内容。如同父类的函数被覆盖一样。

这种情况是函数的另一个特性：**重写(覆盖)**

当子类继承父类，沿袭了父类的功能，到子类中，但是子类虽具备该功能，但是功能的内容却和父类不一致，这时，没有必要定义新功能，而是使用覆盖特殊，保留父类的功能定义，并重写功能内容。

覆盖：
1，子类覆盖父类，必须保证子类权限大于等于父类权限，才可以覆盖，否则编译失败。
2，静态只能覆盖静态。

记住：
重载：只看同名函数的参数列表。
重写：子父类方法要一模一样。

3，子父类中的构造函数。

在对子类对象进行初始化时，父类的构造函数也会运行，那是因为子类的构造函数默认第一行有一条隐式的语句 super();
super() : 会访问父类中空参数的构造函数。而且子类中所有的构造函数默认第一行都是super();

> 为什么子类一定要访问父类中的构造函数?
> 因为父类中的数据子类可以直接获取。所以子类对象在建立时，需要先查看父类是如何对这些数据进行初始化的。
> 所以子类在对象初始化时，要先访问一下父类中的构造函数。
> 如果要访问父类中指定的构造函数，可以通过手动定义super语句的方式来指定。
> **注意：super语句一定定义在子类构造函数的第一行。**

子类的实例化过程。

结论：
子类的所有的构造函数，默认都会访问父类中空参数的构造函数。
因为子类每一个构造函数内的第一行都有一句隐式super();

当父类中没有空参数的构造函数时，子类必须手动通过super语句形式来指定要访问父类中的构造函数。

当然：子类的构造函数第一行也可以手动指定this语句来访问本类中的构造函数。
子类中至少会有一个构造函数会访问父类中的构造函数。

## final

final : 最终。作为一个修饰符，
1，可以修饰类，函数，变量。
2，被final修饰的类不可以被继承。为了避免被继承，被子类复写功能。
3，被final修饰的方法不可以被复写。
4，被final修饰的变量是一个常量只能赋值一次，既可以修饰成员变量，有可以修饰局部变量。

当在描述事物时，一些数据的出现值是固定的，那么这时为了增强阅读性，都给这些值起个名字。方便于阅读。而这个值不需要改变，所以加上final修饰。
作为常量：常量的书写规范所有字母都大写，如果由多个单词组成。单词间通过_连接。
5，内部类定义在类中的局部位置上是，只能访问该局部被final修饰的局部变量。
6,如果将一个类声明为final ，只有其中的方法自动地成为 final ,
而不包括变量。

> **final 的注意事项**
> 设计一个类时，往往需要考虑是否将一个方法设为 final。可能会觉得使用自己的类时执行效率非常重要，没有人想覆盖自己的方法。这种想法在某些时候是正确的。
> 但要慎重作出自己的假定。通常，我们很难预测一个类以后会以什么样的形式再生或重复利用。

## 强制类型转换
将一个子类的引用赋给一个超类变量 ， 编译器是允许的。 但将一个超类的引用赋给一个子类变量 ，必须进行类型转换 ， 这样才能够通过运行时的检査。

在将超类转换成子类之前 ， 应该使用instanceof 进行检查。

> ![示例](https://upload-images.jianshu.io/upload_images/1732196-2b4a881d3eb6bf26.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

在一般情况下 ， 应该尽量少用类型转换和 instanceof 运算符。


## 抽象类

如果自下而上在类的继承层次结构中上移， 位于上层的类更具有通用性 ， 甚至可能更加抽象。 从某种角度看 ，祖先类更加通用， 人们只将它作为派生其他类的基类 ， 而不作为想使用的特定的实例类。

抽象类的特点：
- 抽象方法一定在抽象类中，即包含抽象方法的类必须被声明为抽象类。
- 抽象方法和抽象类都必须被**abstract**关键字修饰。
- 抽象类不可以用new创建对象。因为调用抽象方法没意义。
- 
  ![抽象.png](https://upload-images.jianshu.io/upload_images/1732196-962b2b49633bcfeb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 抽象类中的抽象方法要被使用，必须由子类**复写其所有的抽象方法**后，建立子类对象调用。
  如果子类只覆盖了部分抽象方法，那么该子类还是一个抽象类。

**抽象类和一般类没有太大的不同。**该如何描述事物，就如何描述事物，只不过，该事物出现了一些看不懂的东西。这些不确定的部分，也是该事物的功能，需要明确出现。但是无法定义主体。因而通过抽象方法来表示。
抽象类比一般类多个了抽象函数。就是在类中可以定义抽象方法。抽象类不可以实例化。

> 特殊：抽象类中可以不定义抽象方法，这样做仅仅是不让该类建立对象。

## 模板方法设计模式

需求：获取一段程序运行的时间。
原理：获取程序开始和结束的时间并相减即可。

获取时间：System.currentTimeMillis();

当代码完成优化后，就可以解决这类问题。这种方式，模版方法设计模式。

什么是模版方法呢？
在定义功能时，功能的一部分是确定的，但是有一部分是不确定，而确定的部分在使用不确定的部分，
那么这时就将不确定的部分暴露出去。由该类的子类去完成。
```
abstract class GetTime
{
	public final void getTime()
	{
		long start = System.currentTimeMillis();

		runcode();

		long end = System.currentTimeMillis();

		System.out.println("毫秒："+(end-start));
	}
	public abstract void runcode();

}


class SubTime extends GetTime
{

	public void runcode()
	{
		
		for(int x=0; x<4000; x++)
		{
			System.out.print(x);
		}
	}
}


class  TemplateDemo
{
	public static void main(String[] args) 
	{
		//GetTime gt = new GetTime();
		SubTime gt = new SubTime();
		gt.getTime();
	}
}
```

## 对象包装器和自动装箱

![对象包装器](https://upload-images.jianshu.io/upload_images/1732196-9e83307233726e9f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![自动装箱](https://upload-images.jianshu.io/upload_images/1732196-dae48e7572a01f39.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![自动拆箱](https://upload-images.jianshu.io/upload_images/1732196-b3a16de73444c9f2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![编译器认可](https://upload-images.jianshu.io/upload_images/1732196-c977356320486c49.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



## 反射：框架设计的灵魂

> [Java反射机制详解](https://www.cnblogs.com/lzq198754/p/5780331.html)

**框架：**半成品软件。可以在框架的基础上进行软件开发，简化编码

**反射：**

1. 反射机制是什么
   	反射机制是在运行状态中，对于任意一个类，都能够知道这个类的所有属性和方法；对于任意一个对象，都能够调用它的任意一个方法和属性；这种动态获取的信息以及动态调用对象的方法的功能称为java语言的反射机制。
2. 反射机制能做什么
       在运行时判断任意一个对象所属的类；
       在运行时构造任意一个类的对象；
       在运行时判断任意一个类所具有的成员变量和方法；
       在运行时调用任意一个对象的方法；
       生成动态代理。

![image-20201230221544729](https://gitee.com/aduncmj/PictureBed/raw/master/images/20201230221544.png)

**Java代码在计算机中经历的三个阶段**






	* 获取Class对象的方式：
		1. Class.forName("全类名")：将字节码文件加载进内存，返回Class对象
			* 多用于配置文件，将类名定义在配置文件中。读取文件，加载类
		2. 类名.class：通过类名的属性class获取
			* 多用于参数的传递
		3. 对象.getClass()：getClass()方法在Object类中定义着。
			* 多用于对象的获取字节码的方式
	
		* 结论：
			同一个字节码文件(*.class)在一次程序运行过程中，只会被加载一次，不论通过哪一种方式获取的Class对象都是同一个。


	* Class对象功能：
		* 获取功能：
			1. 获取成员变量们
				* Field[] getFields() ：获取所有public修饰的成员变量
				* Field getField(String name)   获取指定名称的 public修饰的成员变量
	
				* Field[] getDeclaredFields()  获取所有的成员变量，不考虑修饰符
				* Field getDeclaredField(String name)  
			2. 获取构造方法们
				* Constructor<?>[] getConstructors()  
				* Constructor<T> getConstructor(类<?>... parameterTypes)  
	
				* Constructor<T> getDeclaredConstructor(类<?>... parameterTypes)  
				* Constructor<?>[] getDeclaredConstructors()  
			3. 获取成员方法们：
				* Method[] getMethods()  
				* Method getMethod(String name, 类<?>... parameterTypes)  
	
				* Method[] getDeclaredMethods()  
				* Method getDeclaredMethod(String name, 类<?>... parameterTypes)  
	
			4. 获取全类名	
				* String getName()  


	* Field：成员变量
		* 操作：
			1. 设置值
				* void set(Object obj, Object value)  
			2. 获取值
				* get(Object obj) 
	
			3. 忽略访问权限修饰符的安全检查
				* setAccessible(true):暴力反射



	* Constructor:构造方法
		* 创建对象：
			* T newInstance(Object... initargs)  
	
			* 如果使用空参数构造方法创建对象，操作可以简化：Class对象的newInstance方法


	* Method：方法对象
		* 执行方法：
			* Object invoke(Object obj, Object... args)  
	
		* 获取方法名称：
			* String getName:获取方法名


	* 案例：
		* 需求：写一个"框架"，不能改变该类的任何代码的前提下，可以帮我们创建任意类的对象，并且执行其中任意方法
			* 实现：
				1. 配置文件
				2. 反射
			* 步骤：
				1. 将需要创建的对象的全类名和需要执行的方法定义在配置文件中
				2. 在程序中加载读取配置文件
				3. 使用反射技术来加载类文件进内存
				4. 创建对象
				5. 执行方法




## 接口
接口：初期理解，可以认为是一个特殊的抽象类。当抽象类中的方法都是抽象的，那么该类可以通过接口的形式来表示。
> class用于定义类
> interface 用于定义接口。

接口定义时，格式特点：
1，接口中常见定义：常量，抽象方法。
2，接口中的成员都有固定修饰符。
	常量：public static final
	方法：public abstract 
记住：接口中的成员都是public的。

接口是不可以创建对象的，因为有抽象方法。需要被子类实现，子类对接口中的抽象方法全都覆盖后，子类才可以实例化。否则子类是一个抽象类。

> **接口可以被类多实现，也是对多继承不支持的转换形式。java支持多实现。**
> ![](https://upload-images.jianshu.io/upload_images/1732196-b457d7690b1ba50e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 从中可以看到，Hero 将具体类ActionCharacter 同接口 CanFight，CanSwim 以及CanFly合并起来。按这种形式合并一个具体类与接口的时候，具体类必须首先出现，然后才是接口（否则编译器会报错）。
> 注意上述例子已向我们揭示了接口最关键的作用，也是使用接口最重要的一个原因：能上溯造型至多个基础类。
> <br/>**通过继承扩展接口**
> 利用继承技术，可方便地为一个接口添加新的方法声明，也可以将几个接口合并成一个新接口。在这两种情况下，最终得到的都是一个新接口。

> **到底应该使用一个接口还是一个抽象类呢？**
> 若使用接口，我们可以同时获得抽象类以及接口的好处。所以假如想创建的基础类没有任何方法定义或者成员变量，那么无论如何都愿意使用接口，而不要选择抽象类。事实上，如果事先知道某种东西会成为基础类，那么第一个选择就是把它变成一个接口。只有在必须使用方法定义或者成员变量的时候，才应考虑采用抽象类。

## 多态

多态：可以理解为事物存在的多种体现形态。

人：男人，女人
动物：猫，狗。
猫 x = new 猫();
动物 x = new 猫();

1，多态的体现
	父类的引用指向了自己的子类对象。
	父类的引用也可以接收自己的子类对象。

2，多态的前提
	必须是类与类之间有关系。要么继承，要么实现。
	通常还有一个前提：存在覆盖。

3，多态的好处
	多态的出现大大的提高程序的扩展性。

4，多态的弊端：
	提高了扩展性，但是只能使用父类的引用访问父类中的成员。

**如何使用子类特有方法：**
```
class DuoTaiDemo2 
{
	public static void main(String[] args) 
	{
		//Animal a = new Cat();//类型提升。 向上转型。
		//a.eat();

		//如果想要调用猫的特有方法时，如何操作？
		//强制将父类的引用。转成子类类型。向下转型。
		///Cat c = (Cat)a;
		//c.catchMouse();
		//千万不要出现这样的操作，就是将父类对象转成子类类型。
		//我们能转换的是父类应用指向了自己的子类对象时，该应用可以被提升，也可以被强制转换。
		//多态自始至终都是子类对象在做着变化。
//		Animal a = new Animal();
//		Cat c = (Cat)a;
		

		/*
		毕姥爷 x = new 毕老师();

		x.讲课();

		毕老师 y = (毕老师)x;


		y.看电影();
		*/
		function(new Dog());
		function(new Cat());


	}
	public static void function(Animal a)//Animal a = new Cat();
	{
		a.eat();
		/*
		if(a instanceof Animal)
		{
			System.out.println("haha");
		}
		else 
		*/
		if(a instanceof Cat)
		{
			Cat c = (Cat)a;
			c.catchMouse();
		}
		else if(a instanceof Dog)
		{
			Dog c = (Dog)a;
			c.kanJia();
		}


		/*
		instanceof : 用于判断对象的类型。 对象 intanceof 类型(类类型 接口类型)  
		*/
	
	}
	
}
```

**在多态中成员函数的特点：
在编译时期：参阅引用型变量所属的类中是否有调用的方法。如果有，编译通过，如果没有编译失败。
在运行时期：参阅对象所属的类中是否有调用的方法。
简单总结就是：成员函数在多态调用时，编译看左边，运行看右边。**


在多态中，成员变量的特点：
无论编译和运行，都参考左边(引用型变量所属的类)。


在多态中，静态成员函数的特点：
无论编译和运行，都参考做左边。

## 内部类
内部类的访问规则：
- 内部类可以直接访问外部类中的成员，包括私有。
  之所以可以直接访问外部类中的成员，是因为内部类中持有了一个外部类的引用，格式 外部类名.this
- 外部类要访问内部类，必须建立内部类对象。

访问格式：
- 当内部类定义在外部类的成员位置上，而且非私有，可以直接建立内部类对象。
  格式
  外部类名.内部类名  变量名 = 外部类对象.内部类对象;
  Outer.Inner in = new Outer().new Inner();

- 当内部类在成员位置上，就可以被成员修饰符所修饰。
  比如，
  private：将内部类在外部类中进行封装。
  static:内部类就具备static的特性。
  当内部类被static修饰后，只能直接访问外部类中的static成员。出现了访问局限。

- 在外部其他类中，如何直接访问static内部类的非静态成员呢？
  new Outer.Inner().function();

- 在外部其他类中，如何直接访问static内部类的静态成员呢？
  uter.Inner.function();

注意：
当内部类中定义了静态成员，该内部类必须是static的。
当外部类中的静态方法访问内部类时，内部类也必须是static的。

> 当描述事物时，事物的内部还有事物，该事物用内部类来描述。
> 因为内部事务在使用外部事物的内容。

- 内部类定义在局部时，
  1，不可以被成员修饰符修饰
  2，可以直接访问外部类中的成员，因为还持有外部类中的引用。
  但是不可以访问它所在的局部中的变量。只能访问被final修饰的局部变量。

### 匿名内部类
- 匿名内部类其实就是内部类的简写格式。
- 定义匿名内部类的前提：
  内部类必须是继承一个类或者实现接口。
- 匿名内部类的格式：  new 父类或者接口(){定义子类的内容}
- 其实匿名内部类就是一个匿名子类对象。而且这个对象有点胖。	可以理解为带内容的对象。
- 匿名内部类中定义的方法最好不要超过3个。

## 异常
异常：就是程序在运行时出现不正常情况。
异常由来：问题也是现实生活中一个具体的事物，也可以通过java的类的形式进行描述。并封装成对象。其实就是java对不正常情况进行描述后的对象体现。

![](https://upload-images.jianshu.io/upload_images/1732196-eb8dbed2ce65a85c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

对于问题的划分：两种：一种是严重的问题，一种非严重的问题。

![](https://upload-images.jianshu.io/upload_images/1732196-c7330a89e9db30ec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


对于严重的，java通过Error类进行描述。对于Error一般不编写针对性的代码对其进行处理。

对与非严重的，java通过Exception类进行描述。对于Exception可以使用针对性的处理方式进行处理。

![](https://upload-images.jianshu.io/upload_images/1732196-c70f0b6b174d0839.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-445432cefa2f43c2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


2,异常的处理

java 提供了特有的语句进行处理。

```
try
{
	需要被检测的代码；
}
catch(异常类 变量)
{
	处理异常的代码；(处理方式)
}
finally
{
	一定会执行的语句；
}
```

3，对捕获到的异常对象进行常见方法操作。
	String getMessage()：获取异常信息。
```
class Demo
{
	int div(int a,int b)throws Exception//在功能上通过throws的关键字声明了该功能有可能会出现问题。
	{
		return a/b;
	}
}


class  ExceptionDemo
{
	public static void main(String[] args) 
	{
		Demo d = new Demo();
		try
		{
			int x = d.div(4,1);
			System.out.println("x="+x);
		}
		catch (Exception e)//Exception e = new ArithmeticException();
		{
			System.out.println("除零啦");
			System.out.println(e.getMessage());//  / by zero;
			System.out.println(e.toString());// 异常名称 ： 异常信息。

			e.printStackTrace();//异常名称，异常信息，异常出现的位置。
							//其实jvm默认的异常处理机制，就是在调用printStackTrace方法。
							//打印异常的堆栈的跟踪信息。


		}		
		

		System.out.println("over");

	}
}
```

在函数上声明异常。
便于提高安全性，让调用者进行处理。不处理编译失败。

![](https://upload-images.jianshu.io/upload_images/1732196-eaac77113e74ab75.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-fd0be48ca5bb6036.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![](https://upload-images.jianshu.io/upload_images/1732196-c672de0fdff3efdf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


对多异常的处理。
1，声明异常时，建议声明更为具体的异常。这样处理的可以更具体。
2，对方声明几个异常，就对应有几个catch块。不要定义多余的catch块。
如果多个catch块中的异常出现继承关系，父类异常catch块放在最下面。

建立在进行catch处理时，catch中一定要定义具体处理方式。不要简单定义一句 e.printStackTrace(),也不要简单的就书写一条输出语句。

因为项目中会出现特有的问题，而这些问题并未被java所描述并封装对象。
所以对于这些特有的问题可以按照java的对问题封装的思想。将特有的问题。进行自定义的异常封装。

自定义异常。

需求：在本程序中，对于除数是-1，也视为是错误的是无法进行运算的。
那么就需要对这个问题进行自定义的描述。

当在函数内部出现了throw抛出异常对象，那么就必须要给对应的处理动作。
要么在内部try catch处理。要么在函数上声明让调用者处理。

一般情况在，函数内出现异常，函数上需要声明。

发现打印的结果中只有异常的名称，却没有异常的信息。
因为自定义的异常并未定义信息。

如何定义异常信息呢？
因为父类中已经把异常信息的操作都完成了。
所以子类只要在构造时，将异常信息传递给父类通过super语句。
那么就可以直接通过getMessage方法获取自定义的异常信息。

自定义异常：
必须是自定义类继承Exception。


继承Exception原因：
异常体系有一个特点：因为异常类和异常对象都被抛出。
他们都具备可抛性。这个可抛性是Throwable这个体系中独有特点。

只有这个体系中的类和对象才可以被throws和throw操作。

throws和throw的区别
throws使用在函数上。
throw使用在函数内。

throws后面跟的异常类。可以跟多个。用逗号隔开。
throw后跟的是异常对象。

Exceptoin中有一个特殊的子类异常RuntimeException 运行时异常。

如果在函数内容抛出该异常，函数上可以不用声明，编译一样通过。

![](https://upload-images.jianshu.io/upload_images/1732196-ebee60f794064909.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-cfc2bdcf17dc15bc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


如果在函数上声明了该异常。调用者可以不用进行处理。编译一样通过；

之所以不用在函数声明，是因为不需要让调用者处理。
当该异常发生，希望程序停止。因为在运行时，出现了无法继续运算的情况，希望停止程序后，对代码进行修正。

自定义异常时：如果该异常的发生，无法在继续进行运算，就让自定义异常继承RuntimeException。

对于异常分两种：
1，编译时被检测的异常。
	
2，编译时不被检测的异常(运行时异常。RuntimeException以及其子类)



## 集合

### 集合概述

- **集合**：集合是java中提供的一种容器，可以用来存储多个数据。

集合和数组既然都是容器，它们有啥区别呢？

- 数组的长度是固定的。集合的长度是可变的。
- 数组中存储的是同一类型的元素，可以存储基本数据类型值。集合存储的都是对象。而且对象的类型可以不一致。在开发中一般当对象多的时候，使用集合进行存储。

### 集合框架

JAVASE提供了满足各种需求的API，在使用这些API前，先了解其继承与接口操作架构，才能了解何时采用哪个类，以及类之间如何彼此合作，从而达到灵活应用。

集合按照其存储结构可以分为两大类，分别是单列集合`java.util.Collection`和双列集合`java.util.Map`，今天我们主要学习`Collection`集合

- **Collection**：单列集合类的根接口，用于存储一系列符合某种规则的元素，它有两个重要的子接口，分别是`java.util.List`和`java.util.Set`。其中，`List`的特点是元素有序、元素可重复。`Set`的特点是元素无序，而且不可重复。`List`接口的主要实现类有`java.util.ArrayList`和`java.util.LinkedList`，`Set`接口的主要实现类有`java.util.HashSet`和`java.util.TreeSet`。

从上面的描述可以看出JDK中提供了丰富的集合类库，为了便于初学者进行系统地学习，接下来通过一张图来描述整个集合类的继承体系。

![image-20201230215147299](https://gitee.com/aduncmj/PictureBed/raw/master/images/20201230215147.png)



集合本身是一个工具，它存放在java.util包中。在`Collection`接口定义着单列集合框架中最最共性的内容。





### Collection 接口常用方法

Collection是所有单列集合的父接口，因此在Collection中定义了单列集合(List和Set)通用的一些方法，这些方法可用于操作所有的单列集合。方法如下：

- `public boolean add(E e)`：  把给定的对象添加到当前集合中 。
- `public void clear()` :清空集合中所有的元素。
- `public boolean remove(E e)`: 把给定的对象在当前集合中删除。
- `public boolean contains(E e)`: 判断当前集合中是否包含给定的对象。
- `public boolean isEmpty()`: 判断当前集合是否为空。
- `public int size()`: 返回集合中元素的个数。
- `public Object[] toArray()`: 把集合中的元素，存储到数组中。

### Iterator迭代器

#### Iterator接口

在程序开发中，经常需要遍历集合中的所有元素。针对这种需求，JDK专门提供了一个接口`java.util.Iterator`。`Iterator`接口也是Java集合中的一员，但它与`Collection`、`Map`接口有所不同，`Collection`接口与`Map`接口主要用于存储元素，而`Iterator`主要用于迭代访问（即遍历）`Collection`中的元素，因此`Iterator`对象也被称为迭代器。

想要遍历Collection集合，那么就要获取该集合迭代器完成迭代操作，下面介绍一下获取迭代器的方法：

- `public Iterator iterator()`: 获取集合对应的迭代器，用来遍历集合中的元素的。

下面介绍一下迭代的概念：

- **迭代**：即Collection集合元素的通用获取方式。在取元素之前先要判断集合中有没有元素，如果有，就把这个元素取出来，继续在判断，如果还有就再取出出来。一直把集合中的所有元素全部取出。这种取出方式专业术语称为迭代。

Iterator接口的常用方法如下：

- `public E next()`:返回迭代的下一个元素。
- `public boolean hasNext()`:如果仍有元素可以迭代，则返回 true。

接下来我们通过案例学习如何使用Iterator迭代集合中元素：

```java
public class IteratorDemo {
  	public static void main(String[] args) {
        // 使用多态方式 创建对象
        Collection<String> coll = new ArrayList<String>();

        // 添加元素到集合
        coll.add("串串星人");
        coll.add("吐槽星人");
        coll.add("汪星人");
        //遍历
        //使用迭代器 遍历   每个集合对象都有自己的迭代器
        Iterator<String> it = coll.iterator();
        //  泛型指的是 迭代出 元素的数据类型
        while(it.hasNext()){ //判断是否有迭代元素
            String s = it.next();//获取迭代出的元素
            System.out.println(s);
        }
  	}
}
```

> tips:：在进行集合元素取出时，如果集合中已经没有元素了，还继续使用迭代器的next方法，将会发生java.util.NoSuchElementException没有集合元素的错误。

#### 迭代器的实现原理

在调用Iterator的next方法之前，迭代器的索引位于第一个元素之前，不指向任何元素，当第一次调用迭代器的next方法后，迭代器的索引会向后移动一位，指向第一个元素并将该元素返回，当再次调用next方法时，迭代器的索引会指向第二个元素并将该元素返回，依此类推，直到hasNext方法返回false，表示到达了集合的末尾，终止对元素的遍历。

#### 增强for

增强for循环(也称for each循环)是**JDK1.5**以后出来的一个高级for循环，专门用来遍历数组和集合的。它的内部原理其实是个Iterator迭代器，所以在遍历的过程中，不能对集合中的元素进行增删操作。

格式：

```java
for(元素的数据类型  变量 : Collection集合or数组){ 
  	//写操作代码
}
```

它用于遍历Collection和数组。通常只进行遍历元素，不要在遍历的过程中对集合元素进行增删操作。



### 泛型

#### 泛型概述

在前面学习集合时，我们都知道**集合中是可以存放任意对象的，只要把对象存储集合后，那么这时他们都会被提升成Object类型**。当我们在取出每一个对象，并且进行相应的操作，这时必须采用类型转换。

大家观察下面代码：

```java
public class GenericDemo {
	public static void main(String[] args) {
		Collection coll = new ArrayList();
		coll.add("abc");
		coll.add("itcast");
		coll.add(5);//由于集合没有做任何限定，任何类型都可以给其中存放
		Iterator it = coll.iterator();
		while(it.hasNext()){
			//需要打印每个字符串的长度,就要把迭代出来的对象转成String类型
			String str = (String) it.next();
			System.out.println(str.length());
		}
	}
}
```

程序在运行时发生了问题**java.lang.ClassCastException**。                                                                                             为什么会发生类型转换异常呢？                                                                                                                                       我们来分析下：由于集合中什么类型的元素都可以存储。导致取出时强转引发运行时 ClassCastException。                                                                                                                                                       怎么来解决这个问题呢？                                                                                                                                                           Collection虽然可以存储各种对象，但实际上通常Collection只存储同一类型对象。例如都是存储字符串对象。因此在JDK5之后，新增了**泛型**(**Generic**)语法，让你在设计API时可以指定类或方法支持泛型，这样我们使用API的时候也变得更为简洁，并得到了编译时期的语法检查。

- **泛型**：可以在类或方法中预支地使用未知的类型。

> tips:一般在创建对象时，将未知的类型确定具体的类型。当没有指定泛型时，默认类型为Object类型。

#### 使用泛型的好处

上一节只是讲解了泛型的引入，那么泛型带来了哪些好处呢？

- 将运行时期的ClassCastException，转移到了编译时期变成了编译失败。
- 避免了类型强转的麻烦。

通过我们如下代码体验一下：

```java
public class GenericDemo2 {
	public static void main(String[] args) {
        Collection<String> list = new ArrayList<String>();
        list.add("abc");
        list.add("itcast");
        // list.add(5);//当集合明确类型后，存放类型不一致就会编译报错
        // 集合已经明确具体存放的元素类型，那么在使用迭代器的时候，迭代器也同样会知道具体遍历元素类型
        Iterator<String> it = list.iterator();
        while(it.hasNext()){
            String str = it.next();
            //当使用Iterator<String>控制元素类型后，就不需要强转了。获取到的元素直接就是String类型
            System.out.println(str.length());
        }
	}
}
```

> tips:泛型是数据类型的一部分，我们将类名与泛型合并一起看做数据类型。

####  泛型的定义与使用

我们在集合中会大量使用到泛型，这里来完整地学习泛型知识。

泛型，用来灵活地将数据类型应用到不同的类、方法、接口当中。将数据类型作为参数进行传递。

##### 定义和使用含有泛型的类

定义格式：

```
修饰符 class 类名<代表泛型的变量> {  }
```

例如，API中的ArrayList集合：

```java
class ArrayList<E>{ 
    public boolean add(E e){ }

    public E get(int index){ }
   	....
}
```

使用泛型： 即什么时候确定泛型。

**在创建对象的时候确定泛型**

 例如，`ArrayList<String> list = new ArrayList<String>();`

此时，变量E的值就是String类型,那么我们的类型就可以理解为：

```java 
class ArrayList<String>{ 
     public boolean add(String e){ }

     public String get(int index){  }
     ...
}
```

再例如，`ArrayList<Integer> list = new ArrayList<Integer>();`

此时，变量E的值就是Integer类型,那么我们的类型就可以理解为：

```java
class ArrayList<Integer> { 
     public boolean add(Integer e) { }

     public Integer get(int index) {  }
     ...
}
```

##### 含有泛型的方法

定义格式：

```
修饰符 <代表泛型的变量> 返回值类型 方法名(参数){  }
```

例如，

```java
public class MyGenericMethod {	  
    public <MVP> void show(MVP mvp) {
    	System.out.println(mvp.getClass());
    }
    
    public <MVP> MVP show2(MVP mvp) {	
    	return mvp;
    }
}
```

使用格式：**调用方法时，确定泛型的类型**

```java
public class GenericMethodDemo {
    public static void main(String[] args) {
        // 创建对象
        MyGenericMethod mm = new MyGenericMethod();
        // 演示看方法提示
        mm.show("aaa");
        mm.show(123);
        mm.show(12.45);
    }
}
```

##### 含有泛型的接口

定义格式：

```
修饰符 interface接口名<代表泛型的变量> {  }
```

例如，

```java
public interface MyGenericInterface<E>{
	public abstract void add(E e);
	
	public abstract E getE();  
}
```

使用格式：

**1、定义类时确定泛型的类型**

例如

```java
public class MyImp1 implements MyGenericInterface<String> {
	@Override
    public void add(String e) {
        // 省略...
    }

	@Override
	public String getE() {
		return null;
	}
}
```

此时，泛型E的值就是String类型。

 **2、始终不确定泛型的类型，直到创建对象时，确定泛型的类型**

 例如

```java
public class MyImp2<E> implements MyGenericInterface<E> {
	@Override
	public void add(E e) {
       	 // 省略...
	}

	@Override
	public E getE() {
		return null;
	}
}
```

确定泛型：

```java
/*
 * 使用
 */
public class GenericInterface {
    public static void main(String[] args) {
        MyImp2<String>  my = new MyImp2<String>();  
        my.add("aa");
    }
}
```

#### 泛型通配符

当使用泛型类或者接口时，传递的数据中，泛型类型不确定，可以通过通配符<?>表示。但是一旦使用泛型的通配符后，只能使用Object类中的共性方法，集合中元素自身方法无法使用。

##### 通配符基本使用

泛型的通配符:**不知道使用什么类型来接收的时候,此时可以使用?,?表示未知通配符。**

此时只能接受数据,不能往该集合中存储数据。

举个例子大家理解使用即可：

```java
public static void main(String[] args) {
    Collection<Intger> list1 = new ArrayList<Integer>();
    getElement(list1);
    Collection<String> list2 = new ArrayList<String>();
    getElement(list2);
}
public static void getElement(Collection<?> coll){}
//？代表可以接收任意类型
```

> tips:泛型不存在继承关系 Collection<Object> list = new ArrayList<String>();这种是错误的。

##### 通配符高级使用----受限泛型

之前设置泛型的时候，实际上是可以任意设置的，只要是类就可以设置。但是在JAVA的泛型中可以指定一个泛型的**上限**和**下限**。

**泛型的上限**：

- **格式**： `类型名称 <? extends 类 > 对象名称`
- **意义**： `只能接收该类型及其子类`

**泛型的下限**：

- **格式**： `类型名称 <? super 类 > 对象名称`
- **意义**： `只能接收该类型及其父类型`

比如：现已知Object类，String 类，Number类，Integer类，其中Number是Integer的父类

```java
public static void main(String[] args) {
    Collection<Integer> list1 = new ArrayList<Integer>();
    Collection<String> list2 = new ArrayList<String>();
    Collection<Number> list3 = new ArrayList<Number>();
    Collection<Object> list4 = new ArrayList<Object>();
    
    getElement(list1);
    getElement(list2);//报错
    getElement(list3);
    getElement(list4);//报错
  
    getElement2(list1);//报错
    getElement2(list2);//报错
    getElement2(list3);
    getElement2(list4);
  
}
// 泛型的上限：此时的泛型?，必须是Number类型或者Number类型的子类
public static void getElement1(Collection<? extends Number> coll){}
// 泛型的下限：此时的泛型?，必须是Number类型或者Number类型的父类
public static void getElement2(Collection<? super Number> coll){}
```



### List集合（接口）

我们掌握了Collection接口的使用后，再来看看Collection接口中的子类，他们都具备那些特性呢？

接下来，我们一起学习Collection中的常用几个子类（`java.util.List`集合、`java.util.Set`集合）。

#### List接口介绍

`java.util.List`接口继承自`Collection`接口，是单列集合的一个重要分支，习惯性地会将实现了`List`接口的对象称为List集合。在List集合中允许出现重复的元素，所有的元素是以一种线性方式进行存储的，在程序中可以通过索引来访问集合中的指定元素。另外，List集合还有一个特点就是元素有序，即元素的存入顺序和取出顺序一致。

#### List接口中常用方法

List作为Collection集合的**子接口**，不但继承了Collection接口中的全部方法，而且还增加了一些根据元素索引来操作集合的特有方法，如下：

- `public void add(int index, E element)`: 将指定的元素，添加到该集合中的指定位置上。
- `public E get(int index)`:返回集合中指定位置的元素。
- `public E remove(int index)`: 移除列表中指定位置的元素, 返回的是被移除的元素。
- `public E set(int index, E element)`:用指定元素替换集合中指定位置的元素,返回值的更新前的元素。

#### List的子类

##### ArrayList集合

`java.util.ArrayList`集合数据存储的结构是**数组结构**。元素增删慢，查找快，由于日常开发中使用最多的功能为查询数据、遍历数据，所以`ArrayList`是最常用的集合。

许多程序员开发时非常随意地使用ArrayList完成任何需求，并不严谨，这种用法是不提倡的。

##### LinkedList集合

`java.util.LinkedList`集合数据存储的结构是**链表结构**。方便元素添加、删除的集合。

实际开发中对一个集合元素的添加与删除经常涉及到首尾操作，而LinkedList提供了大量首尾操作的方法。这些方法我们作为了解即可：

- `public void addFirst(E e)`:将指定元素插入此列表的开头。
- `public void addLast(E e)`:将指定元素添加到此列表的结尾。
- `public E getFirst()`:返回此列表的第一个元素。
- `public E getLast()`:返回此列表的最后一个元素。
- `public E removeFirst()`:移除并返回此列表的第一个元素。
- `public E removeLast()`:移除并返回此列表的最后一个元素。
- `public E pop()`:从此列表所表示的堆栈处弹出一个元素。
- `public void push(E e)`:将元素推入此列表所表示的堆栈。
- `public boolean isEmpty()`：如果列表不包含元素，则返回true。

LinkedList是List的子类，List中的方法LinkedList都是可以使用，这里就不做详细介绍，我们只需要了解LinkedList的特有方法即可。**在开发时，LinkedList集合也可以作为堆栈，队列的结构使用**。

### Set集合（接口）

`java.util.Set`接口和`java.util.List`接口一样，同样继承自`Collection`接口，它与`Collection`接口中的方法基本一致，并没有对`Collection`接口进行功能上的扩充，只是比`Collection`接口更加严格了。与`List`接口不同的是，`Set`接口中元素无序，并且都会**以某种规则保证存入的元素不出现重复**。

`Set`集合有多个子类，这里我们介绍其中的`java.util.HashSet`、`java.util.LinkedHashSet`这两个集合。

> tips:Set集合取出元素的方式可以采用：迭代器、增强for。

#### HashSet集合

`java.util.HashSet`是`Set`接口的一个实现类，它所存储的元素是不可重复的，并且元素都是无序的(即存取顺序不一致)。`java.util.HashSet`**底层的实现其实是一个`java.util.HashMap`支持**，由于我们暂时还未学习，先做了解。

`HashSet`**是根据对象的哈希值来确定元素在集合中的存储位置，因此具有良好的存取和查找性能**。保证元素唯一性的方式**依赖于：`hashCode`与`equals`方法**。

##### ??HashSet集合存储数据的结构（哈希表）

什么是哈希表呢？

在**JDK1.8**之前，哈希表底层采用数组+链表实现，即使用链表处理冲突，同一hash值的链表都存储在一个链表里。但是当位于一个桶中的元素较多，即hash值相等的元素较多时，通过key值依次查找的效率较低。而JDK1.8中，哈希表存储采用数组+链表+红黑树实现，当链表长度超过阈值（8）时，将链表转换为红黑树，这样大大减少了查找时间。

简单的来说，哈希表是由数组+链表+红黑树（JDK1.8增加了红黑树部分）实现的，如下图所示。

![image-20201230221453303](https://gitee.com/aduncmj/PictureBed/raw/master/images/20201230221453.png)

看到这张图就有人要问了，这个是怎么存储的呢？

为了方便大家的理解我们结合一个存储流程图来说明一下：

![image-20201230215424011](https://gitee.com/aduncmj/PictureBed/raw/master/images/20201230215424.png)



总而言之，**JDK1.8**引入红黑树大程度优化了HashMap的性能，那么对于我们来讲保证HashSet集合元素的唯一，其实就是根据对象的hashCode和equals方法来决定的。如果我们往集合中存放自定义的对象，那么保证其唯一，就必须复写hashCode和equals方法建立属于当前对象的比较方式。

##### LinkedHashSet

我们知道HashSet保证元素唯一，可是元素存放进去是没有顺序的，那么我们要保证有序，怎么办呢？

在HashSet下面有一个子类`java.util.LinkedHashSet`，它是链表和哈希表组合的一个数据存储结构。

#### TreeSet集合

可以对Set集合中的元素进行排序。
			底层数据结构是二叉树。
			保证元素唯一性的依据：
			compareTo方法return 0.
			TreeSet排序的第一种方式：让元素自身具备比较性。
			元素需要实现Comparable接口，覆盖compareTo方法。
			也种方式也成为元素的自然顺序，或者叫做默认顺序。
			TreeSet的第二种排序方式。
			当元素自身不具备比较性时，或者具备的比较性不是所需要的。
			这时就需要让集合自身具备比较性。
			在集合初始化时，就有了比较方式。



### 队列&&栈



#### 队列

![摘自java核心技术](https://gitee.com/aduncmj/PictureBed/raw/master/images/2020-10-20_203156.png)

可按如下方式使用队列：

`LinkedList<Integer> queue = new LinkedList<>()` 

或
`Queue<Integer> queue = new LinkedList<>()`

![image-20201230215707241](C:\Users\aduncmj\AppData\Roaming\Typora\typora-user-images\image-20201230215707241.png)

#### stack栈

Java堆栈Stack类已经过时，Java官方推荐使用Deque替代Stack使用。Deque堆栈操作方法：push()、pop()、peek()。

如需使用栈，如下：

`LinkedList<Integer> stack = new LinkedList<>()` 

或
`Deque<Integer> stack = new LinkedList<Integer>()`

#### 双端队列

Deque是一个双端队列**接口**，继承自Queue接口，Deque的实现类是LinkedList、ArrayDeque、LinkedBlockingDeque，**其中LinkedList是最常用的。**LinkedList集合可作为堆栈，队列的结构使用**。

![image-20201230215818676](https://gitee.com/aduncmj/PictureBed/raw/master/images/20201230215818.png)

#### 优先级队列

### Collections

#### 常用功能

- `java.utils.Collections`是集合工具类，用来对集合进行操作。部分方法如下：

- `public static <T> boolean addAll(Collection<T> c, T... elements)  `:往集合中添加一些元素。
- `public static void shuffle(List<?> list) 打乱顺序`:打乱集合顺序。
- `public static <T> void sort(List<T> list)`:将集合中元素按照默认规则排序。
- `public static <T> void sort(List<T> list，Comparator<? super T> )`:将集合中元素按照指定规则排序。

代码演示：

```java
public class CollectionsDemo {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<Integer>();
        //原来写法
        //list.add(12);
        //list.add(14);
        //list.add(15);
        //list.add(1000);
        //采用工具类 完成 往集合中添加元素  
        Collections.addAll(list, 5, 222, 1，2);
        System.out.println(list);
        //排序方法 
        Collections.sort(list);
        System.out.println(list);
    }
}
结果：
[5, 222, 1, 2]
[1, 2, 5, 222]
```

代码演示之后 ，发现我们的集合按照顺序进行了排列，可是这样的顺序是采用默认的顺序，如果想要指定顺序那该怎么办呢？

我们发现还有个方法没有讲，`public static <T> void sort(List<T> list，Comparator<? super T> )`:将集合中元素按照指定规则排序。接下来讲解一下指定规则的排列。

#### Comparator比较器

我们还是先研究这个方法

`public static <T> void sort(List<T> list)`:将集合中元素按照默认规则排序。

不过这次存储的是字符串类型。

```java
public class CollectionsDemo2 {
    public static void main(String[] args) {
        ArrayList<String>  list = new ArrayList<String>();
        list.add("cba");
        list.add("aba");
        list.add("sba");
        list.add("nba");
        //排序方法
        Collections.sort(list);
        System.out.println(list);
    }
}
```

结果：

```
[aba, cba, nba, sba]
```

我们使用的是默认的规则完成字符串的排序，那么默认规则是怎么定义出来的呢？

说到排序了，简单的说就是两个对象之间比较大小，那么在JAVA中提供了两种比较实现的方式，一种是比较死板的采用`java.lang.Comparable`接口去实现，一种是灵活的当我需要做排序的时候在去选择的`java.util.Comparator`接口完成。

那么我们采用的`public static <T> void sort(List<T> list)`这个方法完成的排序，实际上要求了被排序的类型需要实现Comparable接口完成比较的功能，在String类型上如下：

```java
public final class String implements java.io.Serializable, Comparable<String>, CharSequence {
```

String类实现了这个接口，并完成了比较规则的定义，但是这样就把这种规则写死了，那比如我想要字符串按照第一个字符降序排列，那么这样就要修改String的源代码，这是不可能的了，那么这个时候我们可以使用

`public static <T> void sort(List<T> list，Comparator<? super T> )`方法灵活的完成，这个里面就涉及到了Comparator这个接口，位于java.util包下，排序是comparator能实现的功能之一,该接口代表一个比较器，比较器具有可比性！顾名思义就是做排序的，通俗地讲需要比较两个对象谁排在前谁排在后，那么比较的方法就是：

- ` public int compare(String o1, String o2)`：比较其两个参数的顺序。

  > 两个对象比较的结果有三种：大于，等于，小于。
  >
  > 如果要按照升序排序，
  > 则o1 小于o2，返回（负数），相等返回0，01大于02返回（正数）
  > 如果要按照降序排序
  > 则o1 小于o2，返回（正数），相等返回0，01大于02返回（负数）

操作如下:

```java
public class CollectionsDemo3 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<String>();
        list.add("cba");
        list.add("aba");
        list.add("sba");
        list.add("nba");
        //排序方法  按照第一个单词的降序
        Collections.sort(list, new Comparator<String>() {
            @Override
            public int compare(String o1, String o2) {
                return o2.charAt(0) - o1.charAt(0);
            }
        });
        System.out.println(list);
    }
}
```

结果如下：

```
[sba, nba, cba, aba]
```

#### 简述Comparable和Comparator两个接口的区别。

**Comparable**：强行对实现它的每个类的对象进行整体排序。这种排序被称为类的自然排序，类的compareTo方法被称为它的自然比较方法。只能在类中实现compareTo()一次，不能经常修改类的代码实现自己想要的排序。实现此接口的对象列表（和数组）可以通过Collections.sort（和Arrays.sort）进行自动排序，对象可以用作有序映射中的键或有序集合中的元素，无需指定比较器。

**Comparator**强行对某个对象进行整体排序。可以将Comparator 传递给sort方法（如Collections.sort或 Arrays.sort），从而允许在排序顺序上实现精确控制。还可以使用Comparator来控制某些数据结构（如有序set或有序映射）的顺序，或者为那些没有自然顺序的对象collection提供排序。



### Map集合（接口）

#### 概述

现实生活中，我们常会看到这样的一种集合：IP地址与主机名，身份证号与个人，系统用户名与系统用户对象等，这种一一对应的关系，就叫做映射。Java提供了专门的集合类用来存放这种对象关系的对象，即`java.util.Map`接口。

我们通过查看`Map`接口描述，发现`Map`接口下的集合与`Collection`接口下的集合，它们存储数据的形式不同。

- `Collection`中的集合，元素是孤立存在的（理解为单身），向集合中存储元素采用一个个元素的方式存储。
- `Map`中的集合，元素是成对存在的(理解为夫妻)。每个元素由键与值两部分组成，通过键可以找对所对应的值。
- `Collection`中的集合称为单列集合，`Map`中的集合称为双列集合。
- 需要注意的是，`Map`中的集合不能包含重复的键，值可以重复；每个键只能对应一个值。

#### Map常用子类

通过查看Map接口描述，看到Map有多个子类，这里我们主要讲解常用的HashMap集合、LinkedHashMap集合。

- **HashMap<K,V>**：存储数据采用的哈希表结构，元素的存取顺序不能保证一致。由于要保证键的唯一、不重复，需要重写键的hashCode()方法、equals()方法。
- **LinkedHashMap<K,V>**：HashMap下有个子类LinkedHashMap，存储数据采用的哈希表结构+链表结构。通过链表结构可以保证元素的存取顺序一致；通过哈希表结构可以保证的键的唯一、不重复，需要重写键的hashCode()方法、equals()方法。

> tips：Map接口中的集合都有两个泛型变量<K,V>,在使用时，要为两个泛型变量赋予数据类型。两个泛型变量<K,V>的数据类型可以相同，也可以不同。

#### Map接口中的常用方法

Map接口中定义了很多方法，常用的如下：

- `public V put(K key, V value)`:  把指定的键与指定的值添加到Map集合中。
- `public V remove(Object key)`: 把指定的键 所对应的键值对元素 在Map集合中删除，返回被删除元素的值。
- `public V get(Object key)` 根据指定的键，在Map集合中获取对应的值。
- `boolean containsKey(Object key)  ` 判断集合中是否包含指定的键。
- `public Set<K> keySet()`: 获取Map集合中所有的键，存储到Set集合中。
- `public Set<Map.Entry<K,V>> entrySet()`: 获取到Map集合中所有的键值对对象的集合(Set集合)。

##### **Hashmap**：

##### 遍历键找值方式

键找值方式：即通过元素中的键，获取键所对应的值

分析步骤：

1. 获取Map中所有的键，由于键是唯一的，所以返回一个Set集合存储所有的键。方法提示:`keyset()`
2. 遍历键的Set集合，得到每一个键。
3. 根据键，获取键所对应的值。方法提示:`get(K key)`

##### 遍历键值对方式

**Entry键值对对象**

我们已经知道，`Map`中存放的是两种对象，一种称为**key**(键)，一种称为**value**(值)，它们在在`Map`中是一一对应关系，这一对对象又称做`Map`中的一个`Entry(项)`。`Entry`将键值对的对应关系封装成了对象。即键值对对象，这样我们在遍历`Map`集合时，就可以从每一个键值对（`Entry`）对象中获取对应的键与对应的值。

 既然Entry表示了一对键和值，那么也同样提供了获取对应键和对应值得方法：

- `public K getKey()`：获取Entry对象中的键。
- `public V getValue()`：获取Entry对象中的值。

在Map集合中也提供了获取所有Entry对象的方法：

- `public Set<Map.Entry<K,V>> entrySet()`: 获取到Map集合中所有的键值对对象的集合(Set集合)。

**键值对方式：**

即通过集合中每个键值对(Entry)对象，获取键值对(Entry)对象中的键与值。

操作步骤与图解：

1. 获取Map集合中，所有的键值对(Entry)对象，以Set集合形式返回。方法提示:`entrySet()`。
2. 遍历包含键值对(Entry)对象的Set集合，得到每一个键值对(Entry)对象。
3. 通过键值对(Entry)对象，获取Entry对象中的键与值。  方法提示:`getkey() getValue()`     

```java
public class MapDemo02 {
    public static void main(String[] args) {
        // 创建Map集合对象 
        HashMap<String, String> map = new HashMap<String,String>();
        // 添加元素到集合 
        map.put("胡歌", "霍建华");
        map.put("郭德纲", "于谦");
        map.put("薛之谦", "大张伟");

        // 获取 所有的 entry对象  entrySet
        Set<Entry<String,String>> entrySet = map.entrySet();

        // 遍历得到每一个entry对象
        for (Entry<String, String> entry : entrySet) {
           	// 解析 
            String key = entry.getKey();
            String value = entry.getValue();  
            System.out.println(key+"的CP是:"+value);
        }
    }
}
```

遍历图解：

![](C:/%23/temp/15.%E3%80%90Map%E3%80%91/15.%E3%80%90Map%E3%80%91-%E7%AC%94%E8%AE%B0/%E5%B0%B1%E4%B8%9A%E7%8F%AD-day04-Map/img/Map%E9%9B%86%E5%90%88%E9%81%8D%E5%8E%86%E6%96%B9%E5%BC%8F%E4%BA%8C.bmp)

> tips：Map集合不能直接使用迭代器或者foreach进行遍历。但是转成Set之后就可以使用了。

##### 存储自定义类型键值

练习：每位学生（姓名，年龄）都有自己的家庭住址。那么，既然有对应关系，则将学生对象和家庭住址存储到map集合中。学生作为键, 家庭住址作为值。

> 注意，学生姓名相同并且年龄相同视为同一名学生。

编写学生类：

```java
public class Student {
    private String name;
    private int age;

    public Student() {
    }

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    @Override
    public boolean equals(Object o) {
        if (this == o)
            return true;
        if (o == null || getClass() != o.getClass())
            return false;
        Student student = (Student) o;
        return age == student.age && Objects.equals(name, student.name);
    }

    @Override
    public int hashCode() {
        return Objects.hash(name, age);
    }
}
```

编写测试类：

```java 
public class HashMapTest {
    public static void main(String[] args) {
        //1,创建Hashmap集合对象。
        Map<Student,String>map = new HashMap<Student,String>();
        //2,添加元素。
        map.put(newStudent("lisi",28), "上海");
        map.put(newStudent("wangwu",22), "北京");
        map.put(newStudent("zhaoliu",24), "成都");
        map.put(newStudent("zhouqi",25), "广州");
        map.put(newStudent("wangwu",22), "南京");
        
        //3,取出元素。键找值方式
        Set<Student>keySet = map.keySet();
        for(Student key: keySet){
            Stringvalue = map.get(key);
            System.out.println(key.toString()+"....."+value);
        }
    }
}
```

- 当给HashMap中存放自定义对象时，如果自定义对象作为key存在，这时要保证对象唯一，必须复写对象的hashCode和equals方法(如果忘记，请回顾HashSet存放自定义对象)。
- 如果要保证map中存放的key和取出的顺序一致，可以使用`java.util.LinkedHashMap`集合来存放。

##### LinkedHashMap

我们知道HashMap保证成对元素唯一，并且查询速度很快，可是成对元素存放进去是没有顺序的，那么我们要保证有序，还要速度快怎么办呢？

在HashMap下面有一个子类LinkedHashMap，它是链表和哈希表组合的一个数据存储结构。

```java
public class LinkedHashMapDemo {
    public static void main(String[] args) {
        LinkedHashMap<String, String> map = new LinkedHashMap<String, String>();
        map.put("邓超", "孙俪");
        map.put("李晨", "范冰冰");
        map.put("刘德华", "朱丽倩");
        Set<Entry<String, String>> entrySet = map.entrySet();
        for (Entry<String, String> entry : entrySet) {
            System.out.println(entry.getKey() + "  " + entry.getValue());
        }
    }
}
```

结果:

```
邓超  孙俪
李晨  范冰冰
刘德华  朱丽倩
```

##### TreeMap：

底层是二叉树数据结构。线程不同步。可以用于给map集合中的键进行排序。



## 多线程

我们在之前，学习的程序在没有跳转语句的前提下，都是由上至下依次执行，那现在想要设计一个程序，边打游戏边听歌，怎么设计？

要解决上述问题,咱们得使用多进程或者多线程来解决.

### 并发与并行

- **并发**：指两个或多个事件在**同一个时间段内**发生。
- **并行**：指两个或多个事件在**同一时刻**发生（同时发生）。

### 线程与进程

- Java并发编程：进程和线程之由来

​    [https://www.cnblogs.com/dolphin0520/p/3910667.html](https://www.cnblogs.com/dolphin0520/p/3910667.html)

- **进程**：是指一个内存中运行的应用程序，每个进程都有一个独立的内存空间，一个应用程序可以同时运行多个进程；进程也是程序的一次执行过程，是系统运行程序的基本单位；系统运行一个程序即是一个进程从创建、运行到消亡的过程。
- **线程**：线程是进程中的一个执行单元，负责当前进程中程序的执行，一个进程中至少有一个线程。一个进程中是可以有多个线程的，这个应用程序也可以称之为多线程程序。 

我们可以再电脑底部任务栏，右键----->打开任务管理器,可以查看当前任务的进程：

**进程**

![image-20201230215937227](https://gitee.com/aduncmj/PictureBed/raw/master/images/20201230215937.png)

**线程**



**线程调度:**

- 分时调度

  所有线程轮流使用 CPU 的使用权，平均分配每个线程占用 CPU 的时间。

- 抢占式调度

  优先让优先级高的线程使用 CPU，如果线程的优先级相同，那么会随机选择一个(线程随机性)，**Java使用的为抢占式调度**。

  - 设置线程的优先级

  ![设置线程优先级](https://gitee.com/aduncmj/PictureBed/raw/master/images/状态转移.png)

### 创建线程类方式一

Java使用`java.lang.Thread`类代表**线程**，所有的线程对象都必须是Thread类或其子类的实例。每个线程的作用是完成一定的任务，实际上就是执行一段程序流即一段顺序执行的代码。Java使用线程执行体来代表这段程序流。Java中通过继承Thread类来**创建**并**启动多线程**的步骤如下：

1. 定义Thread类的子类，并重写该类的run()方法，该run()方法的方法体就代表了线程需要完成的任务,因此把run()方法称为线程执行体。
2. 创建Thread子类的实例，即创建了线程对象
3. 调用线程对象的start()方法来启动该线程

### 多线程原理

多线程执行时序图

流程图：

![image-20201230220147149](https://gitee.com/aduncmj/PictureBed/raw/master/images/20201230220147.png)

程序启动运行main时候，java虚拟机启动一个进程，主线程main在main()调用时候被创建。随着调用mt的对象的start方法，另外一个新的线程也启动了，这样，整个应用就在多线程下运行。

通过这张图我们可以很清晰的看到多线程的执行流程，那么为什么可以完成并发执行呢？我们再来讲一讲原理。
多线程执行时，到底在内存中是如何运行的呢？以上个程序为例，进行图解说明：

![image-20201230220245116](C:\Users\aduncmj\AppData\Roaming\Typora\typora-user-images\image-20201230220245116.png)

多线程执行时，在栈内存中，其实**每一个执行线程都有一片自己所属的栈内存空间**。进行方法的压栈和弹栈。

当执行线程的任务结束了，线程自动在栈内存中释放了。但是当所有的执行线程都结束了，那么进程就结束了。

Thread类

API中该类中定义了有关线程的一些方法，具体如下：

**构造方法**：

`public Thread()`:分配一个新的线程对象。

`public Thread(String name)`:分配一个指定名称的新的线程对象。

`public Thread(Runnable target)`:分配一个带有指定目标新的线程对象。

`public Thread(Runnable target,String name)`:分配一个带有指定目标新的线程对象并指定名字。

**常用方法：**

`public String getName() `:获取当前线程名称。

`public void start()` :导致此线程开始执行; Java虚拟机调用此线程的run方法。

`public void run()` :此线程要执行的任务在此处定义代码。

`public static void sleep(long millis)`:使当前正在执行的线程以指定的毫秒数暂停（暂时停止执行）。

`public static Thread currentThread() `:返回对当前正在执行的线程对象的引用。

> 翻阅API后得知创建线程的方式总共有两种，一种是继承Thread类方式，一种是实现Runnable接口方式，方式一我
> 们已经完成，接下来讲解方式二实现的方式。

### 创建线程方式二

采用`java.lang.Runnable`也是非常常见的一种，我们只需要重写run方法即可。

步骤如下：

1. 定义Runnable接口的实现类，并重写该接口的run()方法，该run()方法的方法体同样是该线程的线程执行体。
2. 创建Runnable实现类的实例，并以此实例作为Thread的target来创建Thread对象，该Thread对象才是真正的线程对象。
3. 调用线程对象的start()方法来启动线程。

代码如下：

```java
public class MyRunnable implements Runnable{ 
    @Override
	public void run() {
		for (int i = 0; i < 20; i++) { 								System.out.println(Thread.currentThread().getName()+" "+i);
		}
	}
}


public class Demo {
	public static void main(String[] args) {
		//创建自定义类对象 线程任务对象
		MyRunnable mr = new MyRunnable();
        //创建线程对象
        Thread t = new Thread(mr, "小强");
        t.start();
        for (int i = 0; i < 20; i++) {
			System.out.println("旺财 " + i);
		}
	}
}
```



通过实现Runnable接口，使得该类有了多线程类的特征。run()方法是多线程程序的一个执行目标。所有的多线程代码都在run方法里面。Thread类实际上也是实现了Runnable接口的类。

在启动的多线程的时候，需要先通过Thread类的构造方法Thread(Runnable target)构造出对象，然后调用Thread 对象的start()方法来运行多线程代码。

实际上所有的多线程代码都是通过运行Thread的start()方法来运行的。因此，不管是继承Thread类还是实现Runnable接口来实现多线程，最终还是通过Thread的对象的API来控制线程的，熟悉Thread类的API是进行多线程编程的基础。

> tips:Runnable对象仅仅作为Thread对象的target，Runnable实现类里包含的run()方法仅作为线程执行体。而实际的线程对象依然是Thread实例，只是该Thread线程负责执行其target的run()方法。

### Thread和Runnable的区别

如果一个类继承Thread，则不适合资源共享。但是如果实现了Runable接口的话，则很容易的实现资源共享。
**总结：**

**实现Runnable接口比继承Thread类所具有的优势：**

1. 适合多个相同的程序代码的线程去共享同一个资源。
2. 可以避免java中的单继承的局限性。
3. 增加程序的健壮性，实现解耦操作，代码可以被多个线程共享，代码和线程独立。
4. 线程池只能放入实现Runable或Callable类线程，不能直接放入继承Thread的类。

> 扩充：在java中，每次程序运行至少启动2个线程。一个是main线程，一个是垃圾收集线程。因为每当使用java命令执行一个类的时候，实际上都会启动一个JVM，每一个JVM其实在就是在操作系统中启动了一个进程。

### 匿名内部类方式实现线程的创建

使用线程的内匿名内部类方式，可以方便的实现每个线程执行不同的线程任务操作。

使用匿名内部类的方式实现Runnable接口，重新Runnable接口中的run方法：

```Java
public class NoNameInnerClassThread {
public static void main(String[] args) {
//	new Runnable(){
//		public void run(){
//			for (int i = 0; i < 20; i++) {
//				System.out.println("张宇:"+i);
//			}
//		}
//	}; 
    //‐‐‐这个整体  相当于new MyRunnable() 
    Runnable r = new Runnable(){
		public void run(){
			for (int i = 0; i < 20; i++) {
				System.out.println("张宇:"+i);
			}
		}
	};

	new Thread(r).start();

```



### 线程安全

#### 线程安全

线程安全问题都是由全局变量及静态变量引起的。若每个线程中对全局变量、静态变量只有读操作，而无写操作，一般来说，这个全局变量是线程安全的；若有多个线程同时执行写操作，一般都需要考虑线程同步，否则的话就可能影响线程安全。

#### 线程同步

当我们使用多个线程访问同一资源的时候，且多个线程中对资源有写的操作，就容易出现线程安全问题。要解决上述多线程并发访问一个资源的安全性问题: Java中提供了同步机制(**synchronized**)来解决。



为了保证每个线程都能正常执行原子操作,Java引入了线程同步机制。那么怎么去使用呢？有三种方式完成同步操作：

1. 同步代码块。
2. 同步方法。
3. 锁机制。

##### 同步代码块

**同步代码块**：`Synchronized`关键字可以用于方法中的某个区块中，表示只对这个区块的资源实行互斥访问。

格式：

```java
synchronized(同步锁){
	需要同步操作的代码
}
```

**同步锁**:

对象的同步锁只是一个概念,可以想象为在对象上标记了一个锁.

1. 锁对象 可以是任意类型。
2. 多个线程对象 要使用同一把锁。

> 注意:在任何时候,最多允许一个线程拥有同步锁,谁拿到锁就进入代码块,其他的线程只能在外等着(BLOCKED)。

使用同步代码块解决代码：

```java
public class Ticket implements Runnable{ private int ticket = 100;

Object lock = new Object();
/*
* 执行卖票操作
*/ @Override
public void run() {
//每个窗口卖票的操作
//窗口 永远开启
while(true){
synchronized (lock) {
if(ticket>0){//有票 可以卖
//出票操作
//使用sleep模拟一下出票时间
try {
Thread.sleep(50);
} catch (InterruptedException e) {
// TODO Auto‐generated catch block e.printStackTrace();
}
//获取当前线程对象的名字
String name = Thread.currentThread().getName();
System.out.println(name+"正在卖:"+ticket‐‐);
}

}
```

当使用了同步代码块后，上述的线程的安全问题，解决了。

##### 同步方法

**同步方法**:使用synchronized修饰的方法,就叫做同步方法,保证A线程执行该方法的时候,其他线程只能在方法外等着。

格式：

```java
public synchronized void method(){
	可能会产生线程安全问题的代码
}
```



> 同步锁是谁?
>
> 对于非static方法,同步锁就是this。
>
> 对于static方法,我们使用当前方法所在类的字节码对象(类名.class)。

使用同步方法代码如下：

```java
public class Ticket implements Runnable{ private int ticket = 100;
/*
* 执行卖票操作
*/ @Override
public void run() {
//每个窗口卖票的操作
//窗口 永远开启
while(true){
sellTicket();
}
}

/*
*	锁对象 是 谁调用这个方法 就是谁
*	隐 含 锁 对 象 就 是 this
*
*/
public synchronized void sellTicket(){
if(ticket>0){//有票 可以卖
//出票操作
//使用sleep模拟一下出票时间
try {
Thread.sleep(100);
} catch (InterruptedException e) {
// TODO Auto‐generated catch block
e.printStackTrace();
}
//获取当前线程对象的名字
String name = Thread.currentThread().getName();
System.out.println(name+"正在卖:"+ticket‐‐);


```



##### Lock锁

`java.util.concurrent.locks.Lock`机制提供了比**synchronized**代码块和**synchronized**方法更广泛的锁定操作,同步代码块/同步方法具有的功能Lock都有,除此之外更强大,更体现面向对象。

Lock锁也称同步锁，加锁与释放锁方法化了，如下：

`public void lock()` :加同步锁。

`public void unlock() `:释放同步锁。

使用如下：

```java
public class Ticket implements Runnable{ private int ticket = 100;

Lock lock = new ReentrantLock();
/*
* 执行卖票操作
*/ @Override
public void run() {
//每个窗口卖票的操作
//窗口 永远开启
while(true){
lock.lock();
if(ticket>0){//有票 可以卖
//出票操作
//使用sleep模拟一下出票时间
try {
Thread.sleep(50);
} catch (InterruptedException e) {
// TODO Auto‐generated catch block e.printStackTrace();
}
//获取当前线程对象的名字
String name = Thread.currentThread().getName();
System.out.println(name+"正在卖:"+ticket‐‐);
}
lock.unlock();
}
}
}

```



### 线程状态

#### 线程状态概述

当线程被创建并启动以后，它既不是一启动就进入了执行状态，也不是一直处于执行状态。在线程的生命周期中，有几种状态呢？在API中 这个枚举中给出了六种线程状态：

这里先列出各个线程状态发生的条件，下面将会对每种状态进行详细解析

| **线程状态**            | **导致状态发生条件**                                         |
| ----------------------- | ------------------------------------------------------------ |
| NEW(新建)               | 线程刚被创建，但是并未启动。还没调用start方法。              |
| Runnable(可运行)        | 线程可以在java虚拟机中运行的状态，可能正在运行自己代码，也可能没有，这取决于操作系统处理器。 |
| Blocked(锁阻塞)         | 当一个线程试图获取一个对象锁，而该对象锁被其他的线程持有，则该线程进入Blocked状态；当该线程持有锁时，该线程将变成Runnable状态。 |
| Waiting(无限等待)       | 一个线程在等待另一个线程执行一个（唤醒）动作时，该线程进入Waiting状态。进入这个状态后是不能自动唤醒的，必须等待另一个线程调用notify或者notifyAll方法才能够唤醒。 |
| Timed Waiting(计时等待) | 同waiting状态，有几个方法有超时参数，调用他们将进入Timed Waiting状态。这一状态将一直保持到超时期满或者接收到唤醒通知。带有超时参数的常用方法有Thread.sleep 、 Object.wait。 |
| Teminated(被终止)       | 因为run方法正常退出而死亡，或者因为没有捕获的异常终止了run方法而死亡。 |

我们不需要去研究这几种状态的实现原理，我们只需知道在做线程操作中存在这样的状态。那我们怎么去理解这几个状态呢，新建与被终止还是很容易理解的，我们就研究一下线程从Runnable（可运行）状态与非运行状态之间的转换问题。

#### Timed Waiting（计时等待）

Timed Waiting在API中的描述为：一个正在限时等待另一个线程执行一个（唤醒）动作的线程处于这一状态。单独的去理解这句话，真是玄之又玄，其实我们在之前的操作中已经接触过这个状态了，在哪里呢？

在我们写卖票的案例中，为了减少线程执行太快，现象不明显等问题，我们在run方法中添加了sleep语句，这样就强制当前正在执行的线程休眠（**暂停执行**），以“减慢线程”。

其实当我们调用了sleep方法之后，当前执行的线程就进入到“休眠状态”，其实就是所谓的Timed Waiting(计时等待)，那么我们通过一个案例加深对该状态的一个理解。

**实现一个计数器，计数到100，在每个数字之间暂停1秒，每隔10个数字输出一个字符串**

代码：

```java
public class MyThread extends Thread { public void run() {
for (int i = 0; i < 100; i++) { if ((i) % 10 == 0) {
System.out.println("‐‐‐‐‐‐‐" + i);
}
System.out.print(i); 
   try {
Thread.sleep(1000);
System.out.print("	线程睡眠1秒！\n");
} catch (InterruptedException e) { e.printStackTrace();
}
}
}
public static void main(String[] args) { new MyThread().start();
}

```

通过案例可以发现，sleep方法的使用还是很简单的。我们需要记住下面几点：

1. 进入 TIMED_WAITING 状态的一种常见情形是调用的 sleep
   方法，单独的线程也可以调用，不一定非要有协作关系。
2. 为了让其他线程有机会执行，可以将Thread.sleep()的调用**放线程run()之内**。这样才能保证该线程执行过程中会睡眠
3. sleep与锁无关，线程睡眠到期自动苏醒，并返回到Runnable（可运行）状态。

> 小提示：sleep()中指定的时间是线程不会运行的最短时间。因此，sleep()方法不能保证该线程睡眠到期后就开始立刻执行。

#### BLOCKED（锁阻塞）

Blocked状态在API中的介绍为：一个正在阻塞等待一个监视器锁（锁对象）的线程处于这一状态。

我们已经学完同步机制，那么这个状态是非常好理解的了。比如，线程A与线程B代码中使用同一锁，如果线程A获
取到锁，线程A进入到Runnable状态，那么线程B就进入到Blocked锁阻塞状态。

这是由Runnable状态进入Blocked状态。除此Waiting以及Time
Waiting状态也会在某种情况下进入阻塞状态，而这部分内容作为扩充知识点带领大家了解一下。

Blocked 线程状态图

![image-20201230220936321](https://gitee.com/aduncmj/PictureBed/raw/master/images/20201230220936.png)

#### Waiting（无限等待）



Wating状态在API中介绍为：一个正在无限期等待另一个线程执行一个特别的（唤醒）动作的线程处于这一状态。

那么我们之前遇到过这种状态吗？答案是并没有，但并不妨碍我们进行一个简单深入的了解。我们通过一段代码来学习一下：

```java
public class WaitingTest {
	public static Object obj = new Object();

	public static void main(String[] args) {
// 演示waiting
		new Thread(new Runnable() {
			@Override
			public void run() {
				while (true) {
					synchronized (obj) {
						try {
							System.out.println(
									Thread.currentThread().getName() + "=== 获取到锁对象，调用wait方法，进入waiting状态，释放锁对象");
							obj.wait(); // 无限等待
							// obj.wait(5000); //计时等待, 5秒 时间到，自动醒来

						} catch (InterruptedException e) {
							e.printStackTrace();
						}
						System.out.println(Thread.currentThread().getName() + "=== 从waiting状态醒来，获取到锁对象，继续执行了");
					}
				}
			}
		}, "等待线程").start();

		new Thread(new Runnable() {
			@Override
			public void run() {
//			while (true){	//每隔3秒 唤醒一次

				try {
					System.out.println(Thread.currentThread().getName() + "‐‐‐‐‐ 等待3秒钟");
					Thread.sleep(3000);
				} catch (InterruptedException e) {
					e.printStackTrace();
				}

				synchronized (obj) {
					System.out.println(Thread.currentThread().getName() + "‐‐‐‐‐ 获取到锁对象,调用notify方法，释放锁对象");
					obj.notify();
				}
			}
//			}
		}, "唤醒线程").start();
	}
}

```



通过上述案例我们会发现，一个调用了某个对象的 Object.wait
方法的线程会等待另一个线程调用此对象的Object.notify()方法 或 Object.notifyAll()方法。

其实waiting状态并不是一个线程的操作，它体现的是多个线程间的通信，可以理解为多个线程之间的协作关系，多个线程会争取锁，同时相互之间又存在协作关系。就好比在公司里你和你的同事们，你们可能存在晋升时的竞争，但更多时候你们更多是一起合作以完成某些任务。

当多个线程协作时，比如A，B线程，如果A线程在Runnable（可运行）状态中调用了wait()方法那么A线程就进入
了Waiting（无限等待）状态，同时失去了同步锁。假如这个时候B线程获取到了同步锁，在运行状态中调用了notify()方法，那么就会将无限等待的A线程唤醒。注意是唤醒，如果获取到锁对象，那么A线程唤醒后就进入Runnable（可运行）状态；如果没有获取锁对象，那么就进入到Blocked（锁阻塞状态）。

**Waiting 线程状态图**

![image-20201230220746458](https://gitee.com/aduncmj/PictureBed/raw/master/images/20201230220746.png)



#### 补充知识点

到此为止我们已经对线程状态有了基本的认识，想要有更多的了解，详情可以见下图：



> 一条有意思的tips:
>
> 我们在翻阅API的时候会发现Timed Waiting（计时等待） 与 Waiting（无限等待）状态联系还是很紧密的， 比如Waiting（无限等待）状态中wait方法是空参的，而timed waiting（计时等待）中wait方法是带参的。这种带参的方法，其实是一种倒计时操作，相当于我们生活中的小闹钟，我们设定好时间，到时通知，可是如果提前得到（唤醒）通知，那么设定好时间在通知也就显得多此一举了，那么这种设计方案其实是一举两得。如果没有得到（唤醒）通知，那么线程就处于Timed Waiting状态,直到倒计时完毕自动醒来；如果在倒计时期间得到（唤醒）通知，那么线程从Timed Waiting状态立刻唤醒。



### 等待唤醒机制

#### 线程间通信

**概念：**多个线程在处理同一个资源，但是处理的动作（线程的任务）却不相同。

比如：线程A用来生成包子的，线程B用来吃包子的，包子可以理解为同一资源，线程A与线程B处理的动作，一个是生产，一个是消费，那么线程A与线程B之间就存在线程通信问题。

![image-20201230221157713](https://gitee.com/aduncmj/PictureBed/raw/master/images/20201230221157.png)

**为什么要处理线程间通信：**

多个线程并发执行时, 在默认情况下CPU是随机切换线程的，当我们需要多个线程来共同完成一件任务，并且我们希望他们有规律的执行, 那么多线程之间需要一些协调通信，以此来帮我们达到多线程共同操作一份数据。

**如何保证线程间通信有效利用资源：**

多个线程在处理同一个资源，并且任务不同时，需要线程通信来帮助解决线程之间对同一个变量的使用或操作。 就是多个线程在操作同一份数据时， 避免对同一共享变量的争夺。也就是我们需要通过一定的手段使各个线程能有效的利用资源。而这种手段即—— **等待唤醒机制。**

#### 等待唤醒机制

**什么是等待唤醒机制**

这是多个线程间的一种**协作**机制。谈到线程我们经常想到的是线程间的**竞争（race）**，比如去争夺锁，但这并不是故事的全部，线程间也会有协作机制。就好比在公司里你和你的同事们，你们可能存在在晋升时的竞争，但更多时候你们更多是一起合作以完成某些任务。

就是在一个线程进行了规定操作后，就进入等待状态（**wait()**）， 等待其他线程执行完他们的指定代码过后 再将其唤醒（**notify()**）;在有多个线程进行等待时， 如果需要，可以使用 notifyAll()来唤醒所有的等待线程。

wait/notify 就是线程间的一种协作机制。

**等待唤醒中的方法**

等待唤醒机制就是用于解决线程间通信的问题的，使用到的3个方法的含义如下：

1. wait：线程不再活动，不再参与调度，进入 wait set 中，因此不会浪费 CPU 资源，也不会去竞争锁了，这时的线程状态即是 WAITING。它还要等着别的线程执行一个**特别的动作**，也即是“**通知（notify）**”在这个对象上等待的线程从wait set 中释放出来，重新进入到调度队列（ready queue）中
2. notify：则选取所通知对象的 wait set 中的一个线程释放；例如，餐馆有空位置后，等候就餐最久的顾客最先入座。
3. notifyAll：则释放所通知对象的 wait set 上的全部线程。

> 注意：
>
> 哪怕只通知了一个等待的线程，被通知线程也不能立即恢复执行，因为它当初中断的地方是在同步块内，而此刻它已经不持有锁，所以她需要再次尝试去获取锁（很可能面临其它线程的竞争），成功后才能在当初调用 wait 方法之后的地方恢复执行。
>
> 总结如下：
>
> - 如果能获取锁，线程就从 WAITING 状态变成 RUNNABLE 状态；
> - 否则，从 wait set 出来，又进入 entry set，线程就从 WAITING 状态又变成 BLOCKED 状态

**调用wait和notify方法需要注意的细节**

1. wait方法与notify方法必须要由同一个锁对象调用。因为：对应的锁对象可以通过notify唤醒使用同一个锁对象调用的wait方法后的线程。
2. wait方法与notify方法是属于Object类的方法的。因为：锁对象可以是任意对象，而任意对象的所属类都是继承了Object类的。
3. wait方法与notify方法必须要在同步代码块或者是同步函数中使用。因为：必须要通过锁对象调用这2个方法。

#### 生产者与消费者问题

等待唤醒机制其实就是经典的“生产者与消费者”的问题。

就拿生产包子消费包子来说等待唤醒机制如何有效利用资源：

```java
包子铺线程生产包子，吃货线程消费包子。当包子没有时（包子状态为false），吃货线程等待，包子铺线程生产包子（即包子状态为true），并通知吃货线程（解除吃货的等待状态）,因为已经有包子了，那么包子铺线程进入等待状态。接下来，吃货线程能否进一步执行则取决于锁的获取情况。如果吃货获取到锁，那么就执行吃包子动作，包子吃完（包子状态为false），并通知包子铺线程（解除包子铺的等待状态）,吃货线程进入等待。包子铺线程能否进一步执行则取决于锁的获取情况。
```

**代码演示：**

包子资源类：

```java
public class BaoZi {
     String  pier ;
     String  xianer ;
     boolean  flag = false ;//包子资源 是否存在  包子资源状态
}
```

吃货线程类：

```java
public class ChiHuo extends Thread{
    private BaoZi bz;

    public ChiHuo(String name,BaoZi bz){
        super(name);
        this.bz = bz;
    }
    @Override
    public void run() {
        while(true){
            synchronized (bz){
                if(bz.flag == false){//没包子
                    try {
                        bz.wait();
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                }
                System.out.println("吃货正在吃"+bz.pier+bz.xianer+"包子");
                bz.flag = false;
                bz.notify();
            }
        }
    }
}
```

包子铺线程类：

```java
public class BaoZiPu extends Thread {

    private BaoZi bz;

    public BaoZiPu(String name,BaoZi bz){
        super(name);
        this.bz = bz;
    }

    @Override
    public void run() {
        int count = 0;
        //造包子
        while(true){
            //同步
            synchronized (bz){
                if(bz.flag == true){//包子资源  存在
                    try {

                        bz.wait();

                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                }

                // 没有包子  造包子
                System.out.println("包子铺开始做包子");
                if(count%2 == 0){
                    // 冰皮  五仁
                    bz.pier = "冰皮";
                    bz.xianer = "五仁";
                }else{
                    // 薄皮  牛肉大葱
                    bz.pier = "薄皮";
                    bz.xianer = "牛肉大葱";
                }
                count++;

                bz.flag=true;
                System.out.println("包子造好了："+bz.pier+bz.xianer);
                System.out.println("吃货来吃吧");
                //唤醒等待线程 （吃货）
                bz.notify();
            }
        }
    }
}
```

测试类：

```java
public class Demo {
    public static void main(String[] args) {
        //等待唤醒案例
        BaoZi bz = new BaoZi();

        ChiHuo ch = new ChiHuo("吃货",bz);
        BaoZiPu bzp = new BaoZiPu("包子铺",bz);

        ch.start();
        bzp.start();
    }
}
```

执行效果：

```java
包子铺开始做包子
包子造好了：冰皮五仁
吃货来吃吧
吃货正在吃冰皮五仁包子
包子铺开始做包子
包子造好了：薄皮牛肉大葱
吃货来吃吧
吃货正在吃薄皮牛肉大葱包子
包子铺开始做包子
包子造好了：冰皮五仁
吃货来吃吧
吃货正在吃冰皮五仁包子
```

### 线程池

#### 线程池思想概述

我们使用线程的时候就去创建一个线程，这样实现起来非常简便，但是就会有一个问题：

如果并发的线程数量很多，并且每个线程都是执行一个时间很短的任务就结束了，这样频繁创建线程就会大大降低系统的效率，因为频繁创建线程和销毁线程需要时间。

那么有没有一种办法使得线程可以复用，就是执行完一个任务，并不被销毁，而是可以继续执行其他的任务？

在Java中可以通过线程池来达到这样的效果。今天我们就来详细讲解一下Java的线程池。

#### 线程池概念

- **线程池：**其实就是一个容纳多个线程的容器，其中的线程可以反复使用，省去了频繁创建线程对象的操作，无需反复创建线程而消耗过多资源。

由于线程池中有很多操作都是与优化资源相关的，我们在这里就不多赘述。我们通过一张图来了解线程池的工作原理：

![image-20201230221241037](https://gitee.com/aduncmj/PictureBed/raw/master/images/20201230221241.png)

合理利用线程池能够带来三个好处：

1. 降低资源消耗。减少了创建和销毁线程的次数，每个工作线程都可以被重复利用，可执行多个任务。
2. 提高响应速度。当任务到达时，任务可以不需要的等到线程创建就能立即执行。
3. 提高线程的可管理性。可以根据系统的承受能力，调整线程池中工作线线程的数目，防止因为消耗过多的内存，而把服务器累趴下(每个线程需要大约1MB内存，线程开的越多，消耗的内存也就越大，最后死机)。

#### 线程池的使用

Java里面线程池的顶级接口是`java.util.concurrent.Executor`，但是严格意义上讲`Executor`并不是一个线程池，而只是一个执行线程的工具。真正的线程池接口是`java.util.concurrent.ExecutorService`。

要配置一个线程池是比较复杂的，尤其是对于线程池的原理不是很清楚的情况下，很有可能配置的线程池不是较优的，因此在`java.util.concurrent.Executors`线程工厂类里面提供了一些静态工厂，生成一些常用的线程池。官方建议使用Executors工程类来创建线程池对象。

Executors类中有个创建线程池的方法如下：

- `public static ExecutorService newFixedThreadPool(int nThreads)`：返回线程池对象。(创建的是有界线程池,也就是池中的线程个数可以指定最大数量)

获取到了一个线程池ExecutorService 对象，那么怎么使用呢，在这里定义了一个使用线程池对象的方法如下：

- `public Future<?> submit(Runnable task)`:获取线程池中的某一个线程对象，并执行

  > Future接口：用来记录线程任务执行完毕后产生的结果。线程池创建与使用。

使用线程池中线程对象的步骤：

1. 创建线程池对象。
2. 创建Runnable接口子类对象。(task)
3. 提交Runnable接口子类对象。(take task)
4. 关闭线程池(一般不做)。

Runnable实现类代码：

```java
public class MyRunnable implements Runnable {
    @Override
    public void run() {
        System.out.println("我要一个教练");
        try {
            Thread.sleep(2000);
        } catch (InterruptedException e) {
            e.printStackTrace();
        }
        System.out.println("教练来了： " + Thread.currentThread().getName());
        System.out.println("教我游泳,交完后，教练回到了游泳池");
    }
}
```

线程池测试类：

```java
public class ThreadPoolDemo {
    public static void main(String[] args) {
        // 创建线程池对象
        ExecutorService service = Executors.newFixedThreadPool(2);//包含2个线程对象
        // 创建Runnable实例对象
        MyRunnable r = new MyRunnable();

        //自己创建线程对象的方式
        // Thread t = new Thread(r);
        // t.start(); ---> 调用MyRunnable中的run()

        // 从线程池中获取线程对象,然后调用MyRunnable中的run()
        service.submit(r);
        // 再获取个线程对象，调用MyRunnable中的run()
        service.submit(r);
        service.submit(r);
        // 注意：submit方法调用结束后，程序并不终止，是因为线程池控制了线程的关闭。
        // 将使用完的线程又归还到了线程池中
        // 关闭线程池
        //service.shutdown();
    }
}
```



## Lambda表达式

### 函数式编程思想概述

在数学中，**函数**就是有输入量、输出量的一套计算方案，也就是“拿什么东西做什么事情”。相对而言，面向对象过分强调“必须通过对象的形式来做事情”，而函数式思想则尽量忽略面向对象的复杂语法——**强调做什么，而不是以什么形式做**。

面向对象的思想:

	做一件事情,找一个能解决这个事情的对象,调用对象的方法,完成事情.

函数式编程思想:

	只要能获取到结果,谁去做的,怎么做的都不重要,重视的是结果,不重视过程

### 冗余的Runnable代码

**传统写法**

当需要启动一个线程去完成任务时，通常会通过`java.lang.Runnable`接口来定义任务内容，并使用`java.lang.Thread`类来启动该线程。代码如下：

```java
public class Demo01Runnable {
	public static void main(String[] args) {
    	// 匿名内部类
		Runnable task = new Runnable() {
			@Override
			public void run() { // 覆盖重写抽象方法
				System.out.println("多线程任务执行！");
			}
		};
		new Thread(task).start(); // 启动线程
	}
}
```

本着“一切皆对象”的思想，这种做法是无可厚非的：首先创建一个`Runnable`接口的匿名内部类对象来指定任务内容，再将其交给一个线程来启动。

**代码分析**

对于`Runnable`的匿名内部类用法，可以分析出几点内容：

- `Thread`类需要`Runnable`接口作为参数，其中的抽象`run`方法是用来指定线程任务内容的核心；
- 为了指定`run`的方法体，**不得不**需要`Runnable`接口的实现类；
- 为了省去定义一个`RunnableImpl`实现类的麻烦，**不得不**使用匿名内部类；
- 必须覆盖重写抽象`run`方法，所以方法名称、方法参数、方法返回值**不得不**再写一遍，且不能写错；
- 而实际上，**似乎只有方法体才是关键所在**。

### 编程思想转换

**做什么，而不是怎么做**

我们真的希望创建一个匿名内部类对象吗？不。我们只是为了做这件事情而**不得不**创建一个对象。我们真正希望做的事情是：将`run`方法体内的代码传递给`Thread`类知晓。

**传递一段代码**——这才是我们真正的目的。而创建对象只是受限于面向对象语法而不得不采取的一种手段方式。那，有没有更加简单的办法？如果我们将关注点从“怎么做”回归到“做什么”的本质上，就会发现只要能够更好地达到目的，过程与形式其实并不重要。

**生活举例**

当我们需要从北京到上海时，可以选择高铁、汽车、骑行或是徒步。我们的真正目的是到达上海，而如何才能到达上海的形式并不重要，所以我们一直在探索有没有比高铁更好的方式——搭乘飞机。

而现在这种飞机（甚至是飞船）已经诞生：2014年3月Oracle所发布的Java 8（JDK 1.8）中，加入了**Lambda表达式**的重量级新特性，为我们打开了新世界的大门。

### 体验Lambda的更优写法

借助Java 8的全新语法，上述`Runnable`接口的匿名内部类写法可以通过更简单的Lambda表达式达到等效：

```java
public class Demo02LambdaRunnable {
	public static void main(String[] args) {
		new Thread(() -> System.out.println("多线程任务执行！")).start(); // 启动线程
	}
}
```

这段代码和刚才的执行效果是完全一样的，可以在1.8或更高的编译级别下通过。从代码的语义中可以看出：我们启动了一个线程，而线程任务的内容以一种更加简洁的形式被指定。

不再有“不得不创建接口对象”的束缚，不再有“抽象方法覆盖重写”的负担，就是这么简单！

### 回顾匿名内部类

Lambda是怎样击败面向对象的？在上例中，核心代码其实只是如下所示的内容：

```java
() -> System.out.println("多线程任务执行！")
```

为了理解Lambda的语义，我们需要从传统的代码起步。

**使用实现类**

要启动一个线程，需要创建一个`Thread`类的对象并调用`start`方法。而为了指定线程执行的内容，需要调用`Thread`类的构造方法：

- `public Thread(Runnable target)`

为了获取`Runnable`接口的实现对象，可以为该接口定义一个实现类`RunnableImpl`：

```java
public class RunnableImpl implements Runnable {
	@Override
	public void run() {
		System.out.println("多线程任务执行！");
	}
}
```

然后创建该实现类的对象作为`Thread`类的构造参数：

```java
public class Demo03ThreadInitParam {
	public static void main(String[] args) {
		Runnable task = new RunnableImpl();
		new Thread(task).start();
	}
}
```

**使用匿名内部类**

这个`RunnableImpl`类只是为了实现`Runnable`接口而存在的，而且仅被使用了唯一一次，所以使用匿名内部类的语法即可省去该类的单独定义，即匿名内部类：

```java
public class Demo04ThreadNameless {
	public static void main(String[] args) {
		new Thread(new Runnable() {
			@Override
			public void run() {
				System.out.println("多线程任务执行！");
			}
		}).start();
	}
}
```

**匿名内部类的好处与弊端**

一方面，匿名内部类可以帮我们**省去实现类的定义**；另一方面，匿名内部类的语法——**确实太复杂了！**

**语义分析**

仔细分析该代码中的语义，`Runnable`接口只有一个`run`方法的定义：

- `public abstract void run();`

即制定了一种做事情的方案（其实就是一个函数）：

- **无参数**：不需要任何条件即可执行该方案。
- **无返回值**：该方案不产生任何结果。
- **代码块**（方法体）：该方案的具体执行步骤。

同样的语义体现在`Lambda`语法中，要更加简单：

```java
() -> System.out.println("多线程任务执行！")
```

- 前面的一对小括号即`run`方法的参数（无），代表不需要任何条件；
- 中间的一个箭头代表将前面的参数传递给后面的代码；
- 后面的输出语句即业务逻辑代码。

### Lambda标准格式

Lambda省去面向对象的条条框框，格式由**3个部分**组成：

- 一些参数
- 一个箭头
- 一段代码

Lambda表达式的**标准格式**为：

```
(参数类型 参数名称) -> { 代码语句 }
```

格式说明：

- 小括号内的语法与传统方法参数列表一致：无参数则留空；多个参数则用逗号分隔。
- `->`是新引入的语法格式，代表指向动作。
- 大括号内的语法与传统方法体要求基本一致。

**练习：使用Lambda标准格式（无参无返回）**

**题目**

给定一个厨子`Cook`接口，内含唯一的抽象方法`makeFood`，且无参数、无返回值。如下：

```java
public interface Cook {
    void makeFood();
}
```

在下面的代码中，请使用Lambda的**标准格式**调用`invokeCook`方法，打印输出“吃饭啦！”字样：

```java
public class Demo05InvokeCook {
    public static void main(String[] args) {
        // TODO 请在此使用Lambda【标准格式】调用invokeCook方法
    }

    private static void invokeCook(Cook cook) {
        cook.makeFood();
    }
}
```

**解答**

```java
public static void main(String[] args) {
    invokeCook(() -> {
      	System.out.println("吃饭啦！");
    });
}
```

> 备注：小括号代表`Cook`接口`makeFood`抽象方法的参数为空，大括号代表`makeFood`的方法体。

**Lambda的参数和返回值**

```
需求:
    使用数组存储多个Person对象
    对数组中的Person对象使用Arrays的sort方法通过年龄进行升序排序
```

下面举例演示`java.util.Comparator<T>`接口的使用场景代码，其中的抽象方法定义为：

- `public abstract int compare(T o1, T o2);`

当需要对一个对象数组进行排序时，`Arrays.sort`方法需要一个`Comparator`接口实例来指定排序的规则。假设有一个`Person`类，含有`String name`和`int age`两个成员变量：

```java
public class Person { 
    private String name;
    private int age;
    
    // 省略构造器、toString方法与Getter Setter 
}
```

**传统写法**

如果使用传统的代码对`Person[]`数组进行排序，写法如下：

```java
import java.util.Arrays;
import java.util.Comparator;

public class Demo06Comparator {
    public static void main(String[] args) {
      	// 本来年龄乱序的对象数组
        Person[] array = {
        	new Person("古力娜扎", 19),
        	new Person("迪丽热巴", 18),
       		new Person("马尔扎哈", 20) };

      	// 匿名内部类
        Comparator<Person> comp = new Comparator<Person>() {
            @Override
            public int compare(Person o1, Person o2) {
                return o1.getAge() - o2.getAge();
            }
        };
        Arrays.sort(array, comp); // 第二个参数为排序规则，即Comparator接口实例

        for (Person person : array) {
            System.out.println(person);
        }
    }
}
```

这种做法在面向对象的思想中，似乎也是“理所当然”的。其中`Comparator`接口的实例（使用了匿名内部类）代表了“按照年龄从小到大”的排序规则。

**代码分析**

下面我们来搞清楚上述代码真正要做什么事情。

- 为了排序，`Arrays.sort`方法需要排序规则，即`Comparator`接口的实例，抽象方法`compare`是关键；
- 为了指定`compare`的方法体，**不得不**需要`Comparator`接口的实现类；
- 为了省去定义一个`ComparatorImpl`实现类的麻烦，**不得不**使用匿名内部类；
- 必须覆盖重写抽象`compare`方法，所以方法名称、方法参数、方法返回值**不得不**再写一遍，且不能写错；
- 实际上，**只有参数和方法体才是关键**。

**Lambda写法**

```java
import java.util.Arrays;

public class Demo07ComparatorLambda {
    public static void main(String[] args) {
        Person[] array = {
          	new Person("古力娜扎", 19),
          	new Person("迪丽热巴", 18),
          	new Person("马尔扎哈", 20) };

        Arrays.sort(array, (Person a, Person b) -> {
          	return a.getAge() - b.getAge();
        });

        for (Person person : array) {
            System.out.println(person);
        }
    }
}
```

**练习：使用Lambda标准格式（有参有返回）**

**题目**

给定一个计算器`Calculator`接口，内含抽象方法`calc`可以将两个int数字相加得到和值：

```java
public interface Calculator {
    int calc(int a, int b);
}
```

在下面的代码中，请使用Lambda的**标准格式**调用`invokeCalc`方法，完成120和130的相加计算：

```java
public class Demo08InvokeCalc {
    public static void main(String[] args) {
        // TODO 请在此使用Lambda【标准格式】调用invokeCalc方法来计算120+130的结果ß
    }

    private static void invokeCalc(int a, int b, Calculator calculator) {
        int result = calculator.calc(a, b);
        System.out.println("结果是：" + result);
    }
}
```

**解答**

```java
public static void main(String[] args) {
    invokeCalc(120, 130, (int a, int b) -> {
      	return a + b;
    });
}
```

> 备注：小括号代表`Calculator`接口`calc`抽象方法的参数，大括号代表`calc`的方法体。

### Lambda省略格式

**可推导即可省略**

Lambda强调的是“做什么”而不是“怎么做”，所以凡是可以根据上下文推导得知的信息，都可以省略。例如上例还可以使用Lambda的省略写法：

```java
public static void main(String[] args) {
  	invokeCalc(120, 130, (a, b) -> a + b);
}
```

**省略规则**

在Lambda标准格式的基础上，使用省略写法的规则为：

1. 小括号内参数的类型可以省略；
2. 如果小括号内**有且仅有一个参**，则小括号可以省略；
3. 如果大括号内**有且仅有一个语句**，则无论是否有返回值，都可以省略大括号、return关键字及语句分号。

> 备注：掌握这些省略规则后，请对应地回顾本章开头的多线程案例。

**练习：使用Lambda省略格式**

**题目**

仍然使用前文含有唯一`makeFood`抽象方法的厨子`Cook`接口，在下面的代码中，请使用Lambda的**省略格式**调用`invokeCook`方法，打印输出“吃饭啦！”字样：

```java
public class Demo09InvokeCook {
    public static void main(String[] args) {
        // TODO 请在此使用Lambda【省略格式】调用invokeCook方法
    }

    private static void invokeCook(Cook cook) {
        cook.makeFood();
    }
}
```

**解答**

```java
public static void main(String[] args) {
  	invokeCook(() -> System.out.println("吃饭啦！"));
}
```

### Lambda的使用前提



Lambda的语法非常简洁，完全没有面向对象复杂的束缚。但是使用时有几个问题需要特别注意：

1. 使用Lambda必须具有接口，且要求**接口中有且仅有一个抽象方法**。
   无论是JDK内置的`Runnable`、`Comparator`接口还是自定义的接口，只有当接口中的抽象方法存在且唯一时，才可以使用Lambda。
2. 使用Lambda必须具有**上下文推断**。
   也就是方法的参数或局部变量类型必须为Lambda对应的接口类型，才能使用Lambda作为该接口的实例。

> 备注：有且仅有一个抽象方法的接口，称为“**函数式接口**”。






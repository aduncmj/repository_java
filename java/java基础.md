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
    - [接口](#接口)
    - [多态](#多态)
    - [内部类](#内部类)
        - [匿名内部类](#匿名内部类)
    - [异常](#异常)
    - [多进程](#多进程)
    - [String](#string)
    - [集合](#集合)

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

##强制类型转换
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

##对象包装器和自动装箱

![对象包装器](https://upload-images.jianshu.io/upload_images/1732196-9e83307233726e9f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![自动装箱](https://upload-images.jianshu.io/upload_images/1732196-dae48e7572a01f39.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![自动拆箱](https://upload-images.jianshu.io/upload_images/1732196-b3a16de73444c9f2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![编译器认可](https://upload-images.jianshu.io/upload_images/1732196-c977356320486c49.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)





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



## 多进程
进程：是一个正在执行中的程序。

每一个进程执行都有一个执行顺序。该顺序是一个执行路径，或者叫一个控制单元。

线程：就是进程中的一个独立的控制单元。线程在控制着进程的执行。

一个进程中至少有一个线程。

Java VM  启动的时候会有一个进程java.exe.

该进程中至少一个线程负责java程序的执行。而且这个线程运行的代码存在于main方法中。该线程称之为**主线程**。

> 扩展：其实更细节说明jvm，jvm启动不止一个线程，还有负责垃圾回收机制的线程。


1,如何在自定义的代码中，自定义一个线程呢？

通过对api的查找，java已经提供了对线程这类事物的描述。就Thread类。

创建线程的**第一种方式**：继承Thread类。
步骤：
1，定义类继承Thread。
2，复写Thread类中的run方法。
目的：将自定义代码存储在run方法。让线程运行。
3，调用线程的start方法，
该方法两个作用：启动线程，调用run方法。

发现运行结果每一次都不同。因为多个线程都获取cpu的执行权。cpu执行到谁，谁就运行。明确一点，在某一个时刻，只能有一个程序在运行。(多核除外)cpu在做着快速的切换，以达到看上去是同时运行的效果。我们可以形象把多线程的运行行为在互相抢夺cpu的执行权。
这就是多线程的一个特性：随机性。谁抢到谁执行，至于执行多长，cpu说的算。



为什么要覆盖run方法呢？

Thread类用于描述线程。
该类就定义了一个功能，用于存储线程要运行的代码。该存储功能就是run方法。

也就是说Thread类中的run方法，用于存储线程要运行的代码。

```

class Demo extends Thread
{
	public void run()
	{
		for(int x=0; x<60; x++)
			System.out.println("demo run----"+x);
	}
}





class ThreadDemo 
{
	public static void main(String[] args) 
	{
		//for(int x=0; x<4000; x++)
		//System.out.println("Hello World!");

		Demo d = new Demo();//创建好一个线程。
		//d.start();//开启线程并执行该线程的run方法。
		d.run();//仅仅是对象调用方法。而线程创建了，并没有运行。

		
		for(int x=0; x<60; x++)
			System.out.println("Hello World!--"+x);
		

	

	
	}
}
```

线程都有自己默认的名称。
Thread-编号 该编号从0开始。

static Thread currentThread():获取当前线程对象。
getName(): 获取线程名称。

设置线程名称：setName或者构造函数。

创建线程的**第二种方式**：实现Runable接口

步骤：
1，定义类实现Runnable接口
2，覆盖Runnable接口中的run方法。
将线程要运行的代码存放在该run方法中。
3，通过Thread类建立线程对象。
4，将Runnable接口的子类对象作为实际参数传递给Thread类的构造函数。
	为什么要将Runnable接口的子类对象传递给Thread的构造函数。
	因为，自定义的run方法所属的对象是Runnable接口的子类对象。
	所以要让线程去指定指定对象的run方法。就必须明确该run方法所属对象。
5，调用Thread类的start方法开启线程并调用Runnable接口子类的run方法。


实现方式和继承方式有什么区别呢？

实现方式好处：避免了单继承的局限性。
在定义线程时，建立使用实现方式。

两种方式区别：
继承Thread:线程代码存放Thread子类run方法中。
实现Runnable，线程代码存在接口的子类的run方法。

多线程的运行出现了安全问题。

问题的原因：
	当多条语句在操作同一个线程共享数据时，一个线程对多条语句只执行了一部分，还没有执行完，
	另一个线程参与进来执行。导致共享数据的错误。

解决办法：
	对多条操作共享数据的语句，只能让一个线程都执行完。在执行过程中，其他线程不可以参与执行。



Java对于多线程的安全问题提供了专业的解决方式。

就是同步代码块。

synchronized(对象)
{
	需要被同步的代码

}
对象如同锁。持有锁的线程可以在同步中执行。
没有持有锁的线程即使获取cpu的执行权，也进不去，因为没有获取锁。

火车上的卫生间---经典。

同步的前提：
1，必须要有两个或者两个以上的线程。
2，必须是多个线程使用同一个锁。

必须保证同步中只能有一个线程在运行。


好处：解决了多线程的安全问题。

弊端：多个线程需要判断锁，较为消耗资源，

如何找问题：
1，明确哪些代码是多线程运行代码。
2，明确共享数据。
3，明确多线程运行代码中哪些语句是操作共享数据的。

同步函数用的是哪一个锁呢？
函数需要被对象调用。那么函数都有一个所属对象引用。就是this。
所以同步函数使用的锁是this。

通过该程序进行验证。

使用两个线程来买票。
一个线程在同步代码块中。
一个线程在同步函数中。
都在执行买票动作。

如果同步函数被静态修饰后，使用的锁是什么呢？

通过验证，发现不在是this。因为静态方法中也不可以定义this。

静态进内存是，内存中没有本类对象，但是一定有该类对应的字节码文件对象。
类名.class  该对象的类型是Class


静态的同步方法，使用的锁是该方法所在类的字节码文件对象。 类名.class

线程间通讯：
其实就是多个线程在操作同一个资源，
但是操作的动作不同。

wait:
notify();
notifyAll();

都使用在同步中，因为要对持有监视器(锁)的线程操作。
所以要使用在同步中，因为只有同步才具有锁。

为什么这些操作线程的方法要定义Object类中呢？
因为这些方法在操作同步中线程时，都必须要标识它们所操作线程只有的锁，
只有同一个锁上的被等待线程，可以被同一个锁上notify唤醒。
不可以对不同锁中的线程进行唤醒。

也就是说，等待和唤醒必须是同一个锁。

而锁可以是任意对象，所以可以被任意对象调用的方法定义Object类中。

JDK1.5 中提供了多线程升级解决方案。
将同步Synchronized替换成现实Lock操作。
将Object中的wait，notify notifyAll，替换了Condition对象。
该对象可以Lock锁 进行获取。
该示例中，实现了本方只唤醒对方操作。

Lock:替代了Synchronized
	lock 
	unlock
	newCondition()

Condition：替代了Object wait notify notifyAll
	await();
	signal();
	signalAll();

stop方法已经过时。

如何停止线程？
只有一种，run方法结束。
开启多线程运行，运行代码通常是循环结构。

只要控制住循环，就可以让run方法结束，也就是线程结束。


特殊情况：
当线程处于了冻结状态。
就不会读取到标记。那么线程就不会结束。

当没有指定的方式让冻结的线程恢复到运行状态是，这时需要对冻结进行清除。
强制让线程恢复到运行状态中来。这样就可以操作标记让线程结束。

Thread类提供该方法 interrupt();

join:
当A线程执行到了B线程的.join()方法时，A就会等待。等B线程都执行完，A才会执行。

join可以用来临时加入线程执行。

## String

```
class StringDemo 
{
	public static void main(String[] args) 
	{
		/*
		String s1 = "abc";//s1是一个类类型变量， "abc"是一个对象。
						//字符串最大特点：一旦被初始化就不可以被改变。

		String s2 = new String("abc");

		//s1和s2有什么区别？
		//s1在内存中有一个对象。
		//s2在内存中有两个对象。
		




		System.out.println(s1==s2);
		System.out.println(s1.equals(s2));//String类复写了Object类中equals方法，
										//该方法用于判断字符串是否相同。

		*/

		String s = "abcde";
		method_1(s);
	}

```

String类适用于描述字符串事物。
那么它就提供了多个方法对字符串进行操作。

常见的操作有哪些？
"abcd"

1，获取。
	1.1 字符串中的包含的字符数，也就是字符串的长度。
		int length():获取长度。
	1.2 根据位置获取位置上某个字符。
		char charAt(int index):
	1.3 根据字符获取该字符在字符串中位置。
		int indexOf(int ch):返回的是ch在字符串中第一次出现的位置。
		int indexOf(int ch, int fromIndex) :从fromIndex指定位置开始，获取ch在字符串中出现的位置。

		int indexOf(String str):返回的是str在字符串中第一次出现的位置。
		int indexOf(String str, int fromIndex) :从fromIndex指定位置开始，获取str在字符串中出现的位置。
	
		int lastIndexOf(int ch) ：


​		
2，判断。
​	2.1 字符串中是否包含某一个子串。
​		boolean contains(str):
​		特殊之处：indexOf(str):可以索引str第一次出现位置，如果返回-1.表示该str不在字符串中存在。
​				所以，也可以用于对指定判断是否包含。
​				if(str.indexOf("aa")!=-1)

				而且该方法即可以判断，有可以获取出现的位置。
	
	2.2 字符中是否有内容。
		boolean isEmpty(): 原理就是判断长度是否为0. 
	2.3 字符串是否是以指定内容开头。
		boolean startsWith(str);
	2.4 字符串是否是以指定内容结尾。
		boolean endsWith(str);
	2.5 判断字符串内容是否相同。复写了Object类中的equals方法。
		boolean equals(str);
	2.6 判断内容是否相同，并忽略大小写。
		boolean equalsIgnoreCase();

3，转换。
	3.1 将字符数组转成字符串。
		构造函数：String(char[])
				  String(char[],offset,count):将字符数组中的一部分转成字符串。

		静态方法：
				static String copyValueOf(char[]);
				static String copyValueOf(char[] data, int offset, int count) 
	
				static String valueOf(char[]):


​		
​	3.2 将字符串转成字符数组。**
​		char[] toCharArray():
​	
​	3.3 将字节数组转成字符串。
​			String(byte[])
​			String(byte[],offset,count):将字节数组中的一部分转成字符串。
​	
​	3.4 将字符串转成字节数组。
​			byte[]  getBytes():
​	3.5 将基本数据类型转成字符串。
​		static String valueOf(int)
​		static String valueOf(double)
​	
​		//3+"";//String.valueOf(3);
​	
		特殊：字符串和字节数组在转换过程中，是可以指定编码表的。

4，替换
	String replace(oldchar,newchar);

5，切割
	String[] split(regex);

6，子串。获取字符串中的一部分。
	String substring(begin);
	String substring(begin,end);

7，转换，去除空格，比较。
	7.1 将字符串转成大写或则小写。
		 String toUpperCase();
		 String toLowerCase();

	7.2 将字符串两端的多个空格去除。
		String trim();
	
	7.3 对两个字符串进行自然顺序的比较。
		int compareTo(string);

StringBuffer是字符串缓冲区。

是一个容器。
特点：
1，长度是可变化的。
2，可以字节操作多个数据类型。
3，最终会通过toString方法变成字符串。



C create U update R read D delete

1，存储。
	StringBuffer append():将指定数据作为参数添加到已有数据结尾处。
	StringBuffer insert(index,数据):可以将数据插入到指定index位置。


2，删除。
	StringBuffer delete(start,end):删除缓冲区中的数据，包含start，不包含end。
	StringBuffer deleteCharAt(index):删除指定位置的字符。
	
3，获取。
	char charAt(int index) 
	int indexOf(String str) 
	int lastIndexOf(String str) 
	int length() 
	String substring(int start, int end) 

4，修改。
	StringBuffer replace(start,end,string);
	void setCharAt(int index, char ch) ;


5，反转。
	StringBuffer reverse();

6，
	将缓冲区中指定数据存储到指定字符数组中。
	void getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin) 


JDK1.5 版本之后出现了StringBuilder.

StringBuffer是线程同步。
StringBuilder是线程不同步。

以后开发，建议使用StringBuilder

升级三个因素：
1，提高效率。
2，简化书写。
3，提高安全性。

基本数据类型对象包装类。

byte	Byte
short	short
int		Integer
long	Long
boolean Boolean
float	Float
double	Double
char	Character



基本数据类型对象包装类的最常见作用，
就是用于基本数据类型和字符串类型之间做转换

基本数据类型转成字符串。

	基本数据类型+""
	
	基本数据类型.toString(基本数据类型值);
	
	如： Integer.toString(34);//将34整数变成"34";


字符串转成基本数据类型。

	xxx a = Xxx.parseXxx(String);
	
	int a = Integer.parseInt("123");
	
	double b = Double.parseDouble("12.23");
	
	boolean b = Boolean.parseBoolean("true");
	
	Integer i = new Integer("123");
	
	int num = i.intValue();


​	


十进制转成其他进制。
	toBinaryString();
	toHexString();
	toOctalString();


其他进制转成十进制。
	parseInt(string,radix);

## 集合

枚举就是Vector特有的取出方式。
发现枚举和迭代器很像。
其实枚举和迭代是一样的。

因为枚举的名称以及方法的名称都过长。
所以被迭代器取代了。
枚举郁郁而终了。

Collection定义了集合框架的共性功能。
1，添加
	add(e);
	addAll(collection);

2，删除
	remove(e);
	removeAll(collection);
	clear();

3，判断。
	contains(e);
	isEmpty();

4，获取
	iterator();
	size();

5，获取交集。
	retainAll();

6，集合变数组。
	toArray();



1，add方法的参数类型是Object。以便于接收任意类型对象。

2，集合中存储的都是对象的引用(地址)


什么是迭代器呢？
其实就是集合的取出元素的方式。
如同抓娃娃游戏机中的夹子。

迭代器是取出方式，会直接访问集合中的元素。
所以将迭代器通过内部类的形式来进行描述。
通过容器的iterator()方法获取该内部类的对象。

|--Set：元素是无序(存入和取出的顺序不一定一致)，元素不可以重复。、
	|--HashSet:底层数据结构是哈希表。是线程不安全的。不同步。
			HashSet是如何保证元素唯一性的呢？
			是通过元素的两个方法，hashCode和equals来完成。
			如果元素的HashCode值相同，才会判断equals是否为true。
			如果元素的hashcode值不同，不会调用equals。

			注意,对于判断元素是否存在，以及删除等操作，依赖的方法是元素的hashcode和equals方法。


	|--TreeSet：

Set集合的功能和Collection是一致的。

LinkedList:特有方法：
addFirst();
addLast();

getFirst();
getLast();
获取元素，但不删除元素。如果集合中没有元素，会出现NoSuchElementException

removeFirst();
removeLast();
获取元素，但是元素被删除。如果集合中没有元素，会出现NoSuchElementException


在JDK1.6出现了替代方法。

offerFirst();
offerLast();


peekFirst();
peekLast();
获取元素，但不删除元素。如果集合中没有元素，会返回null。

pollFirst();
pollLast();
获取元素，但是元素被删除。如果集合中没有元素，会返回null。


Collection
	|--List:元素是有序的，元素可以重复。因为该集合体系有索引。
		|--ArrayList:底层的数据结构使用的是数组结构。特点：查询速度很快。但是增删稍慢。线程不同步。
		|--LinkedList:底层使用的链表数据结构。特点：增删速度很快，查询稍慢。线程不同步。
		|--Vector:底层是数组数据结构。线程同步。被ArrayList替代了。因为效率低。


	|--Set：元素是无序，元素不可以重复。、


List：
	特有方法。凡是可以操作角标的方法都是该体系特有的方法。

增
	add(index,element);
	addAll(index,Collection);

删
	remove(index);

改
	set(index,element);
查
	get(index):
	subList(from,to);
	listIterator();
	int indexOf(obj):获取指定元素的位置。
	ListIterator listIterator();





List集合特有的迭代器。ListIterator是Iterator的子接口。

在迭代时，不可以通过集合对象的方法操作集合中的元素。
因为会发生ConcurrentModificationException异常。

所以，在迭代器时，只能用迭代器的放过操作元素，可是Iterator方法是有限的，
只能对元素进行判断，取出，删除的操作，
如果想要其他的操作如添加，修改等，就需要使用其子接口，ListIterator。

该接口只能通过List集合的listIterator方法获取。


Set:无序，不可以重复元素。
	|--HashSet：数据结构是哈希表。线程是非同步的。
				保证元素唯一性的原理：判断元素的hashCode值是否相同。
				如果相同，还会继续判断元素的equals方法，是否为true。

	|--TreeSet：可以对Set集合中的元素进行排序。
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

泛型：JDK1.5版本以后出现新特性。用于解决安全问题，是一个类型安全机制。

好处
1.将运行时期出现问题ClassCastException，转移到了编译时期。，
	方便于程序员解决问题。让运行时问题减少，安全。，

2，避免了强制转换麻烦。


泛型格式：通过<>来定义要操作的引用数据类型。

在使用java提供的对象时，什么时候写泛型呢？

通常在集合框架中很常见，
只要见到<>就要定义泛型。

其实<> 就是用来接收类型的。

当使用集合时，将集合中要存储的数据类型作为参数传递到<>中即可。

当元素自身不具备比较性，或者具备的比较性不是所需要的。
这时需要让容器自身具备比较性。
定义了比较器，将比较器对象作为参数传递给TreeSet集合的构造函数。

当两种排序都存在时，以比较器为主。

定义一个类，实现Comparator接口，覆盖compare方法。

//泛型类定义的泛型，在整个类中有效。如果被方法使用，
//那么泛型类的对象明确要操作的具体类型后，所有要操作的类型就已经固定了。
//
//为了让不同方法可以操作不同类型，而且类型还不确定。
//那么可以将泛型定义在方法上。


/*
特殊之处：
静态方法不可以访问类上定义的泛型。
如果静态方法操作的应用数据类型不确定，可以将泛型定义在方法上。

//泛型类。
/*
什么时候定义泛型类？
当类中要操作的引用数据类型不确定的时候，
早期定义Object来完成扩展。
现在定义泛型来完成扩展。
*/

? 通配符。也可以理解为占位符。
泛型的限定；
？ extends E: 可以接收E类型或者E的子类型。上限。
？ super E: 可以接收E类型或者E的父类型。下限

Map集合：该集合存储键值对。一对一对往里存。而且要保证键的唯一性。
	1，添加。
		put(K key, V value) 
		putAll(Map<? extends K,? extends V> m) 

	2，删除。
		clear() 
		remove(Object key) 
	
	3，判断。
		containsValue(Object value) 
		containsKey(Object key) 
		isEmpty() 


	4，获取。
		get(Object key) 
		size() 
		values() 
	
		entrySet() 
		keySet() 

Map
	|--Hashtable:底层是哈希表数据结构，不可以存入null键null值。该集合是线程同步的。jdk1.0.效率低。
	|--HashMap：底层是哈希表数据结构，允许使用 null 值和 null 键，该集合是不同步的。将hashtable替代，jdk1.2.效率高。
	|--TreeMap：底层是二叉树数据结构。线程不同步。可以用于给map集合中的键进行排序。


和Set很像。
其实大家，Set底层就是使用了Map集合。

map集合的两种取出方式：
1，Set<k> keySet：将map中所有的键存入到Set集合。因为set具备迭代器。
	所有可以迭代方式取出所有的键，在根据get方法。获取每一个键对应的值。
		

	Map集合的取出原理：将map集合转成set集合。在通过迭代器取出。


2，Set<Map.Entry<k,v>> entrySet：将map集合中的映射关系存入到了set集合中，
				而这个关系的数据类型就是：Map.Entry

				Entry其实就是Map中的一个static内部接口。
				为什么要定义在内部呢？
				因为只有有了Map集合，有了键值对，才会有键值的映射关系。
				关系属于Map集合中的一个内部事物。
				而且该事物在直接访问Map集合中的元素。

map扩展知识。

map集合被使用是因为具备映射关系。

"yureban"   Student("01" "zhangsan");

"yureban" Student("02" "lisi");

"jiuyeban" "01" "wangwu";
"jiuyeban" "02" "zhaoliu";

一个学校有多个教室。每一个教室都有名称。

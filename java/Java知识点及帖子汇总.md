<!-- TOC -->

- [帖子](#帖子)
- [检查对象是否相等](#检查对象是否相等)
- [初始化和类装载](#初始化和类装载)
- [从控制台读取数据：](#从控制台读取数据)
- [文件的输入和输出：](#文件的输入和输出)
- [随机数的产生](#随机数的产生)
    - [System.currentTimeMilli()](#systemcurrenttimemilli)
    - [random方法](#random方法)
    - [java.util.Random类](#javautilrandom类)
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
- [其他](#其他)
    - [运算符和表达式](#运算符和表达式)
    - [命令和参数](#命令和参数)
    - [数据存储位置](#数据存储位置)
    - [基本数据类型和引用数据类型的存储位置](#基本数据类型和引用数据类型的存储位置)
    - [作用域](#作用域)
    - [代码重构](#代码重构)
    - [重定向和管道](#重定向和管道)

<!-- /TOC -->

# 帖子

- **Java4android**

[https://study.163.com/course/courseMain.htm?courseId=201001&_trace_c_p_k2_=068513fdaaf74a11af8d33da5cca277f](https://study.163.com/course/courseMain.htm?courseId=201001&_trace_c_p_k2_=068513fdaaf74a11af8d33da5cca277f)

- **hashcode（）和equals（）的作用、区别、联系**
  

[https://www.cnblogs.com/keyi/p/7119825.html](https://www.cnblogs.com/keyi/p/7119825.html)

- **java中equals和“==”的区别**

[https://www.cnblogs.com/smyhvae/p/3929585.html](https://www.cnblogs.com/smyhvae/p/3929585.html)

- **java中基本数据类型和引用数据类型的存储位置**

[https://blog.csdn.net/qq_36596145/article/details/76300922](https://blog.csdn.net/qq_36596145/article/details/76300922)

- **java中system.out.printf()所支持的格式化字符串汇总**

[(https://blog.csdn.net/xhw035/article/details/52433903)](https://blog.csdn.net/xhw035/article/details/52433903)



# 检查对象是否相等
---
![](https://upload-images.jianshu.io/upload_images/1732196-61de5362c99953f0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-00f595897e2cc9d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-566ebc5412a7ba91.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-7260f24182dcfac5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


# 初始化和类装载
---
在许多传统语言里，程序都是作为启动过程的一部分一次性载入的。随后进行的是初始化，再是正式执行程序。在这些语言中，必须对初始化过程进行慎重的控制，保证 static数据的初始化不会带来麻烦。比如在一个static 数据获得初始化之前，就有另一个 static数据希望它是一个有效值，那么在 C++中就会造成问题。
Java 则没有这样的问题，因为它采用了不同的装载方法。由于 Java 中的一切东西都是对象，所以许多活动变得更加简单，这个问题便是其中的一例。正如下一章会讲到的那样，每个对象的代码都存在于独立的文件中。除非真的需要代码，否则那个文件是不会载入的。通常，我们可认为除非那个类的一个对象构造完毕，否则代码不会真的载入。由于static 方法存在一些细微的歧义，所以也能认为“类代码在首次使用的时候载

**继承初始化**

![](https://upload-images.jianshu.io/upload_images/1732196-8c6100a8d2aea0bd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/1732196-e22a22d1323ae04d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

对Beetle 运行Java 时，发生的第一件事情是装载程序到外面找到那个类。在装载过程中，装载程序注意它有一个基础类（即extends 关键字要表达的意思），所以随之将其载入。无论是否准备生成那个基础类的一个对象，这个过程都会发生（请试着将对象的创建代码当作注释标注出来，自己去证实）。
若基础类含有另一个基础类，则另一个基础类随即也会载入，以此类推。接下来，会在根基础类（此时是Insect）执行 static 初始化，再在下一个衍生类执行，以此类推。保证这个顺序是非常关键的，因为衍生类的初始化可能要依赖于对基础类成员的正确初始化。此时，必要的类已全部装载完毕，所以能够创建对象。首先，这个对象中的所有基本数据类型都会设成它们的默认值，而将对象句柄设为null。随后会调用基础类构建器。在这种情况下，调用是自动进行的。但也完全可以用super 来自行指定构建器调用（就象在Beetle()构建器中的第一个操作一样）。基础类的构建采用与衍生类构建器完全相同的处理过程。基础顺构建器完成以后，实例变量会按本来的顺序得以初始化。最后，执行构建器剩余的主体部分。

常用API

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

# 随机数的产生
---
> Java产生随机数的方法主要有三种System.currentTimeMilli()、random方法、Random类。

## System.currentTimeMilli()

currentTimeMilli()方法返回从1970年1月1日0时0分0秒到现在的一个long型的毫秒数，将其返回值取余后可得到所需范围内的随机数。

## random方法

random方法是Math类里的一个方法，通过Math.random()可以获得0.0到1.0间的double型随机数，但不包括1.0。

尽管random方法产生的随机数范围比较小，但我们可以将产生的随机值乘以一个数，这样我们既可以获得更大范围的随机数。

我们还可以结合造型来获得所需范围的随机整数。

## java.util.Random类

![](https://upload-images.jianshu.io/upload_images/1732196-0604c1f6bd997998.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

利用这种方法其比较方便。如可以利用提供的关键字，让程序返回一个随机的整数(采用int nextInt(10))等等。不过其返回控制要比Random方法困难一点。如现在需要系统提供一个10到50之间的随机奇数， 利用这个Random类就无法完成。也就是说，利用这个Random类来生成随机数，其只能够控制上限，而不能够控制下限。换一句话说，其可以指定最大的随机数范围，而不能够指定最小的随机数范围。所以，在灵活性上，其比Random方法要稍微差一点。



# 常用API



## Object类

---
> Java.lang.Object类为类层次结构的根，是所有类的父类。所有对象，包括数组，都实现这个类的方法。

### toString()方法

    public String toString()

 Object 类的 toString（） 方法返回一个字符串，该字符串由类名（对象是该类的一个实例）、at 标记符“@”和此对象哈希码（对象在JVM虚拟出来的内存地址，为整数。不是实际物理内存地址。）的无符号十六进制表示组成。如：[aduncmj.java.practice.toString@60f82f98](mailto:aduncmj.java.practice.toString@60f82f98)。

  但我们可以通过重写toString（）方法来输出对象属性信息，而且通常都需要这么做。

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

### Equals和“==”的比较

**== 的作用：**

　　基本类型：比较的就是值是否相同

　　引用类型：比较的就是地址值是否相同

**equals 的作用:**

　　引用类型：默认情况下，比较的是地址值。

> 注：不过，我们可以根据情况自己重写该方法。一般重写都是自动生成，比较对象的成员变量值是否相同。对于复合数据类型之间进行equals比较，在没有覆写equals方法的情况下，他们之间的比较还是内存中的存放位置的地址值，跟双等号（==）的结果相同。


## Arrays类
---
> java.util.Arrays类包含了许多用于操作数组（比如排序和搜索）的静态方法，是JDK提供的专门用于操作数组的工具类，位于java.util包中，它继承于Object类。

### binarySearch方法
    public static int binarySearch(type[] array ,type key)

通过binarySearch方法能对排序好的各种类型的数组进行二分查找法操作。注意必须事先对数组array进行排序，否则结果不确定。该方法返回待搜索值的索引。

### copyOf方法
    public static type[] copyOf(type[] original,type newLength)

  该方法可复制指定的数组，截取或填充用零(如有必要)，以使副本具有指定的长度。

### fill方法
    public static void fill(type[] a, type val)

  指定的type类型值给指定的数组的每个元素。

### hashCode方法
    public static int hashCode(type[] a)

  返回基于指定数组的内容的哈希码。

### sort方法
    public static void sort(type[] a)

  指定的int型数组排序按数字升序顺序。

### toString 方法
    public static String toString(type[] a)

  返回指定的type数组内容的字符串表示形式。该字符串表示形式由数组的元素，括在方括号(“[]”)的列表。相邻元素由字符分隔“，”(逗号后面有一个空格)。




























# 其他
---

## 运算符和表达式

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-4d4aad5ee066428f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
**&（逻辑与）和&&（短路与）的区别:**
相同点：&与&&两边的算子都为boolean型，且结果也为boolean; 
不同点：&两边的算子都必须执行；&&若左边为false，则右边短路不予执行，若左边为true,右边还要执行。

**|（逻辑或）和 ||（短路或）的区别：**
相同点：两边的算子都为boolean型，且结果也为boolean; 
不同点：|两边的算子都必须执行；||若左边为true，则右边短路不予执行，若左边为false,右边还要执行。


## 命令和参数


![图片.png](https://upload-images.jianshu.io/upload_images/1732196-e9598dd5305990e2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![图片.png](https://upload-images.jianshu.io/upload_images/1732196-af5f52792f99147d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


## 数据存储位置


程序运行时，我们最好对数据保存到什么地方做到心中有数。特别要注意的是内存的分配。有六个地方都可以保存数据： 
(1) 寄存器。这是最快的保存区域，因为它位于和其他所有保存方式不同的地方：处理器内部。然而，寄存器的数量十分有限，所以寄存器是根据需要由编译器分配。我们对此没有直接的控制权，也不可能在自己的程序里找到寄存器存在的任何踪迹。 

(2) 堆栈。驻留于常规RAM（随机访问存储器）区域，但可通过它的“堆栈指针”获得处理的直接支持。堆栈指针若向下移，会创建新的内存；若向上移，则会释放那些内存。这是一种特别快、特别有效的数据保存方式，仅次于寄存器。创建程序时，Java编译器必须准确地知道堆栈内保存的所有数据的“长度”以及“存在时间”。这是由于它必须生成相应的代码，以便向上和向下移动指针。这一限制无疑影响了程序的灵活性，所以尽管有些Java数据要保存在堆栈里——特别是对象句柄，但Java对象并不放到其中。 

(3) 堆。一种常规用途的内存池（也在RAM区域），其中保存了Java对象。和堆栈不同，“内存堆”或“堆”（Heap）最吸引人的地方在于编译器不必知道要从堆里分配多少存储空间，也不必知道存储的数据要在堆里停留多长的时间。因此，用堆保存数据时会得到更大的灵活性。要求创建一个对象时，只需用new命令编制相关的代码即可。执行这些代码时，会在堆里自动进行数据的保存。当然，为达到这种灵活性，必然会付出一定的代价：在堆里分配存储空间时会花掉更长的时间！ 

(4) 静态存储。这儿的“静态”（Static）是指“位于固定位置”（尽管也在RAM里）。程序运行期间，静态存储的数据将随时等候调用。可用static关键字指出一个对象的特定元素是静态的。但Java对象本身永远都不会置入静态存储空间。 

(5) 常数存储。常数值通常直接置于程序代码内部。这样做是安全的，因为它们永远都不会改变。有的常数需要严格地保护，所以可考虑将它们置入只读存储器（ROM）。 

(6) 非RAM存储。若数据完全独立于一个程序之外，则程序不运行时仍可存在，并在程序的控制范围之外。其中两个最主要的例子便是“流式对象”和“固定对象”。对于流式对象，对象会变成字节流，通常会发给另一台机器。而对于固定对象，对象保存在磁盘中。即使程序中止运行，它们仍可保持自己的状态不变。对于这些类型的数据存储，一个特别有用的技巧就是它们能存在于其他媒体中。一旦需要，甚至能将它们恢复成普通的、基于RAM的对象。Java 1.1提供了对Lightweight persistence的支持。未来的版本甚至可能提供更完整的方案。

## 基本数据类型和引用数据类型的存储位置
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















 



 
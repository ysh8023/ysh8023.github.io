---
title: NO.08 Java基础学习&心得体会
date: 2022-04-17 21:35:45 +0800
categories: [Java学习]
tags: [Java学习历程记录]
pin: true
author: 杨圣僧

toc: true
comments: true
typora-root-url: ../../ysh8023.github.io
math: false
mermaid: true



typora-copy-images-to: ..\assets\blog_res\${filename}-img
---





# NO.08 Java基础学习&心得体会



## 一、字符串

### 1、API

**API** (**A**pplication **P**rogramming **I**nterface) ：应用程序编程接口

厂商提供给应用程序编程的接口，大家把这些类称为 API

**Java API ：**指的就是 JDK 中提供的各种功能的 Java类

### 2、String

#### **①、String 概述**

String 类在 **java.lang**（核心包） 包下，所以使用的时候不需要导包

**String** 类代表**字符串**，Java 程序中的所有字符串文字（例如“abc”）都被实现为此类的实例

也就是说，**Java 程序中所有的双引号字符串，都是 String 类的对象**

**字符串不可变，它们的值在创建后不能被更改**

#### **②、String 常见构造方法**

**方法名** 																	**说明**

public String() 									    创建一个空白字符串对象，不含有任何内容

public String(char[] chs) 					   根据字符数组的内容，来创建字符串对象

public String(String original) 				根据传入的字符串内容，来创建字符串对象

String s = “abc”; 									  直接赋值的方式创建字符串对象，内容就是abc

#### **③、==创建字符串对象的区别对比==**

1️⃣以**“ ”**方式给出的字符串，只要字符序列相同(顺序和大小写)，无论在程序代码中出现几次，JVM 都只会建立一个 String 对象，并在字符串常量池中维护

⚫ 字符串常量池（JDK7后在堆内存）：当使用双引号创建字符串对象的时候，系统会检查该字符串是否在字符串常量池中存在

​					不存在：创建															存在：不会重新创建，而是直接复用

2️⃣通过 new 创建的字符串对象，每一次 new 都会申请一个内存空间，虽然内容相同，但是地址值不同

💨**结论：**<u>双引号创建的字符串对象，在字符串常量池中存储，通过构造方法创建的字符串对象，在堆内存中存储</u>

#### **④、String字符串的特点**

⚫ Java 程序中所有的双引号字符串，都是 String 类的对象

⚫ 字符串不可变，它们的值在创建后不能被更改

⚫ 虽然 String 的值是不可变的，但是它们可以被共享。调用String的任意成员方法，这个String对象的内容都不会发生变化。最多返回值是变化后的结果

![image-20220707103724620](/assets/blog_res/2022-04-17-JavaEEBase-NO.8-img/image-20220707103724620.png)



#### **⑤、String常见面试题**

⚫ 问题：下列代码的运行结果是？

![image-20220705102122980](/assets/blog_res/2022-04-17-JavaEEBase-NO.8-img/image-20220705102122980.png)

![image-20220705102139702](/assets/blog_res/2022-04-17-JavaEEBase-NO.8-img/image-20220705102139702.png)

![image-20220705102154846](/assets/blog_res/2022-04-17-JavaEEBase-NO.8-img/image-20220705102154846.png)

![image-20220705102223830](/assets/blog_res/2022-04-17-JavaEEBase-NO.8-img/image-20220705102223830.png)

#### **⑥、字符串的比较**

1️⃣使用 **==** 做比较

⚫ 基本类型：比较的是**数据值**是否相同

⚫ 引用类型：比较的是**地址值**是否相同

2️⃣字符串是对象，它比较内容是否相同，是通过一个方法来实现的，这个方法叫：**equals()**

⚫ public boolean **equals(Object anObject)**：将此字符串与指定对象进行比较。由于我们比较的是字符串

对象，所以参数直接传递一个字符串

#### ⑦、🔴String的常用方法

**1.判断两个字符串内容是否相同。区分大小写**

```java
boolean equals(String s);
使用方法：
    String类型的变量名.equals(另外一个String类型的变量名);
```

**2.比较字符串的内容，忽略大小写**

```java
boolean equalsIgnoreCase(String anotherString);
```

**3.获取传入的索引上的对应的字符**

```java
char charAt(int index);	
```

**4.将字符串拆分为字符数组后返回**

```java
char[] toCharArray();
```

**5.获得字符串的长度** 

```java
int length();
```

**6.从指定位置开始截取。默认到末尾。**（注：会把截取之后的字符串作为一个新值，需要用一个字符串类型接收）

```java
String substring(int index);
```

**7.截取指定范围的字符串。**<u>包头不包尾。</u>（注：会把截取之后的字符串作为一个新值，需要用一个字符串类型接收）

```java
String substring(int start,int end);
```

**8.把字符串中的字符'a'全部替换成'b'** 

```Java
String replace(char oldStr,char newStr);
列如：
    String s1 = s.replace("TMD","***");
```

**9.按照指定规则切割字符串。**例如把一个有规律的字符串例如“a,,bcc,,sss”或者 “qw-ww-rrr”分割成一个字符串数组。

```Java
String[] split(String regex);
列如：
    String[] split = s.split("，");
```

##### **方法总结：**

​	**1.构造方法**

```Java
String();						创建一个内容为空的字符串对象

String(char[] arr);					根据传入的字符数组创建一个字符串对象

String(char[] arr,int index,int count); 		根据传入的字符数组的一部分来创建字符串对象

String(byte[] arr);					根据传入的字节数组创建一个字符串对象

String(byte[] arr,int index,int count);			根据传入的字节数组的一部分来创建字符串对象

String(String s);					根据传入的字符串来创建一个字符串对象
```

**2.判断功能**

```Java
boolean equals(String s);				判断两个字符串内容是否相同。区分大小写
	
boolean equalsIgnoreCase(String s);			判断两个字符串内容是否相同。不区分大小写

boolean startsWith(String s);				判断当前字符串是否以传入的字符串为开头

boolean endsWith(String s);				判断当前字符串是否以传入的字符串为结尾

boolean contains(String s);				判断当前字符串中是否包含传入的字符串

boolean isEmpty();					判断字符串是否为空
```

**3.获取功能**
	

```Java
int length();						获取字符串的长度

char charAt(int index);					获取传入的索引上的对应的字符

int indexOf(String s);					获取传入的字符串在当前字符串中第一次出现的索引位置

int lastIndexOf(String s);				获取传入的字符串在当前字符串中最后一次出现的索引位置

String concat(String s);				拼接字符串

String substring(int index);				从指定位置开始截取。默认到末尾

String substring(int start,int end);			截取指定范围的字符串。包含开始、不包含结束
```

**4.转换功能**
	

```Java
char[] toCharArray();					将字符串转成字符数组

byte[] getBytes();					将字符串转成字节数组

String replace(String oldStr,String newStr);		用新字符串 替换所有的老字符串

String replace(char oldStr,char newStr);		用新字符 替换所有的老字符

String toUpperCase();					将字符串转成大写

String toLowerCase();					将字符串转成小写
```

**5.其他功能**
	

```Java
String[] split(String regex);				按照指定规则切割字符串

String trim();						去除字符串两端的空白
```





### 3、StringBuilder

#### **1.StringBuilder概述**

StringBuilder 是一个**可变的字符串类**，我们可以把它看成是一个容器

⚫ 作用：提高字符串的操作效率

#### 2.构造方法

**无参：**StringBuilder sb = new StringBuilder(); 						创建一个空白可变字符串对象，不含有任何内容

**有参：**StringBuilder sb2 = new StringBuilder("abc");			  根据字符串的内容，来创建可变字符串对象

#### 3.StringBuilder 的常用成员方法

StringBuilder append(任意类型)  							向缓冲区添加内容，并返回对象本身

StringBuilder reverse()    										返回相反的字符序列

String	toString() 													把StringBuilder转换成String

int	length()  															返回值StringBuilder的长度  	( 字符出现的个数)

#### 4.为什么StringBuilder可以提高字符串拼接效率

如果用**+**拼接，每次都会创建一个新的StringBuilder对象，调用append方法，并且最后调用toString方法。

如果自己使用**StringBuilder**来拼接的化，只会创建一个sb对象，调用一次toString方法。

#### **5.StringBuilder和String的区别**

⚫ String ：内容是不可变的

⚫ StringBuilder：内容是可变的

#### **6.StringBuilder 和 String 相互转化**

**1. StringBuilder 转换为 String**

public String **toString()**：通过 toString() 就可以实现把 StringBuilder 转换为 String

**2. String 转换为 StringBuilder**

public **StringBuilder(String s)**：通过构造方法就可以实现把 String 转换为 StringBuilder


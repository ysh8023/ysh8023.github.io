---
title: NO.02 Java基础学习&心得体会
date: 2022-03-31 21:12:20 +0800
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

![33068126881a11ebb6edd017c2d2eca2](/assets/blog_res/33068126881a11ebb6edd017c2d2eca2.jpg)





# NO.02 Java基础学习&心得体会



### 一、运算符

#### 1、算术运算符

**运算符和表达式**

⚫ 运算符：对常量或者变量进行操作的**符号**

⚫ 表达式：用**运算符**把常量或者变量连接起来**符合java语法的式子**就可以称为表达式。

不同运算符连接的表达式体现的是不同类型的表达式。

**符号**                **作用** 

\+                        加 

\-                         减 

\*                        乘 

/                         除 

%                       取余

**注意事项：**

**/**和**%**的区别：两个数据做除法，**/**取结果的**商**，**%**取结果的**余数**。

<u>注：整数操作只能得到整数，要想得到小数，必须有浮点数参与运算。</u>

**字符的“+”操作**

a + b 的运算中，a为int类型，b为char类型

当（byte short char int）在一起运算的时候，都会提升为int之后，再进行运算

⚫ **ASCII码表**

ASCII (American Standard Code for Information Interchange)：美国信息交换标准代码

是计算机中字节到字符的一套对应关系。

‘a’--- 97

‘A’--- 65

‘0’--- 48

**自增自减运算符**

**符号 **     **作用 **   **说明**

++        自增     变量的值加1

\--          自减     变量的值减1 

⚫ ++和-- 既可以放在变量的后边，也可以放在变量的前边。

**注意事项：**

⚫ 单独使用的时候， ++和-- 无论是放在变量的前边还是后边，结果是一样的。

⚫ 参与操作的时候

​	⚫ 如果放在变量的后边，先将该变量原本的值，取出来参与操作，随后再进行自增(++)，自减(--)。

​			int a = 10;

​			int b = a++;

​	⚫ 如果放在变量的前边，先对该变量做自增(++)或者自减(--)，然后再拿变量参与操作。

​			int a = 10;

​			int b = ++a;

最常见的用法：**单独使用**

#### 2、**赋值运算符✨**

**符号**         **作用**         **说明**

=           赋值           a=10，将10赋值给变量a

+=         加后赋值    a+=b，将a+b的值给a 

-=          减后赋值    a-=b，将a-b的值给a 

x=        乘后赋值     a*=b，将a×b的值给a

/=          除后赋值     a/=b，将a**÷**b的商给a

%=       取余后赋值  a%=b，将a**÷**b的余数给a

**注意事项：**扩展的赋值运算符**隐含**了<u>强制类型转换</u>

#### 3、关系运算符 ( 比较运算符 ）

**符号**                                                **说明**

==                                  a==b，判断a和b的值是否相等，成立为true，不成立为false

!=                                   a!=b，判断a和b的值是否不相等，成立为true，不成立为false

\>                                    a>b，判断a是否大于b，成立为true，不成立为false

\>=                                  a>=b，判断a是否大于等于b，成立为true，不成立为false

<                                    a<b，判断a是否小于b，成立为true，不成立为false

<=                                  a<=b，判断a是否小于等于b，成立为true，不成立为false

**注意事项：**关系运算符的**结果**都是**boolean**类型，要么是true，要么是false。千万不要把“==”误写成“=”。

#### 4、**逻辑运算符**

**逻辑运算符**

**符号**           **作用**                    **说明**

&              逻辑**与**                  a & b，a和b都是true，结果为true，否则为false

|              逻辑**或**                  a | b，a和b都是false，结果为false，否则为true

^              逻辑**异或**              a ^ b，a和b结果不同为true，相同为false

!               逻辑**非**                  !a，结果和a的结果正好相反

**短路逻辑运算符**

**符号**            **作用**                     **说明**

&&            短路与              作用和&相同，但是有短路效果

||             短路或              作用和|相同，但是有短路效果

**注意事项：**

⚫ 逻辑与**&**，无论左边真假，右边都要执行。

​	  短路与**&&**，如果左边为真，右边执行；如果**左边为假，右边不执行**。 

⚫ 逻辑或**|**，无论左边真假，右边都要执行。

​	  短路或**||**，如果左边为假，右边执行；如果**左边为真，右边不执行**。

最常用的逻辑运算符：**&&，||，!**

#### 3、**三元运算符**

⚫ 格式：关系表达式 **?** 表达式1 **:** 表达式2;

⚫ 范例：**a > b ? a : b;**

计算规则：

首先计算**关系表达式的值**

如果值为**true**，**表达式1的值**就是运算结果

如果值为**false**，**表达式2的值**就是运算结果

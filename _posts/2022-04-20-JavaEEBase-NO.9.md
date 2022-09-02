---
title: NO.09 Java基础学习&心得体会
date: 2022-04-20 22:31:34 +0800
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





# NO.09 Java基础学习&心得体会



## 一、**集合基础**

### 1、**集合概述**

集合就是用来存储多个数据的容器

直接打印String   StringBulider    list 可以直接打印出里面的数据。

**注：**用equal方法的时候 尽量用常量.equal(变量)

**集合和数组的特点对比**

⚫ 集合类的特点：提供一种存储空间可变的存储模型，存储的数据**容量可以发生改变**

⚫ 集合和数组的区别：

​		⚫ **共同点：都是存储数据的容器**

​		⚫ **不同点：数组的容量是*固定的，*集合的容量是*可变的***

### 2、ArrayList

集合类有很多，先学习：**ArrayList**

#### ①、构造方法

**ArrayList<String> list = new ArrayList();**

*集合容器如果没有加入<> 就可以存储任意数据类型*

**<> 泛型:** 对集合容器存储的数据类型进行限制 ，这里面的数据类型只能是引用数据类型

#### ②、添加元素

​     1️⃣   boolean add(E e)          将指定的元素添加到此列表的尾部。

​     2️⃣   void add(int index, E element)   将指定的元素插入此列表中的指定位置。

```Java
    ArrayList<String> list = new ArrayList<>();

    //添加元素

    list.add("cj",);

    list.add("cj2");

    list.add("cj3");

    list.add("黑马52");

    System.out.println(list);   //["cj","cj2","cj3","黑马52"]
```

#### ③、成员方法

列子：

```java
 public static void main(String[] args) {
//        int[] arr = {1,2,3,4};
        ArrayList<String> list = new ArrayList<>();
        //添加元素
        list.add("剑圣");
        list.add("盲僧");
        list.add("瑞文");
//        for(int i = 0;i<list.size();i++){
//            String s = list.get(i);
//
//            System.out.println(s);
//        }
//        list.add(2,"TIMU");
//
//        //删除元素
//        list.remove(0);
        list.remove("TIMU111");
//
//        //获取元素
//        String s = list.get(0);
//        System.out.println(s);
//
//
//        //修改
//        list.set(0,"瞎子");
//
//        //获取集合大小
//        System.out.println(list.size());
    }
```

**方法名** 																											**说明**

public boolean remove(Object o) 										删除指定的元素，返回删除是否成功

public E remove(int index) 													删除指定索引处的元素，返回被删除的元素

public E set(int index,E element) 										修改指定索引处的元素，返回被修改的元素

public E get(int index) 															返回指定索引处的元素

public int size() 																		返回集合中的元素的个数

#### ④、遍历集合

列子：

```Java
        ArrayList<String> list = new ArrayList<>();
        list.add("瑞文");
        list.add("盖伦");
        list.add("玛尔扎哈");
        for(int i = 0;i<list.size();i++){
            String s = list.get(i);
            System.out.println(s);
        }
```


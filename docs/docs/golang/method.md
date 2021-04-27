---
layout: default
title: 学习笔记
parent: Golang
---

*2021-04-26*
# 方法
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## sort排序方法的设计心得
在Go中，排序使用了sort包中的方法，此方法是interface接口，要求被排序对象有三个方法，这一点与cpp中的面向对象的设计思想有很大不同，在此处记录以下。
### 从对象角度出发
为了设计给对象添加排序方法，一般的做法通常要求排序对象是数组，数组包含对象，对象要有比较运算符或者方法。
Go也是类似的要求， 数组包含元素，元素有比较的方法。
### 排序方法的通用性
在某些场景下，对象需要多种排序方法。cpp一般设计方法是为对象添加多个调用函数，通过函数实现。
Go则是通过定义不同的对象（姑且称之为对象吧，一般为struct，重点是附上方法），通过为对象定义不同的比较算法实现。
<a href="https://books.studygolang.com/gopl-zh/ch7/ch7-06.html">详细例子见</a>
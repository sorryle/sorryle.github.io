---
layout: post
title: 数学公式语法
category: 博客
tags: [博客, Latex]
excerpt: 数学公式语法笔记，加载图片，方便以后查看
typora-root-url: ..
---



## 数学公式语法

[资源出处](https://blog.csdn.net/wait_for_eva/article/details/84307306) - 从CDNS转载而来



![img](../../assets/images/2021/2021-01-28-blog-latex/20200708163549471.png)

![img](/../assets/images/2021/2021-01-27-blog-total/20200708163549471.png)

![img](/../assets/images/2021/2021-01-27-blog-total/20200708163549468.png)

![img](/../assets/images/2021/2021-01-27-blog-total/20200708163549448.png)

![img](/../assets/images/2021/2021-01-27-blog-total/20200708163549451.png)

## 换行对齐方式

[学习地址](https://blog.csdn.net/DUTwangtaiyu/article/details/114281954)

**写法示范**

`\\` 是换行 ; `&`是对齐

```latex
\begin{equation*} %加*表示不对公式编号
	\begin{split} 
		Adv^{Fed}
		& = Pr^{Fed}\left ( A=1\mid x\in D_{T} \right ) - Pr^{Fed}\left ( A=1\mid x\in D_{N} \right ) \\
		& = \underset{x\in D_{T}}{E^{Fed}}\left ( P\left ( A=1\mid x \right ) \right )-\underset{x\in D_{N}}{E^{Fed}}\left ( P\left ( A=1\mid x \right ) \right ) \\
		& = \underset{x\in D_{T}}{E^{Fed}}\left ( 1-\frac{L\left ( \left ( x,y \right ),F \right )}{A} \right )-\underset{x\in D_{N}}{E^{Fed}}\left ( 1-\frac{L\left ( \left ( x,y \right ),F \right )}{A} \right )\\
		& = \frac{1}{A}\cdot \left [ \underset{x\in D_{N}}{E^{Fed}}\left ( L\left ( \left ( x,y \right ),F \right )\right )-\underset{x\in D_{T}}{E^{Fed}}\left ( L\left ( \left ( x,y \right ),F \right ) \right ) \right ] \\
	\end{split}
\end{equation*} 

```

**效果**
$$
\begin{equation*} %加*表示不对公式编号
	\begin{split} 
		Adv^{Fed}
		& = Pr^{Fed}\left ( A=1\mid x\in D_{T} \right ) - Pr^{Fed}\left ( A=1\mid x\in D_{N} \right ) \\
		& = \underset{x\in D_{T}}{E^{Fed}}\left ( P\left ( A=1\mid x \right ) \right )-\underset{x\in D_{N}}{E^{Fed}}\left ( P\left ( A=1\mid x \right ) \right ) \\
		& = \underset{x\in D_{T}}{E^{Fed}}\left ( 1-\frac{L\left ( \left ( x,y \right ),F \right )}{A} \right )-\underset{x\in D_{N}}{E^{Fed}}\left ( 1-\frac{L\left ( \left ( x,y \right ),F \right )}{A} \right )\\
		& = \frac{1}{A}\cdot \left [ \underset{x\in D_{N}}{E^{Fed}}\left ( L\left ( \left ( x,y \right ),F \right )\right )-\underset{x\in D_{T}}{E^{Fed}}\left ( L\left ( \left ( x,y \right ),F \right ) \right ) \right ] \\
	\end{split}
\end{equation*} 
$$

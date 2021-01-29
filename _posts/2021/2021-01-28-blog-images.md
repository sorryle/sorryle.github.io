---
layout: post
title: Typora和Jekyll环境同步图片
category: 博客
tags: [博客,Typora,Jekyll]
excerpt: 解决Typora和Jekyll环境的图片资源不同步问题
typora-root-url: ..
---

## Typora和Jekyll环境同步图片

[参考地址](https://www.zhihu.com/question/31123165/answer/505487857) -博客中如何用相对路径来加载图片？ - 九千鸦的回答 - 知乎

博客是使用`Typora`编写，遇到图片直接就直接截图粘贴进来，但是上传的`Jekyll`的时候就显示不出来错误，变成这个鬼样子![1611808648116](/../assets/images/2021/2021-01-27-blog-total/1611808648116.png)。



### 原因：

- 因为`Jekyll`渲染成`HTML`时候会把`MdrkDown`文件变成的路径变成`/2021/01/28/blog-latex.html`
- 路径前面多`2021`、`01`、`28`三个文件夹，我在`Typora`中设置的相对路径直接失效



### 思路

- 使得`Jekyll`渲染的时候，加载的路径和`Typora`一样寻址，无视新增的那三个文件夹
- 具体为什么成功也不清楚，反正他就可以了



#### 设置`MarkDown`文件为当前路径

在`MarkDown`文件设置为该变量时，在需要加载图片的`MarkDown`的文件前加入`typora-root-url: ..`

![1611809920732](/../assets/images/2021/2021-01-27-blog-total/1611809920732.png)



#### 设置`Typora`

打开Typora文件，点击左上角的 `文件` - `偏好设置` - `图像` 进行如下设置

**我的项目路径:**`sorryle.github.io\_posts\2021`

按照下面的设置，`Typora`会自动在`sorryle.github.io`文件夹下找`assets/images/2021/文件名字`的文件夹

若是没有找到自动创建，然后把图片保存在里面。

![1611810320900](/../assets/images/2021/2021-01-27-blog-total/1611810320900.png)


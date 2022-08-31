---
layout: post
title: Jekyll踩坑合集
category: 博客
tags: [博客,Jekyll]
excerpt: 如题
typora-root-url: ..
---



{% raw %}

### Jekyll解析代码块中数组导致错误

【报错】

```c
jekyll 3.0.1 | Error:  Liquid syntax error: Variable '{{1,2,3}' was not properly terminated with regexp: /\}\}/
```

{% endraw %}

![image-20220821101852369](/../assets/images/2021/2022-08-21-jekyll_error/image-20220821101852369.png)

【原因】

- `Liquid`语法将代码块中的数组当成标签进行解析

【解决办法】

- 【方法】在报错处添加一个标签 ![image-20220821113856662](/../assets/images/2021/2022-08-21-jekyll_error/image-20220821113856662.png)  **备注：左边是图片，放入标签直接不显示**
- 【解决原因】添加这个标签后`Jekyll`不会继续解析这部分内容了

![image-20220821102448577](/../assets/images/2021/2022-08-21-jekyll_error/image-20220821102448577.png)

{% raw %}

【耗时】2小时

【思路】

- 报错后先使用二分法定位出具体有哪几处存在这种问题
- 定位出问题后上网百度是是否存在具体解决方案
  - 第一个方法，这个方法亲测不行：[部署Page时报错: Liquid syntax error: Variable '{{0, 0}' was not properly terminated with regexp: /\}\}/ · Issue #I1BLTM · 开源中国/Gitee Feedback - Gitee.com](https://gitee.com/oschina/git-osc/issues/I1BLTM)
  - 第二个方法：：[GitHub 博客-- Jekyll--代码高亮，Liquid 转义字符_淡竹云开的博客-CSDN博客](https://blog.csdn.net/zhangpeterx/article/details/103920538)  （我刚创建博客的时候好像遇到类似的问题，就是用添加这个标签解决的.....）



{% endraw %}
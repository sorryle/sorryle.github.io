---
layout: post
title: Liquidj基础语法汇总
category: 博客
tags: [博客,Liquid]
excerpt: 由于有一些需要进行定制，所以进行Liquidj的语法进行一个学习，这样就不会看到这玩意就头大
typora-root-url: ..
---



## Liquid的基础语法

{% raw %}

[Liquid学习网址](https://liquid.bootcss.com/basics/introduction/)

[Jekyll—Liquid网站学习](https://jekyllrb.com/docs/liquid/)

### 逻辑操作符号

|    符号    | 意                                                           |
| :--------: | ------------------------------------------------------------ |
|    `==`    | 相等                                                         |
|    `!=`    | 不相等                                                       |
|    `>`     | 大于                                                         |
|    `<`     | 小于                                                         |
|    `>=`    | 大于或等于                                                   |
|    `<=`    | 小于或等于                                                   |
|    `or`    | 逻辑或                                                       |
|   `and`    | 逻辑与                                                       |
| `contains` | 包含                                                                                                                                                         `contains` 只能用于搜索字符串。你不能将其用于从一个对象数组中检查是否存在某个对象 。       只能用于检查在一个字符串是否存在另一个字符串或者一个字符串数组是否存在某个字符串。 |

逻辑操作符号运用实例

```liquid
{% if page.title contains 'Blog' %}
判断如果界面的标题如果包含Blog就输出这行
{% endif%}
```





数据类型

| 数据类型         | 体现                                            | 解释                        |
| ---------------- | ----------------------------------------------- | --------------------------- |
| String（字符串） | site.users = ‘test’                             | 被单引号或者双引的值        |
| Number（数字）   | site.users = 3.141592611111111111               | 整数或者小数（浮点数）      |
| Boolean（布尔）  | site.users = true                               | true 或者 false             |
| Nil（空）        | site.users = Nil                                | 对象若是没有值，默认为Nil， |
| Array（数组）    | site.users = "Tobi", "Laura", "Tetsuro", "Adam" | 使用索引访问，索引从0开始   |




### 对象

- 对象告诉Liquid在哪里展示内容。对象和变量名由双花括号调用：`{{obejct}}`

- 使用`{{}}`包裹的内容会直接被输出展示在界面上

  ```html
  
  <body>
  <h1>{{page.title}}</h1>
  </body>
  ```

  输出：

  ```html
  <body>
  <h1>Blog</h1>
  </body>
  ```



### 标记(tag)

- 标记中可以编写控制流、逻辑，使用`{% logic %}`

- 作用：创建变量、条件语句和循环逻辑

  下方代码的逻辑：判断user对象若是存在则输出`Hello World`，若是user对象若是不存在输出`failure`

  ```html
  <body>
  	{% if user%}
      	Hello World!
      {% else %}
      	failure
      {% endif %}
  </body>
  ```

  输出：

  ```html
  <body>
      failure
  </body>
  ```



### 过滤器

- 改变对象的输出。它们被用在输出上，每个过滤器通过一个`|`符号分隔

- 相当于Python中的关键字，有各自的作用

- 举例过滤器作用：

  - append：在字符串后面拼接字符串
  - capitaliza:  把一段话中首字母变为大写

  ```html
  <body>
  {{"i don't" | append: "care" | capitaliza}}
  <\body>
  ```

  输出：

  ```html
  <body>
      I don't care
  </body>
  ```

  



### 注释

注释的内容不会被输出

```html
<body>
Please {% comment %} and {% endcomment %} go to where
</body>
```

输出：

```html
<body>
Pleas go to where
</body>
```



### 控制流

[学习地址](https://liquid.bootcss.com/tags/control-flow/)

只有当条件为true时才执行一段代码

#### IF语句

```html
<!-- If customer.name = 'anonymous' -->
{% if customer.name == 'kevin' %}
  Hey Kevin!
{% elsif customer.name == 'anonymous' %}
  Hey Anonymous!
{% else %}
  Hi Stranger!
{% endif %}
```

输出：

```
Hey Anonymous!
```



#### case语句

```html
% assign handle = 'cake' %}
{% case handle %}
  {% when 'cake' %}
     This is a cake
  {% when 'cookie' %}
     This is a cookie
  {% else %}
     This is not a cake nor a cookie
{% endcase %}
```

输出

```html
This is a cake
```



### 迭代/循环

[学习地址](https://liquid.bootcss.com/tags/iteration/)

对结构相同的数据，进行重复输出

#### for循环

```html
{% for product in collection.products %}
    {{ product.title }}
  {% endfor %}

```

```
hat shirt pants
```



#### continue

跳过本次循环，

```
{% for i in (1..5) %}
  {% if i == 4 %}
    {% continue %}
  {% else %}
    {{ i }}
  {% endif %}
{% endfor %}

```

输出

```
1 2 3   5
```



#### break

循环过程中若干遇到 `break` 标记（tag）即停止循环。

```html
{% for i in (1..5) %}
  {% if i == 4 %}
    {% break %}
  {% else %}
    {{ i }}
  {% endif %}
{% endfor %}
```

输出

```
1 2 3
```



### 变量

变量是可以变化的量

使用assign定义变量

```
{% assign mysql=true %}
{% if mysql=true %}
	This statement is valid
{% endif %}
```
输出

```
This statement is valid
```
{% endraw %}

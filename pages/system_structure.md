---
layout: page
title: 系统结构
titlebar: 系统结构
subtitle: <span class="mega-octicon octicon-clippy"></span> &nbsp;&nbsp; 学习你的编写的程序是怎么运行的，如何让他运行的更好
menu: 系统结构
css: ['blog-page.css']
permalink: /system_structure
---

<div class="row">

    <div class="col-md-8">

        <!-- Blog list -->
        <ul id="posts-list">
            {% for post in site.posts %}
            <!-- 判断如果界面的category属性是系统结构就添加进进行展示 -->
             {% if post.category == '系统结构' %}
            <li class="posts-list-item">
                <div class="posts-content">
                    <span class="posts-list-meta">{{ post.date | date: "%Y-%m-%d" }}</span>
                    <a class="posts-list-name bubble-float-left" href="{{ site.url }}{{ post.url }}">{{ post.title }}</a>
                    <span class='circle'></span>
                </div>
            </li>
                {% endif %}
            {% endfor %}
        </ul>

        <!-- Pagination -->
        {% include pagination.html %}

        <!-- Comments -->
        {% include disqus-comments.html %}

    </div>

    <div class="col-md-4">
        {% include sidebar-post-tag.html %}
    </div>

</div>
<script>
    $(document).ready(function(){

        // Enable bootstrap tooltip
        $("body").tooltip({ selector: '[data-toggle=tooltip]' });

    });
</script>

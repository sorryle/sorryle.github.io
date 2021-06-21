---
layout: page
title: 程序设计
titlebar: 程序设计
subtitle: <span class="mega-octicon octicon-clippy"></span> &nbsp;&nbsp; 各钟语言的程序设计笔记
menu: 程序设计
css: ['blog-page.css']
permalink: /code
---

<div class="row">

    <div class="col-md-8">
    
        <!-- Blog list -->
        <ul id="posts-list">
            {% for post in site.posts %}
            <!-- 判断如果界面的category属性是code就添加进进行展示 -->
             {% if post.category == 'code' %}
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

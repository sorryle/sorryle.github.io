---
layout: page
title: 博客
titlebar: 博客
subtitle: <span class="mega-octicon octicon-clippy"></span> &nbsp;&nbsp; 作为一个小完美主义，对自己博客是有一定的定制需求的，所以记录一下博客的改造过程
menu: 博客
css: ['blog-page.css']
permalink: /my_blog_index
---

<div class="row">

    <div class="col-md-8">
    
        <!-- Blog list -->
        <ul id="posts-list">
            {% for post in site.posts %}
            <!-- 判断如果界面的category属性是博客就添加进进行展示 -->
             {% if post.category == '博客' %}
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

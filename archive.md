---
bg: "w1.jpg"
layout: page
permalink: /posts/
title: "旧时光"
crawlertitle: "苏跃杰的博客 - 旧时光"
summary: 
active: 旧时光
---

{% for tag in site.tags %}
  {% assign t = tag | first %}
  {% assign posts = tag | last %}

  <h2 class="category-key" id="{{ t | downcase }}">{{ t | capitalize }}</h2>

  <ul class="year">
    {% for post in posts %}
      {% if post.tags contains t %}
        <li>
          {% if post.lastmod %}
            <a href="{{ post.url | relative_url}}">{{ post.title }}</a>
            <span class="date">{{ post.lastmod | date: "%Y-%m-%d"  }}</span>
          {% else %}
            <a href="{{ post.url | relative_url}}">{{ post.title }}</a>
            <span class="date">{{ post.date | date: "%Y-%m-%d"  }}</span>
          {% endif %}
        </li>
      {% endif %}
    {% endfor %}
  </ul>

{% endfor %}

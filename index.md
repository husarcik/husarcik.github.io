---
title: Home
layout: home
---

{% assign postsByDay = 
site.posts | group_by_exp:"post", "post.date | date: '%A, %B %e, %Y'" %}

{% for day in postsByDay %}
  <h1>{{ day.name }}</h1>
    <ul>
      {% for post in day.items %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
      {% endfor %}
    </ul>
{% endfor %}

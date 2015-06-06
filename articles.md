---
layout: default
title: UNIDEV
---

<div class="home" id="articles">

  <h1 class="pageTitle">Articles</h1>
  <!--
  <ul class="posts noList">
    {% for post in site.posts %}
      <li>
      	<span class="date">{{ post.date | date_to_string }}</span>
      	<h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
      	<p class="description">{% if post.description %}{{ post.description  | strip_html | strip_newlines | truncate: 250 }}{% else %}{{ post.content | strip_html | strip_newlines | truncate: 250 }}{% endif %}</p>
      </li>
    {% endfor %}
  </ul>
  -->
  
  {% for post in site.posts %}
    {% capture month %}{{ post.date | date: '%m%Y' }}{% endcapture %}
    {% capture nmonth %}{{ post.next.date | date: '%m%Y' }}{% endcapture %}
    {% if month != nmonth %}
      {% if forloop.index != 1 %}
        </p>
      {% endif %}
      <h3>{{ post.date | date: '%B %Y' }}</h3>
      <p class="description">
    {% endif %}
    <a href="{{ post.url }}">{{ post.title }}</a>
    <span class="date">Day {{ post.date | date: '%d' }}</span>
    <br/>
  {% endfor %}
</div>

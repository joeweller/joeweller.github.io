---
layout: page
title: Debug
permalink: /debug/
---

<div class="home">
<h2 class="post-list-heading">Posts</h2>
  <ul class="post-list">
  {% for post in site.categories["debug"] %}
    <li><span class="post-meta">{{  post.date | date: "%b %d, %Y" }}</span>
      <h3>
        <a class="post-link" href="{{ site.domain }}/{{ post.url }}">
          {{ post.title }}
        </a>
      </h3>
    </li>
  {% endfor %}
  </ul>
</div>

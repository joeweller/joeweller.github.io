---
layout: page
title: Projects
permalink: /projects/
---

<div class="home">
<h2 class="post-list-heading">Posts</h2>
  <ul class="post-list">
  {% for post in site.categories["projects"] %}
    <li><span class="post-meta">{{  post.date | date: "%b %d, %Y" }}</span>
      <h3>
        <a class="post-link" href="{{ site.baseurl }}/{{ post.url }}">
          {{ post.title }}
        </a>
      </h3>
    </li>
  {% endfor %}
  </ul>
</div>

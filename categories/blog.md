---
layout: page
title: Blog
permalink: /blog/
---

<div id="archives">
    {% for post in site.categories["blog"] %}
    <article class="archive-item">
      <h4><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></h4>
    </article>
    {% endfor %}
</div>

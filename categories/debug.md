---
layout: page
title: Debug
permalink: /debug/
---

<div id="archives">
    {% for post in site.categories["debug"] %}
    <article class="archive-item">
      <h4><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></h4>
    </article>
    {% endfor %}
</div>

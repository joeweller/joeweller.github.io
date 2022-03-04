---
layout: page
title: Projects
permalink: /projects/
---

<div id="archives">
    {% for post in site.categories["projects"] %}
    <article class="archive-item">
      <h4><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></h4>
    </article>
    {% endfor %}
</div>

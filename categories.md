---
layout: page
title: Categories
permalink: /categories/
---

{% assign categories = '' | split: '' %}
{% for category in site.categories %}
{% capture category_name %}{{ category | first }}{% endcapture %}
{% assign categories = categories | push: category_name | uniq %}
{% endfor %}
{% assign categories = categories | sort %}

<div id="archives">
{% for category in categories %}
  <div class="archive-group">
    <div id="#{{ category }}"></div>
    <p></p>
    <a name="{{ category }}" href="{{ site.baseUrl }}/{{ category }}"><h3 class="category-head">{{ category }}</h3></a>
  </div>
{% endfor %}
</div>

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
    <div id="{{ category | capitalize }}"></div>
    <br />
    <a href="{{ site.baseurl }}/{{ category }}">
      <h3 class="category-head">
        {{ category | capitalize }}
      </h3>
    </a>
  </div>
{% endfor %}
</div>

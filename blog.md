---
layout: fill
---

# Recent posts

<div class="blog_thumbnail_grid">
{% for post in site.posts limit:9 %}
<a href="{{ post.url }}">
<div class="blog_thumbnail">
  <p>{{ post.title }}</p>
  <div style="background-image: url('/assets/img/blog/{{ post.img }}');"></div>
</div>
</a>
{% endfor %}
</div>

<p class="blog_showall_bar"><a href="/s/all">show all {{ site.posts | size }}</a></p>

<!-- sep -->

# Series

<ul>
{% for series in site.data.blog_series.series %}
  {% assign post_count = 0 %}
  {% assign start = nil %}
  {% assign end = nil %}
  {% for post in site.posts %}
    {% if post.tags contains series.tag %}
      {% assign post_count = post_count | plus: 1 %}
      {% if end == nil %}
        {% assign end = post.date %}
      {% endif %}
      {% assign start = post.date %}
    {% endif %}
  {% endfor %}
  <li><a href="/s/{{ series.tag }}">{{ series.title }}</a> ({{ post_count }} posts) {{ start | date: "%b %Y" }} – {{ end | date: "%b %Y" }}</li>
{% endfor %}
</ul>

---
layout: fill
---

{% assign fn = page.name | remove:'.md' %}
{% for series in site.data.blog_series.series %}
  {% if fn == series.tag %}
    {% assign title = series.title %}
    {% assign output_tag = series.tag %}
  {% endif %}
{% endfor %}

# {{ title }}

<div class="blog_thumbnail_grid">
{% for post in site.posts %}
  {% if post.tags contains output_tag %}
<a href="{{ post.url }}">
<div class="blog_thumbnail">
  <p>{{ post.title }}</p>
  <div style="background-image: url('/assets/img/blog/{{ post.img }}');"></div>
</div>
</a>
  {% endif %}
{% endfor %}
</div>

<!-- sep -->

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

<div style="display: flex; flex-flow: row wrap; justify-content: space-between; margin-bottom: 10px;">
{% for post in site.posts %}
  {% if post.tags contains output_tag %}
<a href="{{ post.url }}">
<div style="width: 290px; height: 135px; display: flex; flex-flow: column; justify-content: flex-end;">
  <p style="width: 290px; white-space: nowrap; overflow: hidden; text-overflow: ellipsis;">{{ post.title }}</p>
  <div style="height: 100px; width: 290px; background-image: url('/assets/img/blog/{{ post.img }}'); background-size: cover; background-position: left bottom;"></div>
</div>
</a>
  {% endif %}
{% endfor %}
</div>

<!-- sep -->

---
layout: fill
---

# Recent posts

<div style="display: flex; flex-flow: row wrap; justify-content: space-between; margin-bottom: 10px;">
{% for post in site.posts limit:9 %}
<a href="{{ post.url }}">
<div style="width: 290px; height: 135px; display: flex; flex-flow: column; justify-content: flex-end;">
  <p style="width: 290px; white-space: nowrap; overflow: hidden; text-overflow: ellipsis;">{{ post.title }}</p>
  <div style="height: 100px; width: 290px; background-image: url('/assets/img/blog/{{ post.img }}'); background-size: cover; background-position: left bottom;"></div>
</div>
</a>
{% endfor %}
</div>

<p style="margin: 0;"><a style="display: block; text-align: center; background-color: #dbdbdb;" href="/blog/all.html">show all {{ site.posts | size }}</a></p>


<!-- sep -->

# Series

<ul>
{% assign series_tags = "MYJ15|NII17" | split: "|" %}
{% assign series_titles = "A year at 松山大学|Nine months at the 国立情報学研究所" | split: "|" %}
{% for series_tag in series_tags %}
  {% assign post_count = 0 %}
  {% for post in site.posts %}
    {% if post.tags contains series_tag %}
      {% assign post_count = post_count | plus: 1 %}
    {% endif %}
  {% endfor %}
  <li><a href="/blog/{{ series_tag }}.html">{{ series_titles[forloop.index0] }}</a> ({{ post_count }} posts)</li>
{% endfor %}
</ul>

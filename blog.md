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

<p style="margin: 0;"><a style="display: block; text-align: center; background-color: #dbdbdb;" href="/blog_all.html">show all</a></p>


<!-- sep -->

# Tags

{% assign tags_sorted = site.tags | sort %}
{% for tag in tags_sorted %}{{ tag[0] }}, {% endfor %}
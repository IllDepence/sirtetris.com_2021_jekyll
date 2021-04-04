---
layout: fill
---

# All posts

<div class="blog_thumbnail_grid">
{% for post in site.posts %}
<a href="{{ post.url }}">
<div class="blog_thumbnail">
  <p>{{ post.title }}</p>
  <div style="background-image: url('/assets/img/blog/{{ post.img }}');"></div>
</div>
</a>
{% endfor %}
</div>

<!-- sep -->

---
layout: default
title: Home
---

<section class="about-me">
  <h2>About Me</h2>
  <p>{{ site.author }}<br>{{ site.description }}</p>
</section>

<section>
  <h2>Posts</h2>
  {% for post in site.posts %}
    <article class="post">
      <h3 class="post-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>
      <small>{{ post.date | date: "%b %-d, %Y" }}</small>
      {% if post.excerpt %}
        <p>{{ post.excerpt }}</p>
      {% endif %}
    </article>
  {% endfor %}
</section>

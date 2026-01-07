---
layout: default
title: Home
---

<section class="post-list">
  <h2>Posts</h2>

  {% for post in paginator.posts %}
    <article class="post">
      <h3 class="post-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h3>

      <small class="post-meta">
        {{ post.date | date: "%b %-d, %Y" }}
      </small>

      {% if post.excerpt %}
        <p>{{ post.excerpt }}</p>
      {% endif %}
    </article>
  {% endfor %}
</section>

{% if paginator.total_pages > 1 %}
<nav class="pagination">
  {% if paginator.previous_page %}
    <a class="pagination-item newer"
       href="{{ paginator.previous_page_path | relative_url }}">
       ← Newer
    </a>
  {% endif %}

  {% if paginator.next_page %}
    <a class="pagination-item older"
       href="{{ paginator.next_page_path | relative_url }}">
       Older →
    </a>
  {% endif %}
</nav>
{% endif %}

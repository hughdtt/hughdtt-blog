---
layout: default
title: Home
---

<div class="posts">
  <h3>Recently published</h3>
  {% for post in site.posts %}
  <article class="post">
    <h1 class="post-title">
      <a href="{{ post.url | relative_url }}">
        {{ post.title }}
      </a>
    </h1>

    <time datetime="{{ post.date | date_to_xmlschema }}" class="post-date">{{ post.date | date_to_string }}</time>

    <p>{{ post.excerpt }}</p>
  </article>
  {% endfor %}
</div>

<!-- <div class="pagination">
  {% if site.next_page %}
    <a class="pagination-item older" href="{{ site.next_page_path | relative_url }}">Older</a>
  {% else %}
    <span class="pagination-item older">Older</span>
  {% endif %}
  {% if site.previous_page %}
    <a class="pagination-item newer" href="{{ site.previous_page_path | prepend: relative_url }}">Newer</a>
  {% else %}
    <span class="pagination-item newer">Newer</span>
  {% endif %}
</div> -->

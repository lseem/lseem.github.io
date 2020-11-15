---
layout: default
title: Blog
---

# Blog
[Full list of tags](/blog/tag.html)

Welcome to my blog! Don't take this blog very seriously.

## Posts

<ul class="post-list">
  {% for post in site.posts %}
    <li class="post-summary">
          <small>
      <span>{{ post.date | date_to_string }}
        {% for tag in post.tags %}
          <a class="tag" href="/blog/tag/#{{ tag | slugify }}">{{ tag }}</a>
        {% endfor %}
	</span>
          </small>
      <h4><a class="post-link" href="{{ post.url }}">
        {{ post.title }}
        {% if post.subtitle %}
          <p><small>{{ post.subtitle }}</small></p>
        {% endif %}
      </a>
      </h4>
    </li>
  {% endfor %}
</ul>

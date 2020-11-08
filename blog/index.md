---
layout: default
title: Blog
---

# Blog
[Full list of tags](/blog/tag.html)

![Not very seriously at all.][silly_me]

Welcome to my blog! The seriousness with which you should read these articles is summarised by the accompanying picture.


## Latest Posts

<table>
  {% for post in site.posts %}
    <tr class="post-summary">
      <td>{{ post.date | date_to_string }}</td>
      <td><a href="{{ post.url }}">
        {{ post.title }}
        {% if post.subtitle %}
        : {{ post.subtitle }}
        {% endif %}
      </a></td>
      <td>
        {% for tag in post.tags %}
          <small>
          <a class="tag" href="/blog/tag/#{{ tag | slugify }}">{{ tag }}</a>
          </small>
        {% endfor %}
      </td>
    </tr>
  {% endfor %}
</table>

[silly_me]: /assets/images/silly_me.jpg

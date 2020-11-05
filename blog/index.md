---
layout: default
title: Blog
---

# Blog
[Full list of tags](/blog/tag.html)

Welcome to my blog! Here you'll find articles mostly on (probably) the lean
theorem prover, philosophy, maths, and maybe the odd rant about the education
system (warning: rants may be contradictory).

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

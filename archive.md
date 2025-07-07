---
layout: default
title: Archive
permalink: /archive/
---

# Post Archive

Here are all my blog posts, organized by date:

{% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}

{% for year in posts_by_year %}
## {{ year.name }}

<div class="post-list">
{% for post in year.items %}
  <article class="post-item">
    <h3 class="post-title">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h3>
    <p class="post-meta">
      <time datetime="{{ post.date | date_to_xmlschema }}">
        {{ post.date | date: "%B %d, %Y" }}
      </time>
      {% if post.tags.size > 0 %}
      <br>
      <span class="post-tags">
        {% for tag in post.tags %}
          <span class="tag">{{ tag }}</span>
        {% endfor %}
      </span>
      {% endif %}
    </p>
    {% if post.excerpt %}
    <div class="post-excerpt">
      {{ post.excerpt }}
    </div>
    {% endif %}
  </article>
{% endfor %}
</div>

{% endfor %}

---

**Total Posts**: {{ site.posts.size }}

{% assign all_tags = site.posts | map: 'tags' | flatten | uniq | sort %}
{% if all_tags.size > 0 %}
## All Tags

{% for tag in all_tags %}
<span class="tag">{{ tag }}</span>
{% endfor %}
{% endif %} 
---
layout: default
title: Home
---

# Welcome to My Blog

This is a Jekyll-powered blog hosted on GitHub Pages. Here are my latest posts:

<div class="post-list">
{% for post in site.posts limit:5 %}
  <article class="post-item">
    <h2 class="post-title">
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h2>
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
    <div class="post-excerpt">
      {{ post.excerpt }}
    </div>
    <a href="{{ post.url | relative_url }}">Read more →</a>
  </article>
{% endfor %}
</div>

{% if site.posts.size > 5 %}
<p><a href="{{ '/archive' | relative_url }}">View all posts →</a></p>
{% endif %}

---

## About This Site

This blog is built with Jekyll and automatically deployed via GitHub Pages. Every time I push changes to the repository, GitHub automatically builds and publishes the site.

### Features

- **Responsive Design**: Looks great on desktop, tablet, and mobile
- **SEO Optimized**: Built-in SEO tags and sitemap generation
- **RSS Feed**: Automatic feed generation for subscribers
- **Fast Loading**: Optimized static site generation 
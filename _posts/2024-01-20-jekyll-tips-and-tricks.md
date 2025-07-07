---
layout: post
title: "Jekyll Tips and Tricks for Beginners"
date: 2024-01-20 14:30:00 -0500
author: Your Name
tags: [jekyll, tips, tutorial, web-development]
excerpt: "Essential tips and tricks I've learned while setting up and customizing my Jekyll blog on GitHub Pages."
---

After spending some time with Jekyll, I've picked up several useful tips and tricks that can help you get the most out of your blog. Here are some of my favorites:

## Front Matter Magic

Every Jekyll page and post starts with front matter - the YAML configuration between the `---` markers. Here are some useful options:

```yaml
---
layout: post
title: "Your Post Title"
date: 2024-01-20 14:30:00 -0500
author: Your Name
tags: [tag1, tag2, tag3]
excerpt: "A custom excerpt for your post"
published: true  # Set to false to save drafts
---
```

## Useful Liquid Filters

Jekyll uses the Liquid templating language. Here are some handy filters:

{% raw %}
- **Date formatting**: `{{ post.date | date: "%B %d, %Y" }}`
- **Truncate text**: `{{ post.content | truncate: 150 }}`
- **Strip HTML**: `{{ post.excerpt | strip_html }}`
- **Capitalize**: `{{ post.title | capitalize }}`
{% endraw %}

## Code Syntax Highlighting

Jekyll has built-in syntax highlighting. Just use fenced code blocks with the language:

```javascript
function greetVisitor(name) {
    console.log(`Hello, ${name}! Welcome to my blog.`);
}

greetVisitor("Reader");
```

```python
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

print(fibonacci(10))
```

## Organizing Your Content

### Categories vs Tags

- **Categories**: Use for broad topics (e.g., "tutorials", "reviews")
- **Tags**: Use for specific topics (e.g., "javascript", "productivity")

### File Organization

```
_posts/
  2024-01-15-welcome-post.md
  2024-01-20-jekyll-tips.md
_drafts/
  upcoming-post.md
_pages/
  about.md
  contact.md
```

## Local Development

To test your site locally before pushing:

```bash
# Install dependencies
bundle install

# Serve the site locally
bundle exec jekyll serve

# With drafts and future posts
bundle exec jekyll serve --drafts --future
```

Your site will be available at `http://localhost:4000`.

## Performance Tips

1. **Optimize images**: Use appropriate sizes and formats
2. **Minimize plugins**: Only use what you need
3. **Use excerpts**: Instead of showing full posts on the homepage
4. **Enable compression**: GitHub Pages supports gzip compression

## Useful Plugins

These plugins work well with GitHub Pages:

- `jekyll-feed`: Generates RSS feeds
- `jekyll-sitemap`: Creates XML sitemaps
- `jekyll-seo-tag`: Adds SEO meta tags
- `jekyll-paginate`: Pagination for post lists

## Custom Includes

Create reusable components in the `_includes` folder:

{% raw %}
```html
<!-- _includes/post-meta.html -->
<div class="post-meta">
  <time>{{ include.date | date: "%B %d, %Y" }}</time>
  {% if include.author %}
    <span> • {{ include.author }}</span>
  {% endif %}
</div>
```
{% endraw %}

Then use it in your layouts:

{% raw %}
```liquid
{% include post-meta.html date=page.date author=page.author %}
```
{% endraw %}

## Final Thoughts

Jekyll is incredibly powerful once you understand its conventions. The key is to start simple and gradually add complexity as you need it.

What Jekyll tips have you found most useful? I'd love to hear about your experiences! 
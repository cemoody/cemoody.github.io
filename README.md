# Jekyll Blog

This is a Jekyll-powered blog that automatically deploys to GitHub Pages.

## Features

- **Automatic Deployment**: Pushes to the main branch automatically trigger a build and deploy
- **Responsive Design**: Modern, mobile-friendly layout
- **SEO Optimized**: Built-in SEO tags, sitemap, and RSS feed
- **Syntax Highlighting**: Code blocks with syntax highlighting
- **Fast Loading**: Optimized static site generation

## Structure

```
├── _config.yml          # Jekyll configuration
├── _layouts/            # Page templates
│   ├── default.html     # Base layout
│   └── post.html        # Blog post layout
├── _posts/              # Blog posts (markdown files)
├── assets/css/          # Stylesheets
├── index.md             # Homepage
├── about.md             # About page
├── archive.md           # Post archive
├── Gemfile              # Ruby dependencies
└── README.md            # This file
```

## Writing Posts

Create new posts in the `_posts/` directory with the filename format:
```
YYYY-MM-DD-title-of-post.md
```

Each post should start with front matter:
```yaml
---
layout: post
title: "Your Post Title"
date: 2024-01-20 14:30:00 -0500
author: Your Name
tags: [tag1, tag2]
excerpt: "A brief description of your post"
---

Your post content here...
```

## Local Development

To run the site locally:

1. Install Ruby and Bundler
2. Run `bundle install` to install GitHub Pages compatible dependencies
3. Run `bundle exec jekyll serve` to start the development server
4. Visit `http://localhost:4000` to see your site

Note: This setup uses the `github-pages` gem to ensure local development matches GitHub Pages exactly.

## Customization

### Site Configuration

Edit `_config.yml` to update:
- Site title and description
- Your name and contact information
- Social media links
- Google Analytics (if desired)

### Styling

Modify `assets/css/style.css` to customize the appearance.

### Adding Pages

Create new `.md` files in the root directory with appropriate front matter.

## Deployment

This site automatically deploys to GitHub Pages when you push to the main branch. No additional configuration needed!

## GitHub Pages Setup

Make sure your repository settings have:
- GitHub Pages enabled
- Source set to "Deploy from a branch"
- Branch set to "main" (or "master")
- Folder set to "/ (root)"

## Support

If you encounter any issues, check the [Jekyll documentation](https://jekyllrb.com/docs/) or [GitHub Pages documentation](https://docs.github.com/en/pages). 
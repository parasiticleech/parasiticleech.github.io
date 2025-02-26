---
layout: home
title: Clyde's Product Reviews
subtitle: A collection of articles and reviews
---

Welcome to Clyde's Product Reviews! I provide honest, thorough reviews to help you make informed purchasing decisions.

## Latest Reviews

<div class="posts-list">
  {% assign blog_posts = site.posts | where_exp: "post", "post.path contains '/blog/'" | sort: "date" | reverse %}
  {% for post in blog_posts limit:10 %}
    <article class="post-preview">
      <a href="{{ post.url | relative_url }}">
        <h2 class="post-title">{{ post.title }}</h2>
        {% if post.subtitle %}
          <h3 class="post-subtitle">{{ post.subtitle }}</h3>
        {% endif %}
      </a>

      <p class="post-meta">
        Posted on {{ post.date | date: "%B %-d, %Y" }}
      </p>

      <div class="post-entry">
        {{ post.excerpt | strip_html | xml_escape | truncatewords: site.excerpt_length }}
        <a href="{{ post.url | relative_url }}" class="post-read-more">[Read&nbsp;More]</a>
      </div>

      {% if post.tags.size > 0 %}
      <div class="blog-tags">
        Tags:
        {% for tag in post.tags %}
        <a href="{{ '/tags' | relative_url }}#{{- tag -}}">{{- tag -}}</a>
        {% endfor %}
      </div>
      {% endif %}
    </article>
  {% endfor %}
</div>

<div class="text-center">
  <a href="/reviews" class="btn btn-primary">View All Reviews</a>
</div>

## Featured Content

Check out my [review of the best AI detector tools](/blog/ai-detector-tools.html) including Undetectable.ai and Originality.ai.

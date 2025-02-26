---
layout: page
title: All Reviews
subtitle: Comprehensive product and service reviews to help you make informed decisions
---

# All Product Reviews

Below you'll find a complete list of all my product and service reviews. Each review follows a consistent methodology including hands-on testing, standardized scoring, and real-world use cases.

<div class="posts-list">
  {% for post in site.posts %}
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

      <div class="post-entry-container">
        {% if post.image %}
        <div class="post-image">
          <a href="{{ post.url | relative_url }}">
            <img src="{{ post.image | relative_url }}">
          </a>
        </div>
        {% endif %}
        <div class="post-entry">
          {{ post.excerpt | strip_html | xml_escape | truncatewords: site.excerpt_length }}
          {% assign excerpt_word_count = post.excerpt | number_of_words %}
          {% if post.content != post.excerpt or excerpt_word_count > site.excerpt_length %}
            <a href="{{ post.url | relative_url }}" class="post-read-more">[Read&nbsp;More]</a>
          {% endif %}
        </div>
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

## Review Methodology

All reviews on this site follow a consistent methodology:

1. **Hands-on Testing**: Each product is tested for a minimum of two weeks
2. **Standardized Scoring**: Products are rated on a 5-point scale across multiple factors
3. **Real-world Use Cases**: Testing focuses on practical, everyday scenarios
4. **Regular Updates**: Reviews are updated when products receive significant updates

Have a product you'd like me to review? Check out the [Contact](/contact.html) page to submit your suggestion. 
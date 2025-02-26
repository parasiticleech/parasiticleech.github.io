---
layout: page
title: All Reviews
subtitle: Comprehensive product and service reviews to help you make informed decisions
---

# All Product Reviews

Below you'll find a complete list of all my product and service reviews. Each review follows a consistent methodology including hands-on testing, standardized scoring, and real-world use cases.

<div class="posts-list">
  {% assign blog_posts = site.posts | where_exp: "post", "post.path contains '/blog/'" | sort: "date" | reverse %}
  {% assign total_posts = blog_posts | size %}
  
  {% assign page_num = 1 %}
  {% if page.url contains '/page' %}
    {% assign url_parts = page.url | split: '/' %}
    {% for part in url_parts %}
      {% if part contains 'page' %}
        {% assign page_num = part | remove: 'page' | plus: 0 %}
      {% endif %}
    {% endfor %}
  {% endif %}
  
  {% assign start_index = page_num | minus: 1 | times: 10 %}
  {% assign end_index = start_index | plus: 10 | minus: 1 %}
  
  {% for i in (start_index..end_index) %}
    {% if i < total_posts %}
      {% assign post = blog_posts[i] %}
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
    {% endif %}
  {% endfor %}
</div>

<!-- Pagination links -->
<div class="pagination">
  {% assign total_pages = total_posts | divided_by: 10.0 | ceil %}
  
  {% if page_num > 1 %}
    <a href="{{ '/reviews' | relative_url }}{% if page_num > 2 %}/page{{ page_num | minus: 1 }}{% endif %}" class="btn btn-primary">&larr; Newer Posts</a>
  {% endif %}
  
  {% if page_num < total_pages %}
    <a href="{{ '/reviews/page' | append: page_num | plus: 1 | relative_url }}" class="btn btn-primary">Older Posts &rarr;</a>
  {% endif %}
</div>

<div class="pagination-info text-center">
  Page {{ page_num }} of {{ total_pages }}
</div>

<style>
.pagination {
  display: flex;
  justify-content: space-between;
  margin-top: 30px;
  margin-bottom: 20px;
}

.pagination-info {
  margin-bottom: 30px;
  color: #777;
}
</style>

## Review Methodology

All reviews on this site follow a consistent methodology:

1. **Hands-on Testing**: Each product is tested for a minimum of two weeks
2. **Standardized Scoring**: Products are rated on a 5-point scale across multiple factors
3. **Real-world Use Cases**: Testing focuses on practical, everyday scenarios
4. **Regular Updates**: Reviews are updated when products receive significant updates

Have a product you'd like me to review? Check out the [Contact](/contact.html) page to submit your suggestion. 
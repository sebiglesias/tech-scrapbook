---
layout: page
title: "Tech Scrapbook"
permalink: /
---

<div class="home">
  <div class="language-selector">
    <a href="{{ site.baseurl }}/_posts/en/" class="language-btn">English</a>
    <a href="{{ site.baseurl }}/_posts/es/" class="language-btn">Español</a>
  </div>

  <h2>Latest Updates</h2>
  
  <div class="posts">
    {% assign posts = site.posts | where: "lang", "en" | slice: 0, 5 %}
    {% for post in posts %}
    <article class="post-preview">
      <h3>
        <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
      </h3>
      <time datetime="{{ post.date | date_to_xmlschema }}">
        {{ post.date | date: "%b %-d, %Y" }}
      </time>
      <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
    </article>
    {% endfor %}
  </div>
</div>

<style>
  .language-selector {
    margin: 2rem 0;
    text-align: center;
  }
  .language-btn {
    display: inline-block;
    padding: 0.5rem 1rem;
    margin: 0 0.5rem;
    background: #f5f5f5;
    border-radius: 4px;
    text-decoration: none;
  }
  .post-preview {
    margin-bottom: 2rem;
    padding-bottom: 1rem;
    border-bottom: 1px solid #eee;
  }
  time {
    color: #666;
    font-size: 0.9rem;
  }
</style>

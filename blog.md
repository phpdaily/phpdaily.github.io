---
layout: default
title: PHP Daily - Blog
---

{% for post in site.posts %}
  <div  itemscope itemtype="http://schema.org/BlogPosting" class="row">
    <div class="col-sm-12 col-md-12 col-lg-7 col-lg-offset-1">
      <br/>
      <h2 itemprop="headline">
        <a href="{{ post.url }}">{{ post.title }}</a>
      </h2>
      <h4>
        <small>
          <span itemprop="datePublished">{{ post.date | date: "%-d %B %Y" }}</span> 
          - <span itemprop="author">{{ post.author }}</span>
          {% for tag in post.categories %}<mark class="tag">PHP {{ tag }}</mark>{% endfor %}
        </small>
      </h4>
      <p itemprop="articleBody">{{ post.excerpt }}</p>
    </div>
  </div>
{% endfor %}

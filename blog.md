---
layout: default
---

{% for post in site.posts %}
  <div class="row">
    <div class="col-sm-12 col-md-12 col-lg-7 col-lg-offset-1">
      <br/>
      <h2>
        <a href="{{ post.url }}">{{ post.title }}</a>
      </h2>
      <h4><small>{{ post.date | date: "%-d %B %Y" }} - {{ post.author }}</small></h4>
      <p>{{ post.excerpt|strip_html }}</p>
    </div>
  </div>
{% endfor %}

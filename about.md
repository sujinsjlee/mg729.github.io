---
layout: page
title: About
permalink: /about/
comments: false
---

<center><h2>Good day fellow readers and welcome to my tech study blog!</h2></center>

<div class="read-more">
  <div class="read-more-header">
    <a href="{{ site.owner.site }}" class="read-more-btn">About the Author</a>
  </div><!-- /.read-more-header -->
  <div class="read-more-content author-info">
    <h3>{{site.owner.name}}</h3>
    <div class="author-container">
      <img class="author-img" src="{{site.url}}/{{site.owner.avatar}}" alt="{{site.owner.name}}" />
      <div class="author-bio">{{site.owner.bio}}</div>
    </div>
    <div class="author-share">
      <ul class="list-inline social-buttons">
        {% for network in site.social %}
          <li><a href="{{ network.url }}" target="_blank"><i class="fa fa-{{ network.title }} fa-fw"></i></a></li>
        {% endfor %}
      </ul>
      {% if site.owner.github %}
        <a aria-label="Follow @{{site.owner.github}} on GitHub" data-style="mega" href="https://github.com/{{site.owner.github}}" class="github-button">Follow @{{site.owner.github}}</a>
      {% endif %}
      <br>
    </div>
  </div>
</div>

---
layout: default
title: All Posts
---

Here are all posts.

<div class="post-list">
  {% assign sorted_posts = site.posts | sort: 'date' | reverse %} {% comment %} Or sort by title: site.games | sort: 'title' {% endcomment %}
  {% for post in sorted_posts %}
    {% include post_listing.html post=post %}
  {% endfor %}
</div>
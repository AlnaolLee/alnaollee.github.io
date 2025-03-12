---
layout: default
title: "Blog"
permalink: /blog/
posts_title: ""
---

# Posts

<select id="tag-filter">
    <option value="all">All</option>
    <option value="school">School</option>
    <option value="hobby">Hobby</option>
    <option value="life">Life</option>
    <option value="misc">Misc.</option>
</select>

{% assign main_posts = site.posts | where_exp:"post", "post.dev_blog != true" %}
{% for post in main_posts %}
  <div class="post" data-tags="{{ post.tags | join:',' }}">
    <small>{{ post.date | date: "%B %d, %Y" }}</small>
    <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
  </div>
{% endfor %}


<script>
  document.getElementById('tag-filter').addEventListener('change', function() {
    var selectedTag = this.value;
    var posts = document.querySelectorAll('.post');
    
    posts.forEach(function(post) {
      var postTags = post.getAttribute('data-tags').split(',');
      if (selectedTag === 'all' || postTags.includes(selectedTag)) {
        post.style.display = '';
      } else {
        post.style.display = 'none';
      }
    });
  });
</script>


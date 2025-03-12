---
layout: default
title: "Blog"
permalink: /blog/
posts_title: ""
---

# Posts

<select id="tag-filter">
  <option value="all">All</option>
  <option value="coding">Coding</option>
  <option value="jekyll">Jekyll</option>
  <!-- Add more options as needed -->
</select>

{% for post in site.posts %}
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


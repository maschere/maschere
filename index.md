---
theme: jekyll-theme-slate
title: Hank Quinlan's Blog
---
test3

## {{ page.title }}

{% assign posts = site.posts | sort: 'date' %}
{% for post in posts %}

* {{ post.date | date_to_string }} [{{ post.title }}]({{ post.url }})

   {{ post.content | split:'<!--break-->' | strip_html | first }}
   
   {% if post.content contains '<!--break-->' %}
   [{{ read more }}]({{ post.url }})
   {% endif %}

{% endfor %}


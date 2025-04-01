---
title: My 11ty Blog
layout: base.html
pagination:
  data: collections.blog
  size: 3
  alias: blog
  reverse: true
---

{% for post in blog %}
[{{ post.data.title }} - {{ post.date | date: "%d-%m-%Y" }}]({{ post.url | url }})

{{ post.content | truncate: 200 }}

[Read more]({{ post.url | url }})
{% endfor %}

{% if pagination.previousPageHref %}
[Newer]({{ pagination.previousPageHref | url }})
{% endif %}

{% if pagination.nextPageHref %}
[Older]({{ pagination.nextPageHref | url }})
{% endif %}

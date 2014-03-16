---
layout: default
---
{% include JB/setup %}

<br/>
# Random musings from your friendly neighborhood misanthrope.
---
## I write [code](https://github.com/{{ site.author.github }}).
## I live and work in [Chicago](https://maps.google.com/maps?q=Chicago).
## I did a tour in [San Francisco](https://maps.google.com/maps?q=San+Francisco).
## Sometimes, I might write about some [stuff]({{ BASE_PATH }}{{ site.JB.archive_path }}).

---

## Latest Posts
{% for post in site.posts %}
  <h3>&raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a> - {{ post.date | date_to_string }}</h3>
{% endfor %}

---
layout: default
---
{% include JB/setup %}

<br/>
# Random musings from your friendly neighborhood misanthrope.
---
## I write [code](https://github.com/{{ site.author.github }}).
## I'm from [Chicago](https://maps.google.com/maps?q=Chicago).
## I live in [San Francisco](https://maps.google.com/maps?q=San+Francisco).
## Sometimes, I write about [things]({{ BASE_PATH }}{{ site.JB.archive_path }}).

---

## Latest Posts
{% for post in site.posts %}
  <h3>&raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a> - {{ post.date | date_to_string }}</h3>
{% endfor %}

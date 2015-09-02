---
layout: page
title: Yunho Github Blog
tagline: Supporting tagline
---
{% include JB/setup %}

Read [Who am i](http://takhwan.mooo.com)


## Sample Posts

This blog contains sample posts which help stage pages and blog data.
When you do not need the samples anymore just delete the `_posts/core-samples` folder.

    $ rm -rf _posts/core-samples

Here is a sample "posts list".

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


---
title: 'Blog'
layout: archive
classes: wide
permalink: categories/blog
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.Blog %} <hr />
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} <hr/>{% endfor %}

&nbsp;

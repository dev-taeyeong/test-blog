---
title: 'TIL' # navbar 카테고리 눌렀을때 페이지 타이틀
layout: archive
permalink: categories/TIL # 게시물 링크
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.TIL %} <hr />
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} <hr />{% endfor %}

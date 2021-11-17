---
title: 'Today I Learned' # navbar 카테고리 눌렀을때 페이지 타이틀
layout: archive
classes: wide
permalink: categories/til # 페이지 링크 (여기로 들어가면 카테고리가 보임)
author_profile: true
sidebar_main: true
---

{% assign posts = site.categories.TIL %} <hr />
{% for post in posts %} {% include archive-single.html type=page.entries_layout %} <hr/>{% endfor %}

&nbsp;

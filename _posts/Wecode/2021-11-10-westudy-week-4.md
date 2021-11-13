---
title: 'WeStudy - HTML & CSS'
excerpt: 'HTML 과 CSS 개념을 익힙니다.'

categories:
  - WeCode

tags:
  - [WeCode, WeStudy, HTML, CSS]

toc: true
toc_sticky: true

date: 2021-11-10T13:45:45+0900
last_modified_at: 2021-11-10T13:45:45+0900
---

<br>
<br>

# What You Will Learn

1. HTML 과 CSS 의 역할에 대해 설명할 수 있다.
2. HTML 에서 자주 쓰이는 태그의 종류와 기능을 익힌다.
3. CSS 의 다양한 스타일 속성을 익히며 HTML 요소에 직접 적용할 수 있다.
4. `.html` 파일과 `.css` 파일을 연결시킬 수 있다.
5. 배운 개념을 활용하여 자기 소개 페이지를 만들수 있다.

<br>

# 스터디 키워드

- HTML, CSS 란 무엇이며 필요한 이유
- HTML, CSS, JavaScript 의 관계
- `.html` `.css` `.js` 세 종류의 파일을 연결하는 방법
- script 태그의 위치에 따른 차이점
- 웹 페이지에서 일어날 수 있는 이벤트의 종류
- 이벤트와 자바스크립트 함수와의 관계

<br>

# HTML, CSS 란 무엇이며 필요한 이유

## HTML, CSS 란?

HTML(HyperText Markup Language)은 그대로 해석하면 **하이퍼텍스트를 마크업 하는 언어** 입니다. 하이퍼텍스트란 웹 사이트에서 링크를 클릭해 다른 문서나 사이트로 즉시 이동할 수 있는 기능을 말하고, 마크업이란 태그를 사용해 문서에서 어느 부분이 제목이고 본문인지, 어느 부분이 사진이고 링크인지 표시하는 것을 말합니다. 즉, 웹에서 자유롭게 오갈 수 있는 웹 문서를 만드는 언어가 HTML 이라고 정리할 수 있습니다.

CSS(Cascading Style Sheets) 는 HTML 요소들이 각종 미디어에서 어떻게 보이는가를 정의하는 데 사용되는 스타일 시트 언어입니다.

<br>

## HTML, CSS 가 필요한 이유

웹 사이트를 만들기 위해서는 사용자에게 보여줄 웹 문서가 있어야 하는데 그것을 작성하기 위해 HTML 이 필요합니다. 또한 아무런 디자인 없이 그냥 웹 문서 그대로를 보여줄 수도 있지만 사용자가 보기 편하고 예쁘도록 디자인을 입히기 위해 필요한 것이 CSS 입니다.

<br>

# HTML, CSS, JavaScript 의 관계

HTML 을 이용해 사용자가 볼 수 있는 웹 문서를 작성하고 CSS 를 이용해 사용자가 보기 편하도록 디자인을 입힙니다.

JavaScript 는 이런 웹 페이지에 여러가지 이벤트와 함수를 사용해 사용자와 상호작용 할 수 있는 웹 페이지로 만들어줍니다.

(수정) 클릭 이벤트 등을 이용해 사용자와 상호작용 할 수 있는 페이지를 동적 웹 페이지라고 알고 있었는데 **서버가 웹 페이지에 대한 요청을 받은 경우 추가적인 처리 과정 이후에 클라이언트에 응답을 보내는** 것이 동적 웹 페이지 라고 합니다!
{: .notice--info}

<br>

# `.html` `.css` `.js` 세 종류의 파일을 연결하는 방법

`.css` 파일은 `.html` 파일의 `<head>` 태그 안에 `<link rel = "stylesheet" herf="css 파일 경로" />` 를 입력하면 연결할 수 있습니다.

`.js` 파일은 `.html` 파일 안에 `<script src="js 파일 경로"></script>` 를 입력하면 연결할 수 있는데 보통 `<body>` 태그 가장 아래에 입력합니다.

```html
<html>
  <head>
    <link rel="stylesheet" href="style.css" />
  </head>

  <body>
    <script src="index.js"></script>
  </body>
</html>
```

<br>

# script 태그의 위치에 따른 차이점

## 브라우저 동작 방식

script 태그의 위치에 따른 차이점을 알기 위해서는 먼저 브라우저의 동작 방식에 대해 알아보아야 합니다. 브라우저는 HTML 파일을 읽고 파싱하여 DOM 트리를 생성합니다. 그 후 Render 트리(DOM tree + CSSOM 트리)가 생성되고 화면에 렌더링된 문서를 표시합니다.

여기서 HTML 을 읽는 도중 `<script>` 태그를 만나면 파싱을 중단하고 JavaScript 파일을 로드 후 JavaScript 코드를 파싱합니다. 이 과정이 완료된 후에 HTML 파싱을 다시 시작합니다.

<br>

## 가장 좋은 위치

브라우저의 동작 방식에 따라 HTML 태그들 사이에 `<script>` 태그가 위치하면 두가지 문제가 발생합니다.

1. HTML 을 읽는 과정에서 `<script>` 태그를 만나면 파일을 로드하는데 시간이 걸리기 때문에 렌더링된 문서를 화면에 표시하는데 까지 시간이 지연됩니다.
2. 자바스크립트가 생성되지도 않은 DOM 조작을 시도할 수 있습니다.

위와 같은 상황을 방지하기 위해 `<script>` 태그를 `<body>` 태그 최하단에 위치시키는 것이 좋습니다.

<br>

# 웹 페이지에서 일어날 수 있는 이벤트의 종류

웹 페이지에서 일어날 수 있는 이벤트는 여러가지 종류가 있는데요, 마우스 이벤트, 키 이벤트, 폼 이벤트, 로드 및 기타 여러가지 이벤트가 있습니다.

## 마우스 이벤트

- click
- dbclick
- mouseover
- mouseout
- mousedown
- mouseup
- mousemove
- contextmenu

<br>

## 키 이벤트

- keydown
- keyup
- keypress

<br>

## 폼 이벤트

- focus
- blur
- change
- submit
- reset
- select

<br>

## 로드 및 기타 이벤트

- load
- abort
- unload
- resize
- scroll

<br>

# 이벤트와 자바스크립트 함수와의 관계

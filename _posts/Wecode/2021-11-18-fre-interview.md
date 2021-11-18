---
title: 'HTML CSS JavaScript 그룹 면접'
excerpt: 'Pre-Course 그룹 면접 준비'

categories: WeCode
  -

tags:
  - [HTML, CSS, JavaScript]

toc: true
toc_sticky: true

date: 2021-11-18T12:30:42+0900
last_modified_at: 2021-11-18T12:30:42+0900
---

<br>
<br>

# HTML/CSS

## HTML이 무엇인가요?

HTML 은 웹문서를 작성하기 위한 언어입니다.

<br>

## HTML 파일의 필수 구조는 어떻게 되나요?

<br>

## `<img alt="profile" src="이미지 주소"></img>` 에서 `alt`, `src`를 가리키는 말은 무엇일까요?

`alt` 는 'alternate' 의 줄임말 입니다.
`src` 는 'source' 의 줄임말 입니다.

  <br>

## `img` 태그의 필수 속성을 설명해 주세요.

`src` 는 `img` 태그의 필수 속성으로 삽입하고자 하는 그림이 어디에 있는지 경로를 지정하는 속성입니다.
`alt` 는 필수 속성은 아니지만 웹 접근성을 위해 꼭 적어주어야 하는 속성입니다. 이미지를 불러오지 못했을 때 이미지를 대체할 설명을 나타내줍니다.

<br>

## CSS는 무엇인가요?

웹 문서에 색상을 입히거나 크기, 위치 조정 등 디자인 요소를 입히는 언어입니다.

<br>

## CSS를 적용하는 방법을 최소 2가지 이상 말씀해 주세요.

### 1. 인라인 방식

해당 태그의 `style` 속성으로 적용하는 방식입니다.

```html
<p style="color: pink;">안녕하세요~</p>
```

<br>

### 2. 내부 스타일 시트

html 파일 내에서 `<style>` 태그를 사용해 내부에 css 코드를 기입하는 방식입니다.

```html
<style>
  p {
    color: pink;
  }
</style>

<p>안녕하세요~</p>
```

<br>

### 3. 외부 스타일 시트

`<link>` 태그를 사용하여 별도의 css 파일을 연결하는 방식입니다.

```css
/* style.css */

p {
  color: pink;
}
```

```html
<!-- index.html -->

<link rel="stylesheet" href="style.css" />

<p>안녕하세요~</p>
```

<br>

## `margin`, `padding`, `border`의 영역을 설명해 주세요.

`margin` 은 요소와 요소 사이의 공간을 말합니다.

`border` 은 요소의 영역을 표현하는 경계선을 말합니다.

`padding` 은 컨텐츠와 `border` 사이의 공간을 말합니다.

<br>

## `block`, `inline`, `inline-block`의 차이점을 설명해 주세요.

`block` 요소는 요소 하나가 그 줄 전체를 차지합니다. 따라서 `block` 요소 옆에는 다른 요소가 올 수 없습니다.

`inline` 요소는 딱 컨텐츠의 크기 만큼만 공간을 차지합니다. 따라서 요소끼리 서로 한 줄에, 즉 바로 옆에 위치할 수 있습니다. 또한 `width` 와 `height` 속성이 적용되지 않습니다.

`inline-block` 요소는 `block` 요소를 사용하고 싶은데 한 줄에 여러 요소들을 나열해야 할 때 사용합니다. `width` 와 `height` 속성을 적용할 수 있으며 요소끼리 한 줄에 위치할 수 있습니다.

<br>

## HTML 태그 중 `block` 요소 3개, `inline` 요소 3개를 각각 설명해 주세요.

`block` 요소

- `<h1>~<h6>`: 제목을 나타내는 태그입니다.
- `<p>`: 문단을 나타내는 태그입니다.
- `<div>`: 아무런 의미 없이 영역을 나누기 위해 사용하는 태그입니다.

`inline` 요소

- `<span>`: `<div>` 태그와 마찬가지로 아무런 의미가 없고 보통 컨텐츠 내의 일부 텍스트에만 스타일을 적용시키고 싶을 때 사용합니다.
- `<a>`: 페이지 내의 다른 부분이나 다른 페이지로 이동할 수 있는 태그입니다.
- `<img>`: 이미지를 삽입하는 태그입니다.

<br>

## 목록과 관련된 태그를 설명해 주세요.

목록과 관련된 태그에는 `<ul>, <ol>, <li>` 가 있습니다.

`<ul>` 은 unordered list 의 약자로 순서가 없는 목록을 만들고 싶을 때 사용합니다.

`<ol>` 은 ordered list 의 약자로 순서가 있는 목록을 만들고 싶을 때 사용합니다.

`<li>` 는 list item 의 약자로 `<ul>` 이나 `<ol>` 안에 사용해 목록을 표현할 수 있습니다.

```html
<ul>
  <li>햄버거</li>
  <li>피자</li>
  <li>치킨</li>
</ul>

<ol>
  <li>첫번째</li>
  <li>두번째</li>
  <li>세번째</li>
</ol>
```

<br>

## 테이블과 관련된 태그를 설명해 주세요.

테이블을 표현하기 위한 태그는 `<table>, <tr>, <th>, <td>, <rowspan>, <colspan>` 등이 있습니다.

`<tr>` 태그는 'table row' 의 줄임말로 한 행을 뜻합니다.

`<td>` 태그는 'table data' 의 줄임말로 `<tr>` 태그 내에 `<td>` 태그를 사용해 행을 각각의 셀로 나눌 수 있습니다.

제목이라는 것을 나타내고 싶은 셀이 있다면 `<td>` 대신 `<th>` 태그를 사용합니다.

<br>

셀을 병합하려면 `rowspan`, `colspan` 속성을 사용하는데요,

`rowspan` 은 해당 셀이 확장될 행의 개수입니다. 따라서 세로로 병합됩니다.

`colspan` 은 해당 셀이 확장될 열의 개수입니다. 따라서 가로로 병합됩니다.

이렇게 만든 테이블은 `<table>` 태그로 감싸주어야 합니다.

```html
<table>
  <tr>
    <th></th>
    <th>제목</th>
    <th>제목</th>
  </tr>
  <tr>
    <th>제목</th>
    <td rowspan="2">내용</td>
    <td>내용</td>
  </tr>
  <tr>
    <th>제목</th>
    <td>내용</td>
  </tr>
</table>
```

<br>

## 사용자의 입력과 관련된 태그를 설명해 주세요.

사용자의 입력과 관련된 태그에는 `<input>, <textarea>` 가 있습니다.

`<input>` 태그에는 보통 `type` 속성과 `placeholder` 속성을 적용합니다.

`type` 속성의 값으로는 `text, password, number` 등이 있습니다.

`placeholder` 은 실제로 입력되는 값이 아닌 도움말을 띄워주는 속성입니다.

`<input>` 태그는 닫는 태그가 없어 안에 텍스트를 입력할 수 없는데요, `value` 속성을 사용해 미리 내용을 입력해 놓을 수 있습니다.

<br>

## `position` 속성에 대해 아는대로 설명해 주세요.

`position` 속성의 값에는 `static, relative, absolute, fixed` 가 있습니다.

`static` 은 기본 속성값으로 잘 사용하지 않습니다.

`relative` 는

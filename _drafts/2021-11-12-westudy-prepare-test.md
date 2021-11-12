---
title: 'westudy - 테스트 준비'
excerpt: 'wecode 사전 스터디 기간에 배운 내용 정리'

categories:
  - Wecode

tags:
  - [Wecode, Westudy]

toc: true
toc_sticky: true

date: 2021-11-12T20:35:31+0900
last_modified_at: 2021-11-12T20:35:31+0900
---

<br>
<br>

# replit 문제 정리

replit 문제들 중 헷갈리거나 중요해 보이는 문제들을 정리해 보려고 합니다. (뭔가 별표 되어있는 문제들은 테스트에 나올 것 같음)

## Variables

### - 변수 이름 정하기

- 대소문자 구분
- 변수 이름을 정할 때, 첫 번째 문자는 반드시 글자나 밑줄( \_ ), 달러기호( $ ) 중 하나 입니다.
- 변수나 함수 이름은 camelCase 방식으로 써야합니다.

```javascript
// camelCase
let someVariable;
let anotherVariableName;
let thisVariableNameIsSoLong;
```

<br>

### - null & undefined

`null` 과 `undefined` 는 모두 자바스크립트 데이터 타입입니다.

`undefined` 는 선언은 됐지만 아직 value 가 할당되지 않은 경우를 의미합니다. `null` 은 '빈 값(blank)'을 의미하는데 사용자가 준 value 입니다. 사용자가 주는 값이기 때문에 자바스크립트는 자동으로 `null` 값을 줄 수 없습니다.

포괄적인 의미로 '값이 없다'는 점에서 `null` 과 `undefined` 가 비슷한 것 같지만 둘은 엄격하게는 같지 않습니다.

```javascript
console.log(null == undefined); // true
console.log(null === undefined); // false

console.log(typeof null); // object
console.log(typeof undefined); // undefined
```

`null` 은 '값이 없음'을 의미하는 할당된 value 이기 때문에 object 타입이 나옵니다.

<br>

## String

<br>

## Function

### - 함수의 정의와 호출

### - 함수의 반환

### - 함수의 인자

<br>

## Math Expression

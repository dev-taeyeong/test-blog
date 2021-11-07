---
title: 'westudy - 사전 스터디 2주차'
excerpt: '2주차 사전 스터티 내용입니다! 배열과 반복문에 대해 알아보고 문제 하나를 같이 풀어보았습니다.'

categories:
  - Wecode

tags:
  - [Wecode, Westudy, JavaScript]

toc: true
toc_sticky: true

permalink: /:slugified_categories/:title/

date: 2021-11-05T15:48:27+0900
last_modified_at: 2021-11-05T15:48:27+0900
---

<br>
<br>

# 스터디 내용

사전 스터디 2주차 스터디 키워드를 하나씩 맡아 발표하였습니다.

발표를 마치고 하늘님이 가져오신 문제를 같이 풀어보았습니다.

<br>

# 문제 풀이

하늘님이 가져오신 문제입니다!

<img width="734" alt="스크린샷 2021-11-05 오후 4 23 48" src="https://user-images.githubusercontent.com/87692499/140473412-bc38ff03-8652-4084-9511-6c0a9243874b.png">

이 문제인데요~ 쉬워보였는데 막상 코드를 짤려니까 쉽게 생각이 나지 않았습니다.

이번 주차의 주제가 배열과 반복문이여서 그런지 배열이였다면 쉽게 풀었을 것 같은데 문자열이라 배열 메서드가 적용이 되지 않아서 고민하다가 답이 나오지 않아 구글링을 했습니다.

"자바스크립트 문자열 중간에 문자 추가" 이런 식으로 검색을 했는데 그런 메서드는 없는 것 같습니다.

그러다 `charAt()` 이라는 메서드를 찾았는데 `charAt()` 은 문자열에서 특정 인덱스에 위치하는 유니코드 단일 문자를 반환해주는 메서드라고 합니다.

이제 대문자를 구분하는 방법을 알아야 하는데 `toUpperCase()` 라는 문자열을 대문자로 변환해 반환하는 메서드를 찾았습니다.

```javascript
const a = 'camelCasing';
const b = 'identifier';
const c = '';

function breakUpCamelCasing(str) {
  let newStr = '';

  for (let i = 0; i < str.length; i++) {
    if (str.charAt(i) === str.charAt(i).toUpperCase()) newStr = newStr + ' ';
    newStr = newStr + str[i];
  }

  return newStr;
}

console.log(breakUpCamelCasing(a));
console.log(breakUpCamelCasing(b));
console.log(breakUpCamelCasing(c));
```

찾은 메서드들을 사용해서 이렇게 코드를 짜보았는데요~

반복문을 i 가 0 부터 str.length 보다 작을 때까지 돌리고 만약 문자열의 i 번 인덱스에 위치하는 문자가 문자열을 대문자로 변환한 문자열의 i 번 인덱스에 위치한 문자와 같을 경우 + 연산자를 이용하여 공백을 문자열에 추가해 주었습니다.

하늘님은 `split` 이라는 메서드를 이용해 문자열을 하나하나 쪼개어 배열로 만들어서 공백을 추가한 후에 다시 문자열로 합쳐주는 메서드를 사용하는 방식으로 문제를 푸셨는데 생각해보니 이번 주차 주제는 배열과 반복문이라 이렇게 푸는 것이 더 좋았을 것 같습니다!

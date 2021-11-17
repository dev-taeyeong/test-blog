---
title: 'Javascript Array 메서드 정리'
excerpt: 'WeCode 사전 스터디 기간에 배운 내용 중 배열 메서드를 정리했습니다.'

categories:
  - JavaScript

tags:
  - [WeCode, WeStudy, Array, JavaScript]

toc: true
toc_sticky: true

date: 2021-11-17T08:17:35+0900
last_modified_at: 2021-11-17T08:17:39+0900
---

<br>
<br>

# Array

## slice

`slice()` 메서드는 배열 내의 특정한 요소의 `index` 범위에 따라 새로운 배열을 리턴합니다.

**`slice()` 메서드는 원본 배열을 변형시키지 않습니다.** 따라서 이 메서드를 사용할 때는 반드시 리턴하는 배열을 받을 새로운 변수를 선언해 주어야 합니다.

```javascript
slice( [begin[, end]] ) // [] 은 배열을 뜻하는 것이 아니라 생략이 가능하다는 것을 나타냅니다.
```

`slice()` 메서드의 기본 형태 입니다. `end` 는 생략 가능합니다. (`end` 가 없을 경우 `begin` 도 생략 가능합니다.)

- `begin`: 추출 시작점에 대한 인덱스를 의미합니다.
- `end`: 추출을 종료할 인덱스를 의미합니다. **`slice()` 는 `end` 인덱스를 제외하고 추출합니다.**

ex) `slice(1, 4)`

'1 <= 인덱스 < 4 추출해줘' 이렇게 이해하시면 됩니다.

```javascript
const arr = [1, 2, 3, 4, 5];
const newArr = arr.slice(1, 4);

console.log(arr); // [1, 2, 3, 4, 5] -> 원본 배열이 변형되지 않음
console.log(newArr); // [2, 3, 4]
```

<br>

`end` 는 생략이 가능하다고 했죠? `begin` 만 있을때는 어떻게 되는지 알아보겠습니다.

```javascript
const arr = [1, 2, 3, 4, 5];
const newArr2 = arr.slice(1);

console.log(newArr2); // [2, 3, 4, 5]
```

이렇게 추출 시작점부터 배열의 끝까지 추출합니다.

<br>

`begin` 에 음수를 넣었을 때는 인덱스가 아닌 '뒤에서 몇 번째 요소인지' 입니다.

ex) `slice(-2)`

'뒤에서 두 개의 요소를 추출해줘' 라고 생각하면 됩니다.

```javascript
const arr = [1, 2, 3, 4, 5];
const newArr3 = arr.slice(-2);

console.log(newArr3); // [4, 5]
```

<br>

그러면 `end` 에 음수를 넣으면 어떻게 될까요? (너무 헷갈려서 맨 뒤로 빼놨는데 그냥 `end` 를 음수로 사용하는 경우까지는 생각 안하는게 편할듯 합니다 ㅎㅎ;)

`slice(1, -2)` 는 '1번 인덱스부터 뒤에서 세 번째 요소까지 추출해줘' 입니다.

음수일 경우 인덱스가 아닌 뒤에서 몇 번째 요소인지를 생각하는데 `end` 이기 때문에 본인은 제외합니다.

```javascript
const arr = [1, 2, 3, 4, 5];
const newArr4 = arr.slice(1, -2);

console.log(newArr4); // [2, 3]
```

<br>

## splice

`splice` 메서드는 세 가지 경우에 사용합니다.

- 배열 내의 특정한 요소를 삭제하고 싶을 때
- 배열 내의 특정한 요소를 다른 요소로 대치하고 싶을 때
- 배열 내에 새로운 요소를 추가하고 싶을 때

<br>

```javascript
splice(start[, deleteCount[, item1[, item2[, ...]]]])
```

- `start`: 배열의 변경을 시작할 인덱스
- `deleteCount`: 배열에서 제거할 요소의 수, 값을 생략하면 `start` 부터 뒤로 모든 요소를 제거합니다.
- `item1, item2, ...`: 배열에 추가할 요소, 아무 요소도 지정하지 않으면 `splice()` 는 요소를 제거하기만 합니다.

<br>

예제를 통해 알아보겠습니다.

```javascript
const arr = [1, 2, 3, 4, 5];
arr.splice(2, 1, 10);

console.log(arr); // [1, 2, 10, 4, 5]
```

`arr.splice(2, 1, 10)` 은 '2번 인덱스부터, 1개의 요소를 삭제하고, 그자리에 10 을 추가해 주세요' 라고 해석하면 됩니다!

`splice()` 메서드는 보통 댓글 삭제 기능을 구현할 때 많이 사용한다고 합니다.
{: .notice--info}

<br>

## filter

`filter()` 메서드는 array 관련 메서드로 조건에 맞는 요소들만 모아서 새로운 배열을 반환합니다. 만약 조건에 부합되는 요소가 아무것도 없다면 빈 배열을 반환합니다.

```javascript
arr.filter(callback(element[, index[, array]])[, thisArg])
```

- `callback`: 각 요소를 시험할 함수, `true` 를 반환하면 요소를 유지하고 `false` 를 반환하면 요소를 버립니다. `element, index, array` 세 가지의 매개변수를 받을 수 있습니다.
- `thisArg`: `callback` 을 실행할 때 `this` 로 사용하는 값

예제를 통해 이해해 보겠습니다.

```javascript
const arr = [43, 28, 7, 3, 20, 33];

function isBiggerThanTen(value) {
  return value > 10;
}

const result = arr.filter(isBiggerThanTen);

console.log(result); // [43, 28, 20, 33]
```

`arr.filter` 에 `isBiggerThanTen` 이라는 함수가 들어가 있습니다.

`filter()` 메서드는 먼저 첫 번째 요소인 43 을 `isBiggerThanTen` 함수에 `value` 라는 인자로 보냅니다.

`isBiggerThanTen` 함수는 43 이 10 보다 크니 `true` 를 반환하고 `filter()` 메서드는 43 요소를 유지합니다.

이런 과정을 마지막 요소까지 진행하면 `[43, 28, 20, 33]` 이라는 배열이 리턴됩니다.

<br>

그런데 콜백함수를 위의 예제와 같이 나눠서 사용하면 불편하고 가독성도 좋지 않으니 Arrow Function 으로 바꿔주겠습니다.

```javascript
const arr = [43, 28, 7, 3, 20, 33];
const result = arr.filter((value) => value > 10);

console.log(result); // [43, 28, 20, 33]
```

이렇게 간단한 코드로 바꿀 수 있습니다.

<br>

## concat

`concat()` 메서드는 주어진 배열에 기존 배열을 합쳐서 새로운 배열을 반환합니다.

원본 배열에 영향을 주지 않으며 새로운 배열이나 원본 배열을 수정해도 서로 영향을 받지 않습니다.

```javascript
const alphabet = ['a', 'b', 'c'];
const hangeul = ['ㄱ', 'ㄴ', 'ㄷ'];

alphabet.concat(hangeul); // ['a', 'b', 'c', 'ㄱ', 'ㄴ', 'ㄷ']
```

<br>

다음은 주의해야 할 점에 대해 알아보겠습니다.

```javascript
const alpha = ['a', 'b', 'c'];
const arr = [1, [2, 3]];

alpha.concat(arr); // ['a', 'b', 'c', 1, [2, 3]]

alpha.concat(1, [2, 3]); // ['a', 'b', 'c', 1, 2, 3]
```

이렇게 똑같은 배열을 넣어도 변수에 지정해서 넣을 때와 함수안에 직접 배열을 작성해서 넣을 때 리턴값에 차이가 있습니다.

<br>

## concat 과 filter 응용

```javascript
const array1 = [1, 2, 3, 4, 5];
const array2 = [3, 4, 5, 6, 7];

const result = array1.concat(array2);

console.log(result); // [1, 2, 3, 4, 5, 3, 4, 5, 6, 7];

const eraseDuplicates = result.filter(
  (el, index) => result.indexOf(el) === index
);

console.log(ereaseDuplicates); // [1, 2, 3, 4, 5, 6, 7]
```

<br>

코드를 이해하기 위해 `indexof()` 라는 메서드를 알아보겠습니다.

```javascript
indexof(searhElement[, fromIndex])
```

- `searchElement`: 배열에서 찾을 요소입니다.
- `fromIndex`: 검색을 시작할 인덱스입니다.

`indexof()` 메서드는 배열 내에서 찾은 최초의 인덱스 값을 반환합니다.

<br>

이제 코드를 해석해보겠습니다.

`filter()` 메서드가 콜백함수에 `result` 변수의 요소와 인덱스를 차례로 넣습니다.

처음에 (1, 0)을 넣었을 때 `result.indexOf(el)` 값은 0 이 되고 `0 === 0` 이므로 `true` 가 반환되어 `eraseDuplicates` 변수에 1이 들어갑니다.

그다음 (2, 1) 을 넣었을 때도 마찬가지겠죠? (3, 2) (4, 3) (5, 4) 까지 똑같이 들어가다가

(3, 5) 가 콜백함수에 전달되었을 때 `result.indexOf(el)` 값은 0 이고 0 은 5와 같지 않음으로 `false` 가 반환되어 두 번째 3은 배열에서 없어지게 됩니다.

이런식으로 `result` 변수의 끝까지 반복하면 `eraseDuplicates` 변수에 중복된 값이 없는 배열이 들어가게 됩니다.

<br>

## push

`push()` 메서드를 사용하면 배열의 끝에 하나 이상의 요소를 추가할 수 있습니다.

```javascript
const arr = [1, 2, 3];

arr.push(4);

console.log(arr); // [1, 2, 3, 4]
```

<br>

## pop

`pop()` 메서드는 배열의 마지막 요소를 제거하며 제거된 요소를 반환합니다.

```javascript
const arr = [1, 4, 6];
const result = arr.pop();

console.log(arr); // [1, 4]
console.log(result); // 6
```

<br>

## shift

`shift()` 메서드는 배열의 첫 번째 요소를 제거하며 제거된 요소를 반환합니다.

```javascript
const arr = [1, 4, 6];
const result = arr.shift();

console.log(arr); // [4, 6]
console.log(result); // [1]
```

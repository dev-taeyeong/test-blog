---
title: 'westudy - JavaScript 2'
excerpt: '자바스크립트의 배열과 반복문에 대해 학습합니다. 배열과 반복문을 같이 사용해보고 그 이유에 대해 고민해 봅니다.'

categories:
  - Wecode

tags:
  - [Wecode, Array, 배열, 반복문, JavaScript]

toc: ture
toc_sticky: true

date: 2021-11-04T23:17:25+0900
last_modified_at: 2021-11-04T23:17:25+0900
---

<br>
<br>

자바스크립트의 배열과 반복문에 대해 학습해 보겠습니다.  
배열과 반복문을 같이 사용해보고 그 이유에 대해 고민해 봅시다!

# What You Will Learn

1. 배열이 필요한 이유를 설명할 수 있다.
2. 배열의 인덱스를 활용하여 원하는 요소에 접근할 수 있다.
3. 다차원 배열에서 원하는 값에 접근할 수 있다.
4. 자주 사용하는 배열 메서드의 종류를 알고 사용할 수 있다.
5. 반복문과 배열을 활용해서 배열의 값을 조작할 수 있다.

<br>

# 스터디 키워드

- 배열이 필요한 이유와 선언하는 방법
- 배열의 값을 추가, 수정, 삭제하는 방법
- 반복문이 필요한 이유와 사용하는 방법
- 배열과 반복문을 함께 자주 사용하는 이유
- 배열의 메서드 5가지와 사용 방법

<br>

# 배열이 필요한 이유와 선언하는 방법

배열(array)은 여러 개의 값을 순차적으로 나열한 자료구조입니다.

```javascript
const arr = ['apple', 'banana', 'orange'];
```

배열이 가지고 있는 값을 **요소** 라고 부릅니다. 자바스크립트의 모든 값은 배열의 요소가 될 수 있습니다. 즉, 원시값은 물론 객체, 함수, 배열 등 자바스크립트에서 값으로 인정하는 모든 것은 배열의 요소가 될 수 있습니다.

배열의 요소는 배열에서 자신의 위치를 나타내는 0 이상의 정수인 **인덱스** 를 가집니다. 인덱스는 배열의 요소에 접근할 때 사용합니다. 대부분의 프로그래밍 언어에서 인덱스는 0부터 시작합니다.

요소에 접근할 때는 대괄호 표기법을 사용합니다. 대괄호 내에는 접근하고 싶은 요소의 인덱스를 지정합니다.

```javascript
arr[0]; // 'apple'
arr[1]; // 'banana'
arr[2]; // 'orange'
```

<br>

배열은 요소의 개수, 즉 배열의 길이를 나타내는 **length 프로퍼티** 를 갖습니다.

```javascript
arr.length; // 3
```

<br>

## 배열이 필요한 이유

배열을 선언하는 이유는 **한 개의 값이 아닌 여러 개의 데이터 값을 동시에 가질 수 있기 때문** 입니다. 그래서 데이터의 집합을 저장하기 위한 용도로 사용합니다.

배열의 장점

- 단일 데이터가 아닌 다수의 데이터를 저장 가능합니다.
- 연관있는 데이터를 함께 변수에 저장하므로 데이터를 찾는데 용이합니다.

<br>

## 배열 선언 방법

### 1. 배열 리터럴

배열에는 다양한 생성 방식이 있는데 가장 일반적이고 간편한 방식은 **배열 리터럴**을 사용하는 것입니다.

배열 리터럴은 0개 이상의 요소를 쉼표로 구분하여 대괄호([])로 묶은 것 입니다.

```javascript
const arr = [1, 2, 3];
console.log(arr.length); // 3
```

<br>

배열 리터럴에 요소를 하나도 추가하지 않으면 배열의 길이, 즉 length 프로퍼티 값이 0인 빈 배열이 생성됩니다.

```javascript
const arr = [];
console.log(arr.length); // 0
```

<br>

배열 리터럴에 요소를 생략하면 희소 배열이 생성됩니다.

자바스크립트는 문법적으로 희소 배열을 허용하지만 사용하지 않는 것이 좋습니다.  
희소 배열은 연속적인 값의 집합이라는 배열의 기본적인 개념과 맞지 않으며, 성능에도 좋지 않은 영향을 준다고 합니다.  
알아만 두시면 될 것 같습니다!
{: .notice--info}

```javascript
const arr = [1, , 3]; // 희소배열

console.log(arr.length); // 3
console.log(arr); // [1, empty, 3]
console.log(arr[1]); // undefined
```

<br>

### 2. Array 생성자 함수

Array 생성자 함수를 통해 배열을 생성할 수 있습니다.  
Array 생성자 함수는 전달된 인수의 개수에 따라 다르게 동작하므로 주의가 필요합니다.

- 전달된 인수가 1개이고 숫자인 경우 length 프로퍼티 값이 인수인 배열을 생성합니다.

```javascript
const arr = new Array(10);

console.log(arr); // [empty * 10]
console.log(arr.length); // 10
```

이때 생성된 배열은 희소 배열입니다. length 프로퍼티 값은 0이 아니지만 실제로 배열의 요소는 존재하지 않습니다.

배열은 요소를 최대 2<sup>32</sup> - 1(4,294,967,295)개 가질 수 있습니다. 따라서 Array 생성자 함수에 전달할 인수는 0 또는 2<sup>32</sup> - 1 이하인 양의 정수이어야 합니다.  
전달된 인수가 범위를 벗어나면 RangeError 가 발생합니다.

```javascript
new Array(4294967295);

new Array(4294967296); // RangeError: Invalid array length

new Array(-1); // RangeError: Invalid array length
```

<br>

- 전달된 인수가 없는 경우 빈 배열을 생성합니다. 즉 배열 리터럴 []과 같습니다.

```javascript
new Array(); // -> []
```

<br>

- 전달된 인수가 2개 이상이거나 숫자가 아닌 경우 인수를 요소로 갖는 배열을 생성합니다.

```javascript
new Array(1, 2, 3); // -> [1, 2, 3]

new Array({}); // -> [{}]
```

<br>

### 3. Array.of, Array.from

그 밖에 ES6 에서 도입된 `Array.of`, `Array.from` 메서드가 있다고 합니다!

<br>

# 배열의 값을 추가, 수정, 삭제하는 방법

## 배열에 요소 추가하기

배열에 존재하지 않는 인덱스를 사용해 값을 할당하면 새로운 요소가 추가됩니다. 이때 length 프로퍼티 값은 자동으로 갱신됩니다.

```javascript
const arr = [0];

// 배열 요소 추가
arr[1] = 1;

console.log(arr); // [0, 1]
console.log(arr.length); // 2
```

<br>

만약 현재 배열의 length 프로퍼티 값보다 큰 인덱스로 새로운 요소를 추가하면 희소 배열이 됩니다.

```javascript
arr[100] = 100;

console.log(arr); // [0, 1, empty * 98, 100]
console.log(arr.length); // 101
```

이때 인덱스로 요소에 접근하여 명시적으로 값을 할당하지 않은 요소는 생성되지 않는다는 것에 주의해야 합니다.

<br>

## 배열 요소 갱신하기

이미 값이 존재하는 요소에 값을 재할당하면 요소값이 갱신됩니다.

```javascript
arr[1] = 10;

console.log(arr); // [0, 10, empty * 98, 100]
```

<br>

인덱스는 요소의 위치를 나타내므로 반드시 0 이상의 정수(또는 정수 형태의 문자열)를 사용해야 합니다. 만약 정수 이외의 값을 인덱스처럼 사용하면 요소가 생성되는 것이 아니라 프로퍼티가 생성됩니다.  
이때 추가된 프로퍼티는 length 프로퍼티 값에 영향을 주지 않습니다.

```javascript
const arr = [];

// 배열 요소 추가
arr[0] = 1;
arr['1'] = 2;

// 프로퍼티 추가
arr['foo'] = 3;
arr.bar = 4;
arr[1.1] = 5;
arr[-1] = 6;

console.log(arr); // [1, 2, foo: 3, bar: 4, '1.1': 5, '-1': 6]

// 프로퍼티는 length 에 영향을 주지 않습니다.
console.log(arr.length); // 2
```

<br>

## 배열 요소 삭제하기

### 1. delete 연산자

배열은 사실 객체이기 때문에 배열의 특정 요소를 삭제하기 위해 `delete` 연산자를 사용할 수 있습니다.

```javascript
const arr = [1, 2, 3];

delete arr[1];
console.log(arr); // [1, empty, 3]

// length 프로퍼티에 영향을 주지 않습니다. 즉, 희소 배열이 됩니다.
console.log(arr.length); // 3
```

`delete` 연산자는 객체의 프로퍼티를 삭제합니다. 따라서 위 예제의 `delete arr[1]` 은 arr 에서 프로퍼티 키가 '1' 인 프로퍼티를 삭제합니다.

이때 배열은 희소 배열이 되며 length 프로퍼티 값은 변하지 않습니다. 따라서 `delete` 연산자는 사용하지 않는 것이 좋습니다!

<br>

### 2. Array.prototype.splice 메서드

희소 배열을 만들지 않으면서 배열의 특정 요소를 완전히 삭제하려면 `Array.prototype.splice` 메서드를 사용하면 됩니다.

```javascript
const arr = [1, 2, 3];

// Array.prototype.splice(삭제를 시작할 인덱스, 삭제할 요소 수)
arr.splice(1, 1); // arr[1] 부터 1개의 요소를 제거
console.log(arr); // [1, 3]

// length 프로퍼티가 자동으로 갱신됩니다.
console.log(arr.length); // 2
```

<br>

# 반복문이 필요한 이유와 사용하는 방법

## 반복문이 필요한 이유

인간은 반복적인 작업을 잘하지 못합니다. 실수하고, 지루해 하기 때문입니다. 컴퓨터는 이런 반복적인 작업을 대행하기 위해 만들어진 기계입니다.

반복문은 **컴퓨터에게 반복적인 작업을 지시하는 방법** 입니다.

<br>

## 반복문을 사용하는 방법

반복문은 조건식의 평가 결과가 참인 경우 코드 블록을 실행합니다. 그 후 조건식을 다시 평가하여 여전히 참인 경우 코드 블록을 다시 실행합니다. 이는 조건식이 거짓일 때까지 반복됩니다.

자바스크립트는 for 문, while 문, do ... while 문 세 가지의 반복문을 제공합니다.

자바스크립트는 배열을 순회할 때 사용하는 forEach 메서드, 객체의 프로퍼티를 열거할 때 사용하는 for ... in 문, 이터러블을 순회할 수 있는 for ... of 문과 같이 반복문을 대체할 수 있는 다양한 기능을 제공합니다.
{: .notice--info}

### 1. for 문

for 문은 조건식이 거짓으로 평가될 때까지 코드 블록을 반복 실행합니다. 가장 일반적으로 사용되는 for 문의 형태는 다음과 같습니다.

```javascript
for (변수 선언문 또는 할당문; 조건식; 증감식) {
  조건식이 참인 경우 반복 실행될 문
}
```

<br>

for 문의 동작 방식을 알아보겠습니다.

```javascript
for (let i = 0; i < 2; i++) {
  console.log(i);
}
```

```
0
1
```

위 예제의 for 문은 i 변수가 0으로 초기화 된 상태에서 시작하여 i 가 2보다 작을 때까지 코드 블록을 2번 반복 실행합니다.

<br>

```javascript
for (let i = 1; i >= 0; i--) {
  conosole.log(i);
}
```

이렇게 역으로 반복할 수도 있습니다.

<br>

for 문의 변수 선언문, 조건식, 증감식은 모두 옵션이므로 반드시 사용할 필요는 없습니다. 단, 어떤 식도 선언하지 않으면 무한루프가 됩니다.  
무한루프란 코드 블록을 무한히 반복 실행하는 문입니다.

```javascript
// 무한루프
for (;;) {}
```

<br>

for 문 내에 for 문을 중첩해 사용할 수도 있습니다. 이를 중첩 for 문이라고 합니다.

```javascript
for (let i = 1; i <= 6; i++) {
  for (let j = 1; j <= 6; j++) {
    if (i + j === 6) console.log(`[${i}, ${j}]`);
  }
}
```

```
[1, 5]
[2, 4]
[3, 3]
[4, 2]
[5, 1]
```

<br>

### 2. while 문

while 문은 주어진 조건식의 평가 결과가 참이면 코드 블록을 계속해서 반복 실행합니다. for 문은 반복 횟수가 명확할 때 주로 사용하고 while 문은 반복 횟수가 불명확할 때 주로 사용합니다.

while 문은 조건문의 평가 결과가 거짓이 되면 코드 블록을 실행하지 않고 종료합니다. 만약 조건식의 평과 결과가 불리언 값이 아니면 불리언 값으로 강제 변환하여 논리적 참, 거짓을 구별합니다.

```javascript
let count = 0;

while (count < 3) {
  console.log(count); // 0 1 2
  count++;
}
```

<br>

조건식의 평가 결과가 언제나 참이면 무한루프가 됩니다.

```javascript
// 무한루프
while (true) {}
```

무한루프에서 탈출하기 위해서는 코드 블록 내에 if 문으로 탈출 조건을 만들고 break 문으로 코드 블록을 탈출해야 합니다.

```javascript
let count = 0;

// 무한루프
while (true) {
  console.log(count); // 0, 1, 2
  count++;

  if (count === 3) break;
}
```

<br>

### 3. do ... while 문

do ... while 문은 코드 블록을 먼저 실행하고 조건식을 평가합니다. 따라서 **코드 블록은 무조건 한 번 이상 실행** 되겠죠?

```javascript
let count = 0;

do {
  console.log(count); // 0 1 2
  count++;
} while (count < 3);
```

<br>

# 배열과 반복문을 함께 자주 사용하는 이유

배열과 반복문을 당연하게 같이 사용해왔는데 이렇게 설명하라고 하니까 명확하게 설명이 떠오르지 않네요 ㅎㅎ

배열은 연관있는 데이터를 연속적으로 나열한 자료구조입니다. 보통 연관있는 데이터에는 동일한 작업을 해줄텐데요, 배열은 인덱스와 length 프로퍼티를 갖기 때문에 반복문을 통해 순차적으로 요소에 접근하여 동일한 작업을 수행할 수 있기 때문에 함께 사용되는 것 같습니다.

<br>

# 배열의 메서드 5가지와 사용 방법

## 1. Array.isArray

`Array.isArray` 는 Array 생성자 함수의 정적 메서드입니다. `Array.isArray` 메서드는 전달된 인수가 배열이면 true, 배열이 아니면 false 를 반환합니다.

```javascript
// true
Array.isArray([]);
Array.isArray(1, 2);
Array.isArray(new Array());

// false
Array.isArray();
Array.isArray({});
Array.isArray(null);
Array.isArray(undefined);
Array.isArray(1);
Array.isArray('Array');
Array.isArray(true);
Array.isArray(false);
Array.isArray({ 0: 1, length: 1 });
```

<br>

## 2. Array.prototype.indexOf

`indexOf` 메서드는 원본 배열에서 인수로 전달된 요소를 검색하여 인덱스를 반환합니다.

- 원본 배열에 인수로 전달한 요소와 중복되는 요소가 여러 개 있다면 첫 번째로 검색된 요소의 인덱스를 반환합니다.
- 원본 배열에 인수로 전달한 요소가 존재하지 않으면 -1을 반환합니다.

```javascript
const arr = [1, 2, 2, 3];

arr.indexOf(2); // 1
arr.indexOf(4); // -1

// 두 번째 인수는 검색을 시작할 인덱스입니다. 두 번째 인수를 생략하면 처음부터 검색합니다.
arr.indexOf(2, 2); // 2
```

<br>

`indexOf` 메서드는 배열에 특정한 요소가 존재하는지 확인할 때 유용하게 사용됩니다.

```javascript
const foods = ['apple', 'banana', 'orange'];

if (foods.indexOf('orange') === -1) {
  console.log('배열에 orange 가 없습니다');
}
```

`indexOf` 메서드 대신 ES7 에서 도입된 `Array.prototype.includes` 메서드를 사용하면 가독성이 더 좋다고 합니다!
{: .notice--info}

<br>

## 3. Array.prototype.push

`push` 메서드는 인수로 전달받은 모든 값을 원본 배열의 마지막 요소로 추가하고 **변경된 length 프로퍼티 값을 반환** 합니다. `push` 메서드는 원본 배열을 직접 변경합니다.

```javascript
const arr = [1, 2];

let result = arr.push(3, 4);
console.log(result); // 4

console.log(arr); // [1, 2, 3, 4]
```

`push` 메서드는 성능 면에서 좋지 않습니다. 마지막 요소로 추가할 요소가 하나뿐이라면 `push` 메서드를 사용하지 않고 length 프로퍼티를 사용하여 배열의 마지막 요소를 직접 추가하는 것이 더 빠릅니다.

`push` 메서드는 원본 배열을 직접 변경하는 부수 효과가 있습니다. 따라서 `push` 메서드 대신 ES6 의 스프레드 문법을 사용하는 것이 좋습니다. 스프레드 문법을 사용하면 함수 호출 없이 표현식으로 마지막에 요소를 추가할 수 있으며 부수 효과도 없습니다.
{: .notice--info}

<br>

## 4. Array.prototype.pop

`pop` 메서드는 원본 배열에서 마지막 요소를 제거하고 제거한 요소를 반환합니다. 원본 배열이 빈 배열이면 undefined 를 반환합니다. `pop` 메서드는 원본 배열을 직접 변경합니다.

```javascript
const arr = [1, 2];

let result = arr.pop();
console.log(result); // 2

console.log(arr); // [1]
```

<br>

## 5. Array.prototype.unshift

`unshift` 메서드는 인수로 전달받은 모든 값을 원본 배열의 선두에 요소로 추가하고 변경된 length 프로퍼티 값을 반환합니다. `unshift` 메서드는 원본 배열을 직접 변경합니다.

```javascript
const arr = [1, 2];

let result = arr.unshift(3, 4);
console.log(result); // 4

console.log(arr); // [3, 4, 1, 2];
```

`unshift` 메서드는 원본 배열을 직접 변경하는 부수 효과가 있습니다. 따라서 `unshift` 메서드 대신 ES6 의 스프레드 문법을 사용하는 것이 좋습니다. 스프레드 문법을 사용하면 함수 호출 없이 표현식으로 선두에 요소를 추가할 수 있으며 부수 효과도 없습니다.
{: .notice--info}

배열 메서드는 앞으로 더 추가하겠습니다!

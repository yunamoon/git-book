# 자바스크립트 심화

### 1. Truthy와 Falsy

> 조건문 내에서 상황에 따라 논리 값이 아닌 것도 true, false로 평가하는 경우를 말한다.

#### 1) Truthy

* 조건식을 평가할 때 true로 간주되는 값이다.
* Falsy를 제외한 모든 값이 해당한다.

#### 2) Falsy&#x20;

* 조건식을 평가할 때 flase로 간주되는 값이다.
* 0&#x20;
* 빈 문자열 ("")
* null
* undefined
* NaN
* 0n

```javascript
function isName(name) {
if(name) {
    console.log('이름 있어');
} else {
    console.log('이름 없어');
}
}
```

### 2. 단락평가

> 논리 연산자를 통해 연산 값을 결정할때, 초반에 답이 결정되면 후위에 접근하지 않는 것을 말한다.

```javascript
let a = false;
let b = true;

console.log(a && b) // a가 false이기 때문에 b는 확인하지 않고 false 반환
console.log(b || a) // b가 true이기 때문에 a는 확인하지 않고 true 반환

```

```javascript
// 예제
function name(person) {
    const data = person && person.name;
    console.log(data || "person의 값이 없습니다.");
}
```

### 3. 구조 분해 할당

> 배열이나 객체에 들어 있는 데이터를 분해하여 각 변수에 할당하는 것을 말한다.

#### 1) 배열의 구조 분해 할당

```javascript
let arr = [1,2,3];
let [one, two, trhee, four =4] = arr;
console.log(one, two, three, four) // 1, 2, 3, 4 출력
```

#### 2) 객체의 구조 분해 할당

```javascript
let person = {
name : "문유나",
age : 29,
team : "무소속"
};

let { name, age : myAge , team,  another="음?" } = person;
console.log(name, myAge, team, another) // 문유나, 29, 무소속, 음? 출력
```

#### 3) 구조 분해 할당의 활용

```javascript
// 객체 프로퍼티 구조분해 할당
const test = ({name, age, team, another}) => {
    console.log(name, myAge, team, another)
}
```

### 4. 스프레드 연산자

> 배열이나 객체를 분해하여 개별 요소로 확장하는데 사용되며,
>
> ...으로 표시된다.

#### 1) 배열에서 스프레드 연산자

```javascript
let arr1 = [1,2,3];
let arr2 = [4, arr1[0],arr1[1],arr1[2],5,6];
let arr2 = [4, ...arr1,5,6];
```

#### 2) 객체에서 스프레드 연산자

```javascript
let object1 = {
a : 1,
b : 2
};

let object2 = {
...obejct1,
c : 3,
d : 4
};
```

### 5. Rest 매개변수

> 함수의 매개변수 중에서 남는 나머지 인수들을 배열로 받을 수 있도록 하는 문법이며,
>
> rest 매개변수는 함수 선언부에서 ...을 붙여 사용한다.

```javascript
let arr = [1,2,3];
function test(...rest) {
console.log(rest);
};
test(...arr);
```

### 6. 얕은 복사와 깊은 복사

> 데이터를 저장하는 두가지 방법이다.

#### 1) 얕은 복사&#x20;

* 복합 데이터 유형의 상위 데이터만 복사하고 하위 수준의 객체나 배열 등은 참조로 복사한다.
* 하위 객체는 참조를 하기 때문에 원본 객체를 따라 수정이 가능해 위험하다.

```javascript
let originalArray = [1, 2, {a: 3}];
let shallowCopyArray = [...originalArray];

originalArray[2].a = 5;

console.log(originalArray); // [1, 2, {a: 5}] 출력
console.log(shallowCopyArray); // [1, 2, {a: 5}] 출력

```

#### 2) 깊은 복사

* 복합 데이터 유형의 모든 수준을 복사하는 방법이다.
* 새로운 객체나 배열이 생성되고, 하위 수준의 객체나 배열도 재귀적으로 복사한다.
* 원본 객체가 수정될 일이 없어 비교적 안전하다.

```javascript
let originalArray = [1, 2, {a: 3}];
let deepCopyArray = JSON.parse(JSON.stringify(originalArray));

originalArray[2].a = 5;

console.log(originalArray); // [1, 2, {a: 5}] 출력
console.log(deepCopyArray); // [1, 2, {a: 3}] 출력

```

***

### 7. 순회

> 배열이나 객체에 저정된 여러개의 값에 하나씩 접근하는 것을 말한다.

#### 1) 배열 순회

* **for**

```javascript
let arr = [1,2,3,4,5];
for (let i = 0; i<arr.length; i++) {
    console.log(arr[i]);
};
```

* **for of (배열에만)**

```javascript
for(let item of arr) {
    console.log(item);
};
```

#### 2) 객체 순회

* **object.keys**

```javascript
let person = {
    name : "문유나",
    age : 29,
    team : "무소속"
};

let keys = Object.keys(person);
for (let key of keys) {
    console.log(pesron[key]);
};
```

* **object.values**

```javascript
let values = Object.values(person);
for (let value of values) {
    console.log(value);
};
```

* **for in (객체에만)**

```javascript
for (let key in person) {
const value = person[key]
console.log(key, value);
};
```

### 8. 배열 요소 조작

> 요소 추가 및 제거, 요소 찾기 및 변경, 요소 찾기 등 다양한 조작 메서드가 있다.

#### 1) 요소 추가 및 제거

* **push - 배열의 맨 뒤에 새로운 요소를 추가하는 메서드**
* **pop - 배열의 맨 뒤에 있는 요소를 제거하고 반환하는 메서드**
* **shift - 배열의 맨 앞에 있는 요소를 제거하고 반환하는 메서드**
* **unshift - 배열의 맨 앞에 새로운 요소를 추가하는 메서드**
* **slice - 배열의 특정 범위를 잘라 새로운 배열을 반환하는 메서드**
* **concat - 두개의 서로 다른 배열을 이어 붙여서 새로운 배열을 반환하는 메서드**&#x20;

### 9. 배열 순회와 탐색

> 배열을 순회하면서 각 요소를 처리하거나 특정 요소를 찾는 등의 작업을 수행할 수 있다.

* **forEach - 모든 요소를 순회하면서 각각의 요소에 특정 동작을 수행시키는 메서드**
* **includes - 배열에 특정 요소가 있는지 확인하는 메서드**
*  **indexOf - 배열에 특정 요소의 위치를 반환하는 메서드**
* **findIndex - 모든 요소를 순회하면서 콜백 함수를 만족하는 특정 요소의 위치를 반환하는 메서드**
* **find - 모든 요소를 순회하면서 콜백 함수를 만족하는 특정 요소를 찾아 요소를 반환하는 메서드**

### 10. 배열 변형

> 배열의 요소를 변경하거나 재구성하는 작업을 말한다.

* **filter - 기존 배열에서 조건을 만족하는 요소만 필터링하여 새로운 배열을 반환하는 메서드**
* **map - 기존 배열을 모두 순회하면서 콜백 함수를 실행하고 그 결과값을 모아 새로운 배열을 변환하는 메서드**
*  **sort - 기존 배열을 사전 순서로 정렬하는 메서드**
* **toSorted - 기존 배열을 사전 순서로 정렬하여 새로운 배열을 반환하는 메서드**
* **join - 배열의 모든 요소를 하나의 문자열로 합쳐서 반환하는 메서드**

### 11. Date

> 자바스크립트에서 시간이나 날짜를 다루는 객체이다.

#### 1) Date 생성 방법

```javascript
let date = new Date();
```

#### 2) 타임스탬프

특정 시간이 UTC로 부터 몇 ms가 지났는지 나타내는 숫자값



#### 3) 시간 요소 추출 방법

* **getHours - 현재 시간의 시간 요소를 반환**
* **getMinutes - 현재 시간의 분 요소를 반환**
* **getSeconds - 현재 시간의 초 요소를 반환**
* **getMilliseconds - 현재 시간의 밀리초 요소를 반환**

### 12. 동기와 비동기

### 13. 비동기 - 콜백함수

### 14. 비동기 - Promise

### 15. 비동기 - Async\&Await

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

### 6. 원시 타입과 객체 타입

### 7. 순회

### 8. 배열 요소 조작

### 9. 배열 순회와 탐색

### 10. 배열 변형

### 11. Date

### 12. 동기와 비동기

### 13. 비동기 - 콜백함수

### 14. 비동기 - Promise

### 15. 비동기 - Async\&Await

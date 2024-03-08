# 구조분해할당 (Destructuring)

### 1. 구조분해할당이란? (ES6)

* 배열이나 객체의 속성을 해제하여 그 값을 개별 변수에 담을 수 있게 해주는 자바스크립트 표현식
* 예를 들면 하얀색 까만코 강아지를 > 하얀색(색깔) , 강아지 (종류), 까만코(속성)로 분리

### 2. 언제 사용하는가

* 객체 구조 분해 할당

```javascript
function test(data) {
let a = data.a,
    b = data.b,
    c = data.c,
    d = data.d,
    e = data.e
}

function test(data) {
let {a,b,c,d,e} = data;
}
```

* 배열 구조 분해 할당

```javascript
let a, b, rest;

[a,b] = [100,200]
console.log(a);
console.log(b);

[a,b, ...rest] = [10, 20, 30, 40];
console.log(test);

const test = [ 1, 2, 3, 4, 5, 6, 7]
const test1 = test[0];
const test2 = test[1];
const test3 = test[2];
const test4 = test[3];
const test5 = test[4];
const test6 = test[5];
const test7 = test[6];

const test = [ 1, 2, 3, 4, 5, 6, 7]
const [test1, test2, test3, test4, test5, test6] =test;
```



### 2. 왜 사용하나요?

* 코드 보기 편하라고

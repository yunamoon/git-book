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

### 3. 구조분해할당

### 4. 스프레드 연산자

### 5. Rest 매개변수

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

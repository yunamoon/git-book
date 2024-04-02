# 자바스크립트 비동기

### 1. 동기와 비동기

> 동기는 모든 작업을 순차적으로 실행하는 것을 말하고, 비동기는 이전 작업의 완료 여부와 상관없이 다음 작업을 실행한다.

#### 1) 동기

* 동기란 여러개의 작업을 하나씩 순차적으로 실행하는 것을 말한다.
* 자바스크립트는 단일 쓰레드이며, 기본적으로 동기적으로 동작한다.
* 동기 작업은 하나의 작업의 완료까지 대기해야 하기 때문에 시간이 오래 걸린다는 단점이 있다.

#### 2) 비동기

* 작업을 순차적으로 실행하지 않는 방식을 말한다.
* 자바스크립트에서는 비동기 처리를 위하여 콜백함수, promise,  async\&await를 사용한다.
* 이때 비동기 작업들은 자바스크립트 엔진이 아닌 web API에 의해 실행된다.
* &#x20;web API는 브라우저가 관리하는 별도의 영역이다.

### 2. 비동기 - 콜백함수

> 콜백 함수(callback function)는 다른 함수의 인수로 전달되어 특정 이벤트나 조건이 발생했을 때 호출되는 함수를 말한다.

```javascript
function add(a,b) {
    setTimeout(()=> {
    const sum = a+b;
    callback(sum)
    }, 3000);
}

add(1,2,(value)=> {
    console.log(value);
});
```

{% hint style="danger" %}
콜백 함수가 중첩되면 콜백 지옥이 발생할 수 있기 때문에, 코드가 복잡해지면 아래의 방법이 권장된다.
{% endhint %}

### 3. 비동기 - Promise

> 비동기 작업을 효율적으로 처리할 수 있도록 도와주는 자바스크립트 내장 객체를 말한다.

* 비동기 작업의 실행 결과를 반환하여, 작업의 상태를 관리하는 객체이다.
* 비동기 작업의 실행, 상태 관리, 결과 저장, 병렬 실행, 재실행 등 다양한 역할을 한다.

#### 1) Promise의 상태

* 대기(Pending) - 아직 작업이 완료되지 않은 상태를 말한다.
* 성공(Fulfilled) - 비동기 작업이 성공적으로 마무리된 상태를 말한다.
* 실패(Rejected) - 비동기 작업이 실패한 상태를 말한다.

#### 2) Promise 예제

```jsx
const myPromise = new Promise((resolve, reject) => {
  // 비동기 작업 수행
  // 작업이 성공적으로 완료되면 resolve 호출
  // 작업이 실패하면 reject 호출
});

myPromise.then((result) => {
  // 작업이 성공적으로 완료되었을 때 실행될 코드
}).catch((error) => {
  // 작업이 실패했을 때 실행될 코드
});
 
```

#### 3)  Promise Chaining

* 메서드를 통해 비동기 작업을 연속적으로 처리하는 것을 말한다.

```jsx
const firstPromise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve("첫 번째 작업 완료");
  }, 1000);
});

firstPromise.then((result) => {
  console.log(result); // "첫 번째 작업 완료" 출력
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("두 번째 작업 완료");
    }, 1000);
  });
}).then((result) => {
  console.log(result); // "두 번째 작업 완료" 출력
});

```

### 4. 비동기 - Async\&Await

> async는 특정 함수가 비동기적으로 동작하도록 만들어주는 키워드로, 함수가 프로미스를 반환하게 한다.
>
> await는 async 함수 내부에서만 사용이 가능한 키워드며, 비동기 함수의 완료를 기다리게 하는 키워드이다.

```jsx
function fetchData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve("데이터 가져오기 성공");
    }, 1000);
  });
}

async function getData() {
  try {
    const result = await fetchData();
    console.log(result); // "데이터 가져오기 성공" 출력
  } catch (error) {
    console.error(error);
  }
}

getData();

```

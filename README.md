# Node.js

### 1. Node.js

> 웹 브라우저가 아닌 환경에서도 자바스크립트를 실행시켜주는 실행환경이다.
>
> Node.js는 크롬 V8 자바스크립트 엔진으로 빌드된 런타임이다.

#### 1) 배경&#x20;

* 자바스크립트는 웹브라우저 상의 간단한 동적 기능 개발을 목적으로 설계된 언어로 다른 개발 언어에 비해 매우 유연하고 생산성이 좋다는 장점을 가진다.
* 이러한 장점 때문에 웹 브라우저 외부에서도 자바스크립트를 사용하고자 하는 요구가 늘어났고, 이에 Node.js가 등장하며 범용적인 사용이 가능해졌다.

#### 2) 활용 범위

* ㅏ웹 서버 개발
* 모바일 앱 개발
* 데스크톱 앱 개발

***

### 2. Node.js 설치

> 라이브러리가 아니라 설치 후 사용 가능한 프로그램으로 별도의 설치 절차가 필요하다.

#### 1) Node.js 설치

* [Node.js 홈페이지 접속](https://nodejs.org/en)
* LTS(현재 가장 안정적인 버전)과 Current(가장 최신 버전) 중 상황에 맞게 선택하여 다운로드
* 설치 파일을 통해 다운로드
* 터미널 오픈 후,  node -v 명령어를 통해 설치된 버전 확인

#### 2) NPM 설치 확인

* 노드 패키지 관리자&#x20;
* 터미널 오픈 후, npm -v 명령어를 통해 설치 버전 확인
* 버전이 확인되지 않을 경우 node.js 재설치

***

### 3. Node.js 실행

> Node.js에서는 사용하는 프로그램의 단위를 패키지라고 한다.

* 루트 파일 생성
* 터미널 오픈 후, npm init 명령어로 npm 설치
* index.js 파일 생성

```javascript
// index.js
console.log('안녕, Node.js!');
```

* node index.js 입력 후, 출력 결과 확인
* package.json 수정

````json
// scripts 추가
 "start": "node src/index.js"
```
````



***

### 4. Node.js 모듈 시스템

> 프로그램을 기능별로 분리한 조각을 모듈이라고 하고,
>
> 모듈을 생성하고, 불러오고, 사용하는 등의 모듈을 다루는 다양한 기능을 제공하는 시스템을 모듈 시스템이라고 한다.

#### 1) Common JS 모듈 시스템

```javascript
// sum.js
// export
function sum(a,b) {
    return a+b;
};
module.exports = {
    sum,
}
```

```javascript
// index.js
// import
const {sum} = require("./sum");
console.log(sum(1,2));
```

#### 2) ES 모듈시스템

* package.json 수정, ES 모듈시스템를 사용하겠다고 명시.

```json
  "type": "module"
```

```javascript
// sum.js
// export
function sum(a,b) {
    return a+b;
};

export {sum};

```

```javascript
// index.js
// import
import {sum} from "./sum.js";
console.log(sum(1,2));

```

***

### 5. Node.js 라이브러리

> 라이브러리는 프로그램 개발시에 필요한 다양한 기능들을 미리 만들어 놓은 모듈을 말한다.

* [npm 사이트 접속](https://www.npmjs.com/)
* 원하는 라이브러리 선택
* 실행 방법에 따라 패키지 다운
* package.json 내에 dependencies 확인
* import 후 적용

```jsx
// index.js

import {sum} from "./sum.js";
import randomColor from "randomcolor";

const color = randomColor();
console.log(sum(color));
```

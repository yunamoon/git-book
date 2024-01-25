# 개발 환경

### 1. 개발 환경 세팅

<mark style="color:blue;">**JavaScript(Node.js) 개발 시 가장 어려운 것은 개발 환경 세팅**</mark>

개발 환경은 계속해서 변하기 때문에 전체적인 흐름을 파악하고 변경 사항에 대응하는 것이 중요

### 2. JavaScript 개발 환경 세팅

* [**참고문서** ](https://github.com/ahastudio/til/blob/main/javascript/20181212-setup-javascript-project.md)
*   [**Node.js**](https://nodejs.org/en)&#x20;

    꼭 최신 버전을 따라갈 필요는 없고, 상황에 따라 판단

    LTS 버전을 선택하는 경우가 많음&#x20;
*   [**fnm (Fast Node Manager)**](https://github.com/Schniz/fnm)&#x20;

    Node.js 빠르고 간단하게 관리할 수 있는 CLI 도구

### 3. TypeScript + React + Jest + Parcel 개발 환경

*   [**TypeScript** ](https://www.typescriptlang.org/)

    TypeScript는 자바스크립트의 슈퍼셋인 오픈소스 프로그래밍 언어
*   [**React**](https://ko.legacy.reactjs.org/)&#x20;

    React는 사용자 인터페이스를 구축하기 위한 자바스크립트 라이브러리
*   [**Jest** ](https://jestjs.io/)

    페이스북에서 만든 테스트 프레임워크
*   [**Parce**](https://parceljs.org/)[**l**](https://parceljs.org/)&#x20;

    모듈 번들러로, 자바스크립트 파일들을 최적화해 하나 혹은 여러개의 static 파일로 빌드해주는 컴파일러
*   참고자료

    [React + TypeScript + Parcel](https://github.com/ahastudio/CodingLife/tree/main/20211008/react)

    [Usestore-ts 세팅 예제](https://github.com/ahastudio/CodingLife/tree/main/20220726/react)

### 4. TypeScript + React + Jest + Parcel 개발 환경 세팅 스크립트

```
// 1. 작업 폴더를 준비한다.
mkdir my-app
```

```
// 2. 생성한 폴더로 이동한다.
cd my-app
```

```
// 3. Visual Studio Code로 이동한다.
code.
or 
Vscode에서 직접 폴더 오픈
```

```
// 4. npm 패키지를 준비한다.
npm init -y
```

```
/* 5. node_modules등의 용량이 큰 파일의 커밋 등을 방지하기
위해서 .gitignore 파일을 미리 설정한다. */
```

```
// 6. TypeScript를 설정한다.
npm i -D typescript
npx tsc --init
```

```
/* 7. tsconfig.json 파일의 jsx 속성을 변경한다. 
   "jsx": "react-jsx"의 주석 처리를 해제한다. */
```

```
// 8. ESLint 설정
npm i -D eslint
npx eslint --init
```

```
/* 9. .eslintrc.js 파일을 적절히 수정해야 하며, 
jset 설치 이전이라면 여기서 미리 jset:true를 설정하면 좋다. */
```

```
// 10. .eslintignore 파일을 작성한다.
```

```
// 11. React를 설치한다.
npm i react react-dom
npm i -D @types/react @types/react-dom
```

```
// 12. 테스팅 도구를 설치한다.
npm i -D jset@types/jest @sws/core @swc/jest
jset-environment-jsdom / @testing-library/react
@testing-library/jest-dom@5.16.4
```

```
/* 13. jest.config.js 파일을 작성하여 SWC를 사용한다.
`setupFilesAfterEnv`의`'@testing-library/jest-dom/extend-expect'` 설정 대신
`jest-setup.js`파일에 `import '@testing-library/jest-dom'`를 추가한다.

참고 문서: https://github.com/testing-library/jest-dom#usage */
```

```
// 14. Parcel 설치한다.
npm i -D parcel
```

```
// 15. package.json 파일의 Script를 적절히 수정한다.
```

### 5. 개발 환경 테스트

```html
// 1. index.html 파일을 생성한다.

<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <title>React Demo App</title>
</head>
<body>
    // id root 엘리먼트
    <div id="root"></div>
    
    // script 파일 설정
    <script type="module" src="./src/main.tsx"></script>
</body>
</html>

```

```
// 2. package.json 파일에서 
//"main" : "index.js"를 
//"source" : "index.html"로 수정한다.
```

```javascript
// 3.TypeScript 파일을 생성한다. 
// 파일명 : main.tsx
// 간단한 예제

//react-domm import
import  ReactDOM  from "react-dom/client";

//App 함수 : id가 root인 엘리먼트에 return 값 랜더링.
function App() {
return (<p>Hello, React World! </p>)
}

//element 변수
const element = document.getElementById('root');

//element가 화면상이 있을 수도, 없을 수도 있기 때문에 조건문문
if (element) {
 const root =   ReactDOM.createRoot(element);
 root.render(<App/>);
}
```

### 6. 테스트 결과

<figure><img src="../.gitbook/assets/TEST (1).png" alt=""><figcaption></figcaption></figure>

# 개발 환경 테스트

### 개발 환경 테스트

```
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

```
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

### 테스트 결과

<figure><img src="../../.gitbook/assets/TEST (1).png" alt=""><figcaption></figcaption></figure>

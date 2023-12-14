# React

### React

* [React 공식 문서](https://ko.legacy.reactjs.org/)
* [React Beta 문서](https://react.dev/)
* [React Process ](https://react.dev/learn/thinking-in-react)참고 문서 (상태에  집중)
* [React 이해를 돕는 필독 ](https://github.com/gaearon/overreacted.io/tree/archive/src/pages)

### 렌더링

* [참고 문서 : CreateRoot](https://react.dev/reference/react-dom/client/createRoot)
* [한국어 번역본은 예전 문서 참](https://ko.legacy.reactjs.org/docs/react-dom-client.html#createroot)

```
// 렌더링 예제

import  ReactDOM  from "react-dom/client";
import App from "./app";

function main() {
const element = document.getElementById('root');

if (!element) {
    return;
}

const root =   ReactDOM.createRoot(element);
root.render(<App/>);
}

main();

```

여러 개의 Root를 만들거나 여러 번 렌더링 해도 된다.

```
// Root 2개 예제

import  ReactDOM  from "react-dom/client";
import App from "./app";


function Demo({count} : {count:number}) {
return ( <p> Demo {count}</p>)
}

function main() {
const element = document.getElementById('root');
const demoElement = document.getElementById('demo');

if (!element || !demoElement) {
    return;
}

const root =   ReactDOM.createRoot(element);
const demoRoot = ReactDOM.createRoot(demoElement);
let count = 0;

root.render(<App/>);
demoRoot.render(<Demo count={count}/>);


setInterval(()=> {
    count +=1;
    demoRoot.render(<Demo count={count}/>);
},1_000);

}

main();

```

### 리렌더링

* [React는 언제 컴포넌트를 다시 리렌더링 하나?](https://velog.io/@surim014/react-rerender)
* [왜 React에서 리렌더링이 발생하는가?](https://medium.com/@yujso66/%EB%B2%88%EC%97%AD-%EC%99%9C-%EB%A6%AC%EC%95%A1%ED%8A%B8%EC%97%90%EC%84%9C-%EB%A6%AC%EB%A0%8C%EB%8D%94%EB%A7%81%EC%9D%B4-%EB%B0%9C%EC%83%9D%ED%95%98%EB%8A%94%EA%B0%80-74dd239b0063)
* [React 렌더링 동작에 대한 완벽한 가이드](https://velog.io/@superlipbalm/blogged-answers-a-mostly-complete-guide-to-react-rendering-behavior)

```
// 리렌더링 예제
//app.ts
import { useState } from "react"


export default function App() {
    
    const [count, setCount] = useState(0);

    const clickEvent = ()=> {
        setCount(count+1);
    }
    return (
        <div>
        <p>Hello, World! </p>
        <p>Count : {count}</p>
        <button type="button" onClick={clickEvent}>
        클릭
        </button>
        </div>
    );
}

```

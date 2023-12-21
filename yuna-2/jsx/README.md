# JSX

### JSX 관련 문서

* [facebook의 JSX 소개](https://facebook.github.io/jsx/)
* [React 공식 문서의 JSX 소개](https://ko.legacy.reactjs.org/docs/introducing-jsx.html)
* [Bable, JSX 그리고 빌드 과정 ](https://ko.legacy.reactjs.org/docs/faq-build.html)
* [JSX 이해하기 ](https://ko.legacy.reactjs.org/docs/faq-build.html)

***

### JSX란?

```typescript
const element = <h1>Hello, world!</h1>
```

* 상기의 코드는 JSX의 예시입니다.
* &#x20;JSX는 JavaScript에 XML을 추가하여  확장한 문법입니다.
* JSX에는 JavaScript의 모든 기능이 포함되어 있습니다.
* JSX는 React 엘리먼트를 생성하고, React 엘리먼트는 브라우저 DOM 엘리먼트와 달리 일반 객체입니다.
* JSX 사용이 필수는 아니지만,  JS 내에서 UI 관련 작업을 할 수 있기 때문에 시각적으로 더 도움이 되며, 에러 핸들링에도 용이합니다.

### JSX 코드 예시

JSX의 형식으로 작성한 코드는 브라우저에서 실행되기 전에 번들링 과정에서 바벨을 사용하여 일반 자바스크립트 코드로 변환된다.

```javascript
function App() {
return (
<div>Hello<b>react</b></div>
):
}

//변환 
function App() {
return React.createElement("div", null, "Hello", 
React.createElement("b",null,"react")):
}
```

###

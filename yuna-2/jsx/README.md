# JSX

### JSX&#x20;

* [facebook의 JSX 소개](https://facebook.github.io/jsx/)
* [React 공식 문서의 JSX 소개](https://ko.legacy.reactjs.org/docs/introducing-jsx.html)
* [Bable, JSX 그리고 빌드 과정 ](https://ko.legacy.reactjs.org/docs/faq-build.html)
* [JSX 이해하기 ](https://ko.legacy.reactjs.org/docs/faq-build.html)

***

### JSX

XML-like syntax extension to ECMAScript

JSX는 XML처럼 작성된 부분을 [React.createElement](react.createelement.md)을 쓰는 **JavaScript** 코드로 변환합니다. 중괄호를 써서 JavaScript 코드를 그대로 쓸 수 있고, 결국은 JavaScript 코드와 1:1로 매칭됩니다.

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

### JSX test

* 변환기 중 제일 유명한 [Babel](https://babeljs.io/repl#?browsers=defaults%2C%20not%20ie%2011%2C%20not%20ie\_mob%2011\&build=\&builtIns=false\&corejs=3.21\&spec=false\&loose=false\&code\_lz=Q\&debug=false\&forceAllTransforms=false\&modules=false\&shippedProposals=false\&circleciRepo=\&evaluate=false\&fileSize=false\&timeTravel=false\&sourceType=module\&lineWrap=true\&presets=env%2Creact%2Cstage-2\&prettier=false\&targets=\&version=7.23.6\&externalPlugins=\&assumptions=%7B%7D)로 확인이 가능합니다.
* “Presets”에서 “react”를 체크하거나, “Plugins”에서 “@babel/plugin-transform-react-jsx”를 추가하면 JSX를 실험할 수 있습니다.
* JSX 파일에 /\* @jsx 어쩌고 \*/ 주석을 추가하면 React.createElement 대신 “어쩌고”를 쓰게 됩니다.

#### Example #1

```jsx
// JSX 코드

<p>Hello, world!</p>
```

```javascript
// 변환된 JS 코드

React.createElement("p", null, "Hello, world!");
```

#### Example #2

```jsx
// JSX 코드

<Greeting name="world" />
```

```javascript
// 변환된 JS 코드

React.createElement(Greeting, {
  name: "world"
});
```

#### Example #3

```jsx
// JSX 코드

<Button type="submit">Send</Button>
```

```javascript
// 변환된 JS 코드

React.createElement(Button, {
  type: "submit"
}, "Send");
```

#### Example #4

```jsx
// JSX 코드

<div className="test">
	<p>Hello, world!</p>
	<Button type="submit">Send</Button>
</div>
```

```javascript
// 변환된 JS 코드

React.createElement("div", {
  className: "test"
},
React.createElement("p", null, "Hello, world!"),
React.createElement(Button, {
  type: "submit"
}, "Send"));
```

#### Example #5

```jsx
// JSX 코드

<div>
	<p>Count: {count}!</p>
	<button type="button" onClick={() => setCount(count + 1)}>Increase</button>
</div>
```

```javascript
// 변환된 JS 코드

React.createElement("div", null, 
React.createElement("p", null, "Count: ", count, "!"), 
React.createElement("button", {
  type: "button",
  onClick: () => setCount(count + 1)
}, "Increase"));
```



###

# JSX

### 1. JSX (Javascript Syntax extension)

* JSX는 자바스크립트의 확장 문법
* 리액트에서는 이 JSX를 이용하여 UI를 나타냄
* JSX를 이용하면 UI를 나타낼 때 자바스크립트와 HTML 구조를 같이 사용 가능함
* 따라서 기본 UI나 데이터 변화, 이벤트 처리를 더욱 쉽게 구현 가능함

### 2. JSX를 꼭 사용해야하나?

* 필수는 아니지만 굳이 안써야 할 이유가 있나...?

### 3. JSX 없이 리액트에서 화면을 그리는 방식

* React createElement API를 사용해서 엘리먼트를 생성
* 이 엘리먼트를 in-memory에 저장
* ReactDON.render 함수를 사용해서 실제 웹브라우저에 랜딩

```jsx
const element = React.createElement('h1', {}, '이건 너무 복잡하잖아요...');
ReactDOM.render(element, document.getElementById('root'));
```

### 4. babel의 등장

* babel이 JSX를 createElement로 자동 변환 해줌&#x20;

### 5. JSX의 문법 규칙

* 얘는 html이 아닙니다.
* 가장 대표적인 규칙은 최상위 부모 요소로 감싸줘야 한다는 것

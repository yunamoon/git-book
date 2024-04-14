# React.js

### 1. React

> 메타에서 개발한 오픈소스 자바스크립트 라이브러리, 대규모 웹 서비스의 UI를 더 편하게 개발하기 위해 만들어진 기술이다.

#### 1) 등장 배경 : JS의 한계

* Javascript로 개발하면 DOM을 조작하기 위해 특정 id로 DOM을 선택하고, 선택한 DOM에 이벤트를 바인딩하고, 이벤트가 발생하면 선택한 DOM의 상태를 변경하는 등 일련의 과정이 너무 길다.
* 하여 인터렉션이 늘어나면 늘어날수록 코드가 복잡해진다.
* 근본적으로 어떻게 업데이트 할 것인가에 대한 고민을 피해가기 어렵다.

#### 2) 등장 배경 : React의 발상의 전환

* React는 아예 DOM을 새로 만들어 화면을 업데이트하는데, 이게 가능한 이유는 VDOM 때문이다.
* React는 메모리상에 DOM을 복제한 가상 DOM(Virtual DOM)을 만들고 상태 변화가 일어났을 때 가상 DOM을 통해 UI를 부분적으로 업데이트한다.&#x20;

### 2. React의 기술적 특징

> 컴포넌트를 기반으로 UI를 표현하고, 화면 업데이트 구현이 쉬우며 심지어 빠르게 처리된다,

#### 1) 일반적인 브라우저의 렌더링

* 아래의 렌더링을 반복
* HTML(DOM) -> CSS(CSSOM) -> Render Tree -> Layout -> Painting&#x20;

#### 2) React 렌더링&#x20;

* **가상 DOM 생성 :** React 애플리케이션은 메모리 상에 가상 DOM을 생성한다. VDOM은 실제 DOM의 가벼운 복제본으로, 실제 DOM의 모든 요소와 구조를 가지고 있다.
* **상태 변화 감지 :** React는 상태 변화를 감지하고 해당 상태 변경을 반영하기 위해 새로운 가상 DOM을 생성한다.
* **가상 DOM 비교**: 이전 가상 DOM과 새로운 가상 DOM을 비교하여 변경된 부분을 식별한다.
* **실제 DOM 업데이트**: 변경된 부분만을 실제 DOM에 패치한다.&#x20;
* 위의 과정을 통해 불필요한 DOM 조작을 최소화해 성능 향상이 가능하다.

### 3. React JSX

> JSX(JavaScript XML)라는 JavaScript에 XML을 추가하여 확장한 문법으로,
>
> HTML 요소도 가지고 있지만 JavaScript 확장식도 사용이 가능하며,
>
> 번들링되는 과정에서 바벨을 사용하여 일반 자바스크립트 형태의 코드로 변환된다.

#### 1) JSX 특징

* JavaScript 표현식을 중괄호 `{}`로 감싸면 해당 표현식이 평가되고 결과가 JSX에 삽입
* HTML과 유사한 문법을 가지고 있어 UI를 작성하기 편리하나, class 대신 className을 사용해야 하고, style 속성에는 객체를 전달해야 한다.
* React 요소를 반환하고, 이 요소는 Virtual DOM에서 사용되는 일종의 템플릿 역할을 한다.
* JSX에서는 HTML 속성과 이벤트 처리를 동일하게 작성할 수 있다.

***

### 4. React 컴포넌트

> 리액트 앱을 이루는 최소한의 단위를 말한다.
>
> 기존의 MVC 기반 웹 프레임워크와 다르게 각 요소가 독립적으로 재활용성이 높다.
>
> 함수형 컴포넌트와 클래스형 컴포넌트가 있고, 최근에는 함수형 컴포넌트가 더 많이 사용된다.

#### 1) 컴포넌트란

* 컴포넌트는 props를 입력받고, state에 따라 DOM을 출력하는 일종의 함수이다.
* 컴포넌트 이름은 항상 대문자로 시작한다. (리액트는 소문자로 시작하는 컴포넌트를 html 태그로 취급)
* 컴포넌트는 단독으로 사용이 가능한 개별적인 조각으로 분리하여 재사용이 가능해야 한다.

#### 2) 컴포넌트 구성 요소

* Porps : 부모 컴포넌트에서 자식 컴포넌트로 전달되는 프로퍼티
* State : 컴포너트의 상태를 저장하고 수정이 가능한 데이터
* Context : 부모 컴포넌트에서 생성하여 provider 내의 모든 자식 컴포넌트에게 전달 가능한 데이터

### 5. 클래스형 컴포넌트

> React에서 클래스형 컴포넌트는 ES6 클래스로 정의된 React 컴포넌트를 말한다.
>
> 지금은 함수형 컴포넌트가 더 선호되나, 클래스형 컴포넌트는 여전히 많은 프로젝트에서 사용되고 있다.

#### 1) 클래스형 컴포넌트의 구조

* 클래스형 컴포넌트는 React.Component클래스를 확장
* &#x20;클래스형 컴포넌트는 상태(state)와 생명주기 메서드(lifecycle methods)를 사용하여 컴포넌트의 동작을 제어

```jsx
import React, { Component } from 'react';

class MyComponent extends Component {
  constructor(props) {
    super(props);
    this.state = {
      // 초기 상태 설정
    };
  }

  componentDidMount() {
    // 컴포넌트가 마운트된 후에 실행되는 코드
  }

  componentDidUpdate(prevProps, prevState) {
    // 컴포넌트가 업데이트된 후에 실행되는 코드
  }

  componentWillUnmount() {
    // 컴포넌트가 언마운트되기 전에 실행되는 코드
  }

  render() {
    return (
      // 컴포넌트의 UI를 정의하는 JSX
    );
  }
}

export default MyComponent;

```

### 6. 함수형 컴포넌트

> 함수로 정의된 React 컴포넌트로, React v16.8에서 도입된 Hooks API를 통해 상태와 생명주기 기능 활용 가능하다.&#x20;
>
> 클래스형 컴포넌트보다 간단하고 직관적이고ㅡ 순수 함수로 이루어져 있으며, 함수의 인자로 props를 받아와서 UI를 반환한다.

#### 1) 함수형 컴포넌트 구조

```jsx

import React from 'react';

const MyFunctionalComponent = (props) => {
  return (
    <div>
      <h1>Hello, {props.name}!</h1>
    </div>
  );
};

export default MyFunctionalComponent;

```

***

### 6. React state

### 7. React props

### 8. React hooks

#### 1) useState

#### 2) useRef

#### 3) useEffect

#### 4) useReducer

### 8. React Context

### 9. React Routing

> 리액트는 html 전환 없이 컴포넌트 단위의 리렌더링을 하기 때문에 새로고침이 발생하지 않는다.

#### 1) React Router

* npmjs.com에 등록되어 있는 라이브러리이며, 대다수의 리액트 앱이 이 라이브러리를 사용해 라우터를 구축한다.
* 다양한 기능들을 제공하며, 자세한 사항은 공식 문서를 참조하면 좋다.

#### 2) React Router 설정

* npm i react-router-dom 명령어를 통해 설치
* App.jsx 이동 후, \<BrowserRouter/> import해서 사용

```jsx
// routing 예시
import { Routes, Route} from 'react-router-dom';

const App= () => {

retrun (
<Routes>
<Route path='/' element={<Component/>}/>
</Routes>
);
}
```

#### 3) 페이지 이동 설정

* Link나 useNavigate 메소드를 사용
* a 태그 사용시 페이지 새로 고침이 일어나기 때문에 리액트 앱에서는 Link를 권창

```jsx
// 페이지 이동 예시

import { Routes, Route, Link, useNavigate} from 'react-router-dom';
const test = () => {

retrun (
const nav = useNavigate();

const handleClick = () => {
    nav('/');
};
<>
<Link to={'/'}> HOME </Link>
<button onclick={handleClick}>이동</button>
</>
);
}
```

### 10. React 동적 경로

> 사용자의 요청이나 프로그램의 상태에 따라 결정되는 경로를 말한다.

#### 1) URL Parameter&#x20;

* / 뒤에 아이템의 id를 명시하는 방식이다.
* 아이템의 id 등 변경되지 않는 값을 주소로 명시하기 위하여 사용한다.

```jsx
// App.jsx
<Route path='/test/:id' element={<Test/>}/>

//Test.jsx
import {useParams} from 'react-router-dom';

const Test = () = > {
const params = useParams();

return(
    <div>{params.id}</div>
    );
}
```

#### 2) Query String

* ? 뒤에 변수명과 값을 명시하는 방식이다.
* 검색어 등 자주 변경되는 값을 주소로 명시하기 위해 사용한다.

```jsx
// 별도 라우터 설정 필요 없음.
import { useSearchParams } from 'react-router-dom'

const Test = () => {
const [ params, setParams] = useSearchParams();
console.log(params.get("string"));
return();
}
 
```

### 11. React img

> 리액트에서 이미지를 사용하는 방법은 이미지의 현재 위치에 따라 달라진다.

#### 1) public 아래

* 이미지가 public 폴더 아래에 있을 경우에는 img src='경로'를 추가하여 사용한다.
* 이 경우 vite의 이미지 최적화가 이루어지지 않는다.

#### 2) src/asset 아래

* 이미지가 src 아래에 있는 경우로, 이미지를 문서 상단에 import해서 사용한다.
* 이 경우 vite의 이미지 최적화가 이루어진다.
* vite는 이미지를 데이터 uri로 변환하여, 데이터 캐싱이 이루어지게 한다.&#x20;

#### 3) 중복으로 사용되는 이미지가 많을 경우

* 모듈로 분리한다.

```jsx
import test from './../assets/img.png';
export function getImg (name) {
     switch(name) {
         case name :  
         return imgName;
         default:
              return null;
     };
 };
```




# 함수형 컴포넌트

### 1. 함수형 컴포넌트

* 함수로 정의된 React 컴포넌트
* 함수형 컴포넌트는 React v16.8에서 도입된 Hooks API를 통해 상태와 생명주기 기능 활용 가능
* 클래스형 컴포넌트보다 간단하고 직관적
* 순수 함수로 이루어져 있으며, 함수의 인자로 props를 받아와서 UI를 반환

### 2. 함수형 컴포넌트 구조

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

# 클래스형 컴포넌트

### 1. 클래스형 컴포넌트

* React에서 클래스형 컴포넌트는 ES6 클래스로 정의된 React 컴포넌트를 말함
* 지금은 함수형 컴포넌트가 더 선호됨
* 그러나 클래스형 컴포넌트는 여전히 많은 프로젝트에서 사용되고 있긴함
* 근데 내가 그러면 혼나겠지...?

### 2. 클래스형 컴포넌트의 구조

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

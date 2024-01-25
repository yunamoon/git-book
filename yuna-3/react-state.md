# React state

### [Thingking in React](https://react.dev/learn/thinking-in-react)

* 3단계 : UI 상태를 최소화하지만 완전한 표현 찾기
* 4단계 : State가 어디에 존재해야 하는 확인
* 5단계 : 역 데이터 흐름 추가

### React State

State는 컴포넌트의 변경을 다루는 요소로, 상위 컴포넌트의 State가 바뀌면 하위 컴포넌트에서 리랜더링이 일어난다. 이때, State는[ DRY(중복 금지)](https://ko.wikipedia.org/wiki/%EC%A4%91%EB%B3%B5%EB%B0%B0%EC%A0%9C)와 [SSOT(단일 진실 공급원)](https://ko.wikipedia.org/wiki/%EB%8B%A8%EC%9D%BC\_%EC%A7%84%EC%8B%A4\_%EA%B3%B5%EA%B8%89%EC%9B%90)의 원칙을 충족해야 합니다.

### React State 조건

* 변경되지 않는 값은 State로 다룰 가치가 없습니다.
* 상위 컨포넌트가 props를 통해 전달한다면 State가 아닙니다.
* 다른 State나 Props를 이용하여 계산이 가능하다면 State가 아닙니다.

상태가 너무 많거나 복잡할 경우 TypeScript를 활용하여 직접 상태 관리를 하는 수를 줄여줄 수 있습니다. 이때 상태 관리를 하는 컴포넌트는 해당 상태에 의존적인 컴포넌트를 모두 포함하는 상위 컴포넌트가 상태를 소유하고 관리해야합니다.

### Inverse Data Flow

하위 컴포넌트의 props로 함수를 전달 (= 콜백 함수)

*   타입스크립트 (자바스크립트)에서는 함수가 일급 객체로, 함수로 인자로 넘겨주거나 리턴값으로 받는 것이 가능

    > 프로그래밍 언어에서는 해당 언어의 함수들이 다른 변수처럼 다루어질 때 일급함수를 갖는다고 함
* 익명 함수, 클로저와 함께 구현

# React Testing Library

### React testing library 란?

React Testing library는 React 컴포넌트의 테스트를 더 쉽고 직관적으로 작성할 수 있도록 도와주는 라이브러리입니다.&#x20;

React Testing library는 행위 주도 테스트 (Behavior Driven Test)를 추구하는 테스트 방법으로 사용자의 관점에서 컴포넌트를 테스트합니다. 따라서 컴포넌트 내부 구현보다는 사용자가 실제로 상호작옹하는 방식에 초점을 맞추어 테스트를 작성하며, 실제 브라우저에서 보여지는 DOM을 기준으로 테스트를 작성하게 됩니다.

### React testing library 설치하기

creat-react-app으로 생성된 프로젝트는 기본적으로 react testing library를 포함하고 있습니다. 하지만 만일 creat-react-app을 사용하지 않았다면 npm을 이용해 패키지를 설치 할 수 있습니다.

<pre><code>// Jest DOM에 특화된 matcher <a data-footnote-ref href="#user-content-fn-1">애드온</a>인 jest-dom도 함께 설치
npm i-D jest @testing-library/react @testing-library/jest-dom
</code></pre>

### React testing library 사용하기

#### render 함수

React Testing Library에서는 테스트 할 컴포넌트를 렌더할 수 있는 API를 제공합니다. render API를 통하여 컴포넌트를 렌더링 하고 그 결과로 나온 DOM에서 element를 탐색할 수 있는 query들을 반환하고, 렌더링 된 DOM 요소를 반환합니다.

```typescript

import {render} from '@testing-library/react';

const Button = () => {
<button> 클릭해~! </button>
);

const { getByText, container} = render(<Button/>);

```

render() 함수는 인자로 렌더링할 react 컴포넌트를 넘깁니다. 그리고 render() 함수는 React-Testing-Library가 제공하는 모든 쿼리 함수와 기타 유틸리티 함수를 담고 있는 객체를 리턴합니다.&#x20;

#### query

렌더링 된 DOM 노드에 접근하여 엘리먼트를 가지고 오는 메서드로, 이러한 메서드 들은 특정 쿼리를 사용하여 DOM 요소를 선택하고 반환합니다.

* get (쿼리타입)
* All (타겟의 개수)
* ByRole (타겟 유형)

#### query type

* get : 동기적으로 처리되면 타겟을 찾지 못할 경우 에러가 발생.
* find : 비동기적으로 처리되며 타겟을 찾지 못할 경우 에러가 발생.
* query : 동기적으로 처리되며 타겟을 찾지 못할 경우 null을 반환합.

가끔 이벤트, 비동기적인 처리가 필요하거나 해당 타겟을 찾지 못해도 에러가 발생하지 않게 하는 경우가 있기 때문에 상황에 맞게 쿼리 타입을 설정해야 합니다.

#### Screen 함수

React Testing Library에서 Screen은 테스트 환경에서 화면을 대표하는 객체입니다. render 함수를 호출한 결과로 쿼리 함수를 사용할 수도 있지만, Screen을 통해 쿼리 함수를 사용할 수도 있습니다.&#x20;

```typescript

import { render, screen} from '@testing-library/react'

const Button = () => (
<button> 클릭해! </button>
);

test('<Button/>', () => {
render(<Button/>);

screen.getByText(/클릭해/i);
});

```

[^1]: "에드온"은 기본적인 기능에 추가적인 기능이나 확장을 제공하는 소프트웨어나 도구를 의미합니다.

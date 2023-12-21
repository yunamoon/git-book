# DOM vs Virtual DOM

### DOM이란?

DOM은 Document Object Model로 HTML이란 코드로 설계된 웹페이지가 브라우저 안에서 화면에 나타나고, 이벤트에 반응하며 값을 입력받는 등 기능들을 수행할 객체들로 실체화된 형태를 의미합니다.

### Virtual DOM이란? <a href="#virtual-dom" id="virtual-dom"></a>

Virtual DOM은 실제 DOM을 모방하는 형태로 메모리 상에서만 존재하는 가상의 DOM을 의미하며, 변화가 실제 DOM에 적용되기 전에 가상의 DOM을 한번 거쳐 미리 처리하고 저장한 후 실제 DOM에 업데이트 할 수 있게 합니다.

즉, 데이터가 변경이 되면 전체 UI는 Virtual DOM에 렌더링 되어져 이전 virtual DOM에 있던 내용과 업데이트 후에 내용을 비교하여 바뀐 부분만 실제 DOM에 적용시키게 됩니다.

React는 Virtual DOM을 이용하는 대표적인 자바스크립트 라이브러리입니다.&#x20;

### DOM vs Virtual DOM

데이터가 변경될 때 마다 DOM은 매번 처음부터 다시 화면이 그려지는 불필요한 반복이 발생되어, DOM을 조작하는 Virtual DOM이 탄생하게 되었습니다.

Virtual Dom은 변화가 실제 DOM에서 적용되기 전에 가상의 DOM을 거쳐서 계산 단계를 줄이고 효율적인 DOM조작을 가능하게 만들어줍니다.

하지만만약 데이터가 변경되지 않는 웹 페이지라면 일반 DOM이 성능이 좋을 수 있고, 장바구니 등 사용자에 따라 데이터가 변경되는 웹페이지라면 DOM 조작이 많이 발생하기에 상황에 맞게 Virtual Dom을 사용하는 것이 좋습니다.

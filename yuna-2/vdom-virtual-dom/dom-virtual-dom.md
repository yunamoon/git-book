# DOM vs Virtual DOM

### DOM이란?

DOM은 Document Object Model로 HTML이란 코드로 설계된 웹페이지가 브라우저 안에서 화면에 나타나고, 이벤트에 반응하며 값을 입력받는 등 기능들을 수행할 객체들로 실체화된 형태를 의미합니다.

### Virtual DOM이란? <a href="#virtual-dom" id="virtual-dom"></a>

Virtual DOM은 실제 DOM을 모방하는 형태로 메모리 상에서만 존재하는 가상의 DOM을 의미하며, 변화가 실제 DOM에 적용되기 전에 가상의 DOM을 한번 거쳐 미리 처리하고 저장한 후 실제 DOM에 업데이트 할 수 있게 합니다.

즉, 데이터가 변경이 되면 전체 UI는 Virtual DOM에 렌더링 되어져 이전 virtual DOM에 있던 내용과 업데이트 후에 내용을 비교하여 바뀐 부분만 실제 DOM에 적용시키게 됩니다.

React는 Virtual DOM을 이용하는 대표적인 자바스크립트 라이브러리입니다.&#x20;

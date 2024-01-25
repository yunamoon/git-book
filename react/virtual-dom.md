# Virtual Dom

### 1. 가상돔

리액트의 주요 특징 중 하나는 가상돔을 사용한다는 것임

기존 방식으로는 인터렉션에 의해 Dom에 변화가 발생할 때마다 Render Tree가 생성됨.&#x20;

인터렉션이 적은 웹이면 괜찮지만 인터렉션이 많은 웹이라면 불필요한 DOM을 조작하는 비용이 너무 큼.

<mark style="color:blue;">**= 그래서 Virtual Dom이 등장!**</mark>

<mark style="color:blue;">**가상돔 (virtual dom)이란 실제 dom을 메모리에 복사해준 것**</mark>

### 2. 가상돔의 작동 방식

데이터가 바뀌면 가상돔에 랜더링되고 이전에 생긴 가상돔과 비교하여 바뀐 부분만 실제돔에 적용.

바뀐 부분을 찾는 과정을 Diffing이라고 하고, 바귄 부분만 실제돔에 적용시켜주는 것을 재조정(reconciliation)이라고 함.


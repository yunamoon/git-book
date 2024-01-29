# Sass

### 1. Sass

[css 확장 언어](https://sass-lang.com/)

css를 사용하는 것만으로 많은 앱을 스타일링 할 수 있지만, 스타일시트가 점점 늘어나고 복잡해지면 유지관리가 어려워지는 데, 이때 sass의 중첩, 믹스인, 상속 등의 기능이 도움이 됨.

### 2. SASS vs SCSS

* SASS는 코드를 CSS로 해석하는 전처리 장치이자 문법
* SCSS는 문법
* SCSS 기반으로 코드를 작성하면 SASS가 전처리 과정을 거쳐 CSS로 변환함.

### 3. Sass 특징

*   **Variables 변수**

    스타일시트 내에서 재사용하는 정보를 변수로 관리할 수 있으며, $ 기호를 사용함.
*   **Nesting**&#x20;

    html과 동일한 시각적 계층 구조로 중첩 가능.
*   **Partials**

    부분 조각으로 나눠서 관리 가능.
*   **Module**

    부분 조각으로 나뉘어진 파일을 모듈이라고 하며, @use를 사용하여 import 가능.
*   **Mixins**

    반복해서 작성하는 부분은 mixins를 이용하여 사이트 전체에서 재사용 가능.
*   **Extend/Inheritance**

    @extend를 사용하면 CSS 속성 집합을 공유할 수 있음.
*   **Operators**

    Sass는 +,-,",math.div(),% 등의 연산자를 사용할 수 있음.


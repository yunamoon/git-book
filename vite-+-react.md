# vite + React

### 1. 프로젝트 생성

<pre><code><strong>npm init vite 
</strong>✔ Project name: … ./
✔ Select a framework: › React
✔ Select a variant: › JavaScript
</code></pre>

```
npm install
```

### 2. 필요한 패키지 설정

```
npm install 
axios 
react-router-dom 
react-redux 
react-icons 
sass 
@reduxjs/toolkit 
react-loading-skeleton
```

### 3. 폴더 구조 생성

* src
  * assets : 정적인 asset 관리
  * components : 컴포넌트
    * cart-empty
    * footer
    * form
    * header
    * layout
    * loader
  * hooks : 커스텀 hooks
  * pages : 페이지&#x20;
    * CartPage
    * DetailPage
    * HomePage
    * LoginPage
    * NotFoundPage
    * OrderPage
    * RegisterPage
  * store : 리덕스
    * cart
    * categories
    * order
    * products
    * user

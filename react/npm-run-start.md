# npm run start

### 1. 리액트 실행하기

<mark style="color:blue;">**npm run start**</mark>

프로젝트를 실행하면, root 내부는 비어 있는데 자동으로 app.js가 렌더링 되는 이유는?

리액트 시작점인 index.js를 보면 확인이 가능

```javascript
// index.js
// root 아래에 app 렌더링
import React from 'react';
import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);

reportWebVitals();

```

# react-router-dom

### 1. react-router-dom

라우팅은 기본적으로 네트워크에서 경로를 선택하는 프로세스를 말함

react-router-dom은 리액트 프로젝트(SPA)에서 페이지 이동이 가능하도록 만들어주는 라이브러리

### 2. router 설정

```jsx
// App.jsx 수정

import {BrowserRouter, Route, Routes} from 'react-router-dom';
import './App.css'
import LayOut from './components/layout/Layout'
import HomePage from './pages/HomePage'
import DetailPage from './pages/DetailPage'
import CartPage from './pages/CartPage'
import LoginPage from './pages/LoginPage'
import RegisterPage from './pages/RegisterPage'
import OrderPage from './pages/OrderPage'
import NotFoundPage from './pages/NotFoundPage'

function App() {

  return (
   <BrowserRouter>
   <Routes>
    <Route path='/' element={<LayOut/>}>
    <Route index element={<HomePage/>} />
    <Route path="product/:id" element={<DetailPage/>} />
    <Route path="cart" element={<CartPage/>} />
    <Route path="login" element={<LoginPage/>} />
    <Route path="register" element={<RegisterPage/>} />
    <Route path="order" element={<OrderPage/>} />
    <Route path="*" element={<NotFoundPage/>} />
    </Route>
   </Routes>
   </BrowserRouter>
  )
}

export default App

```


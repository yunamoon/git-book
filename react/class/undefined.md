---
description: 1차는 class component
---

# 프로젝트 기본 구조 만들기

### 1. 폴더 구조

```css
    src 
     >componets
      >list // 가계 항목 리스트
       >list.js
       >list.css
      >item // 가계 항목 아이템
       >item.js
       >item.css
      >form // 입력 폼
       >form.js
       >form.css 
     App.js
     App.css // App.js 관련 css
     index.css // root css 포함
```

### 2. App.js

* 최상위 컴포넌트
* Form / List 컴포넌트 import

```jsx
import React, { Component } from 'react'
import "./App.css";
import Form from './compnents/form/Form';
import List from './compnents/list/List';

class App extends Component {
    render() {
        return (
            <main className="main-container">
                <h1 >가계부</h1>
                <div style={{width :'100%', backgroundColor:'white', padding:'1rem'}}>
                <Form/>
                <List/>
                </div>
                <div style={{display : 'flex' , justifyContent:'end' , marginTop : '1rem'}}>
                <p style={{fontSize:'2rem'}}>
                    총합:
                    <span>원</span>
                </p>
                </div>  
            </main>
        )
    }
}

export default App;
```

### 2. Form.js

* 가계 항목 입력 폼 컴포넌트

```jsx

import React, { Component } from 'react'
import "./Form.css"
export class Form extends Component {
  render() {
    return (
      <form>
        <div className='form-center'>
            <div className='form-group'>
              <label htmlFor='expenditure'>지출 비용</label>
              <input 
              type='text' 
              className='form-control' 
              id='expenditure'
              name='expenditure' placeholder='지출 항목을 입력해 주세요.'>
              </input>
            </div>
            <div className='form-group'>
              <label htmlFor='charge'>지출 비용</label>
              <input 
              type='number' 
              className='form-control' 
              id='charge'
              name='charge' placeholder='예상 비용을 입력해 주세요.'>
              </input>
          </div>
        </div>

        <button type='submit' className='btn'>
          저장
        </button>
      </form>
    )
  }
}

export default Form
```

### 3. List.js

* Item 컴포넌트 import

```jsx

import React, { Component } from 'react';
import './List.css';
import Item from '../item/Item';

export class List extends Component {
  render() {
    return (
      <>
        <ul className='list'>
        <Item/>
        </ul>
        <button className='btn'>
          전체 삭제
        </button>
      </>
    )
  }
}

export default List
```

### 3. Item.js

* 등록된 가계 아이템 컴포넌

```jsx

import React, { Component } from 'react'
import './Item.css'
export class Item extends Component {
  render() {
    return (
      <div>
        <li className='item'>
          <div className='info'>
            <span className='expenditure'>택시비</span>
            <span className='charge'>500만원</span>
          </div>
          <div className='button'>
            <button className='edit-btn'>수정</button>
            <button className='delete-btn'>삭제</button>
          </div>
        </li>
      </div>
    )
  }
}

export default Item
```

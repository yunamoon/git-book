# 함수형 컴포넌트로 변환

### 1. 왜 굳이 바꿔요...?

이래야 함수형 컴포넌트의 멋짐을 알 수 있다고 누가 그러길래...

그 멋짐을 저도 알고 싶었습니다.

### 2. 컴포넌트 변경&#x20;

```jsx
// App.js

import React, { useState } from 'react'
import "./App.css";
import Form from './compnents/form/Form';
import List from './compnents/list/List';

const App = () => {

    const [charges , setCharges] = useState([
        [
        {id : 1, expenditure : "뭔데" , charge :10000},
        {id : 2, expenditure : "난데" , charge :53000},
        {id : 3, expenditure : "근데" , charge :40000}
        ]
    ])


    const handleDelete = (id) => {
      const newCharges = charges.filter(item => item.id !== id);
      setCharges(newCharges)
    }

  
        return (
            <main className="main-container">
                <h1 >가계부</h1>
                <div style={{width :'100%', backgroundColor:'white', padding:'1rem'}}>
                <Form/>
                <List 
                charges={charges} 
                handleDelete={handleDelete}/>
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

export default App;

```

```jsx
// Form.js

import React from 'react'
import "./Form.css"
import { MdSend } from 'react-icons/md'

const Form = () => {
 
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
        
        <div className='btn-container'>
        <button type='submit' className='btn'>
          저장 <MdSend className='btn-icon'/>
        </button>
        </div>
      </form>
    )
  }

export default Form
```

```jsx
// List.js

import React from 'react';
import './List.css';
import Item from '../item/Item';
import { MdDelete } from 'react-icons/md';


const List = ( {charges, handleDelete}) => {

    return (
      <>
        <ul className='list'>
        {charges.map(item=>  {
          return (      
          <Item key={item.id} 
          charges={charges} 
          handleDelete={handleDelete}/>
          )
    
        })}
      
        </ul>
        <div className='btn-container'>
        <button className='btn'>
          전체 삭제 <MdDelete className='btn-icon'/>
        </button>
        </div>
     
      </>
    )
  }


export default List

```

```jsx
// Item.js

import React from 'react'
import './Item.css'
import {MdEdit , MdDelete} from 'react-icons/md'

const Item = ({charges , handleDelete}) => {

    return (
      <div>
        <li className='item'>
          <div className='info'>
            <span className='expenditure'>{charges.expenditure}</span>
            <span className='charge'>{charges.charge}원</span>
          </div>
          <div className='button'>
            <button className='edit-btn'><MdEdit/></button>
            <button className='delete-btn' onClick={()=> handleDelete(charges.id)}><MdDelete/></button>
          </div>
        </li>
      </div>
    )
  }


export default Item

```

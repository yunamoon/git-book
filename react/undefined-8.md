# 지출 항목 수정

### 1. state 추가

```jsx
    const [edit , setEdit] = useState(false);
    const [id , setId] = useState('');
```

### 2. handleEdit 함수 추가

```jsx

    const hadleEdit = (id) => {
        const newCharges = charges.find(item => item.id === id);
        const {charge, expenditure} = newCharges;
        setId(id);
        setCharge(charge);
        setExpenditure(expenditure);
        setEdit(true);
    }

```

### 3. Item.js 수정 버튼에 함수 추가

```jsx

  <button className='edit-btn' onClick={()=>hadleEdit(charge.id)}>
  <MdEdit/></button>
```

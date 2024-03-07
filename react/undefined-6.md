# 지출 목록 삭제

### 1. 지출 목록 삭제

* 삭제 버튼에 클릭 이벤트 추가

```jsx
 <button 
 className='delete-btn' 
 onClick={()=> console.log('여기에 삭제 이벤트가 들어간다~')}>
 <MdDelete/>
 </button>
```

```jsx
 // App.js 일부
 // 작성된 함수를 props로 내려줌
 
    handleDelete = (id) => {
      const newCharges = this.initialCharges.filter(item => item.id !== id);
      console.log(newCharges);
    }

    <List 
    initialCharges={this.initialCharges} 
    handleDelete={this.handleDelete}/>

  // List.js 일부

   {this.props.initialCharges.map(item=>  {
          return (      
          <Item key={item.id} 
          initialCharges={item} 
          handleDelete={this.props.handleDelete}/>
          )
    
    })}
    
    // Item.js 일부

  <button className='delete-btn' 
          onClick={()=> this.props.handleDelete(this.props.initialCharges.id)}>
  <MdDelete/></button>


```

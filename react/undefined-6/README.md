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

### 2. React State

* 컴포넌트의 랜더링 결과물에 영향을 주는 데이터를 가지고 있는 객체
* state가 변경되면 컴포넌트는 리랜더링된다.
* state는 컴포넌트 안에서 관리된다.
* 컴포넌트 내에서 데이터를 기억하고 있는 방식을 말함.

### 3. State 생성

```jsx

 constructor(props) {
        super(props);
        this.state = {
            charges : [
                {id : 1, expenditure : "뭔데" , charge :10000},
                {id : 2, expenditure : "난데" , charge :53000},
                {id : 3, expenditure : "근데" , charge :40000}
            ]
        
        }
    }

```

### 4. State 변경

```jsx
   
  handleDelete = (id) => {
      const newCharges = this.state.charges.filter(item => item.id !== id);
      this.setState({charges : newCharges})
    }
```


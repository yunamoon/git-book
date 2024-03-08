# 지출 목록 추가

### 1. submit event 추가

```jsx


    const [expenditure, setExpenditure] = useState('');
    const [charge , setCharge] = useState();

    const handleExpend = (e) => {
        setExpenditure(e.target.value);
    }

    const handleCharge = (e) => {
        setCharge(e.target.valueAsNumber);
       
    }
    
    const handleSubmit = (e) => {
        console.log(expenditure, charge)
        e.preventDefault();
        if(expenditure !== "" && charge > 0) {
           const newCharge = {id : crypto.randomUUID(), expenditure, charge}
           const newCharges = [...charges , newCharge];
           setCharges(newCharges);
        } else {
            alert('필수항목을 제대로 입력해주세요.');
        }
```

### 2. form과 input 내에 이벤트 등록

```jsx

  <form onSubmit={handleSubmit}>
        <div className='form-center'>
            <div className='form-group'>
              <label htmlFor='expenditure'>지출 항목</label>
              <input 
              type='text' 
              className='form-control' 
              id='expenditure'
              name='expenditure' 
              placeholder='지출 항목을 입력해 주세요.'
              value={expenditure}
              onChange={handleExpend}
              >
              </input>
            </div>
            <div className='form-group'>
              <label htmlFor='charge'>지출 비용</label>
              <input 
              type='number' 
              className='form-control' 
              id='charge'
              name='charge' 
              placeholder='예상 비용을 입력해 주세요.'
              value={charge}
              onChange={handleCharge}>
              </input>
          </div>
        </div>
        
        <div className='btn-container'>
        <button type='submit' className='btn'>
          저장 <MdSend className='btn-icon'/>
        </button>
        </div>
      </form>

```

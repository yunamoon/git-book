# 목록 전체 삭제

### 1. 목록 전체 삭제

* 전체 삭제 버튼 클릭하면, list state 초기화

### 2. 함수 추가

```jsx

 const handleClear = () => {
        setCharges([]);
    }
    
```

### 3. 버튼에 함수 연결

```jsx

<button className='btn' onClick={handleClear}>
          전체 삭제 <MdDelete className='btn-icon'/>
</button>

```

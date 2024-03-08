# 총 지출 합계

### 1. 총 지출의 합계를 구해보아요.

* reduce 함수

```jsx

 <div style={{display : 'flex' , justifyContent:'end' , marginTop : '1.2rem'}}>
      <p style={{fontSize:'1.5rem', marginRight: '16px'}}>
      총 지출 :
       {charges.reduce((acc, cur) => {
       return (acc += cur.charge)
       },0) }
       <span > 원</span>
       </p>
 </div>  
```

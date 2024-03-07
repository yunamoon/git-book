# Props

### 1. 데이터 플로우

* Redux가 없다면
* App.js > List.js > Item.js 순으로 이동&#x20;

### 2. Props

* Properties&#x20;
* Props는 부모 컴포넌트에서 자식 컴포넌트로 데이터 등을 전달하는 방식
* Props는 immutable 속성으로 자녀 컴포넌트에서 변경을 허용하지 않으며, 수정이 필요하면 부모 컴포넌트에서 state를 변경한다.

### 3. Class 기반에서 Props

```jsx
// 부모 컴포넌트
dataItem = [{}];
<자식 컴포넌트 dataItem ={this.dataItem} />

// 자식 컴포넌트
export class 자식컴포넌트 extends Component {
    render (){
    console.log(this.props.dataItem);
    }
}
```

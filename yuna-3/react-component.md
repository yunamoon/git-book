# React Component

### React Component&#x20;

React 컴포넌트란 React로 만들어진 앱을 이루는 최소한의 단위를 말합니다.&#x20;

기존의 웹 프레임워크는 MVC 방식으로 분리 관리하여 각 요소의 의존성이 매우 높아 재활용이 어렵다는 단점이 있었는데, 컴포넌트를 사용하여 MVC의 뷰를 독립적으로 구성함으로써 재활용을 가능하게 한 것입니다.

### Component 계층 구조

React는 컴포넌트를 기반으로 하며캡슐화 된 간단한 컴포넌트를 조립해서 복잡한 UI를 만들 수 있습니다.&#x20;

* [**단일 책임의 원칙**](https://ko.wikipedia.org/wiki/%EB%8B%A8%EC%9D%BC\_%EC%B1%85%EC%9E%84\_%EC%9B%90%EC%B9%99)&#x20;
  * 모든 클래스는 하나의 책임만을 가져야 하며 그 책임을 완전히 캡슐화해야 합니다.
  * 컴포넌트가 너무 커지고, 변동이 잦다면 컴포넌트를 분리하는 편이 좋습니다.
* 이미 알고 있는 CSS 상식을 활용합니다.
* Design's Layer를 활용합니다.
* 정보 구조를 활용합니다. ( JSON Schema의 영향)
* [Atomic Design](about:blank)



### Props

* [Passing Props to a Component](https://react.dev/learn/passing-props-to-a-component)
* [Components와 Props](https://ko.legacy.reactjs.org/docs/components-and-props.html)

```typescript
// props

function test(props: {props:string}) {
const products = props.products;
=> const {products} = props;
...}

=> function test ({products} : {products:Product[]}) {
...
}
```

### [Extract Function](https://refactoring.com/catalog/extractFunction.html)

우선 코드 초안을 작성하고, 별도 분리가 가능한 코드를 함수로 분리해내는 과정을 의미합니다.

````typescript
// 분리전
import './App.css';

const products =  
[
  { category: "Fruits", price: "$1", stocked: true, name: "Apple" },
  { category: "Fruits", price: "$1", stocked: true, name: "Dragonfruit" },
  { category: "Fruits", price: "$2", stocked: false, name: "Passionfruit" },
  { category: "Vegetables", price: "$2", stocked: true, name: "Spinach" },
  { category: "Vegetables", price: "$4", stocked: false, name: "Pumpkin" },
  { category: "Vegetables", price: "$1", stocked: true, name: "Peas" }
]

function App() {

  const categories = products.reduce((acc:String[], product) => (
  acc.includes(product.category) ? acc : [...acc, product.category]
),[] as String[]);

  return (
    <div className="App">
      <div className="filterable-product-table">
        <div className="search-bar">
          <div>
            <input type="text" placeholder="search..."></input>
          </div>
          <div>
            <input type="checkbox" id="only-stock"></input>
            <label htmlFor="only-stock">Only show produts in stock</label>
          </div>
        </div>
        <table className="product-table">
          <thead>
            <tr>
             <th>Name</th>
             <th>Price</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <th colSpan={2}>
                {categories[0]}
              </th>
            </tr>
            {products.filter((product)=> product.category === categories[0]).map((product) =>(
              <tr key={product.name}>
                <td>{product.name}</td>
                <td>{product.price}</td>
              </tr>
            ))}
            <tr>
              <th colSpan={2}>
                {categories[1]}
              </th>
            </tr>
            {products.filter((product)=> product.category === categories[1]).map((product) =>(
              <tr key={product.name}>
                <td>{product.name}</td>
                <td>{product.price}</td>
              </tr>
            ))}
            
          </tbody>
        </table>
      </div>
    </div>
  );
}

export default App;

```
````

````typescript
// FilterableProductTable

import Product from "../types/Product";
import ProductTable from "./ProductTable";
import SearchBar from "./SearcBar";

type FilterableProductTableProps = {
    products : Product[];
}
export default function FilterableProductTable({products} :FilterableProductTableProps) {
    return (
        <div>
       <SearchBar/>
      <ProductTable products={products}/>
      </div>
    )
}
```
````

````typescript
//CategoryRow

export default function CategoryRow({category} : {
    category:string
  }) {
    return (
      <tr>
        <th colSpan={2}>
          {category}
        </th>
      </tr>
    )
  }
  
```
````

````typescript
//ProductRow

import Product from "../types/Product";

type  ProductRowProps = {
    product : Product;
}
 export default function ProductRow({product} : ProductRowProps) {
    return (
      <tr> 
      <td >{product.name}</td>
      <td >{product.price}</td>
      </tr>)
  }
  
```
````

````typescript
// ProductsInCategory

import Product from "../types/Product";
import selectProducts from "../utils/selectProducts";
import CategoryRow from "./ProductCategoryRow";
import ProductRow from "./ProductRow";

type ProductsInCategoryProps  = {
  category: string;
  products : Product[];
}


export default function ProductsInCategory({
  category, products
}: ProductsInCategoryProps) {
  const productsInCategory =selectProducts(products, category);
  return (
    <>
    <CategoryRow category={category}/>
    {productsInCategory.map((product) =>(
    <ProductRow key={product.name} product={product}/>
   ))}
   </>
  )
}
```
````

````typescript
// ProductTable

import Product from "../types/Product";
import ProductsInCategory from "./ProductsInCategory";

type ProductTableProps = {
    products:Product[];
}
export default function ProductTable({products} : ProductTableProps) {
    const categories = products.reduce((acc:string[], product:Product) => (
      acc.includes(product.category) ? acc : [...acc, product.category]
    ),[] );
  
    return(
      <table className="product-table">
      <thead>
        <tr>
         <th>Name</th>
         <th>Price</th>
        </tr>
      </thead>
      <tbody>
        {categories.map((category) => (
        <ProductsInCategory 
        key={category}
        category={category} 
        products={products}/>
      ))}
      </tbody>
    </table>
    )
  }
```
````

````typescript
// SearchBar

function CheckBoxField({label} : 
{label:string;
}) { 

    const id = `checkbox-${label}`.replace(/ /g, '-').toLowerCase();    
    return (  <div>
    <input type="checkbox" id={id}></input>
    <label htmlFor={id}>{label}</label>
  </div>)
}
export default function SearchBar() {

    return (
        <div className="search-bar">
        <div>
          <input type="text" placeholder="search..."></input>
        </div>
         <CheckBoxField label="어쩌구 저쩌구" />
      </div>
    )
}
```
````

````typescript
// type.ts

interface Product {
    category: string; 
    price: string;
     stocked: boolean;
      name: string;
   
  }

  export default Product;
```
````

````typescript
// selectProducts

import Product from "../types/Product"

export default function selectProducts(
    items : Product[],
    category : string,
): Product[]{
   return items.filter((item) => item.category === category);
}
```
````

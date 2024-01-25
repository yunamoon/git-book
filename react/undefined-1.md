# 컴포넌트란?

### 1. 리액트 컴포넌트란?

<mark style="color:blue;">**컴포넌트는 리액트 앱을 이루는 최소한의 단위**</mark>

하나의 페이지를 리액트로 만들면, 여러개의 컴포넌트가 모여서 하나의 페이지를 이룸

### 2. 클래스형 컴포넌트 vs 함수형 컴포넌트

<pre class="language-typescript"><code class="lang-typescript"><strong>// 클래스형 컴포넌트 (class components) 
</strong>
class App extends Component {
    render() {
    return &#x3C;h1> 안녕하세요. &#x3C;/h1>
    }
}
</code></pre>

```typescript
// 함수형 컴포넌트 (functional components)

function App() {
    return <h1>안녕하세요!</h1>
}
```

리액트 hooks 발표 이후 함수형 컴포넌트가 더 주류로 사용됨

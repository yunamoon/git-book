# Vite

### 1. Vite

[공식문서](https://vitejs.dev/)

* Vite는 기존 webpack, rollup, parcel 과 같은 번들러
* 1세대 번들러보다 속도가 빠름

### 2. Vite 왜 빠르지?

*   esbuild를 사용

    Go로 만들어진 속도 빠른 번들러 라이브러리 사용
* 라이브러리 설치하자마자 미리 bundle 생성
* 소스 코드는 필요한 것만 건드림

### 3. vite + react 프로젝트 생성

```
npm create vite@latest ./
```

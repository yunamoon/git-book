# Express

### 1. Express 란?

[**Express**](http://expressjs.com/ko/)는 웹 애플리케이션을 위한 일련의 기능을 제공하는 node.js 프레임워크

### 2. Express 설치

[**참고 사이트**](https://expressjs.com/ko/)

<pre><code><strong>// node가 이미 설치되어 있다고 가정, 공식 문서 설치 순서
</strong><strong>$ mkdir myapp
</strong>$ cd myapp
$ npm init
$ entry point : index.js
$ npm i express --save
</code></pre>

### 3. 프로젝트 세팅 스크립트

```
// 디렉토리
mkdir express-demo-app
cd mkdir express-demo-app

// .gitignore 
touch .gitignore
echo "/node_modules/" > .gitignore

// 패키지 초기화
npm init -y

// typescript
npm i -D typescript
npx tsc --init

// eslint
npm i -D eslitn
npx eslint --init

// ts-node 설치
npm i -D ts-node

// Express 설치
npm i express
npm i -D @types/express
```

### 4. Express 예제

[참고문서](https://expressjs.com/ko/)

```typescript
// app.ts 작성
import express from 'express';

const port = 3000;
const app = express();

app.get('/', (req,res) => {
    res.send('hello, world');
});

app.listen(port,() => {
    console.log(`server start : ${port}`);
});

// ts-node로 실행
// npx ts-node app.ts
```

### 5. nodemon&#x20;

[참고문서](https://www.npmjs.com/package/nodemon)

개발 중인 node.js 애플리케이션을 자동으로 감지하고 변경 사항이 있을 때마다 애플리케이션을 다시 시작하는 도구

```
// nodemon 설치
npm i -D nodemon
npx nodemon app.ts
```

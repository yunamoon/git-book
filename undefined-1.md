---
description: '개발 환경 : react(javascript) + vite + styled-component +  antd'
---

# 프로젝트 생성

### 1. 프로젝트 생성

<pre><code>// 파일 먼저 생성하고 현재 위치에 프로젝트를 생성하는 편.
<strong>npm create vite@latest ./
</strong></code></pre>

### 2. git 연결

```
git init 
git remote add origin 'ssh'
git branch -M main 
git pull origin main
git add .
git commit -m 'create project'
git push origin main 
```

### 3. npm 패키지 설치

```
npm install
npm run dev // 작동 여부 확인

// 서버 종료 후 이어서
npm install styled-component antd @ant-design/icons
```

### 4. 기본 설정

* 타이틀 및 파비콘 수정
* 기본 css 삭제


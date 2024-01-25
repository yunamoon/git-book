# 리액트 기본 구조

### 1. [react folder-structure](https://create-react-app.dev/docs/folder-structure)

```
my-app/
  README.md
  node_modules/
  package.json
  public/
    index.html
    favicon.ico
  src/
    App.css
    App.js
    App.test.js
    index.css
    index.js
    logo.svg
```

### 2. 이름이 수정되면 안되는 파일

*   <mark style="color:blue;">**public/index.html -> 페이지 템플릿**</mark>

    public 내부의 파일만 public/index.html에서 사용 가능
*   <mark style="color:blue;">**src/index.js -> 자바스크립트 시작점**</mark>

    src 아래 JS와 CSS 파일을 관리

    webpack은 src 아래만 체크, 이 외의 파일은 webpack에 의해 처리되지 않음

### 3. src

대부분의 리액트 소스 코드는 src/ 아래에서 관리

### 4. package.json 파일

<mark style="color:blue;">**프로젝트에 대한 정보**</mark>

*   **dependencies**

    프로젝트 이름, 버전, 필요한 라이브러리, 라이브러리 버전 등이 명시되어 있음
*   **scripts**

    앱 시작 시 사용할 스크립트, 앱 빌드 스크립트, 테스트 스크립트 등이 명시되어 있음
*   **eslintConfig**

    문법이나 코드 포맷 체크 설정 명시

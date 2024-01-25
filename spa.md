# SPA

### 1. SPA (Single Page Application)

MPA는 페이지 별로 템플릿(html)이 존재

SPA는 웹 사이트의 전체 페이지를 하나의 페이지에 담아 동적으로 화면을 바꿔가며 표현

### 2. SPA에서 화면 변경

<mark style="color:blue;">**React-router-dom -> history API 사용**</mark>

MPA에서는 html을 전환해서 화면 변경

SPAsms html5 history API를 사용해서 현재 페이지 내에서 화면 이동이 일어나는 것처럼 보이게 작동함.

### 3. History API

*   History.back()

    세션 기록의 바로 뒤 페이지로 이동하는 비동기 메서드로, 브라우저의 뒤로 가기 효과
*   History.forward()

    세션 기록의 바로 앞 페이지로 이동하는 비동기 메서드로, 브라우저의 앞으로 가기를 누르는 것과 같은 효과
*   History.go()

    특정한 세션ㄱ 기록으로 이동하게 해주는 비동기 메서드로, 1을 넣어 호출하면 바로 앞 페이지로 -1를 넣어 호출하면 바로 뒤 페이지로 이동
*   History.pushState()

    주어진 데이터를 세션 기록 스택에 넣으며, 직렬화 가능한 모든 자바스크립트 객체를 저장
*   History.replaceState()

    최근 세션 기록 스택의 내용을 주어진 데이터로 교체


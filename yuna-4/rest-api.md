# REST API

### 1. REST API

소프트웨어 아키텍처의 일종

* API는 애플리케이션이나 디바이스가 서로 간에 연결하여 통신할 수 있는 방법을 정의하는 규칙
* REST API는 REST 아키텍처 스타일의 디자인 원칙을 준수하는 API
* REST API = RESTful API

### 2. REST 규칙

*   **균일한 인터페이스**

    동일한 리소스에 대한 모든 API 요청은 동일하게 보여야 함
*   **클라이언트-서버 디커플링**

    클라이언트와 서버 애플리케이션은 서로 간에 완전히 독립적이어야 함
*   **Stateless**

    각 요청에서 처리에 필요한 모든 정보를 포함해야 함
*   **캐싱 가능성**&#x20;

    가능하면 리소스를 클라이언트 또는 서버측에서 캐싱할 수 있어야 함
*   **계층 구조 아키텍처**

    REST API에서는 호출과 응답이 서로 다른 계층을 통과
*   **코드 온디맨드**&#x20;

    REST API는 일반적으로 정적 리소스를 전송하지만, 특정한 경우에는 응답에 실행 코드를 포함할 수도 있음

### 3. CRUD

제약 조건을 모두 만족하는 경우는 별로 없고, resource와 HTTP verb만 도입하는 수준으로 사용

* /write-post가 아니라
* /posts -> 뭔가를 함

CRUD에 대해서는 HTTP method를 대입

*   <mark style="color:blue;">**Read (collection : 복수)**</mark>

    GET/products -> 상품 목록 확인
*   <mark style="color:blue;">**Read (Item : 단수)**</mark>

    GET/products/{id} -> 특정 상품 정보 확인
*   <mark style="color:blue;">**Create(collection pattern 활용)**</mark>

    POST/products -> 상품 추가 (JSON 함께 전달)
*   <mark style="color:blue;">**Update(Item)**</mark>

    PUT/products/{id}

    PATCH/products/{id} -> 특정 상품 정보 변경 (JSON 함께 전달)
*   <mark style="color:blue;">**Delete(Item)**</mark>

    DELETE/products/{id} -> 특정 상품 삭제

\

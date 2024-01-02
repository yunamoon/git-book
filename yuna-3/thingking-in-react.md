# Thingking in React

### [Thinking in React](broken-reference)

* “Step 1: Break the UI into a component hierarchy”
* “Step 2: Build a static version in React”

### 데이터

백엔드에서 JSON 형태의 데이터를 리턴하는  API를 제공한다고 가정합니다. 프론트에서는 백엔드가 제공한 데이터를 사용자가 볼 수 있도록 UI를 구성합니다. 이때 React는 선언형(HTML과 유사한 모양의 DSL)으로 UI를 구성할 수 있습니다

**REST API**

REST (Representational State Transfer) 자원을 이름으로 구분하여 해당 자원의 상태를 주고 받는 모든 것을 의미합니다.

* 즉, REST API란? HTTP URL를 통하여 Resource를 명시하고,  HTTP Method (POST, GET, PUT, DELETE, PATCH 등을 통하여, 해당 Resource에 대한 CRUD Opeation을 적용하는 것을 의미합니다.

**GraphQL**

GraphQL은 페이스북에서 발표한 API를 위한 Query 언어 이며, 웹 클라이언트가 서버로부터 데이터를 효율적으로 가지고 오는 것을 목적으로 합니다.&#x20;

* GraphQL은 Query와 Mutation으로 구분되며, Query는 Read시에, Mutation은 Create/Update/Delete에 사용됩니다.
* GraphQL은 클라이언트에서 자기가 필요한 데이터를 Query 할 수 있도록 하고,이를 위해 GraphQL은 클라이언트에서 사용할 Query Language를 정의합니다. 클리이언트가 필요한 데이터에 대한 Query를 선언하여 GraphQL에 넘기면 GraphQL은 Query를 해석해 서버에 필요한 데이터를 가져온 후 클라이언트에 해당 데이터를 반환합니다.
* Query에서 얻고자 하는 걸 지정합니다.
* Query(Read), Mutation(Command: Create, Update, Delete), Subscription(Event)

### [Json](https://ko.wikipedia.org/wiki/JSON)

* JSON (JavaScript Object Notation)은 데이터를 저장하거나 전송할 때 사용되는 경량의 DATA 교환 형식으로 JavaScript에서 객체를 만들 때 사용하는 표현식을 의미합니다.
* JSON은 사람과 기계 모두 이해가 쉬우며 용량이 작다는 장점이 있습니다.
* 하지만 JSON은 데이터 포멧일 뿐, 통신 방법이나 프로그래밍 문법에 속하지 않습니다.
* [**Json 개요**](https://www.json.org/json-ko.html)
* [**Json으로 작업하기**](https://developer.mozilla.org/ko/docs/Learn/JavaScript/Objects/JSON)

[**명령형 프로그래밍**](https://ko.wikipedia.org/wiki/%EB%AA%85%EB%A0%B9%ED%98%95\_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D)

명령형 프로그래밍이란 선언형 프로그래밍과 반대되는 개념으로 프로그래밍의 상태와 상태를 변경 시키는 구문의 관점에서 연산을 설명하는 프로그래밍 패러다임의 일종입니다.&#x20;

즉, 자연 언어의 명령법이 특정 동작에 대한 나열을 명령으로 표현하듯, 명령형 프로그램을 컴퓨터가 수행할 명령들을 순서대로 기재합니다.

[**선언형 프로그래밍**](../yuna-1/node.js.md)

프로그램이 어떻게 계산할지 보다는 무엇과 같은지를 설명하는 경우를 선언형 프로그래밍이라고 합니다.&#x20;

즉, 명령형 프로그램은 알고리즘을 명시하고 목표는 명시하지 않는데 반해, 선언형 프로그램은 목표를 명시하고 알고리즘은 명시하지 않습니다.

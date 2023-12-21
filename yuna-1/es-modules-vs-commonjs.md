# ES Modules vs CommonJS

### JavaScript module이란?

JavaScript 모듈은 각 파일 간의 상호작용을 위한 시스템이다. 모듈이 등장한 배경은 다음과 같습니다.

기존 웹은 JavaScript의 비중이 크지 않았지만, 점점 더 JavaScript가 중요해지면서 스크립트 파일의 수가 늘어나고, 이들 간의 상호작용이 필요해졌습니다. 이를 처리하기 위해 JQuery 등을 사용했으나 여러 문제점이 대두 되어 지금의 모듈 시스템이 적용되었습니다.

Node.js에선 이미 CommonJS와 같은 모듈 시스템이 존재하고 있었고, ES Modules은 JavaScript의 최신 모듈 시스템입니다.

***

### ES Modules이란?

ES Module은 JavaScript의 공식 모듈 시스템으로, import와 export를 사용해 분리된 JavaScript 파일끼리 서로 접근이 가능하게 합니다. 기본적으로 내보내기는 export와 default를 사용하고, 가져오기는 import를 사용합니다.

```
// export 내보내기
// test.js

export functuin example (num) {
// ... 생략
}

or

const example2 = function (num) {
// ... 생략}

export {example2}
```

```
// 사용하려는 객체만 선택해서 가지고 오기

import { example} from './test';
example(10);

// 모든 객체를 가져오기

import * as obj from './test';
obj.example(10);
obj.example2(10);
```

```
// export default를 이용하여 내보내기
// test.js

const obj = {

example1 : function(num) {
//...생략
},

example2 : function(num) {
//...생략
}
}

export default obj
```

```
// default 키워드를 이용하여 내보낼 때 사용한 명칭을 기대로 쓸 필요는 없다.

import testObj from './test'
testObj.example1(10);
testObj.example2(30);
```

### ES Modules의 진행 순서

브라우저에서 ES Modules은 구성, 인스턴스화, 평가 3 단계를 걸쳐 동작합니다. 브러우저는 자바스크립트 파일 자체를 사용할 수 없기 때문에, 모듈 레코드라고 하는 데이터 구조로 변환해야 합니다. 이 과정에서 모듈은 해당 파일의 모든 구문을 분석합니다. 파일을 불러오는 것은 로더가 담당하며 이는 ES Modules 명세가 아니라 HTML 명세를 따릅니다. 하여  script 태그에 type="module"을 적어 entry 파일로 지정합니다.

#### 1. 구성

entry 파일부터 inport 문을 찾아가며 필요한 모든 파일을 모듈 레코드로 구문 분석합니다.

* 모듈이 들어 있는 파일을 어디서 다운로드 할 것인지 확인합니다.&#x20;
* URL이나 파일 시스템에서 파일을 다운로드 합니다.
* 파일을 모듈 레코드로 구문 분석합니다.

#### 2. 인스턴스화

* export된 값을 모두 배치하기 위한 메모리 공간을 찾습니다.
* export와 import들이 이런 메모리 공간을 가리키도록 합니다.
* 이를 연결(linking)이라고 합니다.
* 이 과정에서는 메미로 공간을 찾고 지정할 뿐 실제로 값을 채우진 않습니다.

#### 3. 평가

* 코드를 실행하여 상자의 값을 변수의 실제 값으로 채웁니다.

***

### [CommonJS란?](https://nodejs.org/api/modules.html)

CommonJs는 자바스크립트의 모듈화를 위한 프로젝트 중 하나로,  내보내기의r경우 exports와  module.exports를 사용하고 가져오기의 경우에는 require()을 사용합니다.

```
// exports를 통한 내보내기
//test.js
function example(param) {
//...생략
}

exports.example = example;
```

```
// require을 이용한 가져오기

const obj = require('./test');

obj.example(10);
```

```
// module.exports를 통한 내보내기
// test.js

const obj = {

example : function(num) {
// ... 생략략
}

module.exports = obj;

//가져오기는 동일
```

***

### **CommonJS**

* 파일 시스템에서 파일을 로드한다.
* 파일을 불러오는 동안 **주 스레드를 차단한다.**
* 그렇기에 파일 로드 - 구문 분석 - 인스턴스화 - 평가가 각 파일마다 바로 실행된다.
* 그렇기에 모듈 지정자에 변수를 넣을 수 있다.
* export 객체에 값을 **복사**해서 넣는다.

### **ES Module**

* entry 파일의 구문 분석 후 의존성(import)을 확인해서 해당 의존성 파일을 찾아서 다시 구문 분석을 반복한다.
* 파일을 불러오는 동안 **주 스레드를 차단하지 않는다.**
* 인스턴스화, 평가는 더 이상 구문 분석할 의존성이 발견되지 않으면 실행한다
* 그렇기에 모듈 지정자에 변수를 넣을 수 없다(다만 동적 import를 쓰면 가능)
* export는 **참조**를 반환하는 함수를 정의한다.
* 동적 import는 별개의 entry 파일로 취급되어 새로운 그래프를 만든다.

### **이 차이는 어떤 결과를 부르는가?**

* export하는 파일에서 비동기 처리로 값이 바뀐다면, CommonsJS에서는 반영이 되지 않지만 ESM은 반영 될 수 있다(비동기로 다시 호출한다면).
* 순환 참조의 경우 CommonJS는 빈 객체를, ESM은 RefernceError를 발생시킨다.
* 자세한 설명은 [여기](https://yoeubi28.medium.com/commonjs-esm-%EB%AA%A8%EB%93%88-%EC%88%9C%ED%99%98-%EC%B0%B8%EC%A1%B0-%EC%B0%A8%EC%9D%B4-e5cd1047deaf)에서 확인

\

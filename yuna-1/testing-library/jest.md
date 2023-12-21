# Jest

### [Jest란?](https://jestjs.io/)

jest는 페이스북에서 개발한 Javascript 테스트 프레임워크 이고 기본적으로 JS바탕인 프론트엔드 환경에서 많이 쓰인다. 주로 React 애플리케이션과 함께 사용되지만 Babel , TypeScript , Node , Angular , Vue 등을 사용하는 프로젝트에서 작동한다고 Jest 공식 사이트에 나와있다. 이처럼 출시 초기에는 프론트엔드에서 주로 쓰였지만 최근에는 백엔드에서도 기존의 자바스크립트 테스팅 라이브러리를 대체하고 있다. 또한 Jest는 다양한 기능과 쉬운 사용성으로 인기가 높은데 그 예로, config를 따로 설정하지 않아도 빠르게 테스팅 환경을 만들 수 있고, Jest는 라이브러리 하나만 설치하면, Test Runner와 Test Matcher 그리고 Test Mock 프레임워크까지 제공해주기 때문에 따로 다른 라이브러리를 설치하지 않아도 돼서 사용이 편리하다.

Jest 이전에는 자바스크립트 코드를 테스트하라면 여러 가지 테스팅 라이브러리를 조합해서 사용하곤 했다. 예를 들어, Mocha나 Jasmin을 Test Runner로 사용하고, Chai나 Expect와 같은 Test Matcher를 사용했으며, 또한 Sinon과 Testdouble 같은 Test Mock 라이브러리도 필요했었다. 이 라이브러리들은 굉장히 유사하지만 살짝씩 다른 API를 가지고 있었기 때문에, 여러 프로젝트에 걸쳐서 일하는 자바스크립트 개발자들에게 혼란을 주기도 했다.

Jest는 거의 모든 기능을 갖춘 테스팅 도구이며 Mocha와 Chai처럼 RSpec의 describe-it을 지원하고, expect로 단언(assertion)할 수 있다. Mocking도 다양한 레벨에서 쉽게 사용할 수 있다.

* [BETTER SPECS](https://www.betterspecs.org/) : RSpec Best practice 모음&#x20;
* [Ginkgo - Go 언어 개발자를 위한 BDD 테스팅 프레임워크](https://youtu.be/gfTsSBRvdqI) : Go 언어
* [JUnit5로 계층 구조의 테스트 코드 작성하기](https://johngrib.github.io/wiki/junit5-nested/) : Java 언어
* [Let’s RSpec](https://github.com/ahastudio/til/blob/main/ruby/20161206-rspec-let.md) : Jest는 RSpec의 let 같은 걸 지원하지 않기 때문에, 핵심 아이디어를 가져와서 적당한 수준에서 잘 써야 한다.
* [Given-When-Then](../node.js.md)

### Jest 설치하기

```
// 개발자 도구이기 때문에 -D를 붙여 설치한다.
npm install -D jest
```

### Jest 사용하기

````
// package.json을 설정합니다.

```json
"scripts": {
    "start": "parcel --port 8081",
    "build": "parcel build",
    "check": "tsc --noEmit",
    "lint": "eslint --fix --ext .js,.jsx,.ts,.tsx .",
    "test": "jest",
    "coverage": "jest --coverage --coverage-reporters html",
    "watch:test": "jest --watchAll"
  },
```
````

### Jest Test 실행하기

```
// npm 명령어를 사용합니다.
npm test
```

### Jest Test Code 예시

<pre><code>// example.tsx
<strong>
</strong><strong>export const sum = (a: number, b: number) : number => {
</strong>    return a + b;
}
</code></pre>

```
// example.test.ts

import {sum} from './sum';
import {describe, expect, test} from '@jest/globals';

describe('sum module', () => {
  test('adds 1 + 2 to equal 3', () => {
    expect(sum(1, 2)).toBe(3);
  });
});
```

### Jest가 Test 파일로 인식하는 경우

Jest는 .test나 .spec이 포함되거나 \_\_tests\_\_ 폴더 안에 있는 파일을 감지하여 테스트를 수행한다.

* 테스트를 하려고 하는파일명.test.tsx
* 테스트를 하려고 하는 파일명.spec.tsx
* tests 폴더 안에 있는 파일

### Test

```javascript
import {sum} from './sum';
import {describe, expect, test} from '@jest/globals';

describe('sum module', () => {
  test('adds 1 + 2 to equal 3', () => {
    expect(sum(1, 2)).toBe(3);
  });
});
```

### &#x20;파일의 구조

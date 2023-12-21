# React StrictMode

## [React StrictMode](https://ko.legacy.reactjs.org/docs/strict-mode.html)

StricMode는 애플리케이션 내의 잠재적인 문제를 알아내기 위한 도구입니다. Fragment와 같이 UI를 렌더링하지 않으며, 자손들에 대한 부가적인 검사와 경고를 활성화합니다.

Strict 모드는 개발 모드에서만 활성화되기 때문에, 프로덕션 빌드에는 영향을 끼치지 않습니다.

```typescript
// stricMode 활성화 예제

import React from 'react';

function ExampleApplication() {
  return (
    <div>
      <Header />
      <React.StrictMode>
        <div>
          <ComponentOne />
          <ComponentTwo />
        </div>
      </React.StrictMode>
      <Footer />
    </div>
  );
}
```

### StricMode 장점

* [안전하지 않은 생명주기를 사용하는 컴포넌트 발견](https://ko.legacy.reactjs.org/docs/strict-mode.html#identifying-unsafe-lifecycles)
* [레거시 문자열 ref 사용에 대한 경고](https://ko.legacy.reactjs.org/docs/strict-mode.html#warning-about-legacy-string-ref-api-usage)
* [권장되지 않는 findDOMNode 사용에 대한 경고](https://ko.legacy.reactjs.org/docs/strict-mode.html#warning-about-deprecated-finddomnode-usage)
* [예상치 못한 부작용 검사](https://ko.legacy.reactjs.org/docs/strict-mode.html#detecting-unexpected-side-effects)
* [레거시 context API 검사](https://ko.legacy.reactjs.org/docs/strict-mode.html#detecting-legacy-context-api)
* [Ensuring reusable state](https://ko.legacy.reactjs.org/docs/strict-mode.html#ensuring-reusable-state)

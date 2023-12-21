# ESLint

### [ESLint란?](https://eslint.org/)

* ESLint는 ESCMAScript 코드에서 문제점을 검사하고 더 나은 코드로 정정하는 린트 도구 중 하나입니다.
* 포맷팅, 코드 품질 관리의 역할을 수행합니다.
* [ESLint의 Rules은 문서를 통해 확인이 가능합니다.](https://eslint.org/docs/latest/rules/)
* 이러한 규칙을 미리 설정해 놓은 것이 eslint:recommended 설정입니다.

### [VS code ESLint extension](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)

.vscode/setting.json 파일을 추가하여 JS/TS 파일을 저장할 때마다 ESLint를 실행하고 문제점을 고치게 설정할 수 있다.

```
{
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    }
}
```

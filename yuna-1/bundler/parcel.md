# Parcel

### [Parcel](https://parceljs.org/)

parcel은 간단한 설정만으로 사용이 가능한 번들러입니다. 여러 종류의 파일들을 자동으로 번들링하여 모듈 시스템을 사용하거나 에셋을 로드 할 수 있도록 도와줍니다. 또한 Hot Module Replacement(HMR)의 기능을 지원하여 개발 중인 애플리케이션을 실시간으로 반영할 수도 있습니다.

parcel은 기본적로 bavel과 postCSS를 내장하고 있기에, 새로운 기능이나 문법을 사용해도 호환성에 큰 문제가 발생하지 않으며, 코드 번들링 과정에서 자동으로 최적화를 수행하여 최종 번들의 크기를 최소화합니다.

[또한 내적으로 SWC를 사용하여 기존 도구보다 빠르다는 장점이 있습니다. ](https://github.com/ahastudio/til/tree/main/parcel)

[ES Module적극 활용하는 Vite도 빠른 속도를 자랑합니다.](https://github.com/ahastudio/til/tree/main/vite)

### Pacel 사용하기

```
// 설치하기
npm install -D parcel-bundler
```

```json
// package.json 파일 수정
"source": "./index.html",
```

```json
// parcel-reporter-static-files-copy 패키지 설치.
// .parcelrc 파일 작성
// static 폴더의 파일을 정적 파일로 serving 가능

{
  "extends": ["@parcel/config-default"],
  "reporters":  ["...", "parcel-reporter-static-files-copy"]
}
```

```
// 빌드
npx parcel build

// 정적 서버 실행
npx servor ./dist
```

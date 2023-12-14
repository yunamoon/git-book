# 1주차 TypeScript

### [TypeScript](https://www.typescriptlang.org/ko/)

* [초심자를 위한 문서](https://www.typescriptlang.org/ko/docs/handbook/typescript-from-scratch.html)
* [자바스크립트 유경험자를 위한 문서](https://www.typescriptlang.org/ko/docs/handbook/typescript-in-5-minutes.html)

### REPL&#x20;

간단히 REPL을 쓰고 싶다면 ts-node를 실행하면 된다.

```
// 설치 필요

npm i -D ts-node
npx ts-node
```

#### 1. 타입 지정

```
// TypeScript는 변수 선언 시 타입 지정 가능

// string 타입
let name : string;
// name = 213; > 타입에러 발생

// number 타입
let age : number;
// age = '문유나'; > 타입에러 발생

//  타입 생성
let human : {
name : string;
age : number;
};
// string 타입의 name과 number 타입의 age를 갖는 human 타입
human = {name : '문유나', age:13};
// human = {name:'유나'}; > human 타입의 요구 조건을 충족시키지 못해 오류

```

#### 2. 타입 정의

타입의 재사용을 위하여 타입을 정의하기도 한다.

* [타입 정의하기 ](https://www.typescriptlang.org/ko/docs/handbook/typescript-in-5-minutes.html#%ED%83%80%EC%9E%85-%EC%A0%95%EC%9D%98%ED%95%98%EA%B8%B0-defining-types)
* [타입 별칭과 인터페이스의 차이](https://www.typescriptlang.org/ko/docs/handbook/2/everyday-types.html#%ED%83%80%EC%9E%85-%EB%B3%84%EC%B9%AD%EA%B3%BC-%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4%EC%9D%98-%EC%B0%A8%EC%9D%B4%EC%A0%90)

```
//  타입 정의
let human : {
name : string;
age : number;
};
// string 타입의 name과 number 타입의 age를 갖는 human 타입
human = {name : '문유나', age:13};
//human = {name:'유나'}; > human 타입의 요구 조건을 충족시키지 못해 오류

// 타입 할당
let boy : human;
boy = {name: '문유나', age:28};
```

```
// interface 정의

interface Person {
name : string;
age : number;
};

let boy:Person;
boy = { name: '문유나', age:28};

```

```
// 함수 정의

function add(x:number, y:number):number {
return x+y;
};

add(1,2);
-> 3

add('유나','문')
-> 타입에러
```

#### 3. 고정된 값으로 타입 정의

Union 타입에서 유용하게 쓰인다.

```
// 고정된 값을 갖는 타입

let category: 'food';

category = 'food';
> 가능
category = 'books';
> 타입에러
```

#### 4. 배열 타입

```
// 배열 타입은 뒤에 []을 붙여준다.

let numbers : number[];
numbers = [1,2,3];
```

#### 5. Tuple

배열보다 엄격하게 타입을 관리하고 싶을 경우

```
// number
let numbers : number[];
numbers = [1,3,4,6,7,8];
numbers = ['a','b','c','d'];
> 타입에러

//any
let anythings :any[];
anythings = ['yuna',235]

//위치 지정
let pair : [string,number];
pair = ['yuna', 28];
pair = [28,'yuna'];
> 타입에러
```

#### 6. 타입 추론

타입을 지정하지 않은 경우에도 자동으로 타입을 추론하여 지정

```
const name = '문유나';
name = 32;
> 타입 에러
```

#### Union Type

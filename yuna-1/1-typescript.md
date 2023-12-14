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

function Add(x:number, y:number):number {
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

#### 7. [Union Type](https://www.typescriptlang.org/ko/docs/handbook/typescript-in-5-minutes.html#%EC%9C%A0%EB%8B%88%EC%96%B8-unions)

여러 타입 중 하나 일 수 있음을 지정하는 방법으로레거시 환경이나 코드 때문에 안쓰기 어렵다.

[ReactNode](https://github.com/facebook/react/blob/main/packages/shared/ReactTypes.js)

```
// Boolean
type bool = true | false;
// bool은 true이거나 false.

let test:bool;
test = true;
test = false;
test =3;
> 타입에러
```

```
// 매개변수를 제한하는 경우 유용

type category = 'food' | 'toy' | 'bag';

function FetchProducts({category} : {category:category}){
console.log('Fetch ${category}');
}

FetchProducts({category:'food'});
FetchProducts({category:'yuna'});
> 타입 에러
```

#### 8. [Optional Parameter](https://www.typescriptlang.org/docs/handbook/2/functions.html#optional-parameters)

함수 매개변수에서 사용된다.

```
// undefined가 필요한 경우

let targetName : string | undefined;
targetName = '문유나';
targetName undefined;

// 상기의 경우는 별로 없고, 
// 함수 매개 변수에서 Optional Parameter로 처리한다.
function Greeting(name?:string):string {
return `Hello, ${name || 'world'}`;
}

// 기본값을 잡아주면 더 좋다.
function Greeting(name?:string = 'world'):string {
return `Hello ${name}`;
}

// 매개변수고 오브젝트일 때도 활용할 수 있다.
function Greeting({name,age}:{
name:string;
age?:number;
}):string {
retrun age? `${name}(${age})`:name;
}

//오브젝트르 별도 타입 지정 가능
type human = { 
name:string;
age?:number;
};

function Greeting({name,age}:human):sting {
retrun age? `${name}(${age})`:name;
};
  
```

#### 9. Intersection Type

* [교집합](https://www.typescriptlang.org/ko/docs/handbook/typescript-in-5-minutes-func.html#%EA%B5%90%EC%A7%91%ED%95%A9)
* [Intersection Types](https://www.typescriptlang.org/docs/handbook/2/objects.html#intersection-types)

```
// 타입을 확장하는 가장 간단한 방법.

type human = {
name : string;
age : number;
};

type creature = {
hp : number;
mp : number;
}

type person = human & creature;

let person : person;
person = {name:'문유나', age:28, hp:100, mp:100};
```

### 10. Generics

* [Generics](https://www.typescriptlang.org/docs/handbook/2/generics.html)

### 11. Utility Types

* [Utility Types](https://www.typescriptlang.org/docs/handbook/utility-types.html)

### 12. Tips

* [Tips](https://velog.io/@lky5697/11-tips-that-help-you-become-a-better-typescript-programmer)

### 13. TypeScript의 큰 장점

1. Visual Studio Code 자동 완성과실시간 오류 검사가 가능하다.
2. 오래된 라이브러리의 경우 d.ts 파일만 따로 패키지 제공을 하니 확인 후 설치한다. 형태는 @types/\~\~\~이다.

* [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped)
* [DefinitelyTyped/types](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types)
* [DefinitelyTyped/types/react](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/master/types/react)

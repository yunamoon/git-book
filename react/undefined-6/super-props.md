# super(props)

### 1. class&#x20;

제가 아는 class는 붕어빵 틀입니다.

1. **생성자(Constructor)**: 붕어빵을 만들기 전에 틀을 빡빡 닦는 것처럼, 클래스의 생성자는 객체를 초기화하는데 사용됩니다.
2. **데이터(Data)**: 붕어빵 틀에 갖다 부은 소는 붕어빵을 만들 때 사용되는 데이터입니다.
3. **this 키워드**: 붕어빵 틀에서 특정한 위치에 팥소를 넣는 것처럼, 객체 내부에서 현재 객체를 가리키는 키워드로 사용됩니다.
4. **객체(인스턴스)**: 완성된 붕어빵은 붕어빵 틀로부터 만들어진 객체입니다.
5. **오버라이딩(Overriding)**: 팥붕, 슈붕, 민트붕, 김치붕과 같이 붕어빵의 종류를 다양하게 만드는 것처럼, 클래스에서 부모 클래스의 메서드를 자식 클래스에서 재정의하는 것을 말합니다.
6. **상속(Inheritance)**: 사용하던 붕어빵 틀을 사용해 머리가 두개 달린 붕어빵 틀을 만들 수 있는 것처럼, 부모 클래스의 특성과 기능을 자식 클래스에서 재사용하는 것을 말합니다.
7. **캡슐화(Encapsulation)**: 반죽 안에 소가 갇혀 있는 것을 소가 보호되고 있다고 표현하는 것처럼, 클래스의 데이터와 기능을 하나로 묶어 외부에서의 접근을 제한하는 것을 말합니다.
8. **정적 메서드(Static Method)**: 붕어빵틀 안에서 실행되는 메서드(함수)를 붕어빵의 동작과는 독립적으로 정의하는 것처럼, 객체의 인스턴스와 상관없이 클래스 레벨에서 실행되는 메서드를 말합니다.

### 2. **Constructor**

* 생성자를 사용하면 인스턴스화된 객체에서 다른 메세더를호출하기 전에 수행해야 하는 사용자 지정 초기화를 제공할 수 이있습니다. new class로 새로운 class를 생성하면 넘겨 받은 인수와 함께 생성자가 먼저 실행됩니다.

```javascript
// 예제

class User {
    constructor(name) {
    this.name =name;
    }
    
    sayHello() {
    console.log(`안녕 ${this.name}`)
    }
}

let user = new User('유나')
user.sayHello();

```

### 3. super&#x20;

```jsx

constructor(props) {
        super(props);
        this.state = {
            charges : [
                {id : 1, expenditure : "뭔데" , charge :10000},
                {id : 2, expenditure : "난데" , charge :53000},
                {id : 3, expenditure : "근데" , charge :40000}
            ]
        
        }
    }

```

* 자바스크립트에서 super는 자식 클래스 내에서 부모 클래스의 생성자를 호출할 때 사용
* 자바스크립트에서 super는 자식 클래스 내에서 부모 클래스의 메소드를 호출할 때 사용

```javascript
// 예제 부모 클래스

class User {
    constructor(name) {
    this.name =name;
    }
    
    sayHello() {
    console.log(`안녕 ${this.name}`)
    }
}

// 예제 자식 클래스
class Member extends User {
    constructor(name, age) {
    super(name);
    this.age = age;
    }
    
    whoIs() {
        return  this.age + '살' + super.sayHello();
    }    
}

let member = new Member('문유나', 29);
member.whoIs();
```

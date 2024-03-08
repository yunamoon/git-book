# react 불변성

### 1. React 불변성

* 불변성이란 사전적 의미로 값이나 상태를 변경할 수 없는 것을 의미

### 2. 원시형 vs 참조형

* 원시형 타입 &#x20;
  * 원시타입은 고정된 크기로 콜스택 메모리에 저장되고, 실제 데이터가 변수에 할당
  * boolean ,  string, number, null, undefined, symbol&#x20;
* 참조형 타입
  * 참조타입은 데이터 크기가 정해져있지 않고 콜스택 메모리에 저장됨
  * 변수 값 변경 하면 heap에서만 변경
  * 데이터값이 heap에 저장되고 변수에 heap 메모리 주소 값이 할당
  * object, array

### 3. 왜 지켜야 하나요?

* 원본 데이터가 변경되면 원본 데이터를 참조하는 다른 객체에서 오류가 날 수 있음
* 불변성을 지켜야 변경 사항 확인이 가능함

### 4. 어떻게 지켜요?

* 참조 타입에서는 콜스택 주소는 같은데 heap 메모리 값만 바꿔주기 때문에 불변성을 유지하지 못했으므로 아예 새로운 배열이나 객체를 반환하는 메소드를 사용
  * spread ,  operator, map, slice, reduce 등

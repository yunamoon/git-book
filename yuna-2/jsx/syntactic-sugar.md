# Syntactic sugar

### [Syntactic sugar란?](https://en.wikipedia.org/wiki/Syntactic\_sugar)

프로그래밍 언어 차원에서 제공되는 논리적으로 간결하게 표현하는 것을 말하며, 중복되는 로직을 간결하게 표현하기 위해 등장했습니다.

### Syntactic sugar 예제

```typescript
// Not Syntatic Sugar
int a;
if(SomeFunction() == 2)
   a = 4;
else
   a = 9;
   
//  Syntatic Sugar
int a = SomeFunction() == 2 ? 4 : 9;
```

```typescript
// Not Syntatic Sugar
x = x + 5;

// Syntatic Sugar
x += 5;
x++;
++x;
--x;
```

* [더 많은 예제 ](https://www.quora.com/What-is-syntactic-sugar-in-programming-languages)

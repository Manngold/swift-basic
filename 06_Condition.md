# Condition

## if, else if, else

조건문은 다른 문법과 유사하다

```
var condition : Bool = true

if condition {
    print("condition is true")
} else{
    print("coditions is false")
}
```

조건에 괄호를 생략해도 잘 작동한다

주의할 점은 다른 문법들은 0, 1로 조건문을 작동시켰지만 Swift에서는 동작이 안된다

```
var someInteger : Int = 1

if someInteger {
    print("condition is true")
} else{
    print("coditions is false")
}
```

따라서 위 코드는 오류가 발생한다

## Switch

다른 문법의 switch문은 break를 넣어주지만 Swift는 break가 없어도 허용

### 범위 연산자

`..`, `...`으로 표현할 수 있다

`..<`는 ~이상 ~미만

`...`는 ~이상 ~이하로 표현 가능하다

```
var someIntegers : Int = 50

switch someIntegers {
case 10:
    print("someIntegers is 10")
case 10..<100:
    print("under 100 and over 10")
case 100...Int.max:
    print("Soooooo big")
default:
    print("unknown")
}
```

범위 연산자를 적용한 switch문 작성

그리고 default가 없을 경우 오류 발생

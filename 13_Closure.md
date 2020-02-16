# Closure

코드의 블럭이고 first-citizen이다

따라서 함수는 `이름있는 클로저`라고 볼 수 있다

클로저의 기본적인 정의는

```
{ (매개변수) -> 반환타입 in
    실행코드
}
```

```
var sum: (Int, Int) -> Int = {
    (a: Int, b: Int) -> Int in
    return a + b
}

print(sum(1, 2))
```

이렇게 사용이 가능하다

## 함수의 전달인자로서의 클로저

```
let sum : (Int, Int) -> Int
sum = {(a: Int, b: Int) -> Int in
    return a + b
}

let substract : (Int, Int) -> Int
substract = {(a: Int, b: Int) -> Int in
    return a - b
}

let divide : (Int, Int) -> Int
divide = {(a: Int, b: Int) -> Int in
    return a / b
}

func calculate(a : Int, b: Int, method : (Int, Int) -> Int) -> Int {
    return method(a, b)
}

calculate(a: 5, b: 5, method: sum)
```

# Closure - Advance

## 후행클로저

클로저가 함수의 마지막 전달인자라면 마지막 매개변수 이름을 생략하고 외부에 클로저를 구현할 수 있다

```
func calculate(a : Int, b: Int, method : (Int, Int) -> Int) -> Int {
    return method(a, b)
}

var result : Int

result = calculate(a: 5, b: 5) {(left: Int, right : Int) -> Int in
    return left + right
}
```

## 반환타입 생략

반환타입이 어떤 것인지 알기 때문에 굳이 쓰지 않아도 된다

```
func calculate(a : Int, b: Int, method : (Int, Int) -> Int) -> Int {
    return method(a, b)
}

var result : Int

result = calculate(a: 5, b: 5, method: {(left: Int,right: Int) in
    return left + right
})
```

후행 클로저와 함께 사용이 가능하다

```
func calculate(a : Int, b: Int, method : (Int, Int) -> Int) -> Int {
    return method(a, b)
}

var result : Int

result = calculate(a: 5, b: 5) {(left: Int, right : Int) in
    return left + right
}
```

## 단축인자 이름

클로저의 매개변수 이름이 굳이 불필요하다면 단축인자 이름을 확인할 수 있다

$0 $1 ... 로 표현이 된다

```
func calculate(a : Int, b: Int, method : (Int, Int) -> Int) -> Int {
    return method(a, b)
}

var result : Int

result = calculate(a: 5, b: 5, method : {
    return $0 + $1
})
```

마찬가지로 후행클로저와 함께 사용이 가능하다

```
func calculate(a : Int, b: Int, method : (Int, Int) -> Int) -> Int {
    return method(a, b)
}

var result : Int

result = calculate(a: 5, b: 5) {
    return $0 + $1
}
```

## 암시적 반환

마지막 줄은 반환 값이라는 것을 가정하고 return을 생략한다

```
func calculate(a : Int, b: Int, method : (Int, Int) -> Int) -> Int {
    return method(a, b)
}

var result : Int

result = calculate(a: 5, b: 5) {
    $0 + $1
}
```

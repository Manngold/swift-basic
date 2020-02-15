# Optional

값이 있을 수도 없을 수도 있음을 뜻한다

nil의 가능성을 명시적으로 표현해주는 것이다

그렇다면 전달받는 값이 Optional 값이 아니라면 nil 체크를 하지 않아도 된다

```
func someFunc(option : Int?){}
func otherFunc(option : Int){}

someFunc(option: nil)
otherFunc(option: nil)
```

매개변수의 데이터 타입 뒤에 `?`를 붙이면서 nil이 들어갈 수도 있다는 것을 표시할 수 있다

```
let optionalValue : Optional<Int> = nil
let otherOptional : Int? = nil
```

위와 같이 표현 할 수도 있다

## ! ?

Optional을 표현하는 방식에는 물음표와 느낌표가 존재한다

### ! (암시적 추출 옵셔널)

```
var optionalValue : Int! = 100

optionalValue = optionalValue + 1
optionalValue = nil
optionalValue = optionalValue + 1
```

기존 변수처럼 사용이 가능하지만 nil이 할당된 이후에는 연산 불가

### ? (Optional)

```
var optionalValue : Int? = 100

optionalValue = optionalValue + 1
optionalValue = nil
```

nil은 할당 가능하지만 `!`와 다르게 변수로 사용 불가능

## Optional Unwrapping

Optional 값을 추출해내는데 두 가지 방법이 존재한다

1. Optional Binding

nil 체크 + 안전한 값 추출

변수가 존재 할 때, Optional을 적용하면 보호막에 둘러싸여 있다고 생각하면 쉽다

따라서 값을 추출할 때, 먼저 값이 있는지 체크를 하고 이후 값을 꺼낸다

```
func printName (_ name : String){
    print(name)
}

var myName : String! = nil

printName(myName)
```

일반적인 String 데이터 타입이 아니기 때문에 에러 발생

따라서 `if let` 구문을 사용해서 매개변수를 전달해준다

```
func printName (_ name : String){
    print(name)
}

var myName : String! = nil

if let name: String = myName {
    printName(name)
} else{
    print("myName == nil")
}
```

이때 `name`은 `if let`구문 내에서만 사용이 가능하고 구문 밖에서는 접근이 불가능하다.

여러개의 Optional도 바인딩이 가능하다

```
var myName : String? = "manngold"
var yourName : String? = nil

if let name = myName, let friend = yourName {
    print("\(name) and \(friend)")
}

yourName = "kim"

if let name = myName, let friend = yourName {
    print("\(name) and \(friend)")
}
```

처음 `if let` 구문에서는 `yourName`이 nil이기 때문에 실행이 안되지만 할당 후에는 정상적으로 출력이 된다

2. Force Unwrapping (강제 추출)

Optional의 값을 강제 추출

```
func printName (_ name : String){
    print(name)
}

var myName : String? = "manngold"

printName(myName!)
```

`!`를 붙여서 강제로 Optional 값을 추출한다

```
func printName (_ name : String){
    print(name)
}

var myName : String? = "manngold"

printName(myName!)

myName = nil

printName(myName)
```

두번째 myName은 강제 추출시 값이 없으므로 오류가 발생한다

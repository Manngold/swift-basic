# Function

```
func sum (a: Int, b: Int) -> Int{
    return a + b
}

var num1 = 3
var num2 = 5

sum(a: num1, b: num2)
```

위 코드는 기본적인 함수 선언과 사용이다

```
func printName (name : String) -> Void{
    print(name)
}

let name : String = "manngold"

printName(name: name)
```

return 값이 없는 함수는 Void를 적어준다

```
func printName (name : String) -> Void{
    print(name)
}

let name : String = "manngold"

printName(name: name)
```

`-> Void`를 생략 가능

```
let name : String = "manngold"

func printName (){
    print(name)
}

printName()
```

마찬가지로 매개변수가 없어도 생략이 가능하다

# Function - Advance

```
func greeting (friends : String, me : String = "manngold") {
    print("Hello \(friends)! my name is \(me)")
}

greeting(friends: "minsu")

greeting(friends: "minsu", me: "taeho")
```

매개변수의 기본값을 설정할 수 있따

호출시 기본값을 다른 값으로 바꿔줄 수도 있다

### 전달인자 레이블

```
func greeting (to friends : String, from me : String = "manngold") {
    print("Hello \(friends)! my name is \(me)")
}
greeting(to: "min su", from : "jin su")
```

함수 내부에는 매개변수를 넣고 호출시 레이블을 넣어준다

함수 이름에 레이블까지 포함되므로 전달인자 레이블이 없는 이전 greeting와 중복이 되지 않는다

### 가변인자 레이블

전달받을 값의 갯수를 알기 어려울 때 데이터 타입 뒤에 `...`을 붙여서 사용할 수 있고 함수당 하나만 가질 수 있다

```
func greeting (who friends : String..., from me : String = "manngold") {
    print("Hello \(friends)! my name is \(me)")
}
greeting(who: "min su", "cho", "kim", from : "jin su")
```

### 함수의 할당

함수는 일급 객체로 변수에 할당이 가능하다

```
func greeting (who friends : String, from me : String = "manngold") {
    print("Hello \(friends)! my name is \(me)")
}
greeting(who: "kim", from : "jin su")

var someFunction: (String, String) -> Void = greeting(who:from:)
someFunction("cho","kim")
```

주의사항으로 매개변수의 타입이 다른 경우 할당이 안된다 (가변인자를 받는 함수도 할당이 안된다)

```
func greeting (who friends : String, from me : String = "manngold") {
    print("Hello \(friends)! my name is \(me)")
}
greeting(who: "kim", from : "jin su")

func someFunc (function : (String, String) -> Void){
    function("cho", "kim")
}

someFunc(function: greeting(who:from:))
```

매개변수로 함수를 받아서 실행할 수도 있다

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

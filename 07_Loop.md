# Loop

## for...in...

```
var arr : [Int] = [1,2,3]

var dic : [String: Int] = ["kim": 20, "cho": 27]

for num in arr {
    print(num)
}

for (name, age) in dic{
    print("my name is \(name) and i'm \(age)" )
}
```

다른 문법과 유사하다

## while

```
var arr : [Int] = [1,2,3]

while arr.count > 1 {
    arr.removeLast()
}
```

조건부에 괄호가 안들어가도 된다

## repeat...while

다른 문법들에서 do...while과 같은 동작을 한다

```
var arr : [Int] = [1,2,3]

repeat{
    arr.removeLast()
}while arr.count > 1
```

`arr.removeLast()`가 일단 먼저 실행된다

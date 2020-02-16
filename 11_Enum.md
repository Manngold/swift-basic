# Enum(열거형)

enum은 타입이므로 대문자 카멜 케이스를 사용하여 정의

각 case는 소문자 카멜 케이스로 정의하고 그 자체가 고유의 값이다

```
enum Weekday {
    case mon
    case tue
    case wed
    case thu,fri,sat,sun
}

var day : Weekday = Weekday.mon

day = .fri

switch day {
case .mon, .tue, .wed, .thu:
    print("평일")
case .fri:
    print("불금")
case .sat, .sun :
    print("주말")
}
```

`day`는 `Weekday`라는 열거형 데이터 타입이 명시되어 있기 때문에 `day = .fri`로 할당이 가능하고

`switch`문에서는 `default`를 필수적으로 사용해야 하지만 `enum`에서 모든 케이스를 다 처리했을 경우 default를 처리 안해도 괜찮다

## 원시값

enum은 정수값을 가질 수 있다

`rawValue`를 사용해서 값을 가져올 수 있으며 case별로 다른 값을 가져야 한다

```
enum Fruit : Int {
    case apple = 0
    case grape
    case banana
    // case melon = 0
}

print(Fruit.grape.rawValue)
print(Fruit.banana.rawValue)
```

값을 할당하지 않아도 자동적으로 1씩 증가하며 할당을 해준다

enum 케이스에서 raw value는 항상 `unique`

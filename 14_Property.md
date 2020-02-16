# Property

```
struct Student {
    var name : String = "manngold"
    var age : Int = 27

    var westernAge: Int{
        get {
            return age - 1
        } set(koreanAge){
            age = koreanAge + 1
        }
    }
}

var manngold : Student = Student()

manngold.westernAge = 30
```

`westernAge`는 연산 프로퍼티로 `get`과 `set`을 통해서 연산을 수행할 수 있다

```
struct Student {
    var name : String = "manngold"
    var age : Int = 27

    var westernAge: Int{
        get {
            return age - 1
        } set(koreanAge){
            age = koreanAge + 1
        }
    }

    var selfIntroduce : String {
        get {
            return "hello my Name is \(name)"
        }
    }
}

var manngold : Student = Student()

manngold.westernAge = 30
manngold.selfIntroduce
```

읽기 전용 연산프로퍼티 추가로 get으로만 작동하는 기능을 생성할 수 있다

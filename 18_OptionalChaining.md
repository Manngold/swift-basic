# Optinal Chaining

구조체나 클래스를 선언할 때, 구조체 안에 또 다른 구조체 인스턴스가 들어올 수 있고 계속해서 다른 구조체 인스턴스를 받을 수도 있다

이 때 옵셔널의 값이 nil인지 체크를 해줘야 하는데 Optinal chaining을 유용하게 활용할 수 있다

```
class Person {
    var name : String
    var job : String?
    var home : Apartment?

    init(name : String){
        self.name = name
    }
}

class Apartment {
    var buildingNumber : String
    var roomNumber : String
    var `guard` : Person?
    var owner : Person?

    init(dong: String, ho:String){
        buildingNumber = dong
        roomNumber = ho
    }
}

var manngold : Person? = Person(name: "manngold")
var apert : Apartment? = Apartment(dong: "101", ho: "202")
var kim : Person? = Person(name: "kim")
```

다음과 같이 클래스를 생성하고 `guard`의 `job`프로퍼티를 꺼내기 위해서 다음과 같이 코드를 작성해야 한다.

```
func findJob (owner: Person?){
    if let owner = owner {
        if let home = owner.home{
            if let `guard` = home.guard{
                if let guardJob = `guard`.job{
                    print("my guard's job is \(guardJob)")
                } else{
                    print("no job")
                }
            }
        }
    }
}

findJob(owner: manngold)
```

이렇게 되면 코드가 길어지기 때문에 `Optional Chaining`을 사용해서 코드의 양을 줄이고 가독성도 높일 수 있다

```
func findJobOptinalChaining(owner: Person?) {
    if let guardJob = owner?.home?.guard?.job{
        print(guardJob)
    }else{
        print("no job")
    }
}
```

체인을 따라가면서 nil값이 걸리는 순간 구문은 끝나게 된다

## nil 병합 연산자

옵셔널 체이닝에서 nil을 받았을 때, 값을 설정할 수 있다

```
manngold?.home = apart
manngold?.home?.guard = kim

var guardJob = manngold?.home?.`guard`?.job ?? "경비원"
```

`??`는 job의 값이 nil일 때, 뒤에 있는 값을 할당해준다

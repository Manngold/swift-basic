# Class

1. 상속 (Inheritance) : 클래스의 여러 속성을 다른 클래스에 물려 줌
2. 타입 캐스팅 (Type casting) : 런타임에 클래스 인스턴스의 타입을 확인
3. 소멸자 (Deinitializers) : 할당된 자원을 해제(free up) 시킴
4. 참조 카운트 (Reference counting) : 클래스 인스턴스에 하나 이상의 참조가 가능

구조체는 값 타입인데 클래스는 참조 타입이고 다중 상속이 되지 않는다

```
class Sample {
    var mutableProp : Int = 100 // 가변 프로퍼티
    let immutableProp : Int = 100 // 불변 프로퍼티

    static var typeProp : Int = 100 // 타입 프로퍼티

    // 인스턴스 메서드
    func instanceMethod() {
        print("instance method")
    }

    // 타입 메서드
    // 재정의 불가능
    static func typeMethod(){
        print("type method - static")
    }

    // 재정의 가능 타입 메서드 - class
    class func classMethod(){
        print("type method - class")
    }
}

// 가변 인스턴스

//var mutable : Sample = Sample()

// mutable.mutableProp = 200
// mutable.immutableProp = 200

// 불변 인스턴스

//let immutable: Sample = Sample()

//immutable.mutableProp = 200

Sample.typeProp = 300

Sample.typeMethod()
```

구조체와 크게 다른 부분은 없지만 재정의가 가능한 class method가 존재하고

`let` 키워드로 불변 인스턴스를 생성해도 가변 프로퍼티는 재설정이 가능하다

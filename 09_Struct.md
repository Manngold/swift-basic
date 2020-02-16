# Struct

1. 값을 저장하기 위한 프로퍼티 정의
2. 기능을 제공하기 위한 메소드 정의
3. subscript 문법을 이용해 특정 값을 접근할 수 있는 subscript 정의
4. 초기 상태를 설정할 수 있는 initializer 정의
5. 기본 구현에서 기능 확장
6. 특정한 종류의 표준 기능을 제공하기 위한 프로토콜 순응(conform)

위와 같은 기능을 제공한다. 이후 클래스는 구조체와 달리 더 많은 기능을 제공한다

```
struct Sample {
    var mutableProp : Int = 100 // 가변 프로퍼티
    let immutableProp : Int = 100 // 불변 프로퍼티

    static var typeProp : Int = 100 // 타입 프로퍼티

    // 인스턴스 메서드
    func instanceMethod() {
        print("instance method")
    }

    // 타입 메서드
    static func typeMethod(){
        print("type method")
    }
}

// 가변 인스턴스

var mutable : Sample = Sample()

// mutable.mutableProp = 200
// mutable.immutableProp = 200

// 불변 인스턴스

let immutable: Sample = Sample()

//immutable.mutableProp = 200

Sample.typeProp = 300

Sample.typeMethod()

```

위처럼 구조체를 생성하고 내부에 가변, 불변, 타입 프로퍼티, 메소드를 생성할 수 있다

그리고 인스턴스를 생성할 때도 가변,불변이 있고 가변으로 인스턴스를 생성시 가변 프로퍼티는 수정이 가능하지만 불변 프로퍼티는 수정이 불가능하고

불변 인스턴스는 불변은 물론 가변 프로퍼티도 수정이 불가능하다

타입은 인스턴스를 생성하지 않고 바로 사용이 가능한 프로퍼티와 메소드이다

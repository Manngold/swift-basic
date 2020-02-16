# Inheritance

상송은 다음과 같이 표현된다

```
class 클래스명 : 상속받을 클래스 {
    ...
}
```

그리고 클래스 내에서는 class, final, static, final class 키워드를 사용해서 재정의 권한을 설정할 수 있다

```
class Person {
    var name : String = ""

    func selfIntroduce(){
        print("my name is \(name)")
    }

    // final 키워드를 통한 재정의 방지
    final func sayHello(){
        print("hello! \(name)")
    }

    // static 키워드를 통한 재정의 방지

    static func typeMethod(){
        print("this is type method")
    }

    // class 타입 메소드는 재정의가 가능
    class func classMethod(){
        print("this is class method")
    }

    // final static = static
    final class func finalClassMethod(){
        print("this is final class method")
    }
}
```

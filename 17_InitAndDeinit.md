# Init and Deinit

클래스를 선언했을 때, 프로퍼티의 값을 넣어주지 않으면 에러가 발생한다

따라서 클래스의 생성과 값의 할당을 하고싶을 경우 초기화를 통해서 클래스의 프로퍼티를 정의한다

```
class Student {
    var name : String
    var age : Int

    init(name: String, age: Int) {
        self.name = name
        self.age = age
    }
}

var manngold : Student = Student(name : "manngold", age: 27)

manngold.name
manngold.age
```

`init` 키워드를 통해서 초기화를 할 수 있고 인스턴스를 생성할 때, 초기값을 넣어준다

## 프로퍼티를 초기화할 필요가 없을 때,

프로퍼티를 꼭 초기화 할 필요가 없는 경우가 존재한다 그때는 `Optional`을 사용하고 다른 초기화를 만들어주면 된다

```
class Student {
    var name : String
    var age : Int
    var nickName : String?

    convenience init(name:String, age: Int, nickName: String){
        self.init(name: name, age: age)
        self.nickName = nickName
    }

    init(name: String, age: Int) {
        self.name = name
        self.age = age
    }
}

var manngold : Student = Student(name : "manngold", age: 27)

manngold.name
manngold.age
manngold.nickName // nil
```

이때 init을 여러 개를 생성하게 되면 중복코드가 발생하므로 `convenience` 키워드와 내부에 `self.init`을 통해서 옵셔널에 대한 처리를 중복코드를 최소화해서 사용할 수 있다

## 암시적 추출을 통한 초기화

암시적 추출 `!`를 붙여서 인스턴스에 꼭 필요하지만 값을 나중에 할당할 것이라는 것을 명시적을 표현할 수 있다

```
class Teacher {
    var name : String

    init(name: String){
        self.name = name
    }
}

var kim = Teacher(name : "kim")

class Student {
    var name : String
    var age : Int
    var nickName : String?
    var teacher : Teacher!

    convenience init(name:String, age: Int, nickName: String){
        self.init(name: name, age: age)
        self.nickName = nickName
    }

    init(name: String, age: Int) {
        self.name = name
        self.age = age
    }

    func study() {
        print(" \(name) study with \(teacher.name)")
    }
}

var manngold : Student = Student(name : "manngold", age: 27)

manngold.name
manngold.teacher = kim
manngold.study()
```

할당 전에는 메소드가 실행되지 않지만 할당 후 메소드를 사용할 수 있다

## 실패가능한 이니셜라이저

-   이니셜라이저 매개변수로 잘못된 값이 전달된 경우

-   인스턴스 생성에 실패하면 `nil`을 반환한다

-   실패가능성이 있기 때문에 반환 타입은 Optional이다

```
class Student {
    var name : String
    var age : Int

    init?(name: String, age: Int){
        if (0...120).contains(age) == false{
            return nil
        }
        if name.count == 0{
            return nil
        }
        self.name = name
        self.age = age
    }
}


// var manngold : Student = Student(name: "Manngold", age: 27)
var manngold : Student? = Student(name: "Manngold", age: 27)

```

주석 표시는 실패 가능성이 있기 때문에 `Optional`로 명시 했어야 했지만 하지 않았기 때문에 오류가 발생한다

## 디이니셜라이저

인스턴스가 메모리에서 해제되는 시점에서 호출된다

따라서 인스턴스가 메모리에서 해제될때, 해야할 일을 정의할 수 있다

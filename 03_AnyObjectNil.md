# Any Object Nil

1. Any

Swift의 모든 데이터 타입을 지칭하는 키워드

```
var someAny : Any = 27

someAny = "Hello"

//var someString : String = someAny
```

모든 데이터 타입을 수용할 수 있지만 다른 특정 데이터 타입에 할당할 때 에러가 발생한다



2. AnyObject

모든 클래스 타입을 지칭하는 프로토콜

```
class SomeClass{}

class OtherClass{}

var someObject : AnyObject = SomeClass()

someObject = OtherClass()

//someObject = 123 
```

AnyObject에는 모든 객체가 들어갈 수 있지만 다른 데이터 타입은 에러가 발생한다

3. Nil

없음을 의미하는 키워드

```
var someAny : Any = 123

//someAny = nil
```

null, None, NULL 과 같은 맥락의 값인데 Any계열의 데이터 타입에 들어갈 수 없다



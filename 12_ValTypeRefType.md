# Value Type Reference Type

class, struct, Enum의 특징을 확인해보면

class

-   전통적인 OOP관점에서의 클래스
-   단일 상속
-   (인스턴스/타입) 메소드
-   (인스턴스/타입) 프로퍼티
-   `참조 타입`
-   Apple framework의 대부분이 class 기반이다

struct

-   상속불가
-   (인스턴스/타입) 메소드
-   (인스턴스/타입) 프로퍼티
-   `값 타입`
-   Swift 대부분의 큰 뼈대는 struct로 구성

enum

-   유사한 종류의 여러 값을 유의미한 이름으로 한 곳에 모아 정리 ex) 요일, 상태값, 월 등등..
-   `열거형 자체가 하나의 데이터 타입`이고 case 하나하나가 유의미한 값을 의미한다

최종적으로 class struct enum 은 공통적으로 나중에 나올 개념인 `Extention`을 사용할 수 있고

class는 참조 타입과 상속이 가능하고

struct와 enum은 값 타입이며 상속이 불가능하다

구조체를 사용하는 경우

-   참조가 아닌 복사를 할 때,
-   상속을 받을 필요가 없을 때,

value vs reference

value는 값을 복사해서 전달

reference는 메모리의 위치를 전달

```
struct Sample {
    var value : Int = 1
}

class Sample2 {
    var value : Int = 1
}

var oneStruct : Sample = Sample()
var otherStruct : Sample = oneStruct

oneStruct.value = 2
print(oneStruct.value)
print(otherStruct.value)
```

이처럼 구조체는 값을 복사하기 때문에 서로 다른 구조체의 값에 영향을 주지 않게 된다

이에 반해 클래스는

```
class Sample2 {
    var value : Int = 1
}

let oneClass : Sample2 = Sample2()
let otherClass : Sample2 = oneClass

oneClass.value = 2
print(otherClass.value)
```

위 코드처럼 `otherClass`는 `oneClass`의 `메모리 주소를 참조`하고 있으므로 서로의 값에 영향을 주게 된다

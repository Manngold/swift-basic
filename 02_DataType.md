# Data Type

Swift의 데이터 타입은

-   Bool
-   Int
-   UInt
-   Float
-   Double
-   Character
-   String

1. Bool

참, 거짓을 나타낼 수 있는 자료형

```
var someBool : Bool = true

//someBool = 0
someBool = false
```

다른 언어에서는 0 혹은 1 이 true와 false로 표현되지만 swift에서는 불가능하다

2. Int

정수형 데이터 타입

```
var someInt : Int = 20

//someInt = 20.1
```

실수형 데이터는 들어갈 수 없다

3. Float

32비트 실수형 데이터 타입

```
var someFloat : Float = 3.14

someFloat = 3
```

Int형과 다르게 정수형 데이터를 할당할 수 있다

4. Double

64비트 실수형 데이터 타입

```
var someFloat : Float = 3.14

var someDouble : Double = 3.12

//someDouble = someFloat

```

Float형 데이터 타입을 Double에 할당하려 할 때 에러 발생

Swift는 데이터 타입에 엄격한 것을 확인할 수 있다

5. Character

한 글자만 표현할 수 있는 데이터 타입

```
var someCharacter : Character = "A"

//someCharacter = "123"
```

한 글자 이상을 할당하려 할 때 에러 발생

6. String

여러 글자를 표현할 수 있는 데이터 타입

```
var someCharacter : Character = "A"
var someString : String = "manngold"

//someString = someCharacter
```

Character 데이터 타입을 할당하려 할 때 오류 발생
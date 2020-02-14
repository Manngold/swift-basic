# Collection Type

1. Array

순서가 있는 리스트 컬랙션

```
var integers: Array<Int> = Array<Int>()

integers.append(100)
integers.append(120)
//integers.append(1.23)

integers.contains(100)
integers.remove(at: 0)
integers.removeAll()

integers.count
```

Int형 Array를 생성하고 여러 메소드를 사용할 수 있다

Int형에 맞지 않는 데이터 타입이 들어가면 에러를 출력한다

비어있는 배열 참조는 에러 발생

```
var doubles : Array<Double> = [Double]()

var strings : [String] = [String]()

var characters : [Character] = []

let immutableArray = [1,2,3]

//immutableArray.removeAll()
```

배열 생성의 고전적인 방식에서 리터럴 방식도 제공해서 간편하게 배열의 생성이 가능하다

또한 immutable Array를 생성하면 추가 삭제 변경이 불가능하다

2. Dictionary

키와 값의 쌍으로 이뤄어진 컬랙션

```
var anyDictionary : Dictionary<String, Any> = [String:Any]()

anyDictionary["someKey"] = "some value"
anyDictionary["otherKey"] = "other value"

anyDictionary["someKey"] = "change value"

anyDictionary.removeValue(forKey: "someKey")
anyDictionary
anyDictionary["otherKey"] = nil
anyDictionary
```

처음 선언시 key와 value의 데이터 타입을 설정해주고 key에 따른 value 값을 설정할 수 있다

삭제시 removeValue 메소드나 nil을 할당해주면 해당 key와 value가 삭제된다

```
var emptyDictionary : [String: Any] = [:]
```

Array와 마찬가지로 Dictionary도 리터럴이 존재한다

```
var emptyDictionary : [String: Int] = [:]
emptyDictionary["first"] = 1

//let someNum : Int = emptyDictionary["first"]
```

위 코드는 오류가 발생한다 왜냐하면 emptyDictionary의 value값이 존재하지 않을 수도 있는 불확실성 때문에 Swift의 엄격한 문법 체계에서 막은 것

3. Set

순서가 없고 멤버들이 유일한 컬랙션

```
var integerSet : Set<Int> = Set<Int>()

integerSet.insert(99)
integerSet.insert(99)

integerSet.removeFirst()

integerSet
```

리터럴이 존재하지 않는다 

그리고 원소를 추가할 때 `insert()` 메소드를 사용해서 추가를 하고 만약에 Set 내에 해당 데이터가 존재하면 false를 반환하며 추가가 되지 않는다

```
 let setA: Set<Int> = [1,2,3,4]
 let setB: Set<Int> = [3,4,5,6]
 
 let union: Set<Int> = setA.union(setB)
 let sortedUnion : [Int] = union.sorted()

 let intersection : Set<Int> = setA.intersection(setB)
 let subtracting : Set<Int> = setA.subtracting(setB)
```

set을 활용한 합집합 교집합 차집합을 활용할 수 있고

Set 자료구조의 특성상 정렬이 되어있지 않기 때문에 정렬을 하고자 하면 새로운 배열을 생성해서 `sorted()` 메소드를 사용해서 넣어준다

# Property Observer

```
struct Money{
    var currentRate : Double = 2.3 {
        willSet (newRate) {
            print("Current rate will change \(currentRate) -> \(newRate)")
        } didSet (oldRate){
            print("Current rate changed \(oldRate) to \(currentRate)")
        }
    }

    var dollar : Double = 1100 {
        willSet {
            print("Dollar will change \(dollar) to \(newValue)")
        } didSet {
            print("Dollar changed \(oldValue) to \(dollar)")
        }
    }

    var currentDollar : Double {
        get{
            return currentRate * dollar
        } set {
          dollar = newValue / currentRate
        }
    }
}
```

`willSet`과 `didSet`으로 프로퍼티가 바뀌기 직전, 바뀐 뒤 동작을 수행할 수 있다

프로퍼티 감시자는 연산 프로퍼티와 함께 사용할 수 없다

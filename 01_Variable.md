# Swift - Basic

print - 단순 문자열 출력

dump - 인스턴스의 자세한 설명 출력

interpolation - `/(변수)`로 가능 (JS의 `${}`)과 같은 맥락

## Variable

함수형 패러다임으로 불변객체를 중요시해서 상수 표현이 많이 등장한다

-   var and let

`변수` var : 데이터타입 = 데이터

`상수` let : 데이터타입 = 데이터

만약에 데이터 타입이 명확하다면 데이터 타입을 생략가능

만약에 값이 할당되지 않은 상수를 선언하면 첫 할당은 가능하고 이후에는 할당이 불가능

```
let sum : Int

let input1 : Int = 25

let input2 : Int = 35

sum = input1 + input2 //60

이후 sum의 값을 수정 불가능
```

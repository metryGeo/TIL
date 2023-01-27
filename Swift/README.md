# SWIFT

# 스위프트의 언어적 특성
---

* Safe(안정성), Fast(신속성), Expressive(더 나은 표현성)
* 객체지향은 명령형과 객체지향 프로그래밍 패러다임을 기반으로 한 함수형 프로그래밍 패러다임과 프로토콜 지향 프로그래밍 패러다임을 지향합니다.

## Int, UInt
- Int는 + - 포함한 정수, UInt는 0을 포함한 양의 정수
- Int, UInt 는 엄연히 다른 타입이라 두 타입 모두 사용하면 많은 자원 소모가 우려된다.
- 시스템 아키텍쳐에 따라 타입이 달라진다. ex) 32비트 아키텍처는 Int32, UInt32
- Int의 양의 정수 범위를 초과한 범위를 UInt로 사용하고 나머지는 범위는 Int를 사용하는 것이 권장된다.


## Character
- 단 하나의 문자를 의미한다. JAVA에서 chr와 비슷
```var one_letter: Character = "A"```

## String
- 이니셜라이저를 사용해서 빈 문자열 생성 가능
```var name: String = String() // 빈 문자열```
- append를 사용해서 문자열을 이어붙일 수 있다
```
var name: String = "Metry"
name.append(" is man") // 이어 붙이기
```

- hasPrefix()로 접두어를 확인할 수 있다.
```var prefix: Bool = false
var name: String = "Metry"
prefix = name.hasPrefix("Me")
print(prefix)   //true
```
- hasSuffix()로 접미어를 확인할 수 있다.
```var suffix: Bool = false
var name: String = "Metry"
suffix = name.hasSuffix("try")
print(suffix)   //true
```
- uppercased()로 대문자 변환, lowercased()로 소문자 변환을 할 수 있다.
```var name: String = "Metry"
name = name.uppercased()
print(name)   //METRY
name = name.lowercased()
print(name) //metry
```
- count()로 문자열의 길이를 알 수 있다.
```var name: String = "Metry"
print(name.count)	//5
```

## 배열
```
var arr: Array<String> = ["abc", "def", "ghi"]	// 배열 선언 법
var arr: [String] = ["abc", "def", "ghi"]	// 이 것도 가능

```
```
print(arr.firstIndex(of: "abc"))	// 0
```
- firstIndex(of:_)로 해당 요소의 인덱스를 알 수 있다.

```
print(arr.first) // abc
print(arr.last) // ghi
```
- first로 첫 번째 인덱스 값을 가져올 수 있다.
- last로 마지막 인덱스 값을 가져올 수 있다.

```
let indexRemove: String = arr.remove(at: 0)	// 인덱스 0 값 삭제 후 indexRemove에 값 넣기
print(indexRemove)	// 삭제된 abc값  출력
```
- remove(at:_)로 index 값을 넣어 해당 값을 삭제할 수 있다. 

## 함수
```
func 함수 이름(매개변수) -> 반환 타입 {
  실행구문
  return 반환값


func 함수이름(전달인자 레이블 매개변수 이름: 타입, 전달인자 레이블 매개변수 이름: 타입) -> 변환 타입 {
	실행 구문
    return 반환 값
}
- 전달인자 레이블 추가

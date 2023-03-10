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
func 함수 이름(매개변수) -> 반환 타입 {
  실행구문
  return 반환값



func 함수이름(전달인자 레이블 매개변수 이름: 타입, 전달인자 레이블 매개변수 이름: 타입) -> 변환 타입 {
	실행 구문
    return 반환 값
}
- 전달인자 레이블 추가

## 구조체
- 구조체는 프로그래머가 데이터를 용도에 맞게 묶어 표현하고자 할 때 용이
- 프로퍼티와 메서드를 사용하여 구조화된 데이터와 기능을 가질 수 있다 하나의 새로운 사용자정의 데이터 타입을 만들어 주는 것 </br>


```
struct structor {
    var a: String
    var b: Int
}
```
- struct 구조체이름 {
	// 프로퍼티 및 메서드
} 
이런 식으로 만들 수 있다
``` 
init() {
    // perform some initialization here
}
```
- 구조체 안에서 생성자를 만들 수 있다.
``` 
init() {
    // perform some initialization here
    a = "Metry"
    b = 1234
}
```
- 당연히 변수값을 설정할 수 있다

```
var st: Structor = Structor()	// 인스턴스 st 생성
st.a = "aaa"	// 인스턴스의 변수 a의 값을 "aaa"로 변경
```
- 이것 처럼 인스턴스를 선언해 생성하고 인스턴스로 값에 접근할 수 있다.

## 클래스

```
class ClassName
{
	var name: String = "Metry"
	var grade: Int = 100
    
	init(name: String, grade: Int)
	{
		self.name = name
		self.grade = grade
	}
}
```
- 클래스는 이런식으로 클래스와 생성자를 만들 수 있다.

# Xcode에서 swift를 하면서
---
## IBOutlet
- 코드 상에서 StoryBoard 에 만든 View 객체를 사용하기 위해 연결해주는 역할
```
@IBOutlet weak var 변수이름: UIImageView!
```
- canvas에 배치해놓은 요소를 ctrl을 눌러 코드 있는 곳으로 드래그하면 이러한 형태의 코드가 나타난다.
- 위의 코드는 ImageView를 추가한 것이며 변수이름은 바로 설정 가능하다.
### 변수 활용
- 이렇게 갖고온 변수로 여러 기능을 할 수 있다.
- who(어떤 것으로).what(무엇을) = value
- who 자리에 변수가 들어가고 what할 기능 value에 기능에 필요한 값을 넣는다.
```
변수.image = UIImage(imageLiteralResourceName: "새_이미지")
```
- 변수 이미지를 "새_이미지"라는 이미지로 바꾼다.

## IBAction
- 스토리보드 상에 선언한 View 객체가 특정 이벤트가 발생했을 경우 호출되는 함수
-  이것 역시 드래그하여 설정한다.
<center><img src="https://velog.velcdn.com/images/adad0207/post/5a5c4611-da60-424c-8fc7-6b9594606b69/image.png" width="300" height="200"/></center>
- 드래그 하게 되면 이런 화면이 나오는데 Connection에 Action을 설정하고 Name에 이름을 설정할 수있다.
- Type은 Action을 하는 요소의 타입이고 Event는 일어나는 이벤트이다.

## StackView
- StackView란 AutoLayout을 적용해 내부에 배치된 View들을 열 또는 행에 배치해주는 인터페이스
- 쉽게말해 view들을 묶어주는 새로운 레이아웃
### Distribution
- StackView로 정렬된 view들의 위치를 정하는 것
- fill equally : view들을 같은 크기로 변경한다

## DispatchQueue
- 앱의 기본 스레드 또는 백그라운드 스레드에서 연속적으로 또는 동시에 작업 실행을 관리하는 개체, 순차진행과 동시병렬진행이 있다.
- 순차진행 seral은 main으로사용할 수 있다.
```
DispatchQueue.main(:)
```
- 동시 병렬진행 concurrent는 global로 사용할 수 있다.
```
DispatchQueue.global(:)
```
### 기능
#### async
- 작업 항목을 즉시 실행하도록 예약하고 즉시 반환
```
DispatchQueue.main.async()
```
#### sync
- 현재 대기열에서 실행할 작업 항목을 제출하고 해당 블록의 실행이 완료된 후 반환
```
DispatchQueue.main.sync()
```
#### asyncafter
- 지정된 시간에 실행할 작업 항목을 예약하고 즉시 반환
```
DispatchQueue.main.asyncafter(deadline: , execute: )
```
- deadline : 실행할 작업 예약시간

## AVAudioPlayer
- 소리를 재생시킬 수 있는 개체

### init
- contentsOf url : 재생시킬 로컬파일 url
- fileTypeHint uiString : 파일형식이 String이란 것, 파일형식을 정함

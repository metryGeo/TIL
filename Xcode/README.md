CodeWithChirs의 Xcode 14 Tutorial 강의를 들으며 공부한 글
[CodeWithChris Xcode 강의](https://youtu.be/EJQW864XpmA)

![](https://velog.velcdn.com/images/adad0207/post/4cbf7220-95c6-46cc-be62-2cd4bf62768a/image.png)
- 새 프로젝트를 만드는 과정에서 Interface 와 Language를 결정한다. 
- Interface는 사용자가 사용할 User Interface를 고르는 것인데 storyBoard도 있지만 오래됐고 최근에 많이 사용중인 SwiftUI를 사용한다.
- Language는 Interface를 storyBoard로 사용했다면 Object-C를 사용하지만 그렇지 않으므로 Swift를 사용한다.

![](https://velog.velcdn.com/images/adad0207/post/3d69aeda-44b7-4798-bf5b-73149af36ed2/image.png)

- Xcode는 왼쪽부터<br/>
프로젝트의 파일들을 볼 수 있는 **Navigator area**<br/>코드를 입력하는 **Editor area**
코드에 따른 내용을 출력해 preview 해주는 **Canvas**
Editor area의 디테일한 부분을 보는 **Inspector area**
그리고 위쪽에 프로젝트에 관한 현재 상태를 보여주는 **ToolBar**
맨 밑에 마지막으로 에러등을 볼 수있는 **Debug area**가 있다.

## Navigator Area
-----
### 프로젝트 관련

![](https://velog.velcdn.com/images/adad0207/post/c7e78aa7-0840-4b52-b79e-682f94d63d12/image.png)
- 프로젝트 경로를 보면 이렇게 나오는데 첫 번째 폴더에 프로젝트에 필요한 파일들이 들어있고 두번째 폴더는 프로젝트를 Xcode로 프로젝트를 여는 파일이다.

![](https://velog.velcdn.com/images/adad0207/post/b02cd9eb-66f5-4b5f-ba75-be70aab7f650/image.png)
- 이런식으로 프로젝트 제일 상위파일을 Xcode에서 누르게 되면 Configuration을 설정할 수 있다.


### Swift File
![](https://velog.velcdn.com/images/adad0207/post/428854f7-5bb2-4281-8b9d-c106885df72c/image.png)
- swift 파일 이와같이 코드를 갖는 파일인데 지금 이 코드는 ContentVeiw와 관련된 코드인 것 같습니다.![](https://velog.velcdn.com/images/adad0207/post/2b138ca1-7a5b-4021-aa71-ac72e6266115/image.png)
- 우클릭 후 new file을 눌러 다음과같이 swift 파일을 추가 할 수 있다.


### Asset
![](https://velog.velcdn.com/images/adad0207/post/4fd569e5-ba92-4398-9b57-e66efbc0673c/image.png)
- Asset은 Assets버튼을 눌러 확인할 수 있다. 
- 색이나 이미지를 참조할 수 있도록 하는 기능을한다. 예를 들어 ButtonColor와 같이 한가지 색을 여러 버튼에 일일이 추가하는 것이 아닌 하나의 색을 참조후 사용하여 번거로움을 줄이는 것이다.
- 색을 나타내는 ColorSet은 일반 색깔과 다크모드 색깔로 나눠할 수 있다.

![](https://velog.velcdn.com/images/adad0207/post/93d75254-b520-4ba9-bde1-5242c8c7b674/image.png)
- Image도 마찬가지로 참조하여 사용하는 것이지만, 1X 2X 3X 와 같이 크기별로 나눠 이미지를 설정할 수 있다.

### Preview Content
![](https://velog.velcdn.com/images/adad0207/post/14a22d2a-eb8a-44e4-9033-d406264ca348/image.png)
- asset들을 참조할 경우 어떻게 보여지는 지 Preview하는 것이다.

## Editor Area
```
struct ContentView: View {
    var body: some View {
        VStack {
            Image(systemName: "globe")
                .imageScale(.large)
                .foregroundColor(.accentColor)
            Text("Hello, world!")
        }
        .padding()
    }
}
```
- 먼저 editor 화면을 보면 이러한 코드를 볼 수 있다.
- VStack을 설명하자면 Vertical Stack 즉 수직으로 쌓이는 형태를 의미한다.
- VStack 안에는 Image(systemName: "globe")가 있는데 내장되어 있는 globe이미지를 생성한 것이다.
- 그 다음으로 온 Text("Hello, world!")는 Hello, world라는 문자를 나타낸 것이다.

![](https://velog.velcdn.com/images/adad0207/post/63b08ce8-0df1-453b-a291-5a8d6bb4a8ca/image.png)
<center>파란 모양이 globe 이미지, 그 밑의 문자가 Text이다.</center>

- 이미지 안에 있는 코드 
```
.imageScale(.large)
                .foregroundColor(.accentColor)
```
는 이미지를 수정하는 코드이다.

imageSacle()은 이미지의 크기를 조정하는 속성이고
foregroundColor()는 이미지의 색깔을 결정하는 속성이다. 여기서 .accentColor는 Assets에서 본 AccentColor이다.

마지막으로 VStack의 대괄호를 벗어난 ```.padding()```은 좌우 위아래 간격을 조정하는 속성이다.

### 이미지 넣어보기
![](https://velog.velcdn.com/images/adad0207/post/569c87e5-5dd0-445f-a758-66d41b04aa84/image.png)
- Assets에서 이미지 래퍼런스를 추가한 후![](https://velog.velcdn.com/images/adad0207/post/da6a7977-962a-4df7-a856-6c9fdfdd79c5/image.png)
- Image() 안에 래퍼런스 이름을 넣어주면 이미지가 삽입되는 모습을 canvas에서 볼 수 있다.

<center><img src="https://velog.velcdn.com/images/adad0207/post/04c7ce01-91a2-4421-90d1-6b188d60ce2a/image.png" width="300" height="300"/></center>
- 밑에 있는 variants 탭을 누르면 다크모드도 볼 수 있다.












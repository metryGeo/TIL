# AppDelegate
---
- AppDelegate는 iOS 13이전까지 앱의 메인 창구였고 많은 로직과 앱의 상태가 다뤄지는 곳이였다.
- 앱이 시작 되는 곳인 AppDelegate는 AppDelegate와Scene Delegate로 나뉘었다.
- AppDelegate는 3개의 method가 있다.
```
1. func application(_:didFinishLaunchingWithOptions:) -> Bool
2. func application(_:configurationForConnecting:options:) -> UISceneConfiguration
3. func application(_:didDiscardSceneSessions:)
```
- 첫 번째인 **func application(_:didFinishLaunchingWithOptions:) -> Bool** 앱이 시작되고 set-up이 끝날 때 호출된다.
- 두 번째인 **func application(_:configurationForConnecting:options:) -> UISceneConfiguration**는새 장면이나 창이 필요할 때마다 호출된다.
- 세 번째인 **func application(_:didDiscardSceneSessions:)**는 사용자가 멀티태스킹 창에서 scene을 swiping 해서 삭제하거나 프로그래밍 방식으로 삭제하는 경우 항상 호출된다. 이 메서드는 (_:didDidFinishLaunching withOptions:) 메서드가 실행 중이 아닌 경우 사용자가 해당 scene을 삭제할 때마다 실행된다

# SceneDelegate
---
- SceneDelegate는 UI 및 데이터 측면에서 화면에 표시되는 작업을 담당한다.
```
1. scene(_:willConnectTo:options:)
2. sceneDidDisconnect(_:)
3. sceneDidBecomeActive(_:)
4. sceneWillResignActive(_:)
5. sceneWillEnterForeground(_:)
6. sceneDidEnterBackground(_:)
```
- **scene(_:willConnectTo:options:)**는 라이프사이클에서 호출되는 첫 번째 메서드이다. 이 메서드는 새 UI 창을 만들고 root view controller를 설정하며 새 창을 전시될 key창으로 만든다.
- **sceneWillEnterForeground(_:)**는 앱이 시작될 때와 같이 화면이 처음 나오거나 background에서 foreground로 전환될 때 호출된다.
- **sceneDidBecomeActive(_:)**는WillEnterForground 메소드 바로 뒤에 호출되며 여기서 화면이 설정되고 표시되며 사용할 준비가 된다.
- **sceneWillResignActive(_:) and sceneDidEnterBackground(_:)**는 background로 갔을 때 실행된다.
- **sceneDidDisconnect(_:)**는 scene이 background로 전송될 때 마다 세션 연결을 끊는다. 다른 앱으로 이동할 경우에는 끊지 않는다.

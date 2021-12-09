---
title: "위젯의 생명주기란.."
categories:
- Flutter
  tags:
- lifecycle
---
플러터의 위젯 트리에서 위젯이 등록되고 화면이 생성되고 사라질 때까지의 위젯 내부의 단계적인 상태 변화를 가지는 것을 말합니다.
StatelessWidget도 Constructor -> build() -> dispose() 과정의 상태를 가지고 있지만
화면에 한 번 갱신되면 사라질 때까지 변경될 수 없는 위젯이라고 생각하면 됩니다.
StatefulWidget은 생명주기는 상태가 변경될 수  있기 때문에 StatelessWidget보다 많은 단계를 가지고 있습니다.

|createState()| |StatefulWidget 생성하면 즉시 호출|
|mounted ==true| |createState() 실행되면 모든 위젯이 가지고 있는 속성 this.mounted가 true로 변경된다.|
|initState()| |State 클래스 생성 후 제일 먼저 호출 되는 함수. 생성 후 한번만 한다.|
|didChangeDependencies()| |initState() 다음에 바로 호출된다. 또한 위젯이 의존하는 데이터의 객체가 호출될 때마다 호출된다|
|build()| |위젯을 렌더링 하는 함수. 위젯을 반환. 이 메서드는 자주 호출된다.|
|didUpdateWidget()| |위젯이 변경되어 재 구성해야 하는 경우 호출|
|setState()| |데이터의 변경을 알리는 함수|
|deactivate()| |State가 제거될 때 호출된다.|
|dispose()| |State가 완전히 제거되었을 때 호출|
|mounted == false| |모든 프로세서가 종료된 후 this.mount 속성이 false로 된다.|

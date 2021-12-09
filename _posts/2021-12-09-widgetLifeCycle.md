---
title: "위젯의 생명주기란.."
categories:
  - flutter
tags:
  - lifecycle
  
---

플러터의 위젯 트리에서 위젯이 등록되고 화면이 생성되고 사라질 때까지의 위젯 내부의 단계적인 상태 변화를 가지는 것을 말합니다.
StatelessWidget도 Constructor -> build() -> dispose() 과정의 상태를 가지고 있지만
화면에 한 번 갱신되면 사라질 때까지 변경될 수 없는 위젯이라고 생각하면 됩니다.
StatefulWidget은 생명주기는 상태가 변경될 수  있기 때문에 StatelessWidget보다 많은 단계를 가지고 있습니다.

|제목||내용|
|-----||-----|
|테스트1||테스트|

---
layout: post
title:  "UE5 Action game project"
date:   2024-01-11 06:00:00
categories: UnrealEngine
tags: dev gamedev unrealengine
author: Gyu
mathjax: true
typora-root-url: ../
---

* content
{:toc}

---
## Project Settings

블루프린트와 레이 트레이싱을 킨 상태이다.

![1](/assets/images/2024-01-11-actiongame/1.png)

![2](/assets/images/2024-01-11-actiongame/2.png)

![3](/assets/images/2024-01-11-actiongame/3.png)

시스템 사양이 충분히 하다면 위의 세팅은 그냥 생략해도된다.

![4](/assets/images/2024-01-11-actiongame/4.png)

## Editor Preferences

![5](/assets/images/2024-01-11-actiongame/5.png)

![6](/assets/images/2024-01-11-actiongame/6.png)

![7](/assets/images/2024-01-11-actiongame/7.png)

## Level Settings

레벨 세팅은 아주 간단하다. 라인 마스크로 그리드 라인을 마스킹하고 if, cos 노드로 일정간격마다 라인에 LED가 밝혀지도록 하였다.

![level](/assets/images/2024-01-11-actiongame/level.gif)

## Character Settings

### Enhanced Input

현재 언리얼 엔진에는 input세팅이 여러가지있다. UE5.1부터 새로운 방식이 적용되있다. 

기존의 방식은 곧 제거된다.

![bind_old](/assets/images/2024-01-11-actiongame/bind_old.png)

새롭게 강화된 바인딩을 사용해야한다.

![bind_new](/assets/images/2024-01-11-actiongame/bind_new.png)

Input Action, Input Mapping Context를 사용한다.

![input](/assets/images/2024-01-11-actiongame/image-20240629070852885.png)

정해진 로직을 따라서 만들었던 Input Mapping Context를 참조한다.

![enhancedbind](/assets/images/2024-01-11-actiongame/enhancedbind.png)

### Character  Rotation Vector

캐릭터의 무빙이 카메라의 벡터가 아닌 캐릭터 자체의 벡터를 따라가도록 수정하였다.

![rotate](/assets/images/2024-01-11-actiongame/image-20240629071225419.png)

![char_rot](/assets/images/2024-01-11-actiongame/char_rot.gif)

---

## Enemy Setting

AI를 한군데로 집합하게 만들었다. 여기서 AI가 랜덤으로 이동하도록 만들자.

![ai1](/assets/images/2024-01-11-actiongame/ai1.gif)

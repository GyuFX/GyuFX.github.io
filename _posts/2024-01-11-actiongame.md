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

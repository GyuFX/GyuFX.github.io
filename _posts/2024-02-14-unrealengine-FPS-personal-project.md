---
layout: post
title:  "UE5 C++ FPS personal project"
date:   2024-02-14 22:00:00
categories: UnrealEngine
tags: dev C++
author: Gyu
mathjax: true
typora-root-url: ../
---

* content
{:toc}

---
## 게임이란?

- 정해진 규칙에 따라 목표를 달성하며 재미를 추구
- 우리는 개발자의 시선으로 '비디오(PC, 모바일, 콘솔 등) 게임'에 집중

비디오 게임은 컴퓨터에 의해 실현된다. 즉, 현실에서 경험할 수 없는 것을 체험할 수 있다.
비디오 게임을 즐기는 유저들은 시간과 공간에 제약을 받지 않기 때문에 게임은 '상업성'을 가진다.

## 게임 엔진은 왜 필요할까?

초창기 비디오 게임은 매우 단순한 구조였다. Pong, Pac Man은 단순한 게임성을 가지고 있다. 그러나 이를 개발하는 시간은 엄청나게 길었다. 지금은 유저들이 보유한 하드웨어의 성능이 많이 좋아졌기 때문에 컨텐츠의 질과 완성도가 높은 게임을 더욱더 원하게 되었다.

게이머들의 수준이 많이 성장하였다.

또 대한민국뿐만 아니라 전세계적으로 다양한 'BM'이 연구되고 있다. 이는 더 이상 패키지 게임으로 단 한 번만 판매하는 것이 아닌 지속적으로 수익을 창출할 수 있다는 것이다. ('BM'전문가가 아닌 나도 당장 수익모델 몇개를 생각할 수 있다.)

## Unreal Engine

Epic Games.社의 엔진 1990년대부터 지금까지 꾸준히 개발되고 있다.

## Unreal Engine과 Unity의 차이점

언리얼 엔진은 오픈소스로 코드를 전부 공개하고있다. 내가 한창 공부할 대학시절만해도 유니티가 모바일 시장을 80%이상 점유하고 있었지만, 지금은 언리얼 엔진이 많이 따라왔고, 유니티가 언리얼 엔진을 추격해야하는 입장에 서있다.

언리얼 엔진은 소스 코드를 수정할 수 있기 때문에 유연하게 대처가 가능하다.

---

## 프로젝트 설계

### 규칙

1. 스피드 런
2. 정해진 경로를 따라 이동하며 타겟을 제거함
3. 점수를 랭킹으로 기록

### 주요 기능

- 기본 FPS 조작: Fire, Reload, Aim, Swap, FireMode, Run
- 레이저 포인터
- 과녁 시스템
- 랭킹 시스템
- 환경설정

#### 기본 FPS 조작

- Fire: 잔탄수가 남아있다면, 탄환을 발사
- Reload: 최대 잔탄수보다 적을 경우, 최대 잔탄수로 갱신
- Aim: 조준선이 화면의 중앙에 오도록 정렬. 먼 거리의 목표물 제압에 유리
- Swap: 무기 교체
- FireMode: 현재 무기의 발사방식 변경(자동, 반자동, 수동 등)
- Run: 달리기. 다른 동작 불가능

#### 레이저 포인터

- 레이저가 총구 방향으로 정해진 거리만큼 그려짐
- 가까운 거리의 목표물 제압에 유리

#### 과녁 시스템

- 플레이어가 해치워야할 타겟

#### 랭킹 시스템

- 게임 점수를 로컬 데이터로 남긴다. 최대 10개의 상위 기록 유지

#### 환경설정

- 해상도, 윈도우모드, 마우스감도, 밝기 등을 조절

### 몰입도를 올리기 위한 추가 기능

- 캐릭터 애니메이션
- 총기 반동
- 소리 효과

## 도전과제

BP로 빠르게 구성하고 C++ 변환하는 작업을 한다. 이 과정에서 BP와 C++의 공통점과 차이점을 공부하자. 배포와 프로파일링까지 공부한다.

## 사용할 기능

- [Gameplay Framework](https://dev.epicgames.com/documentation/ko-kr/unreal-engine/gameplay-framework-in-unreal-engine?application_version=5.3)
- [Animation Blueprint](https://docs.unrealengine.com/4.27/ko/InteractiveExperiences/HowTo/CharacterMovement/Blueprints/AnimBlueprint_Walk/) 
- [Animation State Machine](https://dev.epicgames.com/documentation/ko-kr/unreal-engine/state-machines-in-unreal-engine?application_version=5.3)
- [Animation Retargeting](https://dev.epicgames.com/documentation/ko-kr/unreal-engine/animation-retargeting-in-unreal-engine?application_version=5.3)
- [Forward Kinematics & Inverse Kinematics](https://dev.epicgames.com/documentation/ko-kr/unreal-engine/using-kinematic-bodies-with-simulated-parents-in-unreal-engine?application_version=5.3)

---

## 개발 환경 구축

'git'으로 연동을 한 후 버전 관리를 한다. 이번에 깃허브 페이지를 만들면서 깃에 대해 완벽하게 이해했다.

![ue-git](/assets/images/2024-02-14-unrealengine-FPS-personal-project/ue-git.png)

## GamePlay Framework

나의 게임에 맞는 게임 프레임워크를 구성한다.

BP Class Chracter, Controller ,GameMode로 컨트롤을 한다. 그리고 Input Action 프레임 워크 사용하여 캐릭터 이동을 구현했다.

'Add Mapping Context'를 활용하여 캐릭터의 이동을 조작한다.

![char-move-turn](/assets/images/2024-02-14-unrealengine-FPS-personal-project/char-move-turn.gif)

<img src="/assets/images/2024-02-14-unrealengine-FPS-personal-project/image-20240608155351516.png" alt="image-20240608155351516" style="zoom:67%;" />

## Overlap Trigger

Trigger Volume을 Overlap시켜 시작과 끝을 만들어 준다.

![trigger](/assets/images/2024-02-14-unrealengine-FPS-personal-project/trigger.gif)

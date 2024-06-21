---
layout: post
title:  "Niagara Simple Sprite Emitter"
date:   2024-06-20 06:00:00
categories: UnrealEngine
tags: unrealengine niagara sprite particle emitter
author: Gyu
mathjax: true
typora-root-url: ../
---

* content
{:toc}

---
## 프리뷰

<img src="/assets/images/2024-06-20-niagara-simple-sprite-emitter/preview.gif" alt="preview" style="zoom:67%;" />

## 구조

![image-20240621133810940](/assets/images/2024-06-20-niagara-simple-sprite-emitter/image-20240621133810940.png)

### System Script

Niagara는 어떻게 작동할까?
Niagara는 일련의 스크립트를 실행한다. 이를 스택이라고 한다.

파티클 시스템의 전체 수명 주기를 제어한다. 'System Spawn'은 시스템이 스폰하는 첫 번째 프레임에서 발생하는 일을 제어한다. 'System Update'는 그 이후의 모든 프레임에서 실행되는 로직이다.

여기에서 생성된 속성은 데이터가 시스템 -> 이미터 -> 파티클로 흐리기 때문에 시스템의 다른 모든 이미터와 파티클에서 액세스할 수 있다.

![image-20240621134446733](/assets/images/2024-06-20-niagara-simple-sprite-emitter/image-20240621134446733.png)

### Emitter control

오렌지색 섹션은 모든 시스템의 모든 이미터에 대해 실행된다. 각 이미터는 유사한 스폰 및 업데이트 스크립트를 가진다. 여기서 우리는 시스템의 각 개별 이미터의 수명 주기를 제어한다. 루핑하는가? 한 번만 플레이하는가? 파티클을 스폰할 수 있는가? 그렇다면 몇 개인가? 이것들은 이미터 스크립트가 답하려는 질문의 유형이다.

![emitter](/assets/images/2024-06-20-niagara-simple-sprite-emitter/emitter.png)

### Particle control

녹색 파티클 스크립트는 이미터의 모든 개별 입자에 대해 독립적으로 실행된다. 입자 수명의 첫 번째 프레임에 대한 Particle Spawn, 그 이후의 모든 프레임에 대한 Particle update. Particle Spawn과 Particle Update 모두에 ''내장된 동작(모듈이라고 함)'이 많이 있으며, 각 스크립트 헤더 옆에 있는 색상이 있는 "+" 박스를 통해 액세스하거나 모듈을 마우스 오른쪽 버튼을 클릭하여 "위에 삽입"또는 "아래에 삽입"을 선택하여 액세스할 수 있다.

![partile](/assets/images/2024-06-20-niagara-simple-sprite-emitter/partile.png)

### Renderer

마지막은 ''Render''이다. 지금 같은 경우는 Sprite Renderer이다. 머티리얼을 할당하고 속도 정렬이나 카메라 방향과 같은 옵션 중에서 선택할 수 있다. 메쉬, 리본 등 다양한 종류의 렌더러가 있다.

![render](/assets/images/2024-06-20-niagara-simple-sprite-emitter/render.png)

### Emitter sample

언리얼 엔진에서 다양한 샘플을 제공한다. 이를 이용해서 빠르게 나만의 이펙트를 만들 수 있다.

![image-20240621135749184](/assets/images/2024-06-20-niagara-simple-sprite-emitter/image-20240621135749184.png)

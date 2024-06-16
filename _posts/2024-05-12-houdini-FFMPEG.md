---
layout: post
title:  "Houdini FFMPEG"
date:   2024-05-12 22:00:00
categories: Houdini
tags: houdini FFMPEG mp4
author: Gyu
mathjax: true
typora-root-url: ../
---

* content
{:toc}

---
## 오픈 소스 FFMPEG

[FFmpeg](https://ffmpeg.org/)

FFMPEG은 이미지 시퀀스를 영상으로 바꾸거나 영상을 이미지 시퀀스로 바꾸거나 .avi를 .mov로 바꾸는 등 파일 변환을 해주는 오픈 소스이다.

홈페이지에서 각자 자신의 OS에 맞는 릴리즈 파일을 다운로드하면 된다.

![ffmpeg](/assets/images/2024-05-12-houdini-FFMPEG/ffmpeg.png)

후디니에서 경로를 설정해야하기 때문에 파일 경로는 마음대로 설정한다.

![ffmpeg2](/assets/images/2024-05-12-houdini-FFMPEG/ffmpeg2.png)

### 설치

Documents > houdini xx > houdini.env

메모장을 열고 코드를 추가한다.
bin 폴더의 경로를 PATH에 추가하면 된다.

```
# FFMPEG
PATH = "C:\Program Files\Side Effects Software\ffmpeg-7.0-essentials_build\ffmpeg-7.0-essentials_build/bin$PATH"
```



그다음 후디니를 실행한 후 Python Powershell에 다음 명령어를 입력하면 후디니가 인식하는 모든 PATH들이 나온다.

```
hou.getenv("PATH")
```

![ffmpeg3](/assets/images/2024-05-12-houdini-FFMPEG/ffmpeg3.png)

## 사용법

렌더링을 하는 이유는 실제로 씬이 무거워지면 원하는프레임이 안나오기 때문에 정확하게 보기위해서다.
렌더링을 한 후 Export > ffmpeg mp4... 를 하면 간단히 렌더링이 가능하다.

![image-20240616235655240](/assets/images/2024-05-12-houdini-FFMPEG/image-20240616235655240.png)

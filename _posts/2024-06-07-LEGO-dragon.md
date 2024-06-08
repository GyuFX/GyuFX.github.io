---
layout: post
title:  "LEGO Dragon"
date:   2024-06-07 22:00:00
categories: Houdini
tags: vdb measure
author: Gyu
mathjax: true
typora-root-url: ../
---

* content
{:toc}

---
## 에셋 준비

<img src="/assets/images/2024-06-07-LEGO-dragon/image-20240608223815577.png" alt="image-20240608223815577" style="zoom: 50%;" />

<img src="/assets/images/2024-06-07-LEGO-dragon/image-20240608223858488.png" alt="image-20240608223858488" style="zoom:25%;" />

## 작업 과정 

### 버텍스 최적화

vdb 함수들을 사용하여 버텍스를 최적화한다.

<img src="/assets/images/2024-06-07-LEGO-dragon/image-20240608224050622.png" alt="image-20240608224050622" style="zoom:50%;" />

<img src="/assets/images/2024-06-07-LEGO-dragon/vdb-down.gif" alt="vdb-down" style="zoom: 33%;" />

### scatter

<img src="/assets/images/2024-06-07-LEGO-dragon/scatter.gif" alt="scatter" style="zoom:50%;" />

### rint

![rint](/assets/images/2024-06-07-LEGO-dragon/rint.gif)

```
@P *= 15; // 거리를 벌리고
@P = rint(@P); // 정규화
@P /= 15; // 거리를 다시 좁힌다
```



## 완성

<img src="/assets/images/2024-06-07-LEGO-dragon/image-20240608225656958.png" alt="image-20240608225656958" style="zoom: 50%;" />


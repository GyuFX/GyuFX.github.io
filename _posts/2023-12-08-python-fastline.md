---
layout: post
title:  "파이썬의 기본 요소"
date:   2023-08-08 22:00:00
categories: Python
tags: python programming
author: Gyu
mathjax: true
typora-root-url: ../
---

* content
{:toc}

---
## 객체와 자료형

```python
# 자료형을 구하는 함수 type()
type(100)
type(3.14)
type("Hello!")
```



## 객체의 이름

파이썬은 만든것 모두가 객체이다. 이 객체에 이름을 붙여서 사용할 수 있다. 이때 명명한 객체를 '변수'라고 한다.

```python
a = 1 + 2
```

*파이썬에서 대입은 '='이고, 등호는 '=='이다.

```python
# 메모리의 위치를 찾는 함수 id()
id(a)
```

변수를 사용하면 좋은 점은 수정이 편하다는 것이다.

```
# 정육면체의 부피를 구하시오
length = 3
Volume = length * length * length

# 정육면체의 변의 길이가 바뀌면 쉽게 수정할 수 있다.
```


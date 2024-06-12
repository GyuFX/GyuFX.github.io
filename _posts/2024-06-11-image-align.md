---
layout: post
title:  "Github pages image align center"
date:   2024-06-11 22:00:00
categories: Web
tags: blog github css web markdown
author: Gyu
mathjax: true
typora-root-url: ../
---

* content
{:toc}



---
## 고민

깃헙 페이지를 작성하면서 하나의 고민거리가 있었는데, 바로 이미지 정렬이다.
이게 가독성이 정말 꽝이다...

![image-20240612180330056](/assets/images/2024-06-11-image-align/image-20240612180330056.png)

## 과정

가장 쉬운 방법은 모든 이미지에 일일히 태그를 달아주는 것이다.

```markdown
<p align="center">
    <img src="...">
p>
```

이렇게 하느니 차라리 블로그 정리를 안하고 말지...

구글링을 하다 정리를 잘해주신 글을 찾음!
[CSS margin VS padding 어떤 것을 써야할까?](https://blog.naver.com/leesd88/220677131069)
[Markdown : center image](https://dev.to/bdavidxyz/markdown-center-image-39j1)



## CSS

답은 CSS였다. CSS가 웹 프론트의 꾸미기 역할을 해주니까 CSS에 모든 <image> 태그를 종속하도록 만들면 되겠지.

해당 블로그의 게시글이 포스팅되는 CSS에 접근하여 아래의 태그를 입력해주니 간단하게 해결됬다.

```css
img {
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
```

먼저 'display : block'을 사용하여 이미지의 옆에 다른 요소가 들어올 수 없도록 Block 해준다.
그다음 'margin'이 요소의 바깥쪽 여백을 설정하는 속성인데 이미지 좌우의 여백을 자동으로 맞춰준다.

이 코드를 css 코드에 추가하였다.

잘 되었다면 이 글이 푸시되었때 중앙 정렬이 되있겠지...

![deku](/assets/images/2024-06-11-image-align/deku.gif)

---
layout: post
title: 기술 문서 번역하기
description: 번역할때 어떤 과정을 거칠까?
summary: 번역할때 어떤 과정을 거칠까?
comments: true
tags: [translation]
---

저는 다양한 기술 문서들과, 유튜브 영상들을 취미로 번역해 오고 있었습니다. 하지만 최근 uBlock Origin의 문서를 번역하던중, 체계적인 틀이 존재하지 않는것 같아서 이번 기회에 정리해보게 되었습니다.

작년 hacktoberfest seoul에서 이보라님께서 발표해주신 [세션 4: 다르지만 같은 번역 리뷰, 코드 리뷰 (이보라)
](https://www.youtube.com/watch?v=K_al26a9R0c) 를 중심으로 내용을 작성했습니다.

## 번역 원칙

제가 번역을 진행하면서 생각한 점들을 정리해 보았습니다.

### 유동적 번역

번역체 어투를 피하기 위해선, 영어 그대로가 아닌, _한국어로 글을 쓴다_ 라는 생각을 갖고 새로 작성하는것처럼 생각해야 합니다

### 뜻을 살리는 번역

위의 유동적 번역과 같은 맥락의 말 인데요, 과연 이 글을 쓴 사람은 무슨 의도를 갖고 작성했을지 생각해보며 번역 해야 합니다.

### 번역 사용자 타게팅

이 글을 읽는 독자들의 수준을 고려해서, 기술적 내용은 적당히 의역하거나, 전문가 집단이라면 그대로 쓸수도 있습니다

## 번역 방법

다시 본론으로 돌아가 방법론적 이야기를 해보겠습니다.

### 번역가가 종종 저지르는 실수

- 번역체
- 오탈자
- 기본적 맞춤법
- 동의어 반복

### 팁

    번역은 단어-단어 수준으로 정확하지 않아도 됨. 오역이 없고 번역투가 없는 문장이면 충분함. 다만, 번역시 누락이 일어나면 안됨.

    문장 끝(:)이나 문장 맨 앞 (...)같이 영어에서만 사용되는 문장 부호도 최대한 번역해야함.

[출처](https://github.com/javascript-tutorial/ko.javascript.info/blob/master/CONTRIBUTING.md)

### 번역 툴

#### CAT

CAT(Computer-assisted translation) 툴을 사용하면 가장 좋지만, 작은 프로젝트의 경우 CAT의 사용이 오히려 cost를 증가 시킬수 있습니다.

작은 프로젝트의 경우 자주 사용되는 용어를 통일할수 있도록 하는 일이 필요한데요, 저의 경우 VSCode의 창 분할 기능으로 대신합니다.

#### 맞춤법 검사

[맞춤법 검사기](http://speller.cs.pusan.ac.kr/)

### 용어 번역

[마이크로 소프트 용어집](https://www.microsoft.com/en-us/language/Search)
[한글라이즈](https://hangulize.org/)
[국립국어원 한국어 어문 규범](https://kornorms.korean.go.kr//example/exampleList.do)

### 번역 레퍼런스

[React JS 번역 best practise](https://github.com/reactjs/ko.reactjs.org/wiki/Best-practices-for-translation)

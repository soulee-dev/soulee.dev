---
layout: post
title: 내가 jekyll을 선택한 이유
description: 왜 jekyll인가?
summary: 왜 jekyll인가?
comments: true
chart: true
tags: [coding]
---

# 많고 많은 블로그 플랫폼

블로그 플랫폼의 춘추 전국 시대라고 불릴정도로 수많은 플랫폼들이 나와있습니다.
제가 대표적으로 고려한 플랫폼들만 해도,

- 설치형 블로그

  - wordpress
  - jekyll
  - ghost
  - next.js 기반 (vercel 등 사용)
  - svelt 기반

- 서비스
  - velog
  - brunch
  - tistory
  - naver blog
  - medium
  - steemit

...
이렇게 너무나도 많은 플랫폼들 사이에서 jekyll을 고르게 된 이유를 알려드리겠습니다.

# 자율성

서비스로 제공되는 플랫폼들에 비해 자율적으로 디자인, 수정이 가능합니다. LaTex 문법을 위해 사용하는 MathJax나, 태그 추가를 위해 사용하는 jekyll-tags 플러그인등 다른 서비스형 플랫폼에서는 생각도 할수없는 자율성을 제공합니다.

# 커뮤니티

jekyll은 next.js만큼 멋지진 않지만, 수많은 사람들이 사용해왔고, 지금도 사용하고 있는 만큼 다른 플랫폼들과 비교해 엄청난 커뮤니티가 존재하고, 거의 모든 케이스에 대해 솔루션이 존재합니다.

# 무료

github에 호스팅하면 무료로 사용 가능합니다. 평생.

# Markdown!

기본적으로 makrdown을 사용하기때문에 머리아픈 wysiwyg을 다룰 필요가 없습니다!

# 그럼에도 불구하고?

next.js에서 제공하는 code splitting이나, SEO, i18n이 부럽고, jekyll 기본 documentation이 부실하다는게 아쉽지만, 충분히 사용자에 따라 보완할수 있다고 생각합니다.

# 구조

<div class="mermaid">
graph LR;
    A[Github] --> B[Github Actions];
    B --> C[jekyll-deploy-action];
    C --> D[CloudFlare];
            
</div>
Github Actions로 파일을 생성하고, Cloudflare를 사용해서 속도를 올리고 있습니다.

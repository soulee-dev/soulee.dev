---
layout: post

title: 개인프로젝트 개발, 배포, 수익화까지

description: 개인프로젝트 개발, 배포 과정

summary: 개인프로젝트 개발, 배포과정

comments: true

tags: [coding]
---

개인 프로젝트는 속도가 중요하지만, 제가 생각하기엔 더 중요하다고 생각하는점은 **안정적 배포와 마케팅**입니다. 대부분의 사용자들은 처음 웹사이트/앱을 접했을때에 완벽한 모습을 보지 못하면 다시 기회를 주지 않거든요. 그래서 UX를 한층 올려주는 배포, 마케팅에 대해 말해보겠습니다.

이 글에서는 주로 웹관련 기술에 대해 이야기하지만, 앱 관련 내용도 있습니다.

아래 내용은 제 개인적생각들이지만, 개발자분들이 보고 참고하는 내용으로 삼아주시면 감사하겠습니다.

# 프로젝트 소개

우선 제가 만든 세가지 프로젝트에 대해 소개해드리겠습니다.

## chekly - 자가진단 자동화

사용스택

- jQuery + plainJS
- redis
- mariaDB
- AWS Lightsail
- Flask

[Github: lill74/chekly_public](https://github.com/lill74/chekly_public)

## issue-finder - 핵토버페스트 issue 찾기

사용스택

- ReactJS
- MongoDB
- AWS Lightsail
- Flask

[Github: lill74/issue-finder](https://github.com/lill74/issue-finder)

## primeNet - 대통령 임기 보기

사용스택

- NextJS

[Github: lill74/primeNet](https://github.com/lill74/primeNet)

# 개발

제가 생각하기에 개발 과정에서 가장 중점으로 둬야할건, 개발자의 편의가 아니라, 내 아이디어를 중심으로 **UX를 개선하는것이라고 생각합니다**. 많은 개발자들이 착각하는데, 더 좋은 기술 스택, 좋은 언어를 사용하는것보다 우선순위는 UX입니다.

UX는 디자인부터, 설계까지 모든 분야야로 아우를수 있는데 대표적인 레퍼런스로

### 디자인

[UI 폼 디자인의 모든 것(1부) - brunch](https://brunch.co.kr/@thinkaboutlove/262)
[UI 폼 디자인의 모든 것(2부) - brunch](https://brunch.co.kr/@thinkaboutlove/267)
[버튼 색상 적용 UX 가이드 - brunch](https://brunch.co.kr/@ebprux/205)

### 속도

[성능 최적화 - TOAST UI](https://ui.toast.com/fe-guide/ko_PERFORMANCE)

위 내용들을 추천드립니다.

### 설계

#### 보안

- HTTPS 지원
- [개인정보 처리 방침 생성기](https://www.privacy.go.kr/a3sc/per/inf/perInfStep01.do)
- VPN을 이용해 SSH 사용하기

개인정보 처리 방침은 의무이지만, 이 내용을 생략하시는 분들이 많이 있습니다. 개인정보를 처리하는 프로젝트의 경우 개인정보 처리 방침, 개인정보 처리 담당자 연락처등의 내용을 넣는것을 추천드립니다. 사용자가 **이 웹사이트를 믿어도 되나?** 를 결정하는데에 중요한 Factor로 작용하기도 합니다.

# 배포

## 클라우드

### AWS Lightsail

방화벽, SSH, 보안설정등 다양한 설정을 진행해야되서 배포 속도가 느리지만, 그럼에도 불구하고 개인 개발자가 개발하면서 사용하기 좋은 플랫폼이라고 생각합니다.

### Heroku

AWS의 장점을 다 덮지만, 무료 티어는 너무 불편합니다.

### Serverless

## 정적 페이지 호스팅

### Vercel, netlify

둘다 개인 개발자는 무료로 사용할수 있지만, UI나 트래픽 폭이 널널한 Vercel을 추천드립니다.

### Github pages

# 홍보

### 랜딩페이지

랜딩페이지의 디자인도 유저가 웹사이트를 사용할지 생각하게 하는 중요한 Factor중 하나입니다. 홍보 URL을 생성할때는, 랜딩페이지로 직접 트래픽이 들어오게 하고, 그 랜딩페이지에서 서비스 페이지로 redirect하는 방식을 추천드립니다.

[휴대폰 목업 생성](https://mockuphone.com/)

- 구글에서 Landing page templets 를 검색해보세요.

### 개발자 커뮤니티

개발자 커뮤니티는 새로운 제품을 소개하기 가장 좋은 플랫폼중 하나입니다. 개발자라는 특성상 새로운 제품에 거부감이 덜하고, 온라인 활동을 많이 하는 사람들을 타게팅 할수 있습니다. 초기 홍보에 추천드립니다. 각 커뮤니티별 특성이 다르니 고려해서 홍보하는것을 추천드립니다.

[GeekNews](https://news.hada.io/)
[생활코딩 - Facebook](https://www.facebook.com/groups/codingeverybody/)
[코딩이랑 무관합니다만, - Facebook](https://www.facebook.com/groups/System.out.Coding/)
[프로그래밍 갤러리 - dcinside](https://gall.dcinside.com/board/lists?id=programming)

### 공유 버튼

개인적으로 생각하기에 요즘 누가 공유버튼을 쓰겠어? 라는 생각을 했지만 제 웹사이트들에서 들어오는 트래픽의 30%정도가 공유 버튼을 이용해서 들어오고 있었습니다. 꼭 다는것을 추천 드립니다.

### SEO 등록, 최적화

### OG Tag, 썸네일, Favicon

[페이스북 공유 디버거](https://developers.facebook.com/tools/debug/)

# 모니터링

사실상 DevOps가 하는 일과 비슷합니다.
[DevOps 팀을 위한 모니터링 팁 - RIDI](https://www.ridicorp.com/story/monitoring-howto/)

## Sentry

redis, flask등 에러 로그 관리를 도와줍니다.

## Uptime Robot

유저들이 링크를 눌렀을때 반응하지 않는것만큼 싫어하는 일은 없을겁니다.

## [Crontior](https://cronitor.io/)

Cron job을 실행하고, 실패시 Notifcation을 제공하는 프로그램입니다.

# 사후 보고

## Analytics

### Google Analytics

### Facebook Analytics

### GIF 사용

랜딩페이지에 GIF영상을 넣으면

# 수익화

## Google Adsense, Admob

한국에서 가장 광고 단가가 높은 편이지만, 해외 트래픽에 대한 광고 단가가 정말 높습니다. 하지만 요즘 대부분의 사용자가 광고 차단 플러그인을 사용해서 트래픽에 비해 광고 수익은 정말 적습니다, 그와 반대로 Admob은 트래픽만큼 들어옵니다.

## 기타 광고 플랫폼

- Kakao Adfit (한국)
- dable (한국)

## 후원 플랫폼

- Twip (한국)
- Paypal
- Buy me a coffe

# 앱 vs 웹 특징

웹은 초기 홍보가 가장 중요합니다. 그에 반해 앱은 플레이 스토어, 앱스토어라는 플랫폼에 종속 되어있어서 제목, 태그, 설명등의 설정이 중요합니다.

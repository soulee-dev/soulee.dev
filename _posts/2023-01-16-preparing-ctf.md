---
layout: post
title: CTF 대회 준비, 문제 출제하기
description: Docker, AWS 많은 기술 스택이 필요한 CTF 대회 제대로 준비해보자
summary: Docker, AWS 많은 기술 스택이 필요한 CTF 대회 제대로 준비해보자
comments: true
tags: [translation]
---

# 글을 시작하며
2022년 부터 KCTF 운영까지 1학년으로 동아리 회장을 역임하며 운영진분들께 많은 것들을 배웠습니다. 특히나 아래 있는 내용들도 대부분 운영진 분들께서 만들어주신 내용을 회고하며 작성한 내용입니다. 미리 감사인사 전합니다. 이소울 드림.

# 문제 출제
1. 문제 상의
	- 분야와 난이도 조절을 상의한다.
2. 문제 출제
	- 요즘은 워낙 좋은 Material이 많다.
	- 출제 능력이 떨어지면, 다른 ctf를 참고해도 좋다. 물론 배껴오는 것은 지양해야 한다.
3. 문제 업로드
	- Write-up, Binary, Source가 포함된 문제를 업로드 한다.
	- 이 부분에서 Dockerfile도 생성해준다. (아래 참조)
4. 문제 Cross Check
	- 이 부분이 가장 중요하다.
	- 적어도 2일 전에는 문제를 완성해서 Cross Check를 해서, 문제 발생 시 문제를 수정해야 한다.
대부분의 문제는 web, crypto, pwnable, reversing, misc 로 구성되고, 추가적으로 mobile, forensic이 있는 경우가 있다.

# 환경 구성
- AWS EC2
	- 내부 ctf 30명, 25문제 기준 t2.medium 인스턴스를 사용하였다.
	- 고정 IP 할당이 필요하다.
	- Private Key File 잃어버리면 골치아파지니, 중요한 곳에 저장해놓자.
- Docker, docker-compose
	- ctfd의 운영과, 다양한 문제들을 띄우는데 중요하다. 특히 docker의 여러 명령어들을 알고 있어야 한다.
- Portainer
	- Docker container 관리 웹 툴이다. Docker 명령어를 쓰는 것보다, 훨씬 편하게 모니터링과 관리가 가능하다.
* Grafana + Prometheus
	- 서버 상태 모니터링에 필수적이다. 특히나 CTF 오픈 초기, 사용자가 몰려 서버가 과부하 되거나, 문제 설계 잘못으로 많은 리소스를 쓰는 등, 모니터링이 필수적이다.
	- Discord 웹훅에 연결해서 서버 위험 상황에 알림 기능을 사용할 수 있다.
- SFTP
	- EC2 로 접속해서 파일을 옮기는데 사용한다.
	- FileZilla, Terminus 등을 추천한다.
- Social Tool
	- 운영진과 참여자의 소통을 위해 필요하다.
	- Slack, Discord, Kakaotalk 등 다양한 툴이 많지만 개인적으로는 Discord를 추천한다.
	- Discord는 사용률이 높아 새로 회원 가입을 할 필요가 없어서 사용이 편안하다.
- Notion
	- 문제 업로드, Cross Check 등에 사용한다. 문제가 종종 바뀔 수 있으므로 버전 관리에 신경 써야한다.

## Docker
문제 작성이 완료되면, Dockerfile과 docker-compose.yml를 작성한다.
Maintainer를 docker-compose.yml 파일과 일치 시켜준다.

```dockerfile
# --------------- EXAMPLE ---------------
FROM python:3.9

RUN wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -
RUN sh -c 'echo "deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main" >> /etc/apt/sources.list.d/google-chrome.list'
RUN apt-get -y update
RUN apt-get install -y google-chrome-stable
RUN apt-get install -yqq unzip
RUN wget -O /tmp/chromedriver.zip http://chromedriver.storage.googleapis.com/`curl -sS chromedriver.storage.googleapis.com/LATEST_RELEASE`/chromedriver_linux64.zip
RUN unzip /tmp/chromedriver.zip chromedriver -d /usr/local/bin/
ENV DISPLAY=:99
WORKDIR /code
COPY ./requirements.txt /code/requirements.txt
RUN pip install --no-cache-dir --upgrade -r /code/requirements.txt
COPY ./app /code/app
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "80"]
# --------------- EXAMPLE ---------------
MAINTAINER ezxss
```

docker-compose.yml 파일에서 중요한 부분은 두가지이다. Maintainer를 맞춰주는것과 Expose 되는 포트를 맞춰주는것이다.
왼쪽 포트다 Expose되는 포트이고, 오른쪽 포트가 Internal Port이다.

```yaml
version: '3.3'
services:
	ezxss:
		build: ./
		ports:
		- "40083:80"
```
서버에 SFTP로 업로드를 마치고, 폴더에 들어가서 `docker-compose up --build` 를 입력한다.

*`--build` 를 추가해주는 이유는 이미 이미지가 빌드 되어있는 경우, 이미지를 그대로 사용하기 때문에 refresh 하기 위해 추가해준다.*

Portainer를 설치하지 않은 경우, 아래 Docker 명령어들을 숙지하는 게 좋다.

1. 현재 실행 중인 컨테이너를 확인하려면 `docker ps` 명령어를 사용한다.
2. 현재 실행중인 컨테이너의 로그를 확인하려면 `docker logs [container id]` 명령어를 사용한다.
## Grafana Alert 설정
Grafana에서 제공하는 

# 대회 시작 직전
간단한 체크리스트를 작성해보았다.
운영진 다같이 모여서 초기 장애 대응을 하는것이 중요하다.
혼선이 없기 위해서는 한 명이 컨트롤 타워 역할을 하고 서버관리, 공지사항 등록 등을 지시해야 한다.

- [ ] 시작 하면 공지 (사용하는 소셜 툴에 공지를 한다)
- [ ] 시작하면 카운트다운
- [ ] Connection Info 확인 (nc나 http등 모두 정상적으로 작동하는지 확인한다)
- [ ] flag 확인 (문제 내부에 flag가 포함되어있지 않은지, 등록한 flag가 일치하는지 확인이 필요하다)

# 대회중
대회 중에는, Cross Check에서 미처 발견하지 못한 문제 에러나 flag 오류 등이 발생할수 있다. 이에 대응하기 위해 모든 출제자들이 Discord 방에 들어와서 계속 예의 주시해야한다. 문제에 최소한 1 solve는 나올 때까지 대기해야 한다.

# Template
## Notion
- Status (In progress, Done, Challenge Created)
- Category (web, pwnable, misc...)
- Cross Check (checkbox)
- Level (Low, Mid, High)
- Connection info (port, domain)
- Score
- Assign (출제자)

## Discord
채널 템플릿
- alert (Grafana 알림 기능)
- 운영진 채널
- 문제 카테고리별 채널 (web, pwnable, reversing...)
- general (general이 있어야 농담도 하고 대회 분위기가 너무 무거워지지 않는다)

권한 템플릿
- 운영진 권한 (색깔과, 분리 기능을 추가해 구분되게 하고, 모든 권한을 부여하여 문제상황 발생 시 운영진들이 자체적으로 대응할 수 있게 만들어야 한다)
---
layout: post
title: ap 미적분 정리 (2)
description: ap 미적분 정리 (2)
summary: 용어, 기본 원리 정리 (2)
comments: true
mathjax: true
tags: [math]
---

# 용어 정리

| word        | 뜻               |
| :---------- | :--------------- |
| specify     | 구체화           |
| tolerance   | 오차             |
| continuity  | 연속             |
| algebra     | 대수             |
| imply       | 성립하다         |
| derivatives | 미분계수, 도함수 |

# 기호 정리

| phrases        | 뜻                 |
| :------------- | :----------------- |
| $$\forall$$    | for all, for any   |
| $$\exists$$    | there exist        |
| $$\owns$$      | such that, so that |
| $$\mathbb{R}$$ | real numbers       |

# 증명

- 귀류법 : 반례를 이용한, 간접 증명

## 임의의 실수에 0을 곱하면 0이다

### 증명

조건 $$\forall m \in \mathbb{R}$$ 일때,

$$m \cdot 0 = m(0 + 0) = m \cdot 0 + m \cdot 0$$

## 0으로 나눌수 없다

### 증명 (1)

귀류법을 사용해서

조건 $$\forall m \in \mathbb{R}$$ 일때,

$$\frac{b}{a} = \frac{b + a}{a} = \frac{b}{a} + 1$$

$$\frac{b}{a} = k$$

$$\frac{b}{a} + 1 = k$$

$$k \neq k$$ 이므로 모순입니다

### 증명 (2)

$$1 \cdot 0 = 0$$

$$2 \cdot 0 = 0$$

$$3 \cdot 0 = 0$$

$$ ... $$

0으로 나눌수 있다고 가정을 하면

$$1 = \frac{0}{0}$$

$$2 = \frac{0}{0}$$

$$3 = \frac{0}{0}$$

$$1 \neq 2 \neq 3$$ 이므로 모순입니다

# $$\varepsilon - \delta $$ 논법

$$\displaystyle{\lim_{x \to c} f(x) = L}$$

을 증명하는 방법에 대해 이야기 해보겠습니다

## 기본 원리

극한의 엄밀한 정리를 위해서는 $$\displaystyle{\lim_{x \to c} f(x) = L}$$ 이 $$c$$에 '충분히 가까운' $$x$$를 선택했을때 $$f(x)$$ 와 $$L$$ 의 거리가 '선택한만큼 작은' 값을 가져야합니다.

- Thomas' Calculus

## 정의

조건

$$ \forall \varepsilon > 0$$

$$\owns \delta = \delta(\varepsilon) > 0$$

일때

$$\left| x - c \right| < \delta \Longrightarrow \left| f(x) - c \right| < \varepsilon$$

입니다.

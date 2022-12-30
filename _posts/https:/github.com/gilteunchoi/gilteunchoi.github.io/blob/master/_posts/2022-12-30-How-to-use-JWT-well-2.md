---
title: "JWT를 잘 사용하는 방법 (2)"
date: 2022-12-30 11:41:24 +0900
toc: true
toc_sticky: true
categories: [JWT, Java, Spring Boot]
---

## 세차새차 개발 일지 시리즈

## JWT None Algorithm 공격

공격 방식의 이해를 위해서 JWT의 구조를 먼저 알아보도록 하자. JWT는 Header와 Payload, Signiture 세 부분으로 나누어진다. 각 부분은 base64로 인코딩되며, '.'으로 파트 사이를 구분한다. 


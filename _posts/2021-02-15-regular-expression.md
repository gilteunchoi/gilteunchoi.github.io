---
title: "정규표현식"
date: 2021-02-15 20:03:22 +0900
toc: true
toc_sticky: true
categories: regexp
---

문자열의 집합을 나타내는 데 사용하는 정규 표현식은 스티븐 콜레이니가 고안한 정규 언어에 그 기원을 둔다. 
여러한 형태의 정규 표현식이 존재하였지만, POSIX.2 (Portable Operating System Interface)에서 지금의 모습을 갖추었다.

이러한 형태의 정규표현식을 다양한 언어에서 사용하는 모습을 알아보자.
```regexp
/(http|https|ftp|telnet|news|mms):\/\/[^\"'\s()]+/i
```

자바
```java
boolean matches("/(http|https|ftp|telnet|news|mms):\/\/[^\"'\s()]+/i")
```


---
title: "IaaS와 PaaS, SaaS"
date: 2021-01-07 18:04:10 +0900
categories: AWS
---

Amazon Web Services의 Solutions Architect Associate 자격증 준비를 하며 작성하는 포스트입니다.

*****

[Amazon Web Serviecs 개요](https://d1.awsstatic.com/International/ko_KR/whitepapers/aws-overview.pdf)에 등장하는 IaaS와 PaaS, SaaS는 AWS가 제공하는 세 가지 클라우드 컴퓨팅 서비스 모델이다. 이 포스트에서는 이와 함께 On-premise, Off-premise의 개념도 확인한다.

# On-premise와 Off-premise

On-premise 방식의 서비스 구축은 사용자가 목적 달성을 위해 자체적인 데이터 센터를 운영하는 것이다.
이러한 방식은 인프라 전체를 사용자의 입맛대로 변경할 수 있다는 장점이 있지만, 이를 구축하고 유지하는 데 있어 막대한 비용이 들어간다.

위 단점을 보완하기 위해 생겨난 클라우드 컴퓨팅은 공유가 가능한 컴퓨팅 파워를 개별 사용자들이 나누어 사용하는 것에 그 의의가 있고,
클라우드 컴퓨팅과 같은 원격 인프라에 구축한 전산 시스템을 (On-premise와 반대되는 개념인) Off-premise 시스템이라 한다.

 >*premise 1. (주장의) 전제*

# Off-premise 시스템의 단계

Off-premise 시스템은 (AWS와 같은)클라우드 컴퓨팅 서비스의 제공자와 사용자가 관리하는 인프라의 범위에 따라 그 단계를 세분화하고 있다.

||On-premise|IaaS|PaaS|SaaS|
|---|:---:|:---:|:---:|:---:|
|Application|O|O|O|X|
|Database|O|O|O|X|
|Runtime|O|O|X|X|
|Middleware|O|O|X|X|
|Operating System|O|O|X|X|
|Virtualization|O|X|X|X|
|Servers|O|X|X|X|
|Storage|O|X|X|X|
|Netwarking|O|X|X|X|

>*O는 사용자가 직접 관리해야 하는 부분을, X는 제공자가 관리하는 부분을 나타낸다*

## Infastructure as a Service (IaaS)

## Platform e as a Service (PaaS)

## Software as a Service (SaaS)

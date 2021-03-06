---
title: "IaaS, PaaS, SaaS란?"
date: 2021-01-07 18:04:10 +0900
toc: true
toc_sticky: true
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

> *premise 1. (주장의) 전제*

# Off-premise 시스템의 종류

Off-premise 시스템은 (AWS와 같은)클라우드 컴퓨팅 서비스의 제공자와 사용자가 관리하는 인프라의 단계에 따라 그 종류가 나뉜다.

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
|Networking|O|X|X|X|

> *O는 사용자가 직접 관리해야 하는 부분을, X는 제공자가 관리하는 부분을 나타낸다*

## IaaS (Infastructure as a Service)

인프라 제공 서비스

AWS의 [Elastic Compute Cloud](https://aws.amazon.com/ko/ec2)와 같은 IaaS는 사용자에서 운영체제부터 그 상위 계층의 인프라를 관리할 수 있는 기능을 제공한다.
가장 많은 부분을 변경 할 수 있는 많큼 자유도가 가장 높지만 신경써야 할 부분이 많다.

## PaaS (Platform as a Service)

플랫폼 제공 서비스

AWS의 [Lambda](https://aws.amazon.com/ko/lambda)와 같은 PaaS는 사용자에게 데이터와 어플리케이션의 관리 기능만을 제공한다.
사용자가 어플리케이션에 집중할 수 있는 환경을 제공한다.

## SaaS (Software as a Service)

소프트웨어 제공 서비스

AWS의 [Marketplace](https://aws.amazon.com/marketplace)와 같은 SaaS는 사용자에게 어떠한 변경 권한도 주지 않은 채로 소프트웨어와 그 기반 시설 전체를 제공한다.

# 언제 어떠한 서비스를 사용해야 하는가

암호화폐 채굴 등의 ASIC(Application-Specific Integrated Circuit)을 사용할 필요가 있는 일이라면, 해당 하드웨어를 제공하지 않는 클라우드 컴퓨팅은 선택지가 될 수 없다. 
이러한 경우에는 On-Premise 시스템만이 해답일 것이다.

> 사용자 권한
  IaaS > PaaS > SaaS

> 개발 속도
  SaaS > PaaS > IaaS
  
빠른 개발이 필요하다면 모든 기능이 이미 준비되어 있는 SaaS를, 개발 과정에서 많은 customization이 필요하다면 IaaS를 택하자. 중도인 PaaS는 양쪽의 특성을 반씩 가지고 있다.

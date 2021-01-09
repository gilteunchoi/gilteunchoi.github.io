---
title: "AWS Outposts"
date: 2021-01-09 19:59:30 +0900
toc: true
toc_sticky: true
categories: AWS
---

Amazon Web Services의 Solutions Architect Associate 자격증 준비를 하며 작성하는 포스트입니다.

*****

[Amazon Web Serviecs 개요](https://d1.awsstatic.com/International/ko_KR/whitepapers/aws-overview.pdf)에서는 
클라우드와 하이브리드, On-premise 세 가지의 클라우드 컴퓨팅 배포 모델을 제안하고 있다.

> 코카콜라의 경쟁 상대는 다른 음료수가 아니라 물이다. 음료수 시장에서 40%의 점유율을 차지하고 있는 독보적인 1위지만 
  전체 물 시장에서는 고작 3%를 차지하고 있을 뿐이다. - 코카콜라 前 CEO 로베르토 고이주에타

코카콜라가 노는 물은 음료 시장이 아니라 '마실 것' 시장이라는 이야기다. 대단한 배포가 아닐 수 없다. 

이 이야기를 컴퓨팅 시장에도 적용시켜 본다면, AWS 클라우드의 진정한 경쟁 상대는 On-premise 시스템일 것이다. 
그런데 이러한 클라우드 컴퓨팅의 개념에 반하는 On-premise 솔루션을 AWS는 제공하고 있다. 
물리적인 한계를 뛰어넘을 수 없기 때문이겠지만, AWS의 솔루션들 중에서는 조금 따로 노는 듯한 느낌이 든다.

<a href="https://www.statista.com/chart/18819/worldwide-market-share-of-leading-cloud-infrastructure-service-providers/" title="Infographic: Amazon Leads $100 Billion Cloud Market | Statista"><img src="https://cdn.statcdn.com/Infographic/images/normal/18819.jpeg" alt="Infographic: Amazon Leads $100 Billion Cloud Market | Statista" width="50%" height="auto" style="width: 100%; height: auto !important; max-width:960px;-ms-interpolation-mode: bicubic;"/><br/></a> *2020년 2분기 클라우드 컴퓨팅 시장 점유율* <a href="https://www.statista.com/chartoftheday/">- Statista</a>

# AWS Outposts

이번 포스트에서는 [AWS Outpost](https://aws.amazon.com/outposts/)에 대해서 다룬다.
AWS Outpost는 AWS으로부터 42U 규격의 표준 서버를 1에서 96랙까지 대여하는 서비스이다. 2021년부터는 더 작은 폼팩터 단위로도 대여해준다고 한다.

> *outpost 1. (군대의) 전초 기지 2. 벽지의 소도시, 외딴 곳에 있는 건물들*

## On-premise 시스템을 구축하는 이유

### 지연시간

실시간 멀티플레이어 게임과 같은 낮은 지연 시간을 요하는 어플리케이션은 물리적인 한계가 있다.
AWS의 가까운 퍼블릭 클라우드 서비스가 이를 충족하지 못한다면, AWS Outpost가 대안이 될 것이다.

### 로컬 데이터 처리

기상 데이터 분석과 같이 처리하는 데이터의 크기가 크다면 이를 클라우드로 이식하는데 막대한 비용이 들어간다.

### 데이터 상주

데이터가 특정 장소나 국가를 벗어날 수 없는 경우에도 On-premise 시스템을 사용해야 한다.

> 한국의 예시로는『공간정보의 구축 및 관리 등에 관한 법률』 제16조(기본측량성과의 국외 반출 금지), 제21조(공공측량성과의 국외 반출 금지)에 따라 측량성과의 국외반출이 금지되어 있다.

## 기능

## 사용 예시

## 비용 

## 자주 물어보는 질문들

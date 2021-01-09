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

> *outpost 1. (군대의) 전초 기지 2. 벽지의 소도시, 외딴 곳에 있는 건물들*

[AWS Outpost](https://aws.amazon.com/outposts/)는 AWS가 제공하는 하이브리드 클라우드 컴퓨팅 솔루션으로, AWS으로부터 42U 규격의 표준 서버를 1에서 96랙까지 대여받는 서비스이다. 
2021년부터는 더 작은 폼팩터 단위로도 대여가 가능할 것이라고 한다. 하드웨어와 소프트웨어를 같이 제공하며, 이 둘을 개별적으로 구매하거나 대여할 수 없다. 

AWS Outpost는 상위 AWS 리전에 의존하여 근처의 AWS 리전과 상시 연결되어 있어야 하며 별도의 오프라인 서비스는 제공하지 않는다. 
연결이 제한되거나 없는 환경에서 작동하도록 최적화된 [AWS Snowball Edge](https://aws.amazon.com/ko/snowball/)가 존재한다.

AWS Outposts 서비스를 지원하는 지역은 다음과 같다.

> 북아메리카 - 미국, 캐나다, 멕시코

> 유럽, 중동, 아프리카 -모든 EU 국가, 스위스, 노르웨이, 바레인, 아랍 에미리트 (UAE), 사우디 아라비아 왕국 (KSA), 이스라엘, 남아프리카

> 아시아 태평양 - 호주, 뉴질랜드, 일본, 대한민국, 홍콩 특별 행정구, 대만, 싱가포르, 인도네시아, 말레이시아, 태국, 인도

> 남아메리카 - 브라질

## On-premise 시스템을 구축하는 이유

### 1. 지연시간

실시간 멀티플레이어 게임과 같은 낮은 지연 시간을 요하는 어플리케이션은 물리적인 한계가 있다.
AWS의 가까운 퍼블릭 클라우드 서비스가 이를 충족하지 못한다면 AWS Outpost가 대안이 될 것이다.

### 2. 로컬 데이터 처리

기상 데이터 분석과 같이 처리하는 데이터의 크기가 크다면 이를 클라우드로 이식하는데 막대한 비용이 들어간다. 네트워킹 비용을 생각한다면 Outpost가 EC2의 가성비를 뛰어넘을 수 있다.

### 3. 데이터 상주

데이터가 특정 장소나 국가를 벗어날 수 없는 경우에도 On-premise 시스템을 사용해야 한다. 한국의 예시로는『공간정보의 구축 및 관리 등에 관한 법률』 제16조(기본측량성과의 국외 반출 금지), 제21조(공공측량성과의 국외 반출 금지)에 따라 측량성과의 국외반출이 금지되어 있는데, 한국의 경우 아시아 태평양 (서울) 리전이 있어 이 목적으로는 Outpost를 설치하지 않아도 된다.

## 비용 

||AWS Elastic Compute Cloud|AWS Outpost|
|---|---:|---:|
|2 m5.24xlarge|월 $ 6,635.52|월 $ 6,441.78|
|2 c5.24xlarge|월 $ 5,875.20|월 $ 5,823.79|

21년 1월 한국에서 가장 작은 단위의 AWS Outpost 서버를 대여한다면 청구될 금액이다.
AWS EC2는 온디맨드 인스턴스를 24시간 내내 가동했을 경우를 계산했다. Outpost가 설치될 데이터센터의 제반 비용을 포함하지 않았고, 기업이 아니라면 Outpost를 이용할 이유도 없기에 비용은 재미로만 보자.

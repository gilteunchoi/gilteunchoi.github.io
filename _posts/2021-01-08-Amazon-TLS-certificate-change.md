---
title: "Amazon S3와 CloudFront의 TLS 인증서 변경 안내 메일"
date: 2021-01-08 17:23:07 +0900
toc: true
toc_sticky: true
categories: AWS
---

Amazon Web Services의 Solutions Architect Associate 자격증 준비를 하며 작성하는 포스트입니다.

*****

예전에 사용하던 AWS 계정의 이메일로 AWS 안내 메일이 날라왔다.
내 계정 번호와 [조치 필요함] 말머리를 달고 날라왔기에 흠칫 놀라지 않을 수 없었다. 다행히 걱정하던 비용 문제는 아니였지만, 마침 자격중 준비를 하던 도중 날라온 이메일이니 내용과 QA를 확인해보자.

영어 공부도 할 겸 직접 의역을 했기에, 틀린 내용이 있다면 양해를 바란다. 개인정보가 나오는 부분은 지웠다.

# 메일 전문

## Title: [Action Required] Amazon S3 and Amazon CloudFront migrating default certificates to Amazon Trust Services starting March 23, 2021.

> 제목: [조치 필요함] Amazon Simple Storage Service와 Amazon CloudFront의 기본 인증서를 Amazon Trust Service로 이식하는 작업이 21년 3월 23일 시작됩니다.

You are receiving this message because your account has been identified as having used Amazon Simple Storage Service (S3)
and/or Amazon CloudFront within the past 6 months. This message is a reminder of the upcoming migration of both services’
default certificates to Amazon Trust Services, which will begin March 23, 2021. To prepare for this migration, we recommend
that you confirm that your applications trust Amazon Trust Services as a Certificate Authority. If your client trust store does
not trust the Certificate Authority, it will report the TLS certificate as “untrusted” and may close the connection.

> 본 메일은 6개월 내에 Amazon S3 또는 Amazon CloudFront를 사용한 유저에게 발송되었습니다. 
  이 메일은 2021년 3월 23일에 진행되는 다가오는 두 서비스의 기본 인증서를 Amazon Trust Services로 이식하는 작업을 미리 알려드리고자 전송되었습니다.
  이 이식 작업을 미리 준비하기 위해, 우리는 귀하의 어플리케이션이 Amazon Trust Services를 CA(Certificate Authority)로써 신뢰하는 지 확인하는 것을 추천드립니다.
  만약 귀하의 client trust store가 CA를 신뢰하지 않으면 해당 TLS 증명서를 "신뢰 할 수 없음"으로 보고하고 연결을 종료할 수 있습니다.

In 2018, AWS announced a broad migration of AWS services’ TLS certificates to our own Certificate Authority, Amazon Trust
Services (ATS). Consistent with this change, and beginning March 23rd 2021, Amazon S3 and Amazon CloudFront will begin
migrating the Certificate Authority for each services’ default certificate to Amazon Trust Services. Using our own Certificate
Authority, AWS can better manage the security practices used to handle the default certificates for each service.

> 2018년에, AWS는 전반적인 AWS 서비스들의 TLS 증명서를 자체적 CA인 ATS로 이식하고자 한다고 발표한 바 있습니다. 이러한 변화에 발맞추고자 2021년 3월 23일, 
  Amazon S3와 CloudFront는 두 기본 인증서의 CA를 ATS로 변경합니다. 자체적인 CA를 이용함으로써 AWS는 각 증명서들을 다루기 위해 사용되던 보안 정책들을 효과적으로 관리할 수 있습니다.

Your action may be required to ensure your applications continue normal operation after this change. If you already use
other AWS services, your application most likely already trusts Amazon Trust Services as many AWS services have already
migrated. Visit [https://www.amazontrust.com/repository/](https://www.amazontrust.com/repository/) for more information about Amazon Trust Services. 

> 이러한 변화에서 귀하의 어플리케이션이 정상 작동함을 보장하기 위해서는 귀하의 조치가 필요합니다. 귀하가 이미 AWS의 다른 서비스들을 사용하고 있는 중이라면 다른 AWS의 서비스들은 이미 이러한 이   식을 진행하였기 때문에 귀하의 어플리케이션은 이미 ATS를 신뢰하고 있을 가능성이 높습니다. [https://www.amazontrust.com/repository/](https://www.amazontrust.com/repository/)를 방문하여 ATS에 대한 더 많은 정보들을 확인하십시오.

(중략)

### Frequently Asked Questions

> 자주 물어보는 질문들

#### Q1: What is changing?

> 무엇이 바뀌는 건가요?

The Certificate Authority for Amazon S3 and Amazon CloudFront’s default certificates are changing from DigiCert to Amazon
Trust Services. This change does not impact workloads that use HTTP only or use a custom TLS certificate. For S3, many
regions already use Amazon Trust Services including all regional endpoints for the eu-west-3, eu-north-1, me-south-1, ap-
northeast-3, ap-east-1, and us-gov-east-1 regions. S3 will be migrating the remaining AWS Regions to Amazon Trust Services
as well. For CloudFront, all edge location endpoints will be migrating to Amazon Trust Services.

> Amazon S3와 CloudFront의 기본 인증서 CA가 DigiCert에서 ATS로 변경되었습니다. 이 변경은 HTTP통신을 진행하거나 사용자 정의 TLS 인증서를 사용하는 경우에는 영형을 주지 않습니다.
  S3의 경우에는 eu-west-3, eu-north-1, me-south-1, ap-northeast-3, ap-east-1, and us-gov-east-1 region의 엔드포인트를 포함한 많은 region이 이미 ATS를 사용하고 있습니다. 
  따라서 S3는 나머지 AWS region을 ATS로 이식하고자 합니다. CloudFront의 경우에는 모든 edge location 엔드포인트가 ATS로 이식됩니다.
 
#### Q2: When are these changes occurring?

> 언제 이런 변화가 일어날까요?

The changes in Certificate Authority will begin rolling out on March 23, 2021.

> 이러한 CA의 변화는 2021년 3월 23일부터 시작될 것입니다.

#### Q3: What do I need to do?

> 무엇을 해야 하나요?

Check your client certificate trust store to see if it already trusts Amazon Trust Services’ root certificates. If it does no further
action is needed. If it does not trust Amazon Trust Services, perform one of the following actions. Resolution option 1, update
your client certificate trust store to include all of Amazon Trust Services’ root certificates. Resolution option 2, change the
domain name your application requests to a CloudFront Alternative Domain Name (CNAME) that uses an TLS certificate from
an already trusted Certificate Authority.

> 귀하의 client trust store를 확인하여 ATS의 루트 인증서를 이미 신뢰하고 있는지 확인해야 합니다. 이미 이를 신뢰하고 있다면 다른 조치는 필요하지 않습니다.
  그러나 이를 신뢰하고 있지 않다면 다음 중 하나의 조치를 취하십시오. 해결책 1: 귀하의 클라이언트 certificate trust store를 업데이트하여 모든 ATS의 루트 인증서가 포함되도록 하십시오.
  해결책 2: 귀하의 어 (중간 저장)

#### Q4: How do I test if my application trust Amazon Trust Services?

You can verify your application trusts Amazon Trust Services by performing one of the following tests from within your
application. Test option 1, fetch the object https://s3-ats-migration-test.s3.eu-west-3.amazonaws.com/test.jpg and verify a
200 response or that you see the green check mark in the test image. Test option 2, create an S3 bucket in your AWS account
in any of the following regions (eu-west-3, eu-north-1, me-south-1, ap-northeast-3, ap-east-1, and us-gov-east-1) and fetch a
test object over HTTPS.

#### Q5: What root certificates are part of Amazon Trust Services?

Refer to https://www.amazontrust.com/repository/

#### Q6: What happens after March 23, 2021 if my clients do not trust Amazon Trust Services’ Certificate Authorities?

All client HTTPS requests made to a default Amazon S3 or Amazon CloudFront endpoint will receive the services’ default
certificate issued from Amazon Trust Services. If the client trust store does not trust the Certificate Authority, it will report
the TLS certificate as “untrusted” and may close the connection.

Sincerely,
Amazon Web Services

# 요약

AWS는 지금 전반적인 서비스들의 TLS 인증 기관을 자체적으로 운영하기 위해 기존에 사용하던 DigiCert를 버리고 ATS를 만들고 인증서들을 이곳으로 이식하고 있다.
새 CA가 발급한 인증서이므로 사용자의 클라이언트 certificate trust store를 업데이트 하라는 것이다.

내 AWS 계정에서는 TLS 통신을 사용하는 어플리케이션을 운영하고 있지 않으므로, 무서운 [조치 필요함] 말머리와는 다르게 한숨 돌려도 될 것 같다.

---
title: "AWS Certificate Manager"
date: 2021-01-08 17:23:07 +0900
toc: true
toc_sticky: true
categories: AWS
---

Amazon Web Services의 Solutions Architect Associate 자격증 준비를 하며 작성하는 포스트입니다.

*****

예전에 사용하던 AWS 계정의 이메일로 AWS 안내 메일이 날라왔다. 
내 계정 번호와 [조치 필요함] 말머리를 달고 날라왔기에 흠칫 놀라지 않을 수 없었다. 다행히 걱정하던 비용 문제는 아니였지만, 마침 자격중 준비를 하던 도중 날라온 이메일이니 내용을 확인해보자.

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

## Frequently Asked Questions

### Q1: What is changing?

The Certificate Authority for Amazon S3 and Amazon CloudFront’s default certificates are changing from DigiCert to Amazon
Trust Services. This change does not impact workloads that use HTTP only or use a custom TLS certificate. For S3, many
regions already use Amazon Trust Services including all regional endpoints for the eu-west-3, eu-north-1, me-south-1, ap-
northeast-3, ap-east-1, and us-gov-east-1 regions. S3 will be migrating the remaining AWS Regions to Amazon Trust Services
as well. For CloudFront, all edge location endpoints will be migrating to Amazon Trust Services.

### Q2: When are these changes occurring?

The changes in Certificate Authority will begin rolling out on March 23, 2021.

### Q3: What do I need to do?

Check your client certificate trust store to see if it already trusts Amazon Trust Services’ root certificates. If it does no further
action is needed. If it does not trust Amazon Trust Services, perform one of the following actions. Resolution option 1, update
your client certificate trust store to include all of Amazon Trust Services’ root certificates. Resolution option 2, change the
domain name your application requests to a CloudFront Alternative Domain Name (CNAME) that uses an TLS certificate from
an already trusted Certificate Authority.

### Q4: How do I test if my application trust Amazon Trust Services?

You can verify your application trusts Amazon Trust Services by performing one of the following tests from within your
application. Test option 1, fetch the object https://s3-ats-migration-test.s3.eu-west-3.amazonaws.com/test.jpg and verify a
200 response or that you see the green check mark in the test image. Test option 2, create an S3 bucket in your AWS account
in any of the following regions (eu-west-3, eu-north-1, me-south-1, ap-northeast-3, ap-east-1, and us-gov-east-1) and fetch a
test object over HTTPS.

### Q5: What root certificates are part of Amazon Trust Services?

Refer to https://www.amazontrust.com/repository/

### Q6: What happens after March 23, 2021 if my clients do not trust Amazon Trust Services’ Certificate Authorities?

All client HTTPS requests made to a default Amazon S3 or Amazon CloudFront endpoint will receive the services’ default
certificate issued from Amazon Trust Services. If the client trust store does not trust the Certificate Authority, it will report
the TLS certificate as “untrusted” and may close the connection.

Sincerely,
Amazon Web Services

*****

메일을 읽으면서 다시 짚고 넘어가고 싶었던 개념이 많았지만, 이번 포스트는 AWS Certificate Manger에 대해서 서술한다.

# AWS Certificate Manager

## Amazon Trust Service

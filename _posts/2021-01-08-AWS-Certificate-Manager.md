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
migrated. Visit https://www.amazontrust.com/repository/ for more information about Amazon Trust Services. 

To prepare for this migration, visit the announcement blog and review the FAQs below:
https://aws.amazon.com/blogs/security/how-to-prepare-for-aws-move-to-its-own-certificate-authority/

If you have additional questions, or require additional assistance, please open a case in the AWS Support Center:
https://aws.amazon.com/support
 

> 

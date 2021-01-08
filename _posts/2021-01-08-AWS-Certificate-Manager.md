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

 ## [Action Required] Amazon S3 and Amazon CloudFront migrating default certificates to Amazon Trust Services starting March 23, 2021.

> [조치 필요함] Amazon Simple Storage Service와 Amazon CloudFront의 기본 인증서를 Amazon Trust Service로 이식하는 작업이 21년 3월 23일 시작됩니다.

You are receiving this message because your account has been identified as having used Amazon Simple Storage Service (S3)
and/or Amazon CloudFront within the past 6 months. This message is a reminder of the upcoming migration of both services’
default certificates to Amazon Trust Services, which will begin March 23, 2021. To prepare for this migration, we recommend
that you confirm that your applications trust Amazon Trust Services as a Certificate Authority. If your client trust store does
not trust the Certificate Authority, it will report the TLS certificate as “untrusted” and may close the connection.

> 본 메일은 6개월 내에 Amazon S3 또는 Amazon CloudFront를 사용한 유저에게 발송되었습니다. 
  이 메일은 21년 3월 23일에 진행되는 다가오는 양 서비스의 기본 인증서를 Amazon Trust Services로 이식하는 작업을 미리 알려드리고자 합니다.
  ...임시저장...

In 2018, AWS announced a broad migration of AWS services’ TLS certificates to our own Certificate Authority, Amazon Trust
Services (ATS). Consistent with this change, and beginning March 23rd 2021, Amazon S3 and Amazon CloudFront will begin
migrating the Certificate Authority for each services’ default certificate to Amazon Trust Services. Using our own Certificate
Authority, AWS can better manage the security practices used to handle the default certificates for each service.

Your action may be required to ensure your applications continue normal operation after this change. If you already use
other AWS services, your application most likely already trusts Amazon Trust Services as many AWS services have already
migrated. Visit https://www.amazontrust.com/repository/ for more information about Amazon Trust Services. 

To prepare for this migration, visit the announcement blog and review the FAQs below:
https://aws.amazon.com/blogs/security/how-to-prepare-for-aws-move-to-its-own-certificate-authority/

If you have additional questions, or require additional assistance, please open a case in the AWS Support Center:
https://aws.amazon.com/support
 

> 

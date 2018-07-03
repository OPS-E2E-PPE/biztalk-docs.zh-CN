---
title: AS2 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fac8418-3c07-4513-94aa-e7a25087d789
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68ada5722e7b64d6ceaf3b511af5ac500a4dcce7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022595"
---
# <a name="as2-messages"></a>AS2 消息
本主题介绍了 AS2 消息，包括其结构、其上下文属性及其标头。  
  
## <a name="structure-of-an-as2-message"></a>AS2 消息的结构  
 在 BizTalk Server 中的 AS2 消息的结构根据[RFC 4130"基于 MIME 的安全对等业务数据交换使用 HTTP、 Applicability Statement 2 (AS2)](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。  
  
 AS2 消息的基本结构由 HTTP 消息内带有特定于 AS2 的附加标头的 MIME 格式组成。 下面的 HTTP、 AS2 和 MIME 标头的消息的性质取决于消息的类型：  
  
- **签名**– 如果对消息进行签名，将围绕文档负载添加签名包装。  
  
- **压缩**– 如果对消息进行压缩，将围绕文档和签名负载添加压缩包装。  
  
- **加密**– 如果对消息进行加密，将围绕文档、 签名和压缩负载添加加密包装。  
  
  下表显示了基于加密、签名和压缩的 AS2 消息的消息结构。  
  
|AS2 消息选项|消息结构|  
|-------------------------|-----------------------|  
|-无压缩<br /><br /> -无加密<br /><br /> -无签名|`HTTP, AS2, MIME Header      EDI/XML Payload`|  
|压缩<br /><br /> -无加密<br /><br /> -无签名|`HTTP, AS2, MIME Header      PKCS7-MIME Compression           EDI/XML Payload (compressed)`|  
|签名<br /><br /> -无压缩<br /><br /> -无加密|`HTTP, AS2, MIME Header       MIME Security Multipart (signed)           EDI/XML Payload           CMS-PKCS7 Signature`|  
|签名<br /><br /> 压缩<br /><br /> -无加密|`HTTP, AS2, MIME Header       PKCS7-MIME Compression           MIME Security Multipart (signed)(compressed)                EDI/XML Payload (compressed)                CMS-PKCS7 Signature (compressed)`|  
|加密<br /><br /> -无压缩<br /><br /> -无签名|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           EDI/XML Payload (encrypted)`|  
|压缩<br /><br /> 加密<br /><br /> -无签名|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           PKCS7-MIME Compression (encrypted)                EDI/XML Payload (compressed)(encrypted)`|  
|加密<br /><br /> 签名<br /><br /> -无压缩|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           MIME Security Multiparts (signed)(encrypted)                EDI/XML Payload (encrypted)                CMS-PKCS7 Signature (encrypted)`|  
|压缩<br /><br /> 加密<br /><br /> 签名|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           PKCS7-MIME Compression (encrypted)                MIME Security Multiparts (signed)(compressed)(encrypted)                     EDI/XML Payload (compressed)(encrypted)                     CMS-PKCS7 Signature (compressed)(encrypted)`|  
  
 如果文档负载包含多个文档，它们存储在一个多部分/相关 MIME 信封 RFC 2387 中所述。 可使用一个 Content-Disposition MIME 标头来指定消息中每个文档的文件名。  
  
 下表基于消息加密、签名和压缩选项显示了包含多个附件的 AS2 消息的消息结构。  
  
|AS2 消息选项|消息结构|  
|-------------------------|-----------------------|  
|-无压缩<br /><br /> -无加密<br /><br /> -无签名|`HTTP, AS2, MIME Header      MIME Multipart/related           EDI/XML Payloads`|  
|压缩<br /><br /> -无加密<br /><br /> -无签名|`HTTP, AS2, MIME Header      PKCS7-MIME Compression           MIME Multipart/related                EDI/XML Payload (compressed)`|  
|签名<br /><br /> -无压缩<br /><br /> -无签名|`HTTP, AS2, MIME Header       MIME Security Multipart (signed)           MIME Multipart/related                EDI/XML Payload           CMS-PKCS7 Signature`|  
|压缩<br /><br /> 签名<br /><br /> -无加密|`HTTP, AS2, MIME Header       PKCS7-MIME Compression           MIME Security Multipart (signed)(compressed)                MIME Multipart/related (compressed)                     EDI/XML Payload (compressed)                CMS-PKCS7 Signature (compressed)`|  
|-加密<br /><br /> -无压缩<br /><br /> -无签名|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           MIME Multipart/related (encrypted)                EDI/XML Payload (encrypted)`|  
|压缩<br /><br /> 加密<br /><br /> -无签名|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           PKCS7-MIME Compression (encrypted)                MIME Multipart/related                     EDI/XML Payload (compressed)(encrypted)`|  
|加密<br /><br /> 签名<br /><br /> -无压缩|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           MIME Security Multiparts (signed)(encrypted)                MIME Multipart/related                     EDI/XML Payload (encrypted)                CMS-PKCS7 Signature (encrypted)`|  
|压缩<br /><br /> 加密<br /><br /> 签名|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           PKCS7-MIME Compression (encrypted)                MIME Security Multiparts (signed)(compressed)(encrypted)                     MIME Multipart/related                          EDI/XML Payload (compressed)(encrypted)                     CMS-PKCS7 Signature (compressed)(encrypted)`|  
  
## <a name="as2-context-properties"></a>AS2 上下文属性  
 处理 AS2 消息时使用的上下文属性包括可以升级的属性以及未公开但可以在已挂起和跟踪的消息中查看的属性。 有关 AS2 上下文属性的列表，请参阅[AS2 上下文属性](../core/as2-context-properties.md)。  
  
## <a name="as2-headers"></a>AS2 标头  
 AS2 消息中的 AS2 标头描述接收方和发送方，并提供接收方发送 MDN 响应所需的信息。 接收方将使用 MDN 标头，除非**使用的验证和 MDN 的协议设置而非消息标头**在 AS2 协议中，选择属性或如果信息不可用的协议中属性。  
  
 AS2-From 标头、AS2-To 标头和“消息 ID”上下文属性唯一地描述了 AS2 消息。 它们也用于将 MDN 与其要做出响应的 AS2 消息相关联。  
  
 下表列出了这些标头（按字母顺序）：  
  
|AS2 标头|必需/可选|值|  
|----------------|------------------------|------------|  
|AS2-Version|可选|"1.1"|  
|AS2-From|Required|发送 AS2 消息的公司的名称。<br /><br /> 值：字符串，可打印的 ASCII，长度为 1 到 128 个字符|  
|AS2-To|Required|向其发送 AS2 消息的公司的名称。<br /><br /> 值：字符串，可打印的 ASCII，长度为 1 到 128 个字符|  
|AS2-Text|Required|文本（位于消息中的此标头内）<br /><br /> 值：字符串，可打印的 ASCII，长度为 1 到 128 个字符|  
|Disposition-Notification-To|Required|如果出现，则用作对要返回的 MDN 的请求。 如果附带 receipt-delivery-option 标头，则它是对异步 MDN 的请求。 如果不是，则它是对同步 MDN 的请求。<br /><br /> 如果不出现，则不需要 MDN。<br /><br /> 值：必须存在的邮件地址。 但是，不得将此地址用于标识 MDN 的返回目的地。 接收应用程序必须忽略此邮件地址并且不得就地址语法违规进行抗议。|  
|EDIINT-Features|Required|指示发起方系统所支持的功能。 BizTalk 将使用此标头来指示支持多个附件。<br /><br /> 值：“MA”|  
|Receipt-Delivery-Option|Required|指示应向其发送 MDN 的 URL。 如果 Receipt-Delivery-Option 出现，则 Disposition-notification-to 用作对异步 MDN 的请求。 Receipt-Delivery-Option 必须始终附带 Disposition-Notification-To。<br /><br /> 如果 Receipt-Delivery-Option 没有出现同时 Disposition-notification-to 出现，则 Disposition-notification-to 用作对同步 MDN 的请求。<br /><br /> 值：URL 字符串。|  
|signed-receipt-protocol<br /><br /> （位于 Disposition-Notification-Options 中）|可选|如果设置为“pcks7-signature”，则用于从接收方请求签名回执，并指示应返回给请求方的签名回执的格式。<br /><br /> 值：可选，pcks7-signature|  
|signed-receipt-micalg<br /><br /> （位于 Disposition-Notification-Options 中）|可选|请求方用于对返回的回执进行签名的首选 MIC 算法列表。 接收方应从左至右遵守此 MIC 算法列表。<br /><br /> 值：可选，MD5 或 SHA1|  
  
 对于传入消息，AS2EdiReceive 和 AS2Receive 接收管道对来自 AS2 协议属性的“签名的接收协议”和“签名的接收 MIC 算法”的值进行验证。  
  
 对于传出 AS2 消息，AS2EdiSend 和 AS2Send 发送管道使用在 AS2 协议中输入的值填充以上 AS2 标头（AS2-Version 除外，该标头已硬编码为 1.1）。  
  
 **MDN 请求**  
  
 通过将以下标头放在要发送的消息中来生成接收方返回 MDN (Message Disposition Notification) 的请求：  
  
 MDN-request-header = "Disposition-notification-to"  ":"  mail-address  
  
 此邮件地址不用于标识 MDN 的返回目的地。 接收应用程序必须忽略该值并且不得就地址语法违规发布错误。  
  
## <a name="see-also"></a>请参阅  
 [MDN 消息](../core/mdn-messages.md)
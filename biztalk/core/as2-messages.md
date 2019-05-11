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
ms.openlocfilehash: ed6348fcda1c219064d6b84bcf6da53833084020
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528615"
---
# <a name="as2-messages"></a>AS2 消息
本主题介绍了 AS2 消息，包括其结构、 其上下文属性和其标头。  
  
## <a name="structure-of-an-as2-message"></a>AS2 消息的结构  
 在 BizTalk Server 中的 AS2 消息的结构根据[RFC 4130"基于 MIME 的安全对等业务数据交换使用 HTTP、 Applicability Statement 2 (AS2)](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。  
  
 AS2 消息的基本结构由 HTTP 消息与其他特定于 AS2 的标头内的 MIME 格式组成。 下面的 HTTP、 AS2 和 MIME 标头的消息的性质取决于消息的类型：  
  
- **签名**– 如果对消息进行签名，将围绕文档负载添加签名包装。  
  
- **压缩**– 如果对消息进行压缩，将围绕文档和签名负载添加压缩包装。  
  
- **加密**– 如果对消息进行加密，将围绕文档、 签名和压缩负载添加加密包装。  
  
  下表中显示是基于加密、 签名和压缩的 AS2 消息的消息结构。  
  
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
  
 如果文档负载包含多个文档，它们存储在一个多部分/相关 MIME 信封 RFC 2387 中所述。 Content-disposition MIME 标头可用于指定在消息中的每个文档的文件名。  
  
 下表显示了包含多个附件，基于消息加密、 签名和压缩选项的 AS2 消息的消息结构。  
  
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
 处理 AS2 消息时使用的上下文属性包括可以升级以及未公开，但可以在已挂起和跟踪消息中查看的属性的属性。 有关 AS2 上下文属性的列表，请参阅[AS2 上下文属性](../core/as2-context-properties.md)。  
  
## <a name="as2-headers"></a>AS2 标头  
 中的 AS2 消息的 AS2 标头描述接收和发送方，并提供接收方发送 MDN 响应所需的信息。 接收方将使用 MDN 标头，除非**使用的验证和 MDN 的协议设置而非消息标头**在 AS2 协议中，选择属性或如果信息不可用的协议中属性。  
  
 AS2-From 标头、 AS2-标头和 MessageID 上下文属性唯一地描述了 AS2 消息。 它们还用于将 MDN 所响应的 AS2 消息相关联。  
  
 这些标头是下表中列出 （按字母顺序）：  
  
|AS2 标头|必需/可选|值|  
|----------------|------------------------|------------|  
|AS2 版本|可选|"1.1"|  
|AS2-从|Required|发送的 AS2 消息的公司的名称。<br /><br /> 值： 字符串，可打印 ASCII，长度为 1 到 128 个字符|  
|AS2-To|Required|AS2 消息发送到的公司名称。<br /><br /> 值： 字符串，可打印 ASCII，长度为 1 到 128 个字符|  
|AS2-Text|Required|（在此标头消息中） 的文本<br /><br /> 值： 字符串，可打印 ASCII，长度为 1 到 128 个字符|  
|处置-到通知|Required|当存在时，用作 mdn 要返回的请求。 如果它附带回执送达选项标头，则它是对异步 mdn 的请求。 如果没有，则它是对同步 mdn 的请求。<br /><br /> 如果不存在，则不需要 MDN。<br /><br /> 值： 邮件地址必须存在。 但是，该地址必须不用于标识要返回 MDN 的位置。 接收应用程序必须忽略此邮件地址和必须不会抱怨地址语法违规。|  
|EDIINT-功能|Required|指示发起方系统支持的功能。 BizTalk 使用此标头来指示支持多个附件。<br /><br /> 值：“MA”|  
|Receipt-Delivery-Option|Required|指示应将 MDN 发送到的 URL。 存在回执送达选项时，处理设置-通知-向用作请求异步 MDN。 回执送达选项必须始终附带的处置-到通知。<br /><br /> 如果回执送达选项不存在，并且处理设置-通知-已存在，处理设置-通知-向用作请求同步 mdn。<br /><br /> 值： URL 字符串。|  
|signed-receipt-protocol<br /><br /> （在处置通知选项）|可选|如果设置为"pcks7-签名"，用于从接收方请求签名的回执，并指示签名的回执应返回给请求者的格式。<br /><br /> 值： 可选的 pcks7 签名|  
|signed-receipt-micalg<br /><br /> （在处置通知选项）|可选|在返回的回执签名中使用请求方首选 MIC 算法列表。 MIC 算法列表应遵循从左到右接收方。<br /><br /> 值： 可选，MD5 或 SHA1|  
  
 对于传入消息，AS2EdiReceive 和 AS2Receive 接收管道验证 AS2 协议属性的 Signed Receipt Protocol 和 Signed Receipt MIC Algorithm 的值。  
  
 对于传出 AS2 消息，AS2EdiSend 和 AS2Send 发送管道填充以上 AS2 标头 （除了 AS2 的版本，它是硬编码为 1.1） 在 AS2 协议中输入的值。  
  
 **MDN 请求**  
  
 通过将以下标头放置在要发送的消息由接收方返回一个 MDN (Message Disposition Notification) 的请求：  
  
 MDN 请求标头"处置-通知-to"=":"邮件地址  
  
 此邮件地址不用于标识要返回 MDN 的位置。 接收应用程序必须忽略该值并不发布有关地址错误语法违规。  
  
## <a name="see-also"></a>请参阅  
 [MDN 消息](../core/mdn-messages.md)
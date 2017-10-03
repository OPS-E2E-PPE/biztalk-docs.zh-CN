---
title: "加密和签名证书 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, security
- security, certificates
- security, messages
- certificates, encryption
- encryption certificates, messages
- messages, encryption
- messages, certificates
- security, encryption
ms.assetid: 3c3f9de5-4156-4133-8d5e-c30b142b6d61
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 633484a6c5599b9323bfd7798f621b27a501ce6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="encryption-and-signing-certificates"></a>加密和签名证书
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在很大程度上依赖证书提供的安全性。 通过在进行加密和数字签名时使用证书，BizTalk Server 可以发送和接收可信数据，帮助您确保所处理的数据是安全的。 加密和数字签名都有一个公钥证书和一个私钥证书。 对于加密，消息的发件人使用收件人的公钥证书对消息加密，而消息的收件人 (BizTalk Server) 使用其私钥对消息进行解密。 对于数字签名，消息的发件人使用私钥证书对消息进行签名，而消息的收件人 (BizTalk Server) 使用发件人的公钥证书对签名进行验证。  
  
 BizTalk Server 使用公钥证书来验证入站消息的数字签名并对出站消息进行加密。 BizTalk Server 使用私钥证书来解密入站消息并对出站消息进行签名。  
  
 可以在 BizTalk 浏览器和 BizTalk 管理控制台中配置 BizTalk Server 使用的证书。  
  
 有关数字的证书的详细信息，请参阅 Microsoft TechNet 网站，网址[http://go.microsoft.com/fwlink/?LinkId=60508](http://go.microsoft.com/fwlink/?LinkId=60508)。  
  
> [!NOTE]
>  处理安全多用途 Internet 邮件扩展 (S/MIME) 消息时，可以选择让 BizTalk Server 引擎检查证书吊销列表 (CRL) 以确保证书没有过期，并且从证书直至根证书颁发机构 (CA) 的每一环节都是可信任的。 当管道使用 MIME/SMIME 解码器组件处理消息时执行此验证。 有关如何设置的详细信息**检查吊销列表**属性，请参阅[如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [BizTalk Server 使用的证书存储](../core/certificate-stores-that-biztalk-server-uses.md)  
  
-   [BizTalk Server 用于签名的消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)  
  
-   [BizTalk Server 用于加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)
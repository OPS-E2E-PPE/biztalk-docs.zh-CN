---
title: 加密和签名证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee36208b232609c5a73ede9a933f692a0681827f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65349543"
---
# <a name="encryption-and-signing-certificates"></a>加密和签名证书
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]严重依赖于提供证书的安全性。 通过使用证书进行加密和数字签名，BizTalk Server 可以发送和接收数据，可以是受信任，并可帮助确保所处理的数据安全。 对于加密和数字签名，没有公钥证书和私钥证书。 对于加密，消息的发件人使用接收方的公钥证书对消息进行加密，而接收方的消息 (BizTalk Server) 使用其私钥对消息进行解密。 数字签名消息的发件人使用私钥证书对消息进行签名和消息 (BizTalk Server) 的接收方使用发件人的公钥证书来验证签名。  
  
 BizTalk Server 使用公钥证书来验证数字签名的入站消息和出站消息进行加密。 BizTalk Server 使用私钥证书解密入站的消息和出站消息签名。  
  
 在 BizTalk 浏览器和 BizTalk 管理控制台中配置 BizTalk Server 使用的证书。  
  
 有关数字证书的详细信息，请参阅 Microsoft TechNet 网站上的[ http://go.microsoft.com/fwlink/?LinkId=60508 ](http://go.microsoft.com/fwlink/?LinkId=60508)。  
  
> [!NOTE]
>  在处理安全多用途 Internet 邮件扩展 (S/MIME) 消息时，你可以选择允许 BizTalk Server 引擎检查证书吊销列表 (CRL) 以确保证书尚未过期并且受信任根下证书颁发机构 (CA)。 管道处理中的 MIME/SMIME 解码器组件的消息时，将执行此验证。 有关如何设置的详细信息**检查吊销列表**属性，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [BizTalk Server 使用的证书存储](../core/certificate-stores-that-biztalk-server-uses.md)  
  
-   [BizTalk Server 用于签名消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)  
  
-   [BizTalk Server 用于加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)
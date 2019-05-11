---
title: 规划消息安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, security
- security, messages
- security, planning
- messages, security
ms.assetid: c0f93515-a822-425c-9155-270a179d6b61
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 847c53e7e07b4985f5cf2ad1756e3343c335348b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395627"
---
# <a name="planning-message-security"></a>规划消息安全性
根据你的公司中的安全策略，你可能想要考虑下表来确定必须将 BizTalk Server 环境中实现的安全级别中的问题。 这些问题的答案将确定所需的消息传送的安全功能。  
  
|问题|BizTalk Server 安全功能|  
|--------------|-------------------------------------|  
|**当接收消息：**||  
|如何确定消息的发件人标识？|BizTalk 管道和签名的证书或 Windows 安全 ID (SID) 中的参与方解析组件可用于正确标识消息的发件人。 有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。|  
|您是否知道发送消息的参与方？|可以使用 BizTalk 管道中的参与方解析组件以确定发送该消息的参与方是否已在系统中的贸易合作伙伴。 有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。|  
|若要避免接收消息从参与方不知道吗？|可以使用在端口中的身份验证所需的功能需要 BizTalk server 处理仅从已知参与方的消息。 有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。|  
|**如果发送的消息：**||  
|如何确保传出消息的隐私？|可以对要确保只有预期的参与方可以读取该消息的消息进行加密。 有关详细信息，请参阅[出站消息保护](../core/outbound-message-protection.md)。|  
|如何防止恶意用户的攻击者篡改该消息在传输过程？|可以使用数字签名来确保消息的完整性。 有关详细信息，请参阅[出站消息保护](../core/outbound-message-protection.md)。|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [发送和接收消息过程中的安全性](../core/security-for-sending-and-receiving-messages.md)  
  
-   [加密和签名证书](../core/encryption-and-signing-certificates.md)  
  
-   [对消息的发件人进行身份验证](../core/authenticating-the-sender-of-a-message.md)  
  
-   [向消息收件人授权](../core/authorizing-the-receiver-of-a-message.md)
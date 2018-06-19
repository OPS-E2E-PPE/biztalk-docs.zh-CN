---
title: 规划消息安全 |Microsoft 文档
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
ms.openlocfilehash: 5826db8480d378342ee30993f67bbd60e27751d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264285"
---
# <a name="planning-message-security"></a>规划消息安全性
根据你的公司中的安全策略，你可能想要考虑下表来确定必须在 BizTalk Server 环境中实施的安全级别中的问题。 这些问题的答案将确定所需的消息的安全功能。  
  
|问题|BizTalk Server 安全功能|  
|--------------|-------------------------------------|  
|**当接收消息：**||  
|如何确定消息的发送方的标识？|在 BizTalk 管道和签名的证书或 Windows 安全 ID (SID) 的方解析组件可用于明确标识消息的发件人。 有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。|  
|你知道当事方发送消息？|可以使用在 BizTalk 管道中方解析组件以确定将消息发送方是否已在你的系统贸易合作伙伴。 有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。|  
|你想要避免接收来自你不知道的参与方的消息？|可以在端口中使用“要求验证”功能来要求 BizTalk Server 只处理来自已知参与方的消息。 有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。|  
|**当发送消息：**||  
|如何确保传出消息的隐私？|你可以加密消息，从而确保仅预定的接收方能够读取该消息。 有关详细信息，请参阅[出站消息保护](../core/outbound-message-protection.md)。|  
|如何阻止恶意用户的攻击者篡改该消息在传输过程？|可以使用数字签名来确保消息的完整性。 有关详细信息，请参阅[出站消息保护](../core/outbound-message-protection.md)。|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [用于发送和接收消息的安全](../core/security-for-sending-and-receiving-messages.md)  
  
-   [加密和签名证书](../core/encryption-and-signing-certificates.md)  
  
-   [对一条消息的发送方进行身份验证](../core/authenticating-the-sender-of-a-message.md)  
  
-   [授权一条消息的接收方](../core/authorizing-the-receiver-of-a-message.md)
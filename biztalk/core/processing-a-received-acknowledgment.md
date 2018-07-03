---
title: 处理收到的确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f67a95-7368-40c2-a162-6ffc9de076fc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b39e1f0072c3a4b85860d851fcd9dad3fd53dda
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977454"
---
# <a name="processing-a-received-acknowledgment"></a>处理接收的确认
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将要求技术确认，如果协议中指定的相关属性。 对于 X12，这是**预期的 TA1**属性中的**确认**页中的单向协议**协议属性**对话框中或从回退协议属性。 对于 EDIFACT，这是**预期接收消息 (CONTRL)** 属性中的**确认**页中的单向协议**协议属性**对话框框或后备协议属性。 当接收协议处理收到的消息时，它将生成技术确认，ISA14 或 UNB9 的值作为消息中。  
  
 如果协议中指定了相关属性，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 预期将会对 X12 或 EDIFACT 编码进行功能确认。 对于 X12，此属性是**预期的 997**中**确认**页中的单向协议**协议属性**对话框中或从回退协议属性。 对于 EDIFACT，此属性是**确认 (CONTRL) 预期**属性中的**确认**页中的单向协议**协议属性**对话框中或后备协议属性。 当接收协议处理收到的消息时，它将生成技术确认，ISA14 或 UNB9 的值作为消息中。  
  
 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到对 EDI 消息的确认时，将使用确认控制架构验证此确认。 这些架构包括 X12_\<版本号\>*997.xsd 或 X12\\*\<版本号\>*对于 X12，EFACT TA1.xsd\\* \<版本号\>_CONTRL.xsd EDIFACT，和 HIPAA 5010 则为 X12_00501_997.xsd。  
  
 当接收管道处理传入确认时，管道会将此确认与已发送的 EDI 交换关联。 然后，管道将确认放置到 MessageBox 中。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不会对确认进行进一步处理。 此确认将挂起，除非您设置了处理确认的机制。 要处理确认，您可以设置订阅确认的发送端口，然后再将确认放置到某个文件夹中，您可以在此文件夹中例行删除确认。  
  
## <a name="see-also"></a>请参阅  
 [EDI 确认结构](../core/edi-acknowledgment-structure.md)   
 [发送 EDI 确认](../core/sending-an-edi-acknowledgment.md)
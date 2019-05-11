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
ms.openlocfilehash: f6facf54500f3ff28ddba25d03b8a1d96f9cf25d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396999"
---
# <a name="processing-a-received-acknowledgment"></a>处理收到的确认
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将要求技术确认，如果协议中指定的相关属性。 对于 X12，这是**预期的 TA1**属性中的**确认**页中的单向协议**协议属性**对话框中或从回退协议属性。 对于 EDIFACT，这是**预期接收消息 (CONTRL)** 属性中的**确认**页中的单向协议**协议属性**对话框框或后备协议属性。 当接收协议处理收到的消息时，它将生成技术确认，ISA14 或 UNB9 的值作为消息中。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将要求针对 X12 或 EDIFACT 编码，如果协议中指定的相关属性功能确认。 对于 X12，此属性是**预期的 997**中**确认**页中的单向协议**协议属性**对话框中或从回退协议属性。 对于 EDIFACT，此属性是**确认 (CONTRL) 预期**属性中的**确认**页中的单向协议**协议属性**对话框中或后备协议属性。 当接收协议处理收到的消息时，它将生成技术确认，ISA14 或 UNB9 的值作为消息中。  
  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]收到确认对 EDI 消息，它会验证确认使用确认控制架构。 这些架构包括 X12_\<版本号\>*997.xsd 或 X12\\*\<版本号\>*对于 X12，EFACT TA1.xsd\\* \<版本号\>_CONTRL.xsd EDIFACT，和 HIPAA 5010 则为 X12_00501_997.xsd。  
  
 当接收管道处理传入的确认时，它会将此确认与已发送的 EDI 交换关联起来。 然后，管道将确认放置到 MessageBox 中。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不会对确认进行进一步处理。 确认将被挂起，除非设置了一种机制，用于处理它。 若要处理确认，可以设置它，订阅，然后将其放入其中可以例行删除确认的文件夹的发送端口。  
  
## <a name="see-also"></a>请参阅  
 [EDI 确认结构](../core/edi-acknowledgment-structure.md)   
 [发送 EDI 确认](../core/sending-an-edi-acknowledgment.md)
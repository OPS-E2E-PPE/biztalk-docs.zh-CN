---
title: "处理收到的确认 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67f67a95-7368-40c2-a162-6ffc9de076fc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60236295e1e3bdd97a42d2f620de42129646494c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-a-received-acknowledgment"></a>处理接收的确认
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]如果在协议中指定相关的属性，则会认为技术确认。 对于 X12，这是**预期的 TA1**中的属性**确认**中的单向协议页**协议属性**对话框中或来自回退协议属性。 对于 edifact 而言，这是**收到预期消息 (CONTRL)**中的属性**确认**中的单向协议页**协议属性**对话框框或从回退协议属性。 当接收协议处理收到的消息时，它将在消息中生成由于 ISA14 或 UNB9 的值的结果技术确认。  
  
 如果协议中指定了相关属性，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 预期将会对 X12 或 EDIFACT 编码进行功能确认。 对于 X12，该属性是**997 预期**中**确认**中的单向协议页**协议属性**对话框中或来自回退协议属性。 对于 edifact 而言，此属性是**确认 (CONTRL) 预期**中的属性**确认**中的单向协议页**协议属性**对话框中或从回退协议属性。 当接收协议处理收到的消息时，它将在消息中生成由于 ISA14 或 UNB9 的值的结果技术确认。  
  
 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到对 EDI 消息的确认时，将使用确认控制架构验证此确认。 这些架构是 X12_\<版本号 > _997.xsd 或 X12\_\<版本号 > 对于 X12，EFACT _TA1.xsd\_\<版本号 > EDIFACT 和 HIPAA 的 X12_00501_997.xsd _CONTRL.xsd5010。  
  
 当接收管道处理传入确认时，管道会将此确认与已发送的 EDI 交换关联。 然后，管道将确认放置到 MessageBox 中。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不会处理进一步确认。 此确认将挂起，除非您设置了处理确认的机制。 要处理确认，您可以设置订阅确认的发送端口，然后再将确认放置到某个文件夹中，您可以在此文件夹中例行删除确认。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 确认结构](../core/edi-acknowledgment-structure.md)   
 [发送 EDI 确认](../core/sending-an-edi-acknowledgment.md)
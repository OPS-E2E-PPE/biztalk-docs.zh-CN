---
title: "已知问题 EDI 确认 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a769a78e-8a49-4aa4-899e-e9f54fdd5f37
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f02ef54ed8786f8ead12e16fad880040dbcadc8d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-acknowledgments"></a>EDI 确认的已知问题
本主题介绍 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中 EDI 确认的已知问题   
  
## <a name="ak102-in-a-997-acknowledgment-can-be-negative"></a>997 确认中的 AK102 可以是负值  
 X12 997 确认中的 AK102 数据元素（组控制编号）可以是负值。 即使为负值的组控制编号没有意义，带有负值 AK102 数据元素的确认将通过由 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 执行的验证。  
  
## <a name="a-contrl-receipt-may-report-a-status-of-accepted-when-part-of-the-message-is-rejected"></a>在消息的一部分被拒绝时，CONTRL 回执仍可能报告“已接受”状态  
 仅当传入的 EDIFACT 消息重复或信封中存在错误（例如，字符集存在问题）时，CONTRL 回执（EDIFACT 技术确认）才报告“已拒绝”状态。 与 X12 在 TA1 确认的 TA104 字段中报告“已接受交换但存在错误”不同，EDIFACT 不在 CONTRL 技术确认中报告这一状态。 如果接受了 EDIFACT 消息的一部分，CONTRL 技术确认将报告“已接受”。 在某些情况下，虽然消息的一部分将被拒绝，但 CONTRL 确认仍将报告“已接受”状态。 在这种情况下，UCI5 元素可能报告错误。  
  
## <a name="x12-acknowledgments-will-show-accepted-for-a-preserved-interchange-suspend-interchange-on-error-when-a-group-header-or-trailer-is-in-error"></a>在组标头或尾部出现错误时，如已选择了保留交换（出错时挂起交换），X12 确认将显示“已接受”  
 如果入站的批处理对于 X12 消息是设置为"保留交换-出错时暂停交换"，和组头或尾中的字段的选项无效，将为已接受 TA1 和 997 确认中报告的状态。 EDI 状态报告和事务集详细信息也将指示“已接受”状态。 即使交换将挂起，并且事件查看器中的错误将指示交换已挂起，也会出现这种情形。  
  
 TA1 确认将显示“已接受”状态，原因在于该确认的目的在于验证 ISA 标头和 IEA 尾部的正确性，而不是 GS 标头和 GE 尾部的正确性。 不过，997 确认也将显示“已接受”状态。  
  
## <a name="if-groups-in-an-interchange-have-the-same-name-the-status-report-will-show-twice-as-many-acknowledgments"></a>如果交换中有名称相同的组，则状态报告将显示预期确认数两倍的确认  
 BizTalk Server 在处理 EDI 交换时，如果交换中多个组的名称相同，则“EDI 交换和相关 ACK 状态”报告将列出预期功能确认数两倍的确认。 例如，如果交换中有两个组的名称相同，则状态报告将列出四个而不是两个确认。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md)   
 [发送 EDI 确认](../core/sending-an-edi-acknowledgment.md)   
 [处理收到的确认](../core/processing-a-received-acknowledgment.md)   
 [配置 EDI 确认](../core/configuring-edi-acknowledgments.md)
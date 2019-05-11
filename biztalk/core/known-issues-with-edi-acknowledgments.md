---
title: 使用 EDI 确认的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a769a78e-8a49-4aa4-899e-e9f54fdd5f37
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9768bffc83589ae826a9110d994b19b83cdb3fbb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380830"
---
# <a name="known-issues-with-edi-acknowledgments"></a>EDI 确认的已知的问题
本主题介绍在 EDI 确认的已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
## <a name="ak102-in-a-997-acknowledgment-can-be-negative"></a>997 确认中的 AK102 可以是负数  
 AK102 数据元素 （组控制编号） 在 X12 997 确认可以是负值。 带有负值 AK102 数据元素的确认将通过执行验证[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，即使为负值的组控制编号没有意义。  
  
## <a name="a-contrl-receipt-may-report-a-status-of-accepted-when-part-of-the-message-is-rejected"></a>CONTRL 回执仍可能报告的状态消息的一部分被拒绝时接受  
 仅当传入的 EDIFACT 消息重复或信封 （例如，问题的字符集） 中有错误时，CONTRL 回执 （EDIFACT 技术确认） 报告的状态为"已拒绝"。 EDIFACT 不在 CONTRL 技术确认中报告的状态为"已接受交换但出现错误"，如 X12 在 TA1 确认的 TA104 字段中作用。 如果接受 EDIFACT 消息的一部分，CONTRL 技术确认将报告"已接受"。 在某些情况下，将被拒绝消息的一部分，但 CONTRL 确认仍将报告的状态为"已接受"。 在这种情况下，UCI5 元素可能报告错误。  
  
## <a name="x12-acknowledgments-will-show-accepted-for-a-preserved-interchange-suspend-interchange-on-error-when-a-group-header-or-trailer-is-in-error"></a>X12 确认将显示已接受的针对保留交换 （挂起交换错误） 时组标头或尾部处于错误  
 如果入站的批处理选项 X12 消息是设置为"保留交换-出错时挂起交换"和组标头或尾部中的字段无效，将为已接受 TA1 和 997 确认中报告状态。 EDI 状态报告和事务集详细信息也将指示已接受状态。 即使交换将挂起，并且在事件查看器中的出现错误，将指示交换已挂起，将发生这种情况。  
  
 TA1 确认将显示的状态为已接受，因为它用于验证 ISA 标头和 IEA 尾部的正确性，而不是 GS 标头和 GE 尾部的正确性。 但是，997 确认也将显示已接受状态。  
  
## <a name="if-groups-in-an-interchange-have-the-same-name-the-status-report-will-show-twice-as-many-acknowledgments"></a>如果交换中的组具有相同的名称，在状态报告将显示两次确认  
 如果 BizTalk Server 处理 EDI 交换与具有相同名称的多个组，EDI 交换和相关 ACK 状态报表将按预期方式列出功能确认数两倍。 例如，如果交换中的两个组具有相同的名称，在状态报告将列出四个确认，而不是两个。  
  
## <a name="see-also"></a>请参阅  
 [EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md)   
 [发送 EDI 确认](../core/sending-an-edi-acknowledgment.md)   
 [处理收到的确认](../core/processing-a-received-acknowledgment.md)   
 [配置 EDI 确认](../core/configuring-edi-acknowledgments.md)
---
title: AS2 消息和相关的 MDN 状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48ed0ee3-c844-4cb9-a84d-32b719ab8fab
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49bdfbc54ffa393733e8622226eab0b2652634b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358907"
---
# <a name="as2-message-and-correlated-mdn-status-report"></a>AS2 消息和相关的 MDN 状态报告
此报表显示所有由 AS2 处理的 AS2 消息发送和接收管道，以及与这些交换相关的 Mdn。  
  
## <a name="fields-in-the-status-report"></a>在状态报告中的字段  
 AS2 消息和相关 ACK 状态报告显示这些接收或发送交换和相关确认的以下信息：  
  
-   发送方的参与方名称  
  
-   接收方的参与方名称  
  
-   As2 发件人  
  
-   AS2 收件人  
  
-   AS2 消息 ID  
  
-   AS2 消息日期时间  
  
-   接收的日期时间  
  
-   参与方角色  
  
-   MDN 状态  
  
-   加密状态  
  
-   签名状态  
  
-   Edi 交换状态  
  
-   AS2 消息重复  
  
-   检查重复的天数  
  
-   Filename  
  
-   启用可靠消息传送  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>在状态报告的查询表达式中的字段  
 可以通过更改用于确定所显示数据的查询表达式中的字段来自定义 AS2 消息和相关 ACK 状态报告。 可以使用下列域：  
  
|||||  
|-|-|-|-|  
|查询表达式字段|可能的运算符|可能的值|默认情况下包含？|  
|搜索|等于|AS2/MDN 状态|是（必需）|  
|消息状态|等于<br /><br /> 不等于|All<br /><br /> 已确认-已处理<br /><br /> 已确认-失败<br /><br /> 已处理-MDN 挂起<br /><br /> 已处理-非预期的 MDN<br /><br /> 未确认 – 超过重新发送尝试次数<br /><br /> 未确认 – 重新发送持续时间超过|是|  
|AS2 消息日期时间|小于或等于<br /><br /> 大于或等于|特定日期时间<br /><br /> 今天<br /><br /> Today-1|是<br /><br /> 注意：可以包含多个查询表达式中。|  
|最大匹配数|等于|整数 （默认值为 50）|是|  
|AS2 消息 ID|等于|All<br /><br /> 特定的 AS2 消息 ID|否|  
|Direction|等于|所有 （默认值）<br /><br /> Receive<br /><br /> Send|否|  
|接收方的参与方名称|等于|所有 （默认值）<br /><br /> 特定参与方名称|否|  
|发送方的参与方名称|等于|所有 （默认值）<br /><br /> 特定参与方名称|否|  
  
## <a name="additional-as2-message-and-correlated-mdn-status-reports"></a>其他 AS2 消息和相关的 MDN 状态报告  
 如果右键单击 AS2 消息和相关 MDN 状态报告中列出的 AS2 消息，则可以显示一个详细的以下状态报告：  
  
|状态报告|显示状态|  
|-------------------|----------------------|  
|交换 /ACK 状态|AS2 消息的 EDI 负载的状态|  
|重新发送状态详细信息|该消息重新发送状态|  
|消息传输格式|AS2 消息传输格式|  
|解码的消息|AS2 消息解码的格式|  
|MDN 消息|与 AS2 消息相关的 MDN 消息|  
  
 每个最终的三个消息的格式是相同的。 有关详细信息，请参阅[AS2 消息内容状态报告](../core/as2-message-content-status-reports.md)。  
  
## <a name="correlate-an-as2-message-with-its-edi-payload"></a>将 AS2 消息与其 EDI 负载相关联  
 AS2 和 EDI 状态报告，可将 AS2 消息与其 EDI 负载的状态条目相关联。 如果已启用 AS2 和 EDI 状态报告，AS2 消息在 AS2 状态报告中建立了一个状态条目，并且该 AS2 消息的 EDI 负载在 EDI 状态报告中建立了一个状态条目。 如果必须显示在 AS2 状态报告，则可以通过右键单击 AS2 消息状态条目，然后单击显示的 EDI 负载的 AS2 消息的状态**交换 /ACK 状态**。 如果 AS2 消息中只有一个 EDI 交换，此操作将显示为该交换的状态条目。  
  
 如果 AS2 消息包含多个 EDI 交换，并且您尝试显示 AS2 消息中的多个 EDI 交换的状态，则将在交换 /ACK 状态报告中显示仅最后一个 EDI 交换。 此外， **EDI 交换控制编号**AS2/MDN 状态报告中的字段将只显示最后一个交换控制编号。 （交换控制编号关联 AS2 消息与其 EDI 交换负载。）  
  
 AS2 消息中的所有 EDI 交换的数据保存在状态报告数据库。 如果在交换 /ACK 状态报告中的 AS2 消息中显示的所有交换**控制 ID 等于全部**子句位于状态报告查询。 这还可能显示不在 AS2 消息中; 中的其他交换但是，可以确定哪些 EDI 交换中一条 AS2 消息是通过查看其他字段，例如发送方、 接收方和交换日期时间。  
  
 **参与方角色**AS2 状态报告中的字段和**方向**EDI 状态报告中字段的意义是相反。 带有 EDI 负载的传入 AS2 消息**参与方角色**字段为 AS2 消息**发件人**，而**方向**字段为 EDI 交换**接收**。 这样做的原因是从参与方接收的传入消息，该参与方的角色是发送方。 该参与方的属性与它发送是作为 AS2 消息发送方的参与方定义在合作伙伴协议管理中的 AS2 属性对话框中的 AS2 消息。 因此，AS2 参与方角色是与 EDI 方向相反。  
  
## <a name="next-steps"></a>后续步骤
  
-   [AS2 消息内容状态报告](../core/as2-message-content-status-reports.md)  
  
-   [重新发送状态详细信息报告](../core/resend-status-details-report.md)  
  
## <a name="see-also"></a>请参阅  
 [AS2 消息和相关 MDN 状态报告](../core/as2-message-and-correlated-mdn-status-report.md)   

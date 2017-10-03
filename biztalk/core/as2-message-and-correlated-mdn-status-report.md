---
title: "AS2 消息和相关的 MDN 状态报告 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48ed0ee3-c844-4cb9-a84d-32b719ab8fab
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ce4aed138f4e32e87cb1d428050999cc2b764a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="as2-message-and-correlated-mdn-status-report"></a>AS2 消息和相关的 MDN 状态报表
此报告显示了 AS2 发送管道和接收管道处理的所有 AS2 消息以及与相应交换有关的 MDN。  
  
## <a name="fields-in-the-status-report"></a>状态报告中的字段  
 AS2 消息和相关的 ACK 状态报告显示了下列与已接收或已发送交换以及与这些交换相关的确认有关的信息：  
  
-   发送方名称  
  
-   接收方参与方名称  
  
-   AS2 发件人  
  
-   AS2 收件人  
  
-   AS2 消息 ID  
  
-   AS2 消息日期时间  
  
-   接收日期时间  
  
-   参与方角色  
  
-   MDN 状态  
  
-   加密状态  
  
-   签名状态  
  
-   Edi 交换状态  
  
-   是重复的 AS2 消息  
  
-   检查重复的天数  
  
-   Filename  
  
-   启用可靠消息传送  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>状态报告的查询表达式中的字段  
 您可以通过更改查询表达式中用于确定所显示数据的字段来自定义 AS2 消息和相关的 ACK 状态报告。 下列字段可用：  
  
|||||  
|-|-|-|-|  
|查询表达式字段|可能的运算符|可能的值|默认情况下是否包括？|  
|搜索|等于|AS2/MDN 状态|是（必需）|  
|消息状态|等于<br /><br /> 不等于|全部<br /><br /> 已确认 - 已处理<br /><br /> 已确认 - 失败<br /><br /> 已处理 - MDN 挂起<br /><br /> 已处理 - 非预期的 MDN<br /><br /> 未确认 – 超过重新发送尝试次数<br /><br /> 未确认 – 超过重新发送持续时间|是|  
|AS2 消息日期时间|小于或等于<br /><br /> 大于或等于|特定日期时间<br /><br /> 今天<br /><br /> Today-1|是<br /><br /> 注意：可在查询表达式中多次使用。|  
|最大匹配数|等于|整数（默认值为 50）|是|  
|AS2 消息 ID|等于|全部<br /><br /> 特定的 AS2 消息 ID|是|  
|方向|等于|所有 （默认值）<br /><br /> Receive<br /><br /> Send|是|  
|接收方参与方名称|等于|所有 （默认值）<br /><br /> 特定参与方名称|是|  
|发送方名称|等于|所有 （默认值）<br /><br /> 特定参与方名称|是|  
  
## <a name="additional-as2-message-and-correlated-mdn-status-reports"></a>其他 AS2 消息和相关 MDN 状态报告  
 如果右键单击 AS2 消息和相关 MDN 状态报告中列出的 AS2 消息，则可以显示下列其中一种更详细的状态报告：  
  
|状态报表|显示的状态|  
|-------------------|----------------------|  
|交换/ACK 状态|AS2 消息的 EDI 负载的状态|  
|重新发送状态详细信息|消息的重新发送状态|  
|消息传输格式|AS2 消息的传输格式|  
|解码的消息|AS2 消息的解码格式|  
|MDN 消息|与 AS2 消息相关的 MDN 消息|  
  
 最后三个消息中的每个消息格式都相同。 有关详细信息，请参阅[AS2 消息内容状态报表](../core/as2-message-content-status-reports.md)。  
  
## <a name="correlate-an-as2-message-with-its-edi-payload"></a>关联 AS2 消息具有其 EDI 负载  
 利用 AS2 和 EDI 状态报告，您可以将 AS2 消息的状态条目与其 EDI 负载的状态条目相关联。 如果已启用 AS2 和 EDI 状态报告，则在 AS2 状态报告中为 AS2 消息生成一个状态条目并在 EDI 状态报告中为该 AS2 消息的 EDI 负载生成一个状态条目。 如果你有显示 AS2 状态报表，你可以通过右键单击 AS2 消息状态条目，然后单击显示的 AS2 消息的 EDI 负载状态**交换/ACK 状态**。 如果 AS2 消息中只有一个 EDI 交换，此操作将为该交换调出状态条目。  
  
 如果此 AS2 消息包含多个 EDI 交换，并且您试图显示该 AS2 消息中多个 EDI 交换的状态，则在交换/ACK 状态报告中将只显示最后一个 EDI 交换。 此外， **EDI 交换控制否**AS2/MDN 状态报告中的字段将仅显示最后一个的交换控制编号。 （该交换控制编号将 AS2 消息与其 EDI 交换负载关联起来。）  
  
 AS2 消息中所有 EDI 交换的数据都保存在状态报告数据库中。 你可以在交换/ACK 状态报表采用的 AS2 消息中显示所有的交换，如果**控件 ID 等于所有**子句是状态报表查询中。 这还可能显示不属于 AS2 消息的其他交换；但是，通过查看其他字段（如“发送方”、“接收方”和“交换日期时间”），您可以确定 AS2 消息中有哪些 EDI 交换。  
  
 **方角色**AS2 状态报表中的字段和**方向**EDI 状态报表字段是相反的意义。 使用 EDI 负载，传入 AS2 消息的**方角色**字段将 AS2 消息**发件人**，虽然**方向**字段 EDI 交换将**接收**。 其原因在于对于从参与方接收的传入消息来说，参与方的角色是发送方。 与其所发送的 AS2 消息相关的参与方的属性是作为 AS2 消息发送方的参与方的属性，它是在“合作伙伴协议管理器”的“AS2 属性”对话框中定义的。 因此，AS2 参与方角色与 EDI 方向的含义相反。  
  
## <a name="next-steps"></a>后续步骤
  
-   [AS2 消息内容状态报表](../core/as2-message-content-status-reports.md)  
  
-   [重新发送状态详细信息报表](../core/resend-status-details-report.md)  
  
## <a name="see-also"></a>另请参阅  
 [AS2 消息和相关的 MDN 状态报表](../core/as2-message-and-correlated-mdn-status-report.md)   

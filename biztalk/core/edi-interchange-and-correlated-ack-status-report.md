---
title: "EDI 交换和关联的 ACK 状态报表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a112cc3d-d34c-4652-a8ee-3355a31d4a03
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd5f4268badf9907eb90b090abe34a8355b3ab8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-interchange-and-correlated-ack-status-report"></a>EDI 交换和相关 ACK 状态报告
此报告显示由 EDI 发送管道和接收管道处理的所有 EDI 交换，以及与这些交换相关的确认。  
  
## <a name="fields-in-the-status-report"></a>状态报告中的字段  
 EDI 交换和相关 ACK 状态报告将显示有关接收或发送交换及其相关确认的以下信息：  
  
-   发件人方  
  
    > [!NOTE]
    >  发送方的确定原则如下：  
    >   
    >  -   如果交换中的参与方名称与在 EDI 属性中为某个参与方配置的名称相匹配，则将显示配置的名称。  
    > -   如果交换中的参与方名称不与任何配置的现有参与方的 EDI 属性匹配，则将显示交换中所指定的参与方名称。  
  
-   接收方  
  
    > [!NOTE]
    >  接收方名称的确定原则如下：  
    >   
    >  -   如果交换中的参与方名称与在 EDI 属性中为某个参与方配置的名称相匹配，则将显示配置的名称。  
    > -   如果交换中的参与方名称不与任何配置的现有参与方的 EDI 属性匹配，则将显示交换中所指定的参与方名称。  
  
-   控件 ID  
  
-   方向  
  
-   交换日期时间  
  
-   EDI 编码类型  
  
-   交换状态  
  
-   组计数  
  
-   端口 ID  
  
-   发件人方别名  
  
-   接收方方别名  
  
-   事务集相关 ID  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>状态报告的查询表达式中的字段  
 您可更改用于确定所显示数据的查询表达式中的字段来自定义 EDI 交换及相关 ACK 状态报告。 下列字段可用：  
  
|||||  
|-|-|-|-|  
|查询表达式字段|可能的运算符|可能的值|默认情况下是否包括？|  
|搜索|等于|交换/ACK 状态|是（必需）|  
|状态|等于<br /><br /> 不等于|已接受<br /><br /> 已接受但存在错误<br /><br /> 已发送<br /><br /> 全部<br /><br /> 预期的确认<br /><br /> 非预期的确认<br /><br /> 已拒绝<br /><br /> （这些值定义如下。）|是|  
|交换日期时间|小于或等于<br /><br /> 大于或等于|特定日期时间<br /><br /> 今天<br /><br /> Today-1|是<br /><br /> 注意：可在查询表达式中多次使用。|  
|最大匹配数|等于|整数（默认值为 50）|是|  
|控件 ID|等于|交换控制 ID|是|  
|方向|等于|所有 （默认值）<br /><br /> Receive<br /><br /> Send|是|  
|接收方|等于|所有 （默认值）<br /><br /> 特定参与方名称|是|  
|发件人方|等于|所有 （默认值）<br /><br /> 特定参与方名称|是|  
  
## <a name="status-definitions"></a>状态定义  
 EDI 状态报告中使用的状态值具有以下定义：  
  
-   已接受：交换有效  
  
-   已接受但存在错误：错误记录在段中  
  
-   已发送：交换已成功发送  
  
-   全部：显示针对任何其他值的消息  
  
-   预期的确认  
  
    > [!NOTE]
    >  对于一个出站消息，当发送该消息时，如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 期望收到技术确认，则“交换状态和确认详细信息”状态报告中的“交换状态”字段将设置为“预期的确认”。 如果发生这种情况**预期的 TA1**属性在中设置**确认**单向协议选项卡页。已收到并验证技术确认后，状态将更改为“已接受”。 请注意，只有技术确定才会出现此情况，而功能确认则不会。  
  
-   非预期的确认  
  
-   已拒绝：由于出现错误，交换无效。  
  
## <a name="additional-reports-displayed-from-this-report"></a>此报告中显示的其他报告  
 对于在“事务集详细信息”报告中显示的事务集，可以显示以下其他状态报告。 通过右键单击“EDI 交换和相关 ACK 状态”报告中所列出的交换或确认，然后单击相应的命令，可以查看以下报告：  
  
-   [交换状态和 ACK 的详细信息状态报表](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [事务集详细信息状态报告](../core/transaction-set-details-status-report.md)  
  
## <a name="next-steps"></a>后续步骤
  
-   [交换状态和 ACK 的详细信息状态报表](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [事务集详细信息状态报告](../core/transaction-set-details-status-report.md)  
  
-   [EDI 消息内容状态报表](../core/edi-message-content-status-report.md)  
  

---
title: EDI 交换和相关的 ACK 状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a112cc3d-d34c-4652-a8ee-3355a31d4a03
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c7a1246da341cc984995b2222681cb8164919e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350625"
---
# <a name="edi-interchange-and-correlated-ack-status-report"></a>EDI 交换和相关 ACK 状态报告
此报表显示所有 EDI 交换的 edi 处理发送和接收管道，以及与这些交换相关的确认。  
  
## <a name="fields-in-the-status-report"></a>在状态报告中的字段  
 EDI 交换和相关 ACK 状态报告显示这些接收或发送交换和相关确认的以下信息：  
  
- 发送方  
  
  > [!NOTE]
  >  发送方将按如下所示确定：  
  > 
  > - 如果交换中的参与方名称与参与方 EDI 属性中配置的名称相匹配，则会显示配置的名称。  
  >   -   如果交换中的参与方名称不匹配任何已配置的 EDI 属性的现有参与方，则会显示在交换中指定的参与方名称。  
  
- 接收方  
  
  > [!NOTE]
  >  接收方的参与方名称将按如下所示确定：  
  > 
  > - 如果交换中的参与方名称与参与方 EDI 属性中配置的名称相匹配，则会显示配置的名称。  
  >   -   如果交换中的参与方名称不匹配任何已配置的 EDI 属性的现有参与方，则会显示在交换中指定的参与方名称。  
  
- 控件 ID  
  
- Direction  
  
- 交换日期时间  
  
- EDI 编码类型  
  
- 交换状态  
  
- 组计数  
  
- 端口 ID  
  
- 发送方的参与方别名  
  
- 接收方的参与方别名  
  
- 事务集相关 ID  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>在状态报告的查询表达式中的字段  
 可以通过更改用于确定所显示数据的查询表达式中的字段来自定义 EDI 交换和相关 ACK 状态报告。 可以使用下列域：  
  
|||||  
|-|-|-|-|  
|查询表达式字段|可能的运算符|可能的值|默认情况下包含？|  
|搜索|等于|交换 /ACK 状态|是（必需）|  
|“登录属性”|等于<br /><br /> 不等于|接受<br /><br /> 已接受但有错误<br /><br /> 发送<br /><br /> All<br /><br /> 预期的确认<br /><br /> 非预期的确认<br /><br /> 已拒绝<br /><br /> （这些值定义如下。）|是|  
|交换日期时间|小于或等于<br /><br /> 大于或等于|特定日期时间<br /><br /> 今天<br /><br /> Today-1|是<br /><br /> 注意：可以包含多个查询表达式中。|  
|最大匹配数|等于|整数 （默认值为 50）|是|  
|控件 ID|等于|交换控制 ID|否|  
|Direction|等于|所有 （默认值）<br /><br /> Receive<br /><br /> Send|否|  
|接收方|等于|所有 （默认值）<br /><br /> 特定参与方名称|否|  
|发送方|等于|所有 （默认值）<br /><br /> 特定参与方名称|否|  
  
## <a name="status-definitions"></a>状态定义  
 使用 EDI 状态报告中的状态值具有以下定义：  
  
- 已接受：交换有效  
  
- 已接受但有错误：错误记录在段  
  
- 发送：已成功发送该交换  
  
- 所有：显示一条消息与任何其他值  
  
- 预期的确认  
  
  > [!NOTE]
  >  交换状态和确认详细信息状态报告中的交换状态字段将设置为"预期的确认"为出站消息时将消息发送如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要求技术确认。 如果发生这种情况**预期的 TA1**属性中设置**确认**页的单向协议选项卡。当收到并验证技术确认时，状态将更改为"已接受"。 请注意这只是个技术确认，而不进行功能确认。  
  
- 非预期的确认  
  
- 已拒绝：由于出现错误，交换无效。  
  
## <a name="additional-reports-displayed-from-this-report"></a>此报告中显示的其他报表  
 可以显示以下其他状态报告事务集报告中显示的事务集详细信息。 通过右键单击的交换或确认列出在 EDI 交换和相关 ACK 状态报告中，然后单击相应的命令访问报告：  
  
-   [“交换状态和 ACK 详细信息”状态报告](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [事务集详细信息状态报告](../core/transaction-set-details-status-report.md)  
  
## <a name="next-steps"></a>后续步骤
  
-   [“交换状态和 ACK 详细信息”状态报告](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [事务集详细信息状态报告](../core/transaction-set-details-status-report.md)  
  
-   [EDI 消息内容状态报告](../core/edi-message-content-status-report.md)  
  

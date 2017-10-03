---
title: "事务集详细信息状态报告 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d81367c7-c74e-42cb-b856-748962b727ec
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6da167ea995fa05d8e35807d8cf26f23b5444a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transaction-set-details-status-report"></a>事务集详细信息状态报告
该报告显示从“交换/ACK 状态”报告内部选择的特定 EDI 交换中的事务集的详细信息。 要显示此状态报表，请右键单击交换/ACK 状态报表中，查询结果窗格中列出的交换，然后单击**设置事务的详细信息**。  
  
 此报表才可用，仅当你选择**存储事务的一组负载，可用于报告**相关方的 EDI 属性对话框的常规页中的属性。  
  
## <a name="fields-in-the-status-report"></a>状态报告中的字段  
 事务集详细信息状态报告显示已接收或已发送交换中的事务集的以下信息：  
  
-   事务集 ID  
  
-   文档类型  
  
-   发件人方别名  
  
-   应用程序发送方  
  
-   接收方方别名  
  
-   应用程序接收方  
  
-   方向  
  
-   交换控制编号  
  
-   组控制编号  
  
-   事务集控制编号  
  
-   事务集状态  
  
-   交换日期时间（默认情况下不显示）  
  
    > [!NOTE]
    >  对于收到的文档，如果在交换中指定的日期格式为 YYMMDD 且 YY 大于等于 75，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将年份显示为 19YY。 如果日期中的 YY 小于 75，将显示为 20YY。  
    >   
    >  例如，如果你在 ISA09 中收到包含值 991113 的交换，则报告中将列出交换日期时间为 11/13/1999。  
  
-   处理日期/时间（默认情况下不显示）  
  
-   组日期/时间（默认情况下不显示）  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>状态报告的查询表达式中的字段  
 您可更改用于确定所显示数据的查询表达式中的字段来自定义 EDI 交换及相关 ACK 状态报告。 下列字段可用：  
  
|||||  
|-|-|-|-|  
|查询表达式字段|可能的运算符|可能的值|默认情况下是否包括？|  
|搜索|等于|事务集详细信息|是（必需）|  
|交换日期时间|小于或等于<br /><br /> 大于或等于|特定日期时间<br /><br /> 今天<br /><br /> Today-1|是<br /><br /> 注意：可在查询表达式中多次使用。|  
|接收方参与方名称|等于|所有 （默认值）<br /><br /> 特定参与方名称|是|  
|发送方名称|等于|所有 （默认值）<br /><br /> 特定参与方名称|是|  
|方向|等于|所有 （默认值）<br /><br /> Receive<br /><br /> Send|是|  
|控件 ID|等于|交换控制 ID|是|  
|事务集相关 ID|等于|相关性 ID|是|  
|最大匹配数|等于|整数（默认值为 50）|是|  
|状态|等于<br /><br /> 不等于|已接受<br /><br /> 已接受但存在错误<br /><br /> 已发送<br /><br /> 全部<br /><br /> 预期的确认<br /><br /> 非预期的确认<br /><br /> 已拒绝|是|  
|事务集 ID|等于|事务集 ID|是|  
  
## <a name="additional-reports-displayed-from-this-report"></a>此报告中显示的其他报告  
 对于在“事务集详细信息”报告中显示的事务集，可以显示以下其他状态报告：  
  
-   消息内容状态报告。 右键单击详细信息报告中的事务集，再单击“查看事务集内容”可访问此报告。 有关详细信息，请参阅[EDI 消息内容状态报告](../core/edi-message-content-status-report.md)。  
  
-   交换/ACK 状态报告 此报表使用相同的用户界面[EDI 交换和关联 ACK 状态报表](../core/edi-interchange-and-correlated-ack-status-report.md)显示为多个的交换。 区别在于此报告数据仅适用于包含此事务集的交换。  
  

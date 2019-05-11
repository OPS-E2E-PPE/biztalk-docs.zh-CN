---
title: 事务集详细信息状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d81367c7-c74e-42cb-b856-748962b727ec
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf94c5d39bcf304bfb2942d957f1c30d2e365571
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279735"
---
# <a name="transaction-set-details-status-report"></a>事务集详细信息状态报告
此报表显示在交换 /ACK 状态报告中从选择的特定 EDI 交换中事务集的详细信息。 若要显示此状态报告中，右键单击交换 /ACK 状态报表中，在查询结果窗格中列出的交换，然后依次**事务集详细信息**。  
  
 此报表才可用，仅当你选择**存储事务集/负载以用于报告**相关参与方 EDI 属性对话框的常规页中的属性。  
  
## <a name="fields-in-the-status-report"></a>在状态报告中的字段  
 事务的以下信息中设置该事务集详细信息状态报告显示已接收或发送的交换：  
  
- 事务集 ID  
  
- 文档类型  
  
- 发送方别名  
  
- 应用程序发送方  
  
- 接收方别名  
  
- 应用程序接收方  
  
- Direction  
  
- 交换控制编号  
  
- 组控制编号  
  
- 事务集控制编号  
  
- 事务集状态  
  
- 交换日期时间 （默认情况下不显示）  
  
  > [!NOTE]
  >  对于收到的文档，如果交换中指定的日期格式为 YYMMDD 且 YY 大于或等于 75，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会将年份显示为 19YY。 如果日期是小于 75，将显示为 20YY。  
  > 
  >  例如，如果收到包含在 ISA09 中的值 991113 的交换，交换日期时间将会报告中列出为 1999 年 11/13。  
  
- 处理日期/时间 （默认情况下不显示）  
  
- 组日期/时间 （默认情况下不显示）  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>在状态报告的查询表达式中的字段  
 可以通过更改用于确定所显示数据的查询表达式中的字段来自定义 EDI 交换和相关 ACK 状态报告。 可以使用下列域：  
  
|||||  
|-|-|-|-|  
|查询表达式字段|可能的运算符|可能的值|默认情况下包含？|  
|搜索|等于|事务集详细信息|是（必需）|  
|交换日期时间|小于或等于<br /><br /> 大于或等于|特定日期时间<br /><br /> 今天<br /><br /> Today-1|是<br /><br /> 注意：可以包含多个查询表达式中。|  
|接收方的参与方名称|等于|所有 （默认值）<br /><br /> 特定参与方名称|是|  
|发送方的参与方名称|等于|所有 （默认值）<br /><br /> 特定参与方名称|是|  
|Direction|等于|所有 （默认值）<br /><br /> Receive<br /><br /> Send|是|  
|控件 ID|等于|交换控制 ID|是|  
|事务集相关 Id|等于|相关 Id|是|  
|最大匹配数|等于|整数 （默认值为 50）|是|  
|“登录属性”|等于<br /><br /> 不等于|接受<br /><br /> 已接受但有错误<br /><br /> 发送<br /><br /> All<br /><br /> 预期的确认<br /><br /> 非预期的确认<br /><br /> 已拒绝|否|  
|事务集 Id|等于|事务集 Id|否|  
  
## <a name="additional-reports-displayed-from-this-report"></a>此报告中显示的其他报表  
 可以显示以下其他状态报告事务集报告中显示的事务集详细信息：  
  
-   消息内容状态报告。 通过右键单击事务集详细信息报告中，然后单击查看事务集内容，可以访问此报表。 有关详细信息，请参阅[EDI 消息内容状态报告](../core/edi-message-content-status-report.md)。  
  
-   交换 /ACK 状态报告。 此报表使用相同的用户界面[EDI 交换和相关 ACK 状态报告](../core/edi-interchange-and-correlated-ack-status-report.md)显示多个交换。 不同之处在于此报表数据的交换，其中包含此事务设置。  
  

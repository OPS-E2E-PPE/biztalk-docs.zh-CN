---
title: 交换聚合报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4619e8d0-9e9e-4d19-a67a-ac1058a0579b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df8163506f3b71379038e8beb82bc8f9f2297249
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381950"
---
# <a name="interchange-aggregation-report"></a>交换聚合报告
此报表提供了一条记录，用于指示共享同一 EDI 编码类型、 发送方、 接收方和方向的 EDI 交换。 此报表不提供有关单个交换的详细信息。  
  
 通过单击中的组中心页底部的交换聚合报告链接可显示此状态报告[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="fields-in-the-status-report"></a>在状态报告中的字段  
 交换聚合报告显示每个记录的以下信息：  
  
- 交换计数共享同一 EDI 编码类型、 发送方、 接收方和方向  
  
- 记录中每个交换的发送方参与方  
  
- 记录中每个交换的接收方参与方  
  
- 方向 （接收或发送） 的记录中每个交换  
  
- 日期和时间的最早时间范围内发送或接收交换 （最早开始日期/时间）  
  
  > [!NOTE]
  >  对于收到的文档，如果交换中指定的日期格式为 YYMMDD 且 YY 大于或等于 75，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会将年份显示为 19YY。 如果日期是小于 75，将显示为 20YY。  
  > 
  >  例如，如果您收到的交换包含值 991113 在 ISA09，最早开始日期/时间将为 1999 年 11/13/报告中列出。  
  
- 日期和时间的最新时间范围内发送或接收交换 （最新结束日期/时间）  
  
- EDI 编码类型的记录中每个交换  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>在状态报告的查询表达式中的字段  
 您可以更改用于确定所显示数据的查询表达式中的字段来自定义交换聚合报告。 可以使用下列域：  
  
|||||  
|-|-|-|-|  
|查询表达式字段|可能的运算符|可能的值|默认情况下包含？|  
|搜索|等于|交换聚合报告|是（必需）|  
|交换日期时间|小于或等于<br /><br /> 大于或等于|特定日期时间<br /><br /> 今天<br /><br /> Today-1|是<br /><br /> 注意：可以包含在查询表达式中，一次用于小于两次-运算符，一次用于大于-运算符，以提供一个范围。|  
|最大匹配数|等于|整数 （默认值为 50）|是|  
|Direction|等于|所有 （默认值）<br /><br /> Receive<br /><br /> Send|否|  
|接收方的参与方名称|等于|所有 （默认值）<br /><br /> 特定参与方名称 （字符串）|否|  
|发送方的参与方名称|等于|所有 （默认值）<br /><br /> 特定参与方名称 （字符串）|否|  
|“登录属性”|等于<br /><br /> 不等于|接受<br /><br /> 已接受但有错误<br /><br /> 发送<br /><br /> All<br /><br /> 预期的确认<br /><br /> 非预期的确认<br /><br /> 已拒绝|否|
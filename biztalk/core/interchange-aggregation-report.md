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
ms.openlocfilehash: 578747267c73c4428e28eefd8b07ba51e8196fed
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977950"
---
# <a name="interchange-aggregation-report"></a>交换聚合报告
此报告中提供的一项记录指明了共享同一 EDI 编码类型、发送方、接收方和方向的 EDI 交换的数量。 此报告不提供有关单个交换的详细信息。  
  
 通过单击 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中“组中心”页底部的“交换聚合报告”链接可显示此状态报告。  
  
## <a name="fields-in-the-status-report"></a>状态报告中的字段  
 在交换聚合报告的每项记录中将显示如下信息：  
  
- 共享同一 EDI 编码类型、发送方、接收方和方向的交换的数量。  
  
- 记录中每个交换的发送方  
  
- 记录中每个交换的接收方  
  
- 记录中每个交换的方向（接收或发送）  
  
- 在时间范围内发送或接收最早交换的日期和时间（最早开始日期/时间）  
  
  > [!NOTE]
  >  对于收到的文档，如果在交换中指定的日期格式为 YYMMDD 且 YY 大于等于 75，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将年份显示为 19YY。 如果日期中的 YY 小于 75，将显示为 20YY。  
  > 
  >  例如，如果您收到的交换在 ISA09 中包含值 991113，则在报告中将“最早开始日期/时间”显示为 11/13/1999。  
  
- 在时间范围内发送或接收最晚交换的日期和时间（最晚结束日期/时间）  
  
- 记录中每个交换的 EDI 编码类型  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>状态报告的查询表达式中的字段  
 您可以通过更改用于确定所显示数据的查询表达式中的字段来自定义交换聚合报告。 下列字段可用：  
  
|||||  
|-|-|-|-|  
|查询表达式字段|可能的运算符|可能的值|默认情况下是否包括？|  
|搜索|等于|交换聚合报告|是（必需）|  
|交换日期时间|小于或等于<br /><br /> 大于或等于|特定日期时间<br /><br /> 今天<br /><br /> Today-1|是<br /><br /> 注意： 可以包含两次在查询表达式中，一次用于小于-运算符，一次用于大于-运算符，以提供一个范围。|  
|最大匹配数|等于|整数（默认值为 50）|是|  
|方向|等于|所有 （默认值）<br /><br /> Receive<br /><br /> Send|“否”|  
|接收方的参与方名称|等于|所有 （默认值）<br /><br /> 特定参与方名称（AN 字符串）|“否”|  
|发送方名称|等于|所有 （默认值）<br /><br /> 特定参与方名称（AN 字符串）|“否”|  
|“登录属性”|等于<br /><br /> 不等于|已接受<br /><br /> 已接受但存在错误<br /><br /> 已发送<br /><br /> All<br /><br /> 预期的确认<br /><br /> 非预期的确认<br /><br /> 已拒绝|“否”|
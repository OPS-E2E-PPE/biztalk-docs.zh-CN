---
title: 批处理状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04dad016-e7bb-45cd-b36a-a9c83d073501
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a717d35073ead8a15aaec47cdcbe85e41988107
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529169"
---
# <a name="batch-status-report"></a>批处理状态报告
此报告显示批处理业务流程实例的活动。 在报表中的每一行指示批处理业务流程的单个实例正在处理的批的状态。  
  
 保留批的状态中批处理状态报告中，将不报告，但在交换 /ACK 状态报告中报告。  
  
## <a name="fields-in-the-status-report"></a>在状态报告中的字段  
 批处理状态报告显示批处理交换的以下信息：  
  
-   批处理状态  
  
-   批处理名称  
  
-   目标参与方名称  
  
-   激活时间  
  
-   批处理出现次数计数  
  
-   EDI 编码类型  
  
-   批处理类型  
  
-   批处理目标  
  
-   批处理元素计数： 批处理元素的数量已累计的批处理业务流程实例  
  
-   被拒绝的元素计数  
  
-   最新的操作：可以是激活的批处理、 计划发布、 基于计数的发布、 手动覆盖发布、 批处理已终止/停止发布、 添加的元素或外部发布  
  
-   交换控制编号  
  
-   交换日期时间  
  
-   （默认情况下不显示） 的批大小 （以字符为单位）  
  
## <a name="view-related-interchanges-status-reports"></a>查看相关的交换状态报告  
 如果您右键单击的交换或确认批处理状态报告中列出，可以显示有关与批处理相关的交换的详细信息。  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>在状态报告的查询表达式中的字段  
 您可以更改用于确定所显示数据的查询表达式中的字段来自定义批处理状态报告。 可以使用下列域：  
  
|||||  
|-|-|-|-|  
|查询表达式字段|可能的运算符|可能的值|默认情况下包含？|  
|搜索|等于|批处理状态|是（必需）|  
|批处理状态|等于<br /><br /> 不等于|定义：配置了批实例但开始日期时间晚于当前日期时间。<br /><br /> 处于活动状态 （默认值）：批处理实例已配置且正在收集用于批处理的事务集。 开始日期时间是早于当前日期时间。<br /><br /> 发布日期：已满足发布条件，并已发送批，或处理任何消息前，停止批处理业务流程。<br /><br /> 已完成：发布条件已满足，但尚未发送批。<br /><br /> 所有：显示处于上述状态之一的任何批处理实例。|是|  
|最大匹配数|等于|整数 （默认值为 50）|是|  
|激活日期时间|小于或等于<br /><br /> 大于或等于|日期时间<br /><br /> 今天<br /><br /> Today-5|否<br /><br /> 注意：可以包含多个查询表达式中。|  
|批处理名称|等于|所有 （默认值）<br /><br /> 特定批处理名称|否|  
|目标参与方|等于|所有 （默认值）<br /><br /> 特定参与方名称|否|  
|EDI 编码类型|等于|X12<br /><br /> EDIFACT<br /><br /> 所有 （默认值）|否|  
  

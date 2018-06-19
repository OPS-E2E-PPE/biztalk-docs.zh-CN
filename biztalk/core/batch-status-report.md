---
title: 批处理状态报告 |Microsoft 文档
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
ms.openlocfilehash: 7c033f58432c8ae5a2d87b87b56223b8f64a7201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231797"
---
# <a name="batch-status-report"></a>批处理状态报告
此报告显示批处理业务流程实例的活动。 报告中的每行都指示出正在由一个批处理业务流程实例处理的批的状态。  
  
 保留批的状态不是在批处理状态报告中报告，而是在交换/确认状态报告中报告。  
  
## <a name="fields-in-the-status-report"></a>状态报告中的字段  
 批处理状态报告显示批处理交换的下列信息：  
  
-   批状态  
  
-   批名称  
  
-   目标方名称  
  
-   激活时间  
  
-   批处理出现次数计数  
  
-   EDI 编码类型  
  
-   批处理类型  
  
-   批处理目标  
  
-   批处理元素计数： 进行批处理的业务流程实例累积批处理元素数量  
  
-   被拒绝元素计数  
  
-   最新的操作： 可以是批处理激活、 计划的版本、 计数基于版本、 手动重写版本、 批处理已终止/停止版本、 添加元素，或外部的版本  
  
-   交换控制编号  
  
-   交换日期时间  
  
-   批大小（以字符数表示）（默认情况下不显示）  
  
## <a name="view-related-interchanges-status-reports"></a>查看相关交换状态报告  
 如果右键单击批处理状态报告中列出的交换或确认，则可以显示有关与批处理相关的交换的详细信息。  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a>状态报告的查询表达式中的字段  
 您可更改用于确定显示的数据的查询表达式中的字段来自定义批处理状态报告。 下列字段可用：  
  
|||||  
|-|-|-|-|  
|查询表达式字段|可能的运算符|可能的值|默认情况下是否包括？|  
|搜索|等于|批状态|是（必需）|  
|批状态|等于<br /><br /> 不等于|定义： 配置的批处理实例但开始日期时间晚于当前日期时间。<br /><br /> 活动 （默认值）： 批处理实例配置并且正在收集一批的事务集。 起始日期时间早于当前日期时间。<br /><br /> 发布日期： 已满足释放条件，并已发送的批，或批处理业务流程已停止之前已处理的任何消息。<br /><br /> 完成： 释放条件已满足，但尚未发送批处理。<br /><br /> All： 显示任何处于上述状态之一的批处理实例。|是|  
|最大匹配数|等于|整数（默认值为 50）|是|  
|激活日期时间|小于或等于<br /><br /> 大于或等于|日期时间<br /><br /> 今天<br /><br /> 今日 - 5|是<br /><br /> 注意：可在查询表达式中多次使用。|  
|批名称|等于|全部（默认值）<br /><br /> 特定批处理名称|是|  
|目标方|等于|所有 （默认值）<br /><br /> 特定参与方名称|是|  
|EDI 编码类型|等于|X12<br /><br /> EDIFACT<br /><br /> 所有 （默认值）|是|  
  

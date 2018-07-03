---
title: Windows Workflow Foundation 中的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a048dfc0-26b2-4f20-9d2f-c52f1ab19ac3
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 057154a2e64541b00c704be7078ef27ba596de20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007598"
---
# <a name="operations-in-windows-workflow-foundation"></a>Windows Workflow Foundation 中的操作
本部分包含 BAM WF 侦听器支持的自定义操作。  
  
## <a name="determining-where-operations-are-allowed"></a>确定允许操作  
 由 BAM WF 侦听器提供的自定义操作可按关联的 Windows Workflow Foundation 跟踪点类型进行分类：  
  
- 活动  
  
- 工作流  
  
- 用户  
  
  BAM WF 侦听器使用类别将分配给每个跟踪点类型**OnEvent**。 它的操作中发现的类型将根据此分配**OnEvent**筛选器和数据提取和处理部分。 例如，如果**OnEvent**包含**更新**使用的元素**GetUserData**操作，它是用户跟踪点类型，因为此操作的活动和工作流事件不支持此操作。 有关跟踪点的详细信息，请参阅 System.Workflow.Runtime.Tracking，网址[ http://go.microsoft.com/fwlink/?LinkId=80242 ](http://go.microsoft.com/fwlink/?LinkId=80242)。  
  
> [!NOTE]
>  工作流跟踪点无法从工作流提取数据。  
  
 操作在筛选器表达式中以及 `OnEvent` 元素中的筛选器表达式与数据提取和处理部分之间均必须兼容。 下表显示对于每个跟踪点类型可在筛选器表达式中使用哪些操作。  
  
|筛选器表达式运算|是否对活动跟踪点有效？|是否对工作流跟踪点有效？|是否对用户跟踪点有效？|  
|---------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|等于|是|是|是|  
|And|是|是|是|  
|连接|“否”|否|“否”|  
|常量|是|是|是|  
|GetActivityEvent|是|否|“否”|  
|GetActivityName|是|否|是|  
|GetActivityProperty|是|否|是|  
|GetActivityType|是|否|是|  
|GetContextProperty|“否”|否|“否”|  
|GetUserData|“否”|否|“否”|  
|GetUserDataType|“否”|否|是|  
|GetUserKey|“否”|否|是|  
|GetWorkflowEvent|“否”|是|“否”|  
|GetWorkflowProperty|“否”|否|“否”|  
  
 如果混合使用不兼容的操作，则会在部署侦听器配置文件时收到一个错误。 例如，如果同时使用这两者`GetActivityEvent`并`GetWorkflowEvent`筛选器，或通过在筛选器和数据提取或处理事件中 (如**CorrelationID**)，将收到错误。  
  
 下表总结了每个活动类型在数据提取或处理中支持的操作。  
  
|数据提取或处理操作|是否对活动跟踪点有效？|是否对工作流跟踪点有效？|是否对用户跟踪点有效？|  
|-----------------------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|等于|是|是|是|  
|And|是|是|是|  
|连接|是|是|是|  
|常量|是|是|是|  
|GetActivityEvent|是|否|“否”|  
|GetActivityName|是|否|是|  
|GetActivityProperty|是|否|是|  
|GetActivityType|是|否|是|  
|GetContextProperty|是|是|是|  
|GetUserData|“否”|否|是|  
|GetUserDataType|“否”|否|是|  
|GetUserKey|“否”|否|是|  
|GetWorkflowEvent|“否”|是|“否”|  
|GetWorkflowProperty|是|否|是|  
  
> [!NOTE]
>  没有单个之间的一对一映射**OnEvent**和单个跟踪点。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [GetActivityEvent](../core/getactivityevent.md)  
  
-   [GetActivityName](../core/getactivityname.md)  
  
-   [GetActivityProperty](../core/getactivityproperty.md)  
  
-   [GetActivityType](../core/getactivitytype.md)  
  
-   [GetContextProperty](../core/getcontextproperty2.md)  
  
-   [GetUserData](../core/getuserdata.md)  
  
-   [GetUserDataType](../core/getuserdatatype.md)  
  
-   [GetUserKey](../core/getuserkey.md)  
  
-   [GetWorkflowEvent](../core/getworkflowevent.md)  
  
-   [GetWorkflowProperty](../core/getworkflowproperty.md)  
  
## <a name="see-also"></a>请参阅  
 [BAM WF 侦听器](../core/bam-wf-interceptor.md)
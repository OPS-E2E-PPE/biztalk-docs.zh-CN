---
title: "Windows Workflow Foundation 中的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a048dfc0-26b2-4f20-9d2f-c52f1ab19ac3
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62cb1ba3cb82a21bb573145d00057112784c89a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-in-windows-workflow-foundation"></a>Windows Workflow Foundation 中的操作
本部分包含 BAM WF 侦听器支持的自定义操作。  
  
## <a name="determining-where-operations-are-allowed"></a>确定允许执行操作  
 由 BAM WF 侦听器提供的自定义操作可按关联的 Windows Workflow Foundation 跟踪点类型进行分类：  
  
-   活动  
  
-   工作流  
  
-   用户  
  
 BAM WF 侦听器使用类别来将跟踪点类型分配给每个**OnEvent**。 它将根据此分配的操作中它发现的类型上**OnEvent**筛选器和数据提取和操作部分。 例如，如果**OnEvent**包含**更新**用元素**GetUserData**操作，它是用户跟踪点类型，因为此操作的活动和工作流事件不支持此操作。 有关跟踪点的详细信息，请参阅在 System.Workflow.Runtime.Tracking [http://go.microsoft.com/fwlink/?LinkId=80242](http://go.microsoft.com/fwlink/?LinkId=80242)。  
  
> [!NOTE]
>  工作流跟踪点无法从工作流提取数据。  
  
 操作在筛选器表达式中以及 `OnEvent` 元素中的筛选器表达式与数据提取和处理部分之间均必须兼容。 下表显示对于每个跟踪点类型可在筛选器表达式中使用哪些操作。  
  
|筛选器表达式操作|是否对活动跟踪点有效？|是否对工作流跟踪点有效？|是否对用户跟踪点有效？|  
|---------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|等于|是|是|是|  
|And|是|是|是|  
|连接|是|“否”|是|  
|常量|是|是|是|  
|GetActivityEvent|是|“否”|是|  
|GetActivityName|是|“否”|是|  
|GetActivityProperty|是|“否”|是|  
|GetActivityType|是|“否”|是|  
|GetContextProperty|是|“否”|是|  
|GetUserData|是|“否”|是|  
|GetUserDataType|是|是|是|  
|GetUserKey|是|是|是|  
|GetWorkflowEvent|是|是|是|  
|GetWorkflowProperty|是|“否”|是|  
  
 如果混合使用不兼容的操作，则会在部署侦听器配置文件时收到一个错误。 例如，如果你同时使用`GetActivityEvent`和`GetWorkflowEvent`筛选器，或者在筛选器和数据提取或操作事件 (如**CorrelationID**)，你将收到一个错误。  
  
 下表总结了每个活动类型在数据提取或处理中支持的操作。  
  
|数据提取或处理操作|是否对活动跟踪点有效？|是否对工作流跟踪点有效？|是否对用户跟踪点有效？|  
|-----------------------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|等于|是|是|是|  
|And|是|是|是|  
|连接|是|是|是|  
|常量|是|是|是|  
|GetActivityEvent|是|“否”|是|  
|GetActivityName|是|“否”|是|  
|GetActivityProperty|是|“否”|是|  
|GetActivityType|是|“否”|是|  
|GetContextProperty|是|是|是|  
|GetUserData|是|是|是|  
|GetUserDataType|是|是|是|  
|GetUserKey|是|是|是|  
|GetWorkflowEvent|是|是|是|  
|GetWorkflowProperty|是|“否”|是|  
  
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
  
## <a name="see-also"></a>另请参阅  
 [BAM WF 拦截器](../core/bam-wf-interceptor.md)
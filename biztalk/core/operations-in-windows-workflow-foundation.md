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
ms.openlocfilehash: b602bfee7c2f57453243fb56bccd63183a45f543
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263025"
---
# <a name="operations-in-windows-workflow-foundation"></a>Windows Workflow Foundation 中的操作
本部分包含 BAM WF 侦听器支持的自定义操作。  
  
## <a name="determining-where-operations-are-allowed"></a>确定允许操作  
 BAM WF 侦听器提供的自定义操作可按关联的 Windows Workflow Foundation 跟踪点类型进行分类：  
  
- 活动  
  
- 工作流  
  
- “用户”  
  
  BAM WF 侦听器使用类别将分配给每个跟踪点类型**OnEvent**。 它的操作中发现的类型将根据此分配**OnEvent**筛选器和数据提取和处理部分。 例如，如果**OnEvent**包含**更新**使用的元素**GetUserData**操作，它是用户跟踪点类型，因为此操作的活动和工作流事件不支持此操作。 有关跟踪点的详细信息，请参阅 System.Workflow.Runtime.Tracking，网址[ http://go.microsoft.com/fwlink/?LinkId=80242 ](http://go.microsoft.com/fwlink/?LinkId=80242)。  
  
> [!NOTE]
>  工作流跟踪点无法从工作流中提取数据。  
  
 操作必须是中的筛选器表达式和筛选器表达式和数据提取和处理部分内的之间兼容`OnEvent`元素。 下表显示了哪些操作可在筛选器表达式中的每个跟踪点类型。  
  
|筛选器表达式运算|对活动跟踪点有效？|对工作流跟踪点有效？|对用户跟踪点有效？|  
|---------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|等于|是|是|是|  
|And|是|是|是|  
|连接|否|否|否|  
|常量|是|是|是|  
|GetActivityEvent|是|否|否|  
|GetActivityName|是|否|是|  
|GetActivityProperty|是|否|是|  
|GetActivityType|是|否|是|  
|GetContextProperty|否|否|否|  
|GetUserData|否|否|否|  
|GetUserDataType|否|否|是|  
|GetUserKey|否|否|是|  
|GetWorkflowEvent|否|是|否|  
|GetWorkflowProperty|否|否|否|  
  
 如果混合使用不兼容的操作，将收到错误，在部署侦听器配置文件时。 例如，如果同时使用这两者`GetActivityEvent`并`GetWorkflowEvent`筛选器，或通过在筛选器和数据提取或处理事件中 (如**CorrelationID**)，将收到错误。  
  
 下表总结了支持数据提取或处理中的每个活动类型的操作。  
  
|数据提取或处理操作|对活动跟踪点有效？|对工作流跟踪点有效？|对用户跟踪点有效？|  
|-----------------------------------------------|-------------------------------------|-------------------------------------|---------------------------------|  
|等于|是|是|是|  
|And|是|是|是|  
|连接|是|是|是|  
|常量|是|是|是|  
|GetActivityEvent|是|否|否|  
|GetActivityName|是|否|是|  
|GetActivityProperty|是|否|是|  
|GetActivityType|是|否|是|  
|GetContextProperty|是|是|是|  
|GetUserData|否|否|是|  
|GetUserDataType|否|否|是|  
|GetUserKey|否|否|是|  
|GetWorkflowEvent|否|是|否|  
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
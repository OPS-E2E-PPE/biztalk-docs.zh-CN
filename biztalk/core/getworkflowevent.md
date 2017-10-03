---
title: "GetWorkflowEvent |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2534e0b8-26df-4554-b0df-742014deb64d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8dc753bd45452af6ab586a11f216bc65f9539fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getworkflowevent"></a>GetWorkflowEvent
将当前工作流事件的名称推送到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetWorkflowEvent" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前工作流事件的字符串。  
  
## <a name="remarks"></a>注释  
 一个工作流实例在执行的过程中可以传递几个状态。 例如，工作流实例可能变为空闲状态，也可能处于挂起状态。 工作流实例每次更改状态时，会向运行时跟踪基础结构发出一个工作流状态事件。 Windows Workflow Foundation BAM 侦听器支持由定义的事件的大多数`System.Workflow.Runtime.Tracking.TrackingWorkflowEvent`枚举下, 表中所示。  
  
|活动事件|Description|  
|--------------------|-----------------|  
|已更改|工作流更改已经在工作流实例上发生。|  
|已完成|工作流实例已完成。|  
|创建时间|工作流实例已创建。|  
|异常|已出现未处理的异常。|  
|Idle|工作流实例处于空闲状态。|  
|Loaded|工作流实例已加载到内存中。|  
|Persisted|工作流实例已持久化。|  
|Resumed|以前挂起的工作流实例已恢复运行。|  
|Started|工作流实例已启动。|  
|已挂起|工作流实例已挂起。|  
|Terminated|工作流实例已终止。|  
|Unloaded|工作流实例已从内存中卸载。|  
  
> [!NOTE]
>  你不能同时使用`GetWorkflowEvent`和`GetActivityEvent`相同 OnEvent 元素中。  
  
## <a name="example"></a>示例  
 下面的示例包含一个配置为在工作流中查找特定活动（“FoodAndDrinksPolicy”）的筛选器。 在该示例中，一个筛选器配置为在关闭的工作流中查找名称为“FoodAndDrinksPolicy”的活动。 这是通过将 `GetWorkflowEvent` 返回的值与常量“Created”相比较来完成的。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowEvent" />   
      <ic:Operation Name="Constant">  
        <ic:Argument>Created</ic:Argument>   
      </ic:Operation>  
    <ic:Operation Name="Equals" />   
  </ic:Expression>  
</ic:Filter>  
```  
  
 对于跟踪工作流的生存期和检测工作流的异常或其他问题，此操作非常有用。  
  
## <a name="see-also"></a>另请参阅  
 [System.Workflow.Runtime.Tracking.TrackingWorkflowEvent 枚举](http://go.microsoft.com/fwlink/?LinkId=119568)
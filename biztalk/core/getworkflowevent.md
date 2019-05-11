---
title: GetWorkflowEvent | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2534e0b8-26df-4554-b0df-742014deb64d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68cf89a168606ae64a83c67b29eb058770b67f44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387648"
---
# <a name="getworkflowevent"></a>GetWorkflowEvent
将推送到堆栈上的当前工作流事件的名称。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetWorkflowEvent" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前的工作流事件的字符串。  
  
## <a name="remarks"></a>备注  
 工作流实例在其执行过程期间可以传递几种状态。 例如，工作流实例可能会进入空闲状态，或可能被挂起。 每次工作流实例更改状态，它会发出到运行时跟踪基础结构的工作流状态事件。 Windows Workflow Foundation BAM 侦听器支持由定义的事件的大多数`System.Workflow.Runtime.Tracking.TrackingWorkflowEvent`枚举下, 表中所示。  
  
|活动事件|Description|  
|--------------------|-----------------|  
|已更改|工作流实例上发生了工作流更改。|  
|已完成|工作流实例已完成。|  
|创建时间|已创建工作流实例。|  
|异常|发生未经处理的异常。|  
|Idle|工作流实例处于空闲状态。|  
|加载|工作流实例加载到内存。|  
|保留|已保留工作流实例。|  
|恢复|先前挂起的工作流实例已继续运行。|  
|Started|已启动工作流实例。|  
|挂起|工作流实例已挂起。|  
|终止|工作流实例已终止。|  
|卸载|已从内存中卸载工作流实例。|  
  
> [!NOTE]
>  不能使用两者`GetWorkflowEvent`和`GetActivityEvent`同一个 OnEvent 元素中。  
  
## <a name="example"></a>示例  
 下面的示例包含配置为查找特定活动的筛选器-"FoodAndDrinksPolicy"，在工作流中。 在示例中，配置筛选器来查找关闭的工作流中名为"FoodAndDrinksPolicy"的活动。 这是通过比较返回的值`GetWorkflowEvent`常量"Created"。  
  
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
  
 此操作可用于跟踪工作流的生存期和检测异常或其他问题与工作流。  
  
## <a name="see-also"></a>请参阅  
 [System.Workflow.Runtime.Tracking.TrackingWorkflowEvent 枚举](http://go.microsoft.com/fwlink/?LinkId=119568)
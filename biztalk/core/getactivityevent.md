---
title: GetActivityEvent |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fe824c9-4cea-44da-b830-5520d67988e0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fb039c0e9946091214a52fbb605753a212c233c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246245"
---
# <a name="getactivityevent"></a>GetActivityEvent
将当前活动事件的名称推送到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetActivityEvent"/>  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前活动事件的字符串。  
  
## <a name="remarks"></a>注释  
 一个工作流活动在工作流的生存期中可以传递几种状态。 Windows Workflow Foundation BAM 侦听器支持的定义的执行状态值大多数`System.Workflow.ComponentModel.ActivityExecutionStatus`枚举下, 表中所示。  
  
|执行状态|Description|  
|----------------------|-----------------|  
|Canceling|正在取消活动时，可表示的状态。|  
|已关闭|表示活动关闭时的状态。|  
|Compensating|表示活动正在补偿时的状态。|  
|Executing|表示活动正在执行时的状态。|  
|Faulting|表示活动发生故障时的状态。|  
  
> [!NOTE]
>  你不能同时使用`GetActivityEvent`和`GetWorkflowEvent`相同 OnEvent 元素中。  
  
## <a name="example"></a>示例  
 下面的示例包含一个配置为在关闭的工作流中查找特定活动 (FoodAndDringPolicy) 的事件筛选器表达式。 这可通过使用的操作包括组合`GetActivityEvent`， `GetActivityName`，和逻辑运算。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 该筛选模式常用于 Windows Workflow Foundation 侦听器配置文件。  
  
> [!NOTE]
>  参数不需要使用引号，除非您明确尝试匹配包含引号的字符串。  
  
## <a name="see-also"></a>另请参阅  
 [System.Workflow.ComponentModel.ActivityExecutionStatus 枚举](http://go.microsoft.com/fwlink/?LinkId=119570)
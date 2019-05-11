---
title: GetActivityEvent | Microsoft Docs
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
ms.openlocfilehash: 28c237cc32afb41d0fde2e702c9b0b42a2d14f41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345151"
---
# <a name="getactivityevent"></a>GetActivityEvent
将推送到堆栈上的当前活动事件的名称。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetActivityEvent"/>  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前活动事件的字符串。  
  
## <a name="remarks"></a>备注  
 工作流活动在工作流的生存期内可以传递几种状态。 Windows Workflow Foundation BAM 侦听器支持的执行状态值定义的大多数`System.Workflow.ComponentModel.ActivityExecutionStatus`枚举下, 表中所示。  
  
|执行状态|Description|  
|----------------------|-----------------|  
|正在取消|正在取消活动时表示的状态。|  
|已关闭|表示活动已关闭的状态。|  
|补偿|表示正在补偿活动的状态。|  
|执行|表示正在执行活动的状态。|  
|出错|表示正在进行错误处理活动的状态。|  
  
> [!NOTE]
>  不能使用两者`GetActivityEvent`和`GetWorkflowEvent`同一个 OnEvent 元素中。  
  
## <a name="example"></a>示例  
 下面的示例包含配置为查找特定活动的事件筛选器表达式-FoodAndDringPolicy — 关闭的工作流中。 这是通过使用的操作，包括组合`GetActivityEvent`， `GetActivityName`，和逻辑运算。  
  
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
  
 此筛选器模式非常常见的 Windows Workflow Foundation 侦听器配置文件。  
  
> [!NOTE]
>  参数不需要引号，除非您明确尝试匹配包含引号的字符串。  
  
## <a name="see-also"></a>请参阅  
 [System.Workflow.ComponentModel.ActivityExecutionStatus 枚举](http://go.microsoft.com/fwlink/?LinkId=119570)
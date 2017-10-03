---
title: "GetActivityName |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 479552fa-1535-4f3d-90ff-4615f14c88b1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55e8f35746f5f4ed1bbbe10a4d45300895340869
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getactivityname"></a>GetActivityName
将当前活动的名称推送到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetActivityName"/>  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前活动名称的字符串。  
  
## <a name="remarks"></a>注释  
 Windows Workflow Foundation 所执行的工作为开发人员配置的一系列活动。 在工作流中将为每个活动分配唯一的名称。 根据活动的唯一名称进行筛选，您可以侦听特定活动的数据。  
  
## <a name="example"></a>示例  
 下面的示例包含一个配置为在关闭的工作流中查找特定活动 FoodAndDrinksPolicy 的事件筛选器表达式。 这可通过使用的操作包括组合`GetActivityName`， `GetActivityEvent`，和逻辑运算。  
  
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
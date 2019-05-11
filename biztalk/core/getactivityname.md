---
title: GetActivityName | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 479552fa-1535-4f3d-90ff-4615f14c88b1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 597b08fc9ea9f19b6c3d7f7e3488ae7f77b2c62f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387743"
---
# <a name="getactivityname"></a>GetActivityName
将推送到堆栈上当前活动的名称。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetActivityName"/>  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前活动名称的字符串。  
  
## <a name="remarks"></a>备注  
 Windows Workflow Foundation 作为一系列由开发人员配置的活动执行其工作。 每个活动分配在工作流中的唯一名称。 通过筛选根据其唯一名称，可以拦截特定活动的数据。  
  
## <a name="example"></a>示例  
 下面的示例包含配置为查找特定活动的事件筛选器表达式-FoodAndDrinksPolicy — 关闭的工作流中。 这是通过使用的操作，包括组合`GetActivityName`， `GetActivityEvent`，和逻辑运算。  
  
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
---
title: GetActivityType | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65a5aae3-9688-4c49-a78e-1d9c1cc85fea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ded881aa0d7e952ed9fd425c2006982973f3ac5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387697"
---
# <a name="getactivitytype"></a>GetActivityType
将推送到堆栈上的当前活动类型的名称。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetActivityType" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含程序集限定类名格式中的当前活动类型的字符串。  
  
## <a name="remarks"></a>备注  
 `GetActivityType`操作检索当前活动类型，并将其放在程序集限定类名格式中的堆栈：  
  
```  
TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08, processorArchitecture=MSIL  
```  
  
 在比较时，您可以指定尽可能多的类型，以满足您的特定搜索需求。 例如，您可以比较常量与 GetActivityType 的结果：  
  
 TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0  
  
 这是限制性比程序集限定类名格式。  
  
## <a name="special-filter-behavior"></a>特殊筛选器行为  
 在筛选器内部执行此操作时，也始终匹配派生的活动。  
  
## <a name="example"></a>示例  
 下面的示例包含的事件筛选器表达式的计算结果将为`true`有关`System.Workflow.ComponentModel.Activity`实例和派生的类中的任何实例`System.Workflow.ComponentModel.Activity`。  
  
```  
<ic:Expression>  
  <wf:Operation Name="GetActivityType" />  
  <ic:Operation Name="Constant">  
    <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
  </ic:Operation>  
  <ic:Operation Name="Equals" />  
</ic:Expression>  
```
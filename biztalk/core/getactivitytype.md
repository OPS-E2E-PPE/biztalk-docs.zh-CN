---
title: GetActivityType |Microsoft 文档
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
ms.openlocfilehash: 67e6f31331907e20e810c11e82002fb08b89abe4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246413"
---
# <a name="getactivitytype"></a>GetActivityType
将当前活动类型的名称推送到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetActivityType" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前活动类型且采用了程序集限定类名格式的字符串。  
  
## <a name="remarks"></a>注释  
 `GetActivityType`操作检索当前的活动类型，并将其放在程序集限定类名的格式中的堆栈：  
  
```  
TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0, Culture=neutral, PublicKeyToken=b17a5c561934e08, processorArchitecture=MSIL  
```  
  
 进行比较时，您可以指定尽可能多的类型，以满足您的特定搜索需求。 例如，您可以将 GetActivityType 的结果与常数比较：  
  
 TopNamespace.SubNameSpace.ContainingClass+NestedClass, MyAssembly, Version=1.3.0.0  
  
 这比程序集限定类名格式的限制更少。  
  
## <a name="special-filter-behavior"></a>特殊筛选器行为  
 在筛选器内部执行此操作时，还将始终匹配派生的活动。  
  
## <a name="example"></a>示例  
 下面的示例包含计算结果将为事件筛选器表达式`true`为`System.Workflow.ComponentModel.Activity`实例和从其中派生类中的所有实例`System.Workflow.ComponentModel.Activity`。  
  
```  
<ic:Expression>  
  <wf:Operation Name="GetActivityType" />  
  <ic:Operation Name="Constant">  
    <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
  </ic:Operation>  
  <ic:Operation Name="Equals" />  
</ic:Expression>  
```
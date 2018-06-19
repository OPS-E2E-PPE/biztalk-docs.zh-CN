---
title: 和 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80bd8f1f-edae-476d-b488-78e6c5ee70bf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 676940dfa5cbc23d0c8127923d292e382a4e3cad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230013"
---
# <a name="and"></a>And
删除前两个项从堆栈中，执行一个布尔值**AND**的两个项，并将然后将推送到堆栈的结果。  
  
## <a name="syntax"></a>语法  
  
```  
  
<ic:Operation Name="And" />  
```  
  
#### <a name="parameters"></a>Parameters  
 堆栈最上方的两项。  
  
## <a name="pushed-value"></a>推送的值  
 字符串的布尔值结果**AND**操作。  
  
## <a name="remarks"></a>注释  
  
## <a name="example"></a>示例  
 **和**当你需要评估多个语句时，操作非常有用。 下面的示例筛选器表达式检查是否活动的名称为"CheckPO"并通过使用关闭活动事件**和**操作。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
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
  
 在此示例中**和**是表达式中的最后一个操作，因为它依赖于的比较结果 （和从要执行比较的堆栈中弹出）。 你可以扩展此办法执行**和**对两个以上的项的操作。 例如，若要计算条件 A、条件 B 和条件 C 是否都为真，可以使用类似于如下内容的表达式：  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityType"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyType</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>   
```  
  
## <a name="see-also"></a>另请参阅  
 [拦截器操作](../core/interceptor-operations.md)
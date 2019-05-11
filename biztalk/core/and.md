---
title: And | Microsoft Docs
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
ms.openlocfilehash: 2da29c40091664112ee8b481f3feeba9d7463b5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359704"
---
# <a name="and"></a>And
删除前两个项从堆栈中，执行一个布尔值**AND**的两个项，并将然后将推送到堆栈上的结果。  
  
## <a name="syntax"></a>语法  
  
```  
  
<ic:Operation Name="And" />  
```  
  
#### <a name="parameters"></a>Parameters  
 在堆栈上前两个项。  
  
## <a name="pushed-value"></a>推送的值  
 一个布尔值的字符串结果**AND**操作。  
  
## <a name="remarks"></a>备注  
  
## <a name="example"></a>示例  
 **和**操作时，你需要评估多个语句。 下面的示例筛选器表达式检查是否活动名称为"CheckPO"，并通过使用关闭的活动事件**和**操作。  
  
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
  
 在此示例中**和**是在表达式中的最后一个操作，因为它依赖于比较的结果 （并从要进行比较的堆栈中弹出它们）。 您可以扩展执行这一思路**和**对两个以上的项的操作。 例如，若要评估条件 A、 条件 B 和条件 C 是否，则返回 true，将使用的表达式如下所示：  
  
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
  
## <a name="see-also"></a>请参阅  
 [侦听器运算](../core/interceptor-operations.md)
---
title: Equals | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac93031a-9d18-443d-9e38-71ef9edd5a30
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e376445e8349663ab6196e99f9f31df8e5c1e139
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530735"
---
# <a name="equals"></a>等于
从堆栈中移除的前两个项、 进行比较的两个项目，然后将推送到堆栈上的结果。  
  
## <a name="syntax"></a>语法  
  
```  
  
<ic:Operation Name="Equals" />  
```  
  
#### <a name="parameters"></a>Parameters  
 在堆栈上前两个项。  
  
## <a name="pushed-value"></a>推送的值  
 字符串比较操作的结果。  
  
## <a name="remarks"></a>备注  
  
## <a name="example"></a>示例  
 下面的示例筛选器表达式使用**等于**操作以比较当前的活动名称与常数"CheckPO"。 如果两者相等，该表达式计算结果为`true`。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 你可能想要完全按照您写入语句，则生成表达式C#执行比较时。 例如，你可能想要比较三个值;在C#需要编写类似：  
  
```  
bool res = a == b == c;  
```  
  
 但是，表达式筛选器的模型作为此语句有些短。 相反，请考虑修改后 （但等效） 语句：  
  
```  
Bool res = (a == b) && (a == c);  
```  
  
 这与将用于执行比较的筛选器表达式更加匹配。 有关更多详细信息和示例，请参阅[和](../core/and.md)。  
  
## <a name="see-also"></a>请参阅  
 [侦听器运算](../core/interceptor-operations.md)
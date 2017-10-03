---
title: "常量 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0af49bf5-e7de-41da-ac27-70301b8ee4d4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 674307acea439bc260399cc01da4165eedaa2da5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="constant"></a>常量
将单一常数值推送到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<ic:Operation Name="Constant">  
  <ic:Argument>val</ic:Argument>  
</ic:Operation>  
```  
  
#### <a name="parameters"></a>Parameters  
 常量值。  
  
## <a name="pushed-value"></a>推送的值  
 包含常数值的字符串。  
  
## <a name="remarks"></a>注释  
  
## <a name="example"></a>示例  
 下面的示例筛选器表达式使用**常量**操作以将一个值，然后将使用在推送**等于**操作以确保当前的活动名称是"FoodAndDrinksPolicy"。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 这是常用的使用情况模式**常量**操作。  
  
## <a name="see-also"></a>另请参阅  
 [拦截器操作](../core/interceptor-operations.md)
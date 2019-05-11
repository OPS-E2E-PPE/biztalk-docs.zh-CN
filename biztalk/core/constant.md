---
title: 常量 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0af49bf5-e7de-41da-ac27-70301b8ee4d4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba1da4a690ca37a5012f5abb2e31f1229cb1b4bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354651"
---
# <a name="constant"></a>常量
将推送到堆栈上的单个常数值。  
  
## <a name="syntax"></a>语法  
  
```  
  
<ic:Operation Name="Constant">  
  <ic:Argument>val</ic:Argument>  
</ic:Operation>  
```  
  
#### <a name="parameters"></a>Parameters  
 常量值。  
  
## <a name="pushed-value"></a>推送的值  
 包含的常量值的字符串。  
  
## <a name="remarks"></a>备注  
  
## <a name="example"></a>示例  
 下面的示例筛选器表达式使用**常量**操作将随后可在使用一个值推**等于**操作以确保当前的活动名称是"FoodAndDrinksPolicy"。  
  
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
  
 这是常见的使用模式**常量**操作。  
  
## <a name="see-also"></a>请参阅  
 [侦听器运算](../core/interceptor-operations.md)
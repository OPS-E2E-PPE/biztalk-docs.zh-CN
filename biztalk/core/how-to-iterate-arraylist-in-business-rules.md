---
title: "如何循环访问业务规则中的 ArrayList |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, ArrayList
- business rules, arrays
- Business Rules Framework, programming
ms.assetid: 935e8648-72dc-4128-986c-72b0487bc074
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9010907cfe9fb6d79a8d9fcead533376b014640e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-iterate-arraylist-in-business-rules"></a>如何循环访问业务规则中的 ArrayList
本部分提供了循环访问的成员的一个示例**ArrayList**业务规则中。  
  
 假定您有**ArrayList**采用一系列**MyClass**对象。 该业务规则应与下面所列相似：  
  
## <a name="rule-a"></a>规则 A  
 IF 1==1  
  
 THEN Assert (ArrayList.GetEnumerator)   
  
 **IEnumerator**类型被声明到工作内存中，因为规则条件 (1 = = 1) 始终计算结果为 true。  
  
## <a name="rule-b"></a>规则 B  
 IF IEnumerator.MoveNext  
  
 THEN    Assert (IEnumerator.get_Current)  
  
 Update (IEnumerator)  
  
 由于此规则通过循环**ArrayList**，每个**MyClass**到工作内存断言集合中的对象。  
  
## <a name="rule-c"></a>规则 C  
 IF MyClass.MyProperty==2  
  
 然后\<执行某些操作...\>  
  
 当对象的属性值与条件中所列值匹配时，此规则将执行操作。
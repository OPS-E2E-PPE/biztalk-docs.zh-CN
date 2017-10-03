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
ms.openlocfilehash: 95896b63e5bb982a4778b05970900c989ebc66b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
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
  
 然后\<做些什么...>  
  
 当对象的属性值与条件中所列值匹配时，此规则将执行操作。
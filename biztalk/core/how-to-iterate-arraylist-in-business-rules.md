---
title: 如何循环访问业务规则中的 ArrayList |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, ArrayList
- business rules, arrays
- Business Rules Framework, programming
ms.assetid: 935e8648-72dc-4128-986c-72b0487bc074
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9753ce1208312ade51950cd36a1df4210d763268
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384872"
---
# <a name="how-to-iterate-arraylist-in-business-rules"></a>如何循环访问业务规则中的 ArrayList
本部分举例说明循环访问的成员**ArrayList**业务规则中。  
  
 假设您有**ArrayList**了一系列**MyClass**对象。 您的业务规则如以下所示。  
  
## <a name="rule-a"></a>规则 A  
 IF 1==1  
  
 THEN Assert (ArrayList.GetEnumerator)  
  
 **IEnumerator**类型将添加到工作内存中，因为规则条件 (1 = = 1) 计算结果始终为 true。  
  
## <a name="rule-b"></a>规则 B  
 IF IEnumerator.MoveNext  
  
 THEN    Assert (IEnumerator.get_Current)  
  
 更新 (IEnumerator)  
  
 因为规则循环访问**ArrayList**，则每个**MyClass**添加到工作内存中集合中的对象。  
  
## <a name="rule-c"></a>规则 C  
 IF MyClass.MyProperty==2  
  
 然后\<执行一些操作...\>  
  
 该对象的属性值匹配条件中时，此规则将执行操作。
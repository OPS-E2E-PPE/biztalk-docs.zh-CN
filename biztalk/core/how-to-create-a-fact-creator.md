---
title: 如何创建事实创建器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- GetFactTypes method
- CreateFacts method
- IFactCreator interface
- Business Rules Framework, code samples
- Business Rules Framework, fact creator
- Business Rules Framework, programming
ms.assetid: 0589be8e-34d6-4e55-b678-c1f8436d1f61
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9784be0a26fd6f5b60cf68401faf36e816b54c08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340041"
---
# <a name="how-to-create-a-fact-creator"></a>如何创建事实创建器
您可以编写事实创建器来创建自己的事实实例。 事实创建器必须实现**IFactCreator**并将其**CreateFacts**方法和**GetFactTypes**方法。 创建事实创建器 dll 之后，您可以在策略测试器浏览到它从。 下面是事实创建器实现的示例。  
  
```  
public class MyFactCreator : IFactCreator  
{  
   private object[] myFacts;  
   public MyFactCreator()  
   {  
   }  
   public object[] CreateFacts ( RuleSetInfo rulesetInfo )  
   {  
      myFacts = new object[1];  
      myFacts.SetValue(new MySampleBusinessObject(),0);  
      return myFacts;  
   }  
   public Type[] GetFactTypes (RuleSetInfo rulesetInfo)  
   {  
      return null;  
   }  
}  
```
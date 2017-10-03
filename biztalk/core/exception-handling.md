---
title: "异常处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00a9125c-7c7c-4d2a-ae04-c923cd89683c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 520f4eb47fb98bf497753a8348031f7c2ab93d29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="exception-handling"></a>异常处理
**RuleEngine**类具有属性**CompensationHandlerInfo**，该子元素又具有两个属性： **CompensationHandler**和**UserData**. **CompensationHandler**属性属于类型**RuleEngineCompensationHandler**，和**UserData**属性属于类型**对象**. 定义**RuleEngineCompensationHandler**如下：  
  
```  
public delegate bool RuleEngineCompensationHandler(  
   Exception ex,  
   object userData  
);  
```  
  
 规则引擎使用者通过指定处理程序和用户数据的规则引擎**CompensationHandlerInfo**属性**RuleEngine**类。 处理程序必须具有相同的签名**RuleEngineCompensationHandler**委托。 如果出现运行时异常，则引擎将调用处理程序并将异常和预定义用户数据作为参数传递给处理程序。 如果处理程序返回`true`，则规则引擎会继续处理。 否则，规则引擎中止处理并将原始异常返回给用户。 如你所见，仅当通过调用该策略，您可以使用此异常处理机制**RuleEngine.Execute**方法。  
  
 如果你使用**Policy.Execute**方法以执行策略，你将需要使用 try catch 块来捕获执行策略时生成的规则引擎对任何异常。  
  
 如果你使用**调用规则**形状以执行策略，请使用**捕获异常**阻止**作用域**形状来捕捉由规则引擎在执行时引发的异常策略。  
  
## <a name="see-also"></a>另请参阅  
 [如何添加 Catch 异常块](../core/how-to-add-a-catch-exception-block3.md)
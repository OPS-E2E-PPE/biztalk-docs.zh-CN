---
title: 异常处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00a9125c-7c7c-4d2a-ae04-c923cd89683c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 235e49aedf477088e8524b7d6aa7a1a9f5f243ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346027"
---
# <a name="exception-handling"></a>异常处理
**RuleEngine**类具有属性**CompensationHandlerInfo**，该子元素又具有两个属性：**CompensationHandler**并**UserData**。 **CompensationHandler**属性属于类型**RuleEngineCompensationHandler**，并**UserData**属性属于类型**对象**. 用于定义**RuleEngineCompensationHandler**如下所示：  
  
```  
public delegate bool RuleEngineCompensationHandler(  
   Exception ex,  
   object userData  
);  
```  
  
 规则引擎使用者通过使用指定的处理程序和用户数据到规则引擎**CompensationHandlerInfo**的属性**RuleEngine**类。 处理程序必须具有相同的签名**RuleEngineCompensationHandler**委托。 如果没有运行时异常，引擎将调用处理程序，并将异常和预定义的用户数据作为参数传递给处理程序。 如果处理程序返回`true`，则规则引擎将继续处理。 否则为规则引擎中止处理并返回到原始异常的用户。 正如您所看到的仅当使用调用策略，您可以使用此异常处理机制**RuleEngine.Execute**方法。  
  
 如果您使用**Policy.Execute**方法以执行策略，将需要使用 try catch 块来捕获执行策略时生成的规则引擎的任何异常。  
  
 如果您使用**调用规则**形状中，以执行策略，请使用**捕获异常**块**范围**要捕获由规则引擎执行时引发异常形状策略。  
  
## <a name="see-also"></a>请参阅  
 [如何添加捕获异常块](../core/how-to-add-a-catch-exception-block3.md)
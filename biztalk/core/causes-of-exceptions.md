---
title: 引发异常的原因 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, errors
- errors, orchestrations
- errors, causes
ms.assetid: b0422382-d034-4c58-87c6-fc269dbbfe43
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71c6bf04421ca538400545239711637990e3adf5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357597"
---
# <a name="causes-of-exceptions"></a>引发异常的原因
可以通过以下方式在业务流程中生成异常：  
  
-   通过**引发异常**形状，它立即无条件地将引发异常。 控制权将传递从**引发异常**形状直接向相应的异常处理程序。  
  
-   通过在一个长时间运行的事务过期超时。 预定义的系统异常 —**Microsoft.XLANG.BaseTypes.TimeOutException**— 在这种情况下引发。  
  
-   由某些其他事务失败。 运行时引擎会引发如 Microsoft.XLANG.BaseTypes.PersistenceException 这些故障的系统定义消息。  
  
-   通过用户代码异常。 当业务流程中进行时对外部用户代码的调用时，调用的公共语言运行时类可能会引发异常。 如果未在用户代码中处理这些异常，它们最终向上传播到在其中进行调用用户代码的作用域。  
  
-   由某些其他系统异常 （例如，持久化错误，例如类型加载程序异常的另一个.NET 或系统异常或数据转换错误）。  
  
> [!NOTE]
>  当引发类型加载程序异常时，可能不会捕获异常在**捕获异常**在同一个阻止**作用域**形状。 这是由于的例外是从类型加载程序，不能从 BizTalk 业务流程进程。 因此，它不遵循控制流的 BizTalk 规则。  
  
-   通过停止执行周围的作用域中的同级分支。 Microsoft.XLANG.BaseTypes.ForcedTerminationException 引发向每个分支，在这种情况下，并且你可能想要添加到每个异常处理程序。 此类异常处理程序不能重新引发的异常，也不应尝试会引发任何其他类型的异常。  
  
-   由一个外部的消息，指示错误的回执。  
  
## <a name="see-also"></a>请参阅  
 [错误消息](../core/fault-messages.md)   
 [异常](../core/exceptions.md)
---
title: 异常的原因 |Microsoft 文档
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
ms.openlocfilehash: 9006234d71751078269e5a88559839fdadd91e91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232461"
---
# <a name="causes-of-exceptions"></a>引发异常的原因
可以通过以下方式在业务流程中产生异常：  
  
-   通过**引发的异常**形状，立即无条件地将引发异常。 控制权将传递从**引发的异常**形状上直接与相应的异常处理程序。  
  
-   通过在长时间运行事务过期超时。 预定义的系统异常-**Microsoft.XLANG.BaseTypes.TimeOutException**— 在这种情况下引发。  
  
-   通过某些其他事务失败。 运行时引擎将引发如 Microsoft.XLANG.BaseTypes.PersistenceException 这些故障的系统定义消息。  
  
-   通过用户代码异常。 当业务流程中进行调用外部用户代码时，调用的公共语言运行时类可以引发异常。 如果未在用户代码中处理这些异常，它们最终向上传播到在其中进行的用户代码调用该范围。  
  
-   由某些其他系统异常 （例如，持久性失败，例如类型加载程序异常的另一个.NET 或系统异常或将数据转换错误）。  
  
> [!NOTE]
>  当引发类型加载程序异常时，可能不会捕获异常中**捕获异常**块中，在相同**作用域**形状。 这是由于异常是从类型加载程序，不是从 BizTalk 业务流程过程。 因此，它不遵循控制流的 BizTalk 规则。  
  
-   通过中止执行周边范围中的一个同级分支。 Microsoft.XLANG.BaseTypes.ForcedTerminationException 引发到每个分支，这种情况下，并且你可能想要将异常处理程序添加到每个。 此类异常处理程序无法重新引发的异常，也不应尝试引发任何其他类型的异常。  
  
-   通过接收外部的消息，该值指示错误。  
  
## <a name="see-also"></a>另请参阅  
 [错误消息](../core/fault-messages.md)   
 [异常](../core/exceptions.md)
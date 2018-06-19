---
title: 创建自定义异常处理程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 401aec8d-d9ca-4a88-9e5b-d3ab605dc0a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91f725084c838d026f9028f0ac2e684ec2d727c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290629"
---
# <a name="creating-custom-exception-handlers"></a>创建自定义异常处理程序
应用程序，以检测异常并做出响应，开发人员必须提供异常处理程序。 此异常处理程序可以订阅到单一类型的异常消息或系统或应用程序的全部或部分中生成的异常消息。 例如，你可能需要单个处理程序的所有消息从一个特定的系统 （如在的工资支付系统中发生的任何异常） 或者您而是可能需要目标的处理程序特定的失败 （例如检测如果检查打印过程失败）。  
  
 若要订阅特定类型的异常，请使用具有激活的接收形状, 一个筛选器业务流程，如下面的示例中所示。  
  
```csharp  
Microsoft.Practices.ESB.ExceptionHandling.Schemas.Property.FaultCode == "1000";  
```  
  
 你还可能具有将消息发送到文件系统或通过电子邮件上，如果消息满足特定筛选器条件发送端口筛选条件。  
  
## <a name="sample-exception-handling-projects"></a>示例异常处理项目  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括几个示例 BizTalk 应用程序演示异常处理。 \Source\Samples\Exception 处理文件夹中找不到这些示例。  
  
 也有四个 BizTalk 项目，位于 GlobalBank.ESB.Samples.ExceptionHandling 解决方案中，演示如何使用 ESB 失败业务流程异常路由机制。 这些项目已预先配置为将部署到 GlobalBank.ESB BizTalk 应用程序。 项目如下所示：  
  
-   **ESB。ExceptionHandling.Schemas。** 此项目包含用于示例业务流程的架构。  
  
-   **ESB。ExceptionHandling.Pipelines。** 此项目包含与异常处理器，在订阅的所有异常发送端口中使用配置的发送管道。 这包括由 BizTalk 和异常异常管理框架生成的生成的异常。  
  
-   **ESB。ExceptionHandling.Processes。** 此项目包含 EAIProcess.odx 业务流程，后者通过尝试除以零和调用来模拟异常**CreateFaultMessage**和**AddMessage**要生成合适的方法错误消息，如图 1 中所示。  
  
     ![业务流程处理示例](../esb-toolkit/media/ch4-orchestrationprocessessample.gif "第四章第 4 OrchestrationProcessesSample")  
  
     **图 1**  
  
 **EAIProcess.odx 业务流程进程示例项目中**  
  
-   **ESB。ExceptionHandling.Handlers。** 此项目包含 EAIGenericHandler.odx 业务流程，后者将调用**GetMessages**方法并循环访问**MessageCollection**使用**MoveNext**方法，如图 2 所示。  
  
 ![业务流程处理程序示例泛型](../esb-toolkit/media/ch4-orchestrationhandlerssamplegeneric.gif "第四章第 4 OrchestrationHandlersSampleGeneric")  
  
 **图 2**  
  
 **EAIGenericHandler.odx 业务流程处理程序示例项目中**  
  
 ESB。ExceptionHandling.Handlers 项目还包含调用 EAIProcessHandler.odx 编排**GetMessage**和**GetException**方法，如图 3 中所示。  
  
 ![业务流程处理程序示例过程](../esb-toolkit/media/ch4-orchestrationhandlerssampleprocess.gif "第四章第 4 OrchestrationHandlersSampleProcess")  
  
 **图 3**  
  
 **EAIProcessHandler.odx 业务流程处理程序示例项目中**
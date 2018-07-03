---
title: 创建自定义异常处理程序 |Microsoft Docs
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
ms.openlocfilehash: 33d49fddb8a42c440f62acdd4ea337f43b876f6b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971518"
---
# <a name="creating-custom-exception-handlers"></a>创建自定义异常处理程序
应用程序以检测异常并做出响应，开发人员必须提供异常处理程序。 此异常处理程序可以订阅到单一类型的异常消息或从一个系统或应用程序的全部或部分生成的异常消息。 例如，所可能需要单个处理程序的所有消息从特定系统 （如工资系统中发生任何异常） 或所而是可能需要目标处理程序的特定故障 （例如检测如果检查打印过程失败）。  
  
 若要订阅特定类型的异常，使用的业务流程的筛选器对激活的接收形状，如下面的示例中所示。  
  
```csharp  
Microsoft.Practices.ESB.ExceptionHandling.Schemas.Property.FaultCode == "1000";  
```  
  
 此外可能将消息发送到文件系统或通过电子邮件上，如果消息满足特定筛选器条件的发送端口上的筛选条件。  
  
## <a name="sample-exception-handling-projects"></a>示例异常处理项目  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括几个示例 BizTalk 应用程序演示异常处理。 可以 \Source\Samples\Exception 处理文件夹中找到这些示例。  
  
 也有四个 BizTalk 项目，GlobalBank.ESB.Samples.ExceptionHandling 解决方案中，演示如何使用 ESB 失败，业务流程异常路由机制。 预配置这些项目将部署到 GlobalBank.ESB BizTalk 应用程序。 项目如下所示：  
  
- **ESB。ExceptionHandling.Schemas。** 此项目包含示例业务流程所使用的架构。  
  
- **ESB。ExceptionHandling.Pipelines。** 此项目包含与订阅的所有异常发送端口中使用的异常处理器配置的发送管道。 这包括生成 BizTalk 和生成的异常管理框架异常的异常。  
  
- **ESB。ExceptionHandling.Processes。** 此项目包含 EAIProcess.odx 业务流程，以模拟通过尝试除以零和调用的异常**CreateFaultMessage**并**AddMessage**要生成合适的方法错误消息，如图 1 中所示。  
  
   ![业务流程处理示例](../esb-toolkit/media/ch4-orchestrationprocessessample.gif "Ch4-OrchestrationProcessesSample")  
  
   **图 1**  
  
  **进程示例项目中的 EAIProcess.odx 业务流程**  
  
- **ESB。ExceptionHandling.Handlers。** 此项目包含 EAIGenericHandler.odx 业务流程，后者调用**GetMessages**方法和循环**MessageCollection**使用**MoveNext**方法，如图 2 所示。  
  
  ![业务流程处理程序示例](../esb-toolkit/media/ch4-orchestrationhandlerssamplegeneric.gif "Ch4-OrchestrationHandlersSampleGeneric")  
  
  **图 2**  
  
  **EAIGenericHandler.odx 业务流程处理程序示例项目中**  
  
  ESB。ExceptionHandling.Handlers 项目还包含调用 EAIProcessHandler.odx 业务流程**GetMessage**并**GetException**方法，如图 3 所示。  
  
  ![业务流程处理程序示例进程](../esb-toolkit/media/ch4-orchestrationhandlerssampleprocess.gif "Ch4-OrchestrationHandlersSampleProcess")  
  
  **图 3**  
  
  **EAIProcessHandler.odx 业务流程处理程序示例项目中**
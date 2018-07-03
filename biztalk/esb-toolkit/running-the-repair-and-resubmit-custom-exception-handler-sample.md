---
title: 运行修复和重新提交自定义异常处理程序示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7363c440-44aa-4d08-8290-72787d17ac60
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34bb03565f7b044f9c6c2f29332862ae8aafef7e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004478"
---
# <a name="running-the-repair-and-resubmit-custom-exception-handler-sample"></a>运行修复和重新提交自定义异常处理程序示例
修复和重新提交自定义异常处理程序示例演示如何将人为干预集成到 ESB 和 Microsoft 基于 BizTalk 的应用程序处理，并实现有用的设计模式的极有效技术。 示例代码无缝集成到 ESB 异常管理系统。  
  
 此示例演示如何在业务流程中使用自定义异常处理程序。 当业务流程 (EAIProcess.odx) 中的进程时遇到错误时，异常处理程序生成并发布到 ESB 的错误消息。 此错误消息包括在其有效负载"中"处理状态消息 （包括其 BizTalk 相关上下文属性） 时出现异常和 BizTalk 业务流程引擎捕获到当前 System.Exception 实例。 当发生这种情况时，并显示错误消息保持"拒绝"消息和"已批准"消息。  
  
 名为 EAIProcessHandler.odx，它以分离的方式部署并可作为一个自定义异常处理程序，第二个业务流程订阅 EAIProcess.odx 业务流程中生成的特定错误代码，并使用错误消息。 此异常处理程序中提取原始邮件 （如类型化文档），并且 System.Exception 实例最初保存在错误消息。  
  
 原始消息现在变得可供处理其中的所有原始上下文属性。 自定义异常处理程序 (EAIProcessHandler.odx) 然后将写入到以下位置中的文件系统的"拒绝"和"已批准"消息：  
  
- 已批准的消息：  
  
  -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcess.PostApproval  
  
- 用于修复和重新提交被拒绝的消息：  
  
  -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcessHandler.RepairSubmit  
  
- 被拒绝的消息：  
  
  -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcessHandler.PostDecline  
  
  异常处理程序序列化的修复和重新提交到使用 Microsoft InfoPath 处理指令的文件系统"拒绝"消息。 InfoPath 模板允许用户编辑窗体，然后重新提交结果 （请参阅图 1），从而启动验证消息的 EAIProcess.odx 业务流程。  
  
  ![修复重新提交](../esb-toolkit/media/ch6-repairresubmit.gif "Ch6-RepairResubmit")  
  
  **图 1**  
  
  **通过 InfoPath 修复并重新提交模板生成的测试消息**  
  
  此外，还有一个名为所有的泛型的发送端口。配置为使用 GlobalFaultProcessor 管道 Exceptions_FILE。 此端口订阅系统中的所有异常，这两个 BizTalk 故障消息路由的消息和 ESB 错误消息。 异常管理框架将其规范化所有为一种格式并将其使用文件夹 \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions InfoPath 处理指令序列化。  
  
## <a name="installation"></a>安装  
 所有异常管理示例都使用的相同的一套核心服务和 BizTalk 应用程序项目。 因此，必须安装异常管理示例项目一次可以运行所有异常管理示例。 有关如何安装异常管理示例的信息，请参阅[安装异常管理示例](../esb-toolkit/installing-the-exception-management-samples.md)。  
  
## <a name="running-the-sample-application"></a>运行示例应用程序  
 **若要运行修复和重新提交自定义异常处理程序示例**  
  
1.  第一次运行此示例之前，请确保接收位置和发送端口 Url 指向 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中的相应目录。 接收位置应指定文件夹 EAIProcess.RequestPort，而发送端口 Url 应指定文件夹 EAIProcess.PostApproval 和 EAIProcessHandler.PostDecline。  
  
2.  如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。  
  
3.  将名为 Request_EAIProcessHandler.xml，在 \Source\Samples\Exception Handling\Test\Data 文件夹中，为指定为 EAIProcess.RequestPort_FILE 接收位置的文件夹位于该示例文件复制启动示例： \Source\Samples\异常 Handling\Test\Filedrop\EAIProcess.RequestPort。  
  
4.  打开名为 EAIProcessHandler.PostDecline （在 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中） 的文件夹。 您将看到生成的异常处理业务流程的"已拒绝 *"消息。  
  
5.  打开名为 EAIProcessHandler.RepairSubmit （在 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中） 的文件夹。 您将看到生成的异常处理业务流程的"RepairSubmit"消息。  
  
6.  双击 RepairSubmit 文件以在相应的 InfoPath 模板中打开它。 您将看到可以进行编辑和重新提交消息。  
  
7.  更改的值**单价**字段从**0**到**2**，然后单击**提交**按钮位于工具栏上的 InfoPath窗体提交回 BizTalk 用于处理编辑的文档。 提交进程使用 BizTalk 配置 HTTP 接收位置。  
  
8.  导航到 EAIProcess.PostApproval 文件夹 （在 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中）。 现在，您将看到"批准 *"文档，其中包含的单位价格更新后的值。  
  
## <a name="how-the-sample-works"></a>示例工作原理  
 您提交的消息激活 EAIProcess 业务流程。 当 EAIProcess 业务流程处理消息时，它会尝试将 1 除以单位价格。 由于的单位价格为零，则会发生被零除异常。 业务流程的事件处理程序中的代码会捕获此异常，并创建错误消息。 消息中的订单数量大于 10，因此业务逻辑决定了此异常有**FaultCode**字段的值**1000年**。  
  
 EAIProcess 业务流程随后将错误消息发布到 BizTalk 消息框通过直接绑定端口，并在业务流程结束。  
  
 一个名为 EAIProcessHandler，订阅消息的自定义错误处理程序业务流程**FaultCode**字段的值**1000年**，提取新的错误消息。 在业务流程中的代码创建"拒绝"消息和 InfoPath 文件，并将它放置此 EAIProcessHandler.PostDecline 和 EAIProcessHandler.RepairSubmit 文件夹到准备好进行人工干预。
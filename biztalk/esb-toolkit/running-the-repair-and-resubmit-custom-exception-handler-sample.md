---
title: "运行修复并重新提交自定义异常处理程序示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7363c440-44aa-4d08-8290-72787d17ac60
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8b33765cbe3ca1c8c0c7c3e7679e543678325af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-repair-and-resubmit-custom-exception-handler-sample"></a>运行修复并重新提交自定义异常处理程序示例
此修复和重新提交自定义异常处理程序的示例演示一种用于将人工干预集成到 ESB 和 Microsoft 基于 BizTalk 应用程序处理并实现一种有用的设计模式的极其有效方法。 示例代码可无缝集成到 ESB 异常管理系统。  
  
 此示例演示如何在业务流程中使用自定义异常处理程序。 当业务流程 (EAIProcess.odx) 中的进程遇到错误时，异常处理程序生成并发布 ESB 错误消息。 此错误消息包括其有效负载中的消息 （包括其 BizTalk 相关上下文属性）"中航班"时出现异常和由 BizTalk 业务流程引擎捕获当前 System.Exception 实例。 发生这种情况，"拒绝"消息和"已批准"消息将通过错误消息中持久化。  
  
 名为 EAIProcessHandler.odx，部署方式分离并作为一个自定义异常处理程序，这第二个业务流程订阅生成 EAIProcess.odx 业务流程中的特定错误代码，并使用该错误消息。 此异常处理程序中提取原始消息 （作为类型化的文档），且 System.Exception 实例最初保留在错误消息。  
  
 原始消息现在变得可用于处理与所有原始上下文属性。 自定义异常处理程序 (EAIProcessHandler.odx) 然后将"拒绝"和"已批准"消息写入文件系统在以下位置：  
  
-   已批准的消息：  
  
    -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcess.PostApproval  
  
-   修复，重新提交的被拒绝的消息：  
  
    -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcessHandler.RepairSubmit  
  
-   被拒绝的消息：  
  
    -   \Source\Samples\Exception Handling\Test\Filedrop\EAIProcessHandler.PostDecline  
  
 异常处理程序修复，重新提交序列化到使用 Microsoft InfoPath 处理指令的文件系统的"拒绝"消息。 InfoPath 模板允许用户编辑该表单，然后重新提交结果 （参见图 1），以启动验证消息 EAIProcess.odx 业务流程。  
  
 ![修复重新提交](../esb-toolkit/media/ch6-repairresubmit.gif "Ch6 RepairResubmit")  
  
 **图 1**  
  
 **InfoPath 修复和重新提交模板生成的测试消息**  
  
 此外，没有名为所有泛型发送端口。配置为使用 GlobalFaultProcessor 管道的 Exceptions_FILE。 此端口在系统中订阅的所有异常，这两个 BizTalk 失败消息将消息路由和 ESB 错误消息。 异常管理框架对它们进行规范化所有成单一格式，并序列化这些使用到文件夹 \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions InfoPath 处理指令。  
  
## <a name="installation"></a>安装  
 所有异常管理示例都使用的相同的一套核心服务以及 BizTalk 应用程序项目。 因此，你必须安装异常管理示例项目仅一次能够运行管理示例的所有异常。 有关如何安装异常管理示例的信息，请参阅[安装异常管理示例](../esb-toolkit/installing-the-exception-management-samples.md)。  
  
## <a name="running-the-sample-application"></a>运行示例应用程序  
 **若要运行修复和重新提交自定义异常处理程序示例**  
  
1.  首次运行此示例之前，请确保接收位置和发送端口 Url 指向 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中的相应目录。 接收位置应指定文件夹 EAIProcess.RequestPort，而发送端口 Url 应指定 EAIProcess.PostApproval 和 EAIProcessHandler.PostDecline 的文件夹。  
  
2.  如果 GlobalBank.ESB 应用程序尚未运行，使用 BizTalk 管理控制台来启动它。  
  
3.  将名为 Request_EAIProcessHandler.xml，在 \Source\Samples\Exception Handling\Test\Data 文件夹中，为 EAIProcess.RequestPort_FILE 接收位置指定的文件夹位于该示例文件复制启动示例： \Source\Samples\异常 Handling\Test\Filedrop\EAIProcess.RequestPort。  
  
4.  打开名为 EAIProcessHandler.PostDecline （在 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中） 的文件夹。 你将看到"已拒绝 *"消息生成的异常处理业务流程。  
  
5.  打开名为 EAIProcessHandler.RepairSubmit （在 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中） 的文件夹。 你将看到生成的异常处理业务流程的"RepairSubmit"消息。  
  
6.  双击 RepairSubmit 文件以在适当的 InfoPath 模板中打开它。 你将看到准备好进行编辑并重新提交消息。  
  
7.  更改的值**单价**字段从**0**到**2**，然后单击**提交**按钮位于工具栏上的 InfoPath要提交编辑的文档，返回到以进行处理的 BizTalk 窗体。 提交过程使用 BizTalk 配置 HTTP 接收位置。  
  
8.  导航到 EAIProcess.PostApproval 文件夹 （在 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中）。 现在，你将看到"批准 *"文档包含的单位价格的更新的值。  
  
## <a name="how-the-sample-works"></a>此示例的工作原理  
 提交消息激活 eai 进程业务流程。 当 eai 进程业务流程处理消息时，它尝试 1 除以单位价格。 因为单位价格为零，则会发生被零除异常。 业务流程的事件处理程序中的代码会捕获此异常，并创建错误消息。 消息中的订单数量是大于 10，因此业务逻辑指示此异常有**FaultCode**字段的值**1000年**。  
  
 Eai 进程业务流程然后发布到 BizTalk 消息框通过直接绑定的端口，错误消息和业务流程结束。  
  
 名为 EAIProcessHandler，订阅具有消息的自定义错误处理程序业务流程**FaultCode**字段的值**1000年**，选取新的错误消息。 业务流程中的代码创建"拒绝"消息和 InfoPath 文件，并将它放置这到 EAIProcessHandler.PostDecline 和 EAIProcessHandler.RepairSubmit 文件夹准备好进行人工干预。
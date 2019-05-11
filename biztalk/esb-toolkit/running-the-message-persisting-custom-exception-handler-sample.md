---
title: 运行消息保留自定义异常处理程序示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0a4c819-f6bd-4dea-8be9-e3006337665f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ba7ef5fda253f4dc96d4e29a109d0bb0c576cee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242733"
---
# <a name="running-the-message-persisting-custom-exception-handler-sample"></a>运行消息保留自定义异常处理程序示例
消息保留自定义异常处理程序示例演示的松散耦合、 泛型处理程序收到错误消息时，它们包含的并将其作为磁盘文件写入到文件系统的 Microsoft BizTalk 消息中提取。  
  
 此示例演示如何在业务流程中使用自定义异常处理程序。 当业务流程 (EAIProcess.odx) 中的进程时遇到错误时，异常处理程序生成并发布到 ESB 的错误消息。 此错误消息包括在其有效负载"中"处理状态消息 （包括其 BizTalk 相关上下文属性） 时出现异常，以及当前由 BizTalk 业务流程引擎捕获到的 System.Exception 实例。 当发生这种情况时，并显示错误消息保持"拒绝"消息和"已批准"消息。  
  
 名为 EAIGenericHandler.odx，它以分离的方式部署并可作为一个自定义异常处理程序，第二个业务流程订阅 EAIGenericHandler.odx 业务流程中生成的特定错误代码，并使用错误消息。 此异常处理程序中提取原始邮件 （如类型无文档），并且 System.Exception 实例最初保存在错误消息。  
  
 消息保留自定义异常处理程序示例不同于修复和重新提交自定义异常处理程序示例，在此示例中使用的 EAIGenericHandler.odx 业务流程中错误发布使用的架构不具有依赖关系业务流程进程 (EAIProcess.odx)。 具体而言，EAIGenericHandler.odx 业务流程检索原始消息的错误消息为 System.Xml.XmlDocument 实例而不是基于 EAIProcess.odx 业务流程中使用的架构的类型化消息。 它还返回的集合的代码可以轻松地枚举形式的消息。  
  
 自定义异常处理程序 (EAIGenericHandler.odx) 然后将写入到文件系统位置 \Source\Samples\Exception Handling\Test\Filedrop\EAIGenericHandler.PostTmpMsg 的"拒绝"和"已批准"消息。  
  
 此外，还有一个名为所有的泛型的发送端口。Exceptions_FILE 配置为使用 GlobalFaultProcessor 管道的一部分安装[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]异常管理框架。 此端口订阅系统中的所有异常，这两个 BizTalk 故障消息路由的消息和 ESB 错误消息。 异常管理框架将其规范化所有为一种格式，并将其使用位置 \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions Microsoft InfoPath 处理指令序列化。  
  
## <a name="installation"></a>安装  
 所有异常管理示例都使用的相同的一套核心服务和 BizTalk 应用程序项目。 因此，必须安装异常管理示例项目一次可以运行所有异常管理示例。 有关如何安装异常管理示例的信息，请参阅[安装异常管理示例](../esb-toolkit/installing-the-exception-management-samples.md)。  
  
## <a name="running-the-sample-application"></a>运行示例应用程序  
 **若要运行消息保留自定义异常处理程序示例**  
  
1.  第一次运行此示例之前，请确保，接收位置和发送端口 URL 指向 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中的相应目录。 接收位置应指定文件夹 EAIProcess.RequestPort，而发送端口 URL 应指定文件夹 EAIGenericHandler.PostTmpMsg。  
  
2.  如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。  
  
3.  将名为 Request_EAIGenericHandler.xml，在 \Source\Samples\Exception Handling\Test\Data 文件夹中，为指定为 EAIProcess.RequestPort_FILE 接收位置的文件夹位于该示例文件复制启动示例： \Source\Samples\异常 Handling\Test\Filedrop\EAIProcess.RequestPort。  
  
4.  打开名为 EAIGenericHandler.PostTmpMsg （在 \Source\Samples\Exception Handling\Test\Filedrop\ 文件夹中） 的文件夹。 您将看到原始消息。  
  
## <a name="how-the-sample-works"></a>示例工作原理  
 您提交的消息激活 EAIProcess 业务流程。 当 EAIProcess 业务流程处理消息时，它会尝试将 1 除以单位价格。 由于的单位价格为零，则会发生被零除异常。 业务流程的事件处理程序中的代码会捕获此异常，并创建错误消息。 消息中的订单数量是小于 10，因此业务逻辑决定了此异常有**FaultCode**字段的值**2000年**。  
  
 EAIProcess 业务流程随后将错误消息发布到 BizTalk 消息框通过直接绑定端口，并在业务流程结束。  
  
 一个名为 EAIGenericHandler，订阅消息的自定义错误处理程序业务流程**FaultCode**字段的值**2000年**，提取新的错误消息。 在业务流程中的代码从异常 （错误） 消息中提取的所有消息，并将其写入到磁盘文件。
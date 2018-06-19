---
title: 运行保留自定义异常处理程序的示例消息 |Microsoft 文档
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
ms.openlocfilehash: f6d7927357e4c2be03ecd8b2e77d45558b5bc692
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295325"
---
# <a name="running-the-message-persisting-custom-exception-handler-sample"></a>运行保留自定义异常处理程序的示例消息
消息保留自定义异常处理程序示例演示如何实现松耦合、 泛型的处理程序收到错误消息时，它们包含，并将其作为磁盘文件写入到文件系统的 Microsoft BizTalk 消息中提取。  
  
 此示例演示如何在业务流程中使用自定义异常处理程序。 当业务流程 (EAIProcess.odx) 中的进程遇到错误时，异常处理程序生成并发布 ESB 错误消息。 此错误消息包括其有效负载中的消息 （包括其 BizTalk 相关上下文属性）"中航班"时出现异常，以及由 BizTalk 业务流程引擎捕获当前 System.Exception 实例。 发生这种情况，"拒绝"消息和"已批准"消息将通过错误消息中持久化。  
  
 名为 EAIGenericHandler.odx，部署方式分离并作为一个自定义异常处理程序，这第二个业务流程订阅生成 EAIGenericHandler.odx 业务流程中的特定错误代码，并使用该错误消息。 此异常处理程序中提取原始消息 （作为类型无文档），且 System.Exception 实例最初保留在错误消息。  
  
 消息保留自定义异常处理程序示例修复和重新提交自定义异常处理程序中的示例不同之处在于此示例中使用 EAIGenericHandler.odx 业务流程没有错误发布中使用的架构的依赖关系业务流程过程 (EAIProcess.odx)。 具体而言，EAIGenericHandler.odx 业务流程从中检索原始消息的错误消息作为 System.Xml.XmlDocument 实例而不是基于 EAIProcess.odx 业务流程中使用的架构的类型化消息。 它还返回的集合的代码可以轻松地枚举形式的消息。  
  
 自定义异常处理程序 (EAIGenericHandler.odx) 然后将"拒绝"和"已批准"消息写入文件系统位置 \Source\Samples\Exception Handling\Test\Filedrop\EAIGenericHandler.PostTmpMsg。  
  
 此外，没有名为所有泛型发送端口。Exceptions_FILE 配置为使用作为的一部分安装 GlobalFaultProcessor 管道[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]异常管理框架。 此端口在系统中订阅的所有异常，这两个 BizTalk 失败消息将消息路由和 ESB 错误消息。 异常管理框架对它们进行规范化所有成单一格式，并序列化这些使用到位置 \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions Microsoft InfoPath 处理指令。  
  
## <a name="installation"></a>安装  
 所有异常管理示例都使用的相同的一套核心服务以及 BizTalk 应用程序项目。 因此，你必须安装异常管理示例项目仅一次能够运行管理示例的所有异常。 有关如何安装异常管理示例的信息，请参阅[安装异常管理示例](../esb-toolkit/installing-the-exception-management-samples.md)。  
  
## <a name="running-the-sample-application"></a>运行示例应用程序  
 **若要运行消息持久保存自定义异常处理程序示例**  
  
1.  首次运行此示例之前，请确保该接收位置和发送端口 URL 指向 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中的相应目录。 接收位置应指定文件夹 EAIProcess.RequestPort，并发送端口 URL 应指定文件夹 EAIGenericHandler.PostTmpMsg。  
  
2.  如果 GlobalBank.ESB 应用程序尚未运行，使用 BizTalk 管理控制台来启动它。  
  
3.  将名为 Request_EAIGenericHandler.xml，在 \Source\Samples\Exception Handling\Test\Data 文件夹中，为 EAIProcess.RequestPort_FILE 接收位置指定的文件夹位于该示例文件复制启动示例： \Source\Samples\异常 Handling\Test\Filedrop\EAIProcess.RequestPort。  
  
4.  打开名为 EAIGenericHandler.PostTmpMsg （在 \Source\Samples\Exception Handling\Test\Filedrop\ 文件夹中） 的文件夹。 你将看到原始消息。  
  
## <a name="how-the-sample-works"></a>此示例的工作原理  
 提交消息激活 eai 进程业务流程。 当 eai 进程业务流程处理消息时，它尝试 1 除以单位价格。 因为单位价格为零，则会发生被零除异常。 业务流程的事件处理程序中的代码会捕获此异常，并创建错误消息。 消息中的订单数量是小于 10，因此业务逻辑指示此异常有**FaultCode**字段的值**2000年**。  
  
 Eai 进程业务流程然后发布到 BizTalk 消息框通过直接绑定的端口，错误消息和业务流程结束。  
  
 名为 EAIGenericHandler，订阅具有消息的自定义错误处理程序业务流程**FaultCode**字段的值**2000年**，选取新的错误消息。 业务流程中的代码从异常 （错误） 消息中提取所有消息，并将其写入到磁盘文件。
---
title: "运行 BizTalk 失败消息路由 ESB 处理示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2a536a0-cfc8-4ba3-adcd-2b8b580bff85
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81a2b225e5316d16e31d2ed2ca830387dc14048d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="running-the-biztalk-failed-message-routing-esb-processing-sample"></a>运行 BizTalk 失败消息路由 ESB 处理示例
Microsoft BizTalk 失败消息路由 ESB 处理示例演示如何使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]异常管理框架作为通用机制，管理、 序列化，并呈现在 BizTalk 中的所有情况下发生的异常服务器。 这包括由 BizTalk 失败消息路由机制和错误消息框架生成的异常管理从业务流程中生成的异常。  
  
 BizTalk 失败消息路由机制是 BizTalk Server; 的错误处理功能通过使用它，设计器可以指定自动的处理的消息作为传统的替代方法失败 （现在默认值） 的放置的行为失败"已挂起"队列中的消息。 这将自动处理路由到任何订阅的路由目标，如发送端口或业务流程的错误信息。 错误消息是与降级的所有以前升级的属性和提升到消息上下文与特定的消息传递失败相关的所选属性的原始消息的克隆。  
  
 若要启用接收端口或发送端口上的 BizTalk 失败消息路由机制，请选择**启用路由失败消息**复选框，如图 1 中所示。  
  
 ![启用路由](../esb-toolkit/media/ch6-enabledrouting.gif "Ch6 EnabledRouting")  
  
 **图 1**  
  
 **启用 BizTalk 失败消息路由机制**  
  
 但是，没有因错误或故障在业务流程中发生的类似机制。 相反，异常处理程序的业务流程中的代码可以充分利用异常管理 Framework API，以模拟 BizTalk 失败消息路由机制的功能。  
  
 在此示例中，名为 EAIProcess.RequestPort_FILE 接收位置选取复制到位置 \Source\Samples\Exception Handling\Test\Filedrop\EAIProcess.RequestPort 文件。  
  
 此外，没有名为所有泛型发送端口。Exceptions_FILE 配置为使用 GlobalFaultProcessor 管道作为异常 Management Framework 的一部分安装。 此端口订阅系统中发生的所有异常，这两个 BizTalk 失败消息将消息路由和 ESB 错误消息，如图 2 中所示。  
  
 ![发送端口](../esb-toolkit/media/ch6-sendport.gif "Ch6 发送端口")  
  
 **图 2**  
  
 **所有。异常发送端口订阅的所有类型的故障或异常**  
  
 异常管理框架规范化到一种格式的所有异常，并序列化这些使用到位置 \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions Microsoft InfoPath 处理指令。  
  
## <a name="installation"></a>安装  
 所有异常管理示例都使用的相同的一套核心服务以及 BizTalk 应用程序项目。 因此，你必须安装异常管理示例项目仅一次能够运行管理示例的所有异常。 有关如何安装异常管理示例的信息，请参阅[安装异常管理示例](../esb-toolkit/installing-the-exception-management-samples.md)。  
  
## <a name="running-the-sample-application"></a>运行示例应用程序  
 **若要运行 BizTalk 失败消息路由 ESB 处理示例**  
  
1.  首次运行此示例之前，请确保该接收位置和发送端口 URL 指向 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中的相应目录。 接收位置应指定文件夹 EAIProcess.RequestPort，并发送端口 URL 应指定文件夹 All_Exceptions。  
  
2.  如果 GlobalBank.ESB 应用程序尚未运行，使用 BizTalk 管理控制台来启动它。  
  
3.  将复制到名为 （在 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中） 的 EAIProcess.RequestPort 接收位置文件夹名 FlatFileReceive_in.txt 为从文件夹 \Source\Samples\Exception Handling\Test\Data 的文件。  
  
4.  此消息是一个文本文件，文件，它将会引发异常。 打开 All_Exceptions （在 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中），名为的文件夹，然后双击以打开到使用适当的模板的 InfoPath 的错误消息。 你将看到，ESB 异常处理机制序列化内容适当地以允许 InfoPath 呈现它。  
  
5.  接下来，将名为转换为 EAIProcess.RequestPort 从文件夹 \Source\Samples\Exception Handling\Test\Data soapmessage [1].xml 文件复制接收位置文件夹。  
  
6.  此消息是包含 CDATA 节内，一个 XML 文档，它将会引发异常。 打开 All_Exceptions 输出文件夹，然后双击以打开到 InfoPath 的错误消息。 你将看到，ESB 异常处理机制序列化此内容适当地以允许 InfoPath 呈现它。  
  
7.  最后，将名为 EAIProcess.RequestPort 从文件夹 \Source\Samples\Exception Handling\Test\Data Csqzav01.pdf 文件复制接收位置。  
  
8.  此消息为 PDF 文件，并且它将导致异常。 打开 All_Exceptions 输出文件夹并双击该错误消息，以在 InfoPath 中打开它。 你将看到 ESB 异常处理机制序列化和 Base 64 进行编码的内容，以允许 InfoPath 呈现它。
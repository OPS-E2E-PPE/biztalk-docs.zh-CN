---
title: 运行 BizTalk 故障消息路由 ESB 处理示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2a536a0-cfc8-4ba3-adcd-2b8b580bff85
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8181c426bac76885b7e06aea93c9c3bb32dc1564
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292565"
---
# <a name="running-the-biztalk-failed-message-routing-esb-processing-sample"></a>运行 BizTalk 故障消息路由 ESB 处理示例
Microsoft BizTalk 失败消息路由 ESB 处理示例演示如何使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]异常管理框架作为通用机制来管理、 序列化，并呈现在 BizTalk 中的所有情况下出现的异常服务器。 这包括由 BizTalk 失败消息路由机制和容错生成的消息异常管理框架从业务流程中生成的异常。  
  
 BizTalk 失败消息路由机制是 BizTalk Server; 错误处理功能通过使用它，在设计器可以指定作为传统的替代方法消息传送失败进行自动的处理放置的 （现在是默认） 行为失败"已挂起"队列中的消息。 这将自动处理路由到任何订阅路由目标，例如发送端口或业务流程的错误消息。 错误消息是使用所有以前升级的属性降级和升级到消息上下文中的特定消息传送失败相关的所选属性的原始消息的克隆。  
  
 若要启用的接收端口或发送端口上的 BizTalk 失败消息路由机制，请选择**失败消息启用路由功能**复选框，如图 1 中所示。  
  
 ![已启用的路由](../esb-toolkit/media/ch6-enabledrouting.gif "Ch6 EnabledRouting")  
  
 **图 1**  
  
 **启用 BizTalk 失败消息路由机制**  
  
 但是，没有错误或故障发生在业务流程中的类似机制。 相反，业务流程的异常处理程序中的代码可以充分利用异常管理框架 API 将模拟的 BizTalk 失败消息路由机制功能。  
  
 在此示例中，名为 EAIProcess.RequestPort_FILE 的接收位置提取文件复制到位置 \Source\Samples\Exception Handling\Test\Filedrop\EAIProcess.RequestPort。  
  
 此外，还有一个名为所有的泛型的发送端口。Exceptions_FILE 配置为使用 GlobalFaultProcessor 管道异常管理框架的一部分安装。 此端口订阅系统中发生的所有异常，这两个 BizTalk 故障消息路由的消息和 ESB 错误消息，如图 2 中所示。  
  
 ![发送端口](../esb-toolkit/media/ch6-sendport.gif "Ch6-SendPort")  
  
 **图 2**  
  
 **所有。异常的发送端口订阅用于所有类型的故障或异常**  
  
 异常管理框架规范化所有异常的一种格式，并将其使用位置 \Source\Samples\Exception Handling\Test\Filedrop\All_Exceptions Microsoft InfoPath 处理指令序列化。  
  
## <a name="installation"></a>安装  
 所有异常管理示例都使用的相同的一套核心服务和 BizTalk 应用程序项目。 因此，必须安装异常管理示例项目一次可以运行所有异常管理示例。 有关如何安装异常管理示例的信息，请参阅[安装异常管理示例](../esb-toolkit/installing-the-exception-management-samples.md)。  
  
## <a name="running-the-sample-application"></a>运行示例应用程序  
 **若要运行 BizTalk 失败消息路由 ESB 处理示例**  
  
1.  第一次运行此示例之前，请确保，接收位置和发送端口 URL 指向 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中的相应目录。 接收位置应指定文件夹 EAIProcess.RequestPort，而发送端口 URL 应指定文件夹 All_Exceptions。  
  
2.  如果尚未运行 GlobalBank.ESB 应用程序，使用 BizTalk 管理控制台来启动它。  
  
3.  名为 FlatFileReceive_in.txt 文件夹 \Source\Samples\Exception Handling\Test\Data 到名为 EAIProcess.RequestPort （在 \Source\Samples\Exception Handling\Test\Filedrop 文件夹中） 的接收位置文件夹将文件复制。  
  
4.  此消息是一个文本文件，并且将导致异常。 打开名为 All_Exceptions （\Source\Samples\Exception Handling\Test\Filedrop 文件夹） 中的文件夹，然后双击要在使用相应的模板的 InfoPath 打开的错误消息。 你将看到，ESB 异常处理机制序列化内容相应地允许 InfoPath 来呈现它。  
  
5.  接下来，将名为 EAIProcess.RequestPort 从文件夹 \Source\Samples\Exception Handling\Test\Data soapmessage [1].xml 文件复制接收位置文件夹中。  
  
6.  此消息是包含 CDATA 节内，一个 XML 文档，它会导致异常。 打开 All_Exceptions 输出文件夹，然后双击要在 InfoPath 打开的错误消息。 你将看到，ESB 异常处理机制将序列化此内容相应地允许 InfoPath 来呈现它。  
  
7.  最后，将名为 EAIProcess.RequestPort 从文件夹 \Source\Samples\Exception Handling\Test\Data Csqzav01.pdf 文件接收位置。  
  
8.  此消息是 PDF 文件，并且将导致异常。 打开 All_Exceptions 输出文件夹，然后双击要在 InfoPath 中打开的错误消息。 您将看到 ESB 异常处理机制进行序列化和 Base-64 编码的内容，以允许 InfoPath 来呈现它。
---
title: 收集异常并保留有效负载使用 ESB 异常处理器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52650eed-e760-4ade-bc3f-2b5b2a1c43ff
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c43925006153ccfdcfa0c9700dd1ecf27fd3fd2f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994814"
---
# <a name="collecting-exceptions-and-persisting-the-payload-using-the-esb-exception-processor"></a>收集异常并保留使用 ESB 异常处理器的有效负载
在此用例，业务流程的异常处理程序将到 ESB 的错误消息发布到 BizTalk Server 消息框，或者 BizTalk 失败消息路由机制将生成错误消息。 使用 ESB 异常编码器管道组件，预配置的发送端口订阅这两种错误消息。 它处理的错误消息，然后将其保留为磁盘文件，你可以查看使用 InfoPath，如图 1 中所示。  
  
 ![收集异常负载](../esb-toolkit/media/ch3-collectingexceptionspayload.gif "Ch3-CollectingExceptionsPayload")  
  
 **图 1**  
  
 **捕获的错误消息并将其保存到磁盘文件**  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括以下：  
  
- **预配置的发送端口使用 ESB 故障处理器发送管道。** 您可以依据特定要求配置此发送端口。  
  
- **消息保留自定义异常处理程序示例。** 此示例演示如何松散耦合的一般异常处理程序可以接收错误消息中提取 BizTalk Server 消息包含、 规范化和增强消息，并将其作为磁盘文件写入到文件系统。  
  
- **BizTalk 失败消息路由的示例。** 此示例演示如何 ESB 异常管理框架可以标准化和丰富本机生成的 BizTalk Server 中的失败消息路由机制的错误消息。  
  
  有关详细信息，请参阅[运行消息保留自定义异常处理程序示例](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)并[运行 BizTalk 失败消息路由 ESB 处理示例](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)。
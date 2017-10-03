---
title: "收集异常和保持使用 ESB 异常处理器负载 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52650eed-e760-4ade-bc3f-2b5b2a1c43ff
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec3ca7a33b5a38b625894e391c5bf014eb824414
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="collecting-exceptions-and-persisting-the-payload-using-the-esb-exception-processor"></a>收集异常和保持使用 ESB 异常处理器负载
在使用此种情况下，为业务流程的异常处理发布到 ESB 错误消息[!INCLUDE[prague](../includes/prague-md.md)]消息框或 BizTalk 失败消息路由机制将生成错误消息。 发送端口，预先配置为使用 ESB 异常编码器管道组件，订阅这两个类型的错误消息。 它处理的错误消息，并将保持它们为磁盘文件，你可以查看使用 InfoPath，如图 1 中所示。  
  
 ![收集异常负载](../esb-toolkit/media/ch3-collectingexceptionspayload.gif "Ch3 CollectingExceptionsPayload")  
  
 **图 1**  
  
 **捕获的错误消息并将它保存到磁盘文件**  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括以下：  
  
-   **预配置发送使用 ESB 错误处理器发送管道的端口。** 你可以依据特定要求配置此发送端口。  
  
-   **消息保留自定义异常处理程序的示例。** 此示例演示松散耦合的一般异常处理程序接收错误消息的方式提取 BizTalk Server 消息包含、 规范化和丰富消息，并为磁盘文件将它们写入文件系统。  
  
-   **BizTalk 失败消息路由示例中。** 此示例演示如何规范化 ESB 异常管理框架和扩充本机由 BizTalk Server 中的失败的邮件路由机制生成的错误消息。  
  
 有关详细信息，请参阅[运行消息持久保存自定义异常处理程序示例](../esb-toolkit/running-the-message-persisting-custom-exception-handler-sample.md)和[运行 BizTalk 失败消息路由 ESB 处理示例](../esb-toolkit/running-the-biztalk-failed-message-routing-esb-processing-sample.md)。
---
title: FileAct 适配器实时端到端基元 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8591120-7259-49cb-90ac-954d8be226ed
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c95e52d4fbd5ec0df8ee580583f429ffe9e0f08d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224925"
---
# <a name="fileact-adapter-real-time-end-to-end-primitives"></a>FileAct 适配器实时端到端基元
SWIFTNet 基元是两个应用程序和 SWIFTNet 链接 (SNL) 之间交换的 XML 文档。 为每个端到端基元，这里是两个版本的基元 – 一个在客户端 （或发送） 一侧，在服务器上的另一个 （或接收） 端。 这包含四个消息总数： 将文件基元、 获取文件基元和每个发送传递通知。  
  
 下图显示 FileAct 端到端基元。  
  
 ![FileAct 结束 &#45; 到 &#45; 结束基元](../../adapters-and-accelerators/fileact-interact/media/6e3520cc-9ec4-445c-9114-c7cb760c1068.gif "6e3520cc-9ec4-445c-9114-c7cb760c1068")  
  
## <a name="put-file"></a>将文件放  
 应用程序启动放置文件的基元，以便将文件发送到文件系统中的另一个 SWIFTNet 用户。 作为一个端到端的函数，没有客户端和服务器端放文件基元。 这些共同协作以成功完成的文件传输。  
  
 每个此类协作发送单个文件。 可能中并行执行多个放置文件基元。  
  
## <a name="get-file"></a>获取文件  
 应用程序启动获取文件的基元，以便从另一个 SWIFTNet 用户的文件系统中检索文件。 作为一个端到端的函数，没有客户端和服务器端获取文件基元。 这些共同协作以成功完成的文件传输。  
  
 每个此类协作检索单个文件。 可能中并行执行多个获取文件基元。  
  
## <a name="send-delivery-notification"></a>发送传递通知  
 每个放置文件和基元每个获取文件已拥有的文件请求的接收端返回相关的文件传输传递通知的发送端的选项。 对于 Put 文件基元，该请求消息包含传递通知的请求。  
  
 如果是获取文件基元，响应消息包含传递通知的请求。  
  
 在任一情况下，验证该文件，已接收到整个 （通过执行以检查传输达到已完成的状态的状态基元之一），该文件已被充分安全存储 （例如，在后端系统中） 后,接收应用程序单独执行传递通知的基元，以便返回传递到发件人的肯定确认。 作为一个端到端的函数，没有客户端和服务器端传递通知基元。 这些共同协作以成功完成文件传递通知。  
  
 传递通知需要服务设计器建立并强制使用发送方和接收方的文件之间的协议。  
  
## <a name="see-also"></a>另请参阅  
 [FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct 适配器传递通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)
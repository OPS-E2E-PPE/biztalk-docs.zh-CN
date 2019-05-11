---
title: FileAct 适配器实时端到端基元 |Microsoft Docs
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
ms.openlocfilehash: 0532c0240be0032a46100e46d9cd58d4ff4820e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367179"
---
# <a name="fileact-adapter-real-time-end-to-end-primitives"></a>FileAct 适配器实时端到端基元
SWIFTNet 基元是两个应用程序和 SWIFTNet 链接 (SNL) 之间交换 XML 文档。 以每个端到端基元，存在两个版本的基元-一个在客户端 （或发送） 位置，在服务器上的一个 （或接收） 端。 这包括共四个消息：将为每个文件基元、 文件获取基元和发送送达通知。  
  
 下图显示了 FileAct 端到端基元。  
  
 ![FileAct 端&#45;到&#45;结束基元](../../adapters-and-accelerators/fileact-interact/media/6e3520cc-9ec4-445c-9114-c7cb760c1068.gif "6e3520cc-9ec4-445c-9114-c7cb760c1068")  
  
## <a name="put-file"></a>将文件放入  
 应用程序发起的 Put 文件基元将文件发送到另一个 SWIFTNet 用户的文件系统。 作为应用的端到端函数，是客户端和服务器端将文件基元。 这些共同协作以成功完成文件传输。  
  
 每个这种协作将发送单个文件。 可能会并行执行多个放置文件基元。  
  
## <a name="get-file"></a>获取文件  
 应用程序启动的文件系统的另一个 SWIFTNet 用户从文件中检索的文件获取基元。 作为应用的端到端函数，是客户端和服务器端文件获取基元。 这些共同协作以成功完成文件传输。  
  
 每个此类协作检索单个文件。 可能会并行执行多个文件获取基元。  
  
## <a name="send-delivery-notification"></a>送达通知  
 每个放置文件和每个文件获取基元已拥有的文件请求的接收方返回送达通知以便与相关的文件传输的发送端的选项。 对于 Put 文件基元，请求消息包含送达通知的请求。  
  
 如果是获取文件基元，响应消息包含送达通知的请求。  
  
 在任一情况下，验证该文件已接收到全部 （通过执行其中一个状态基元来检查在传输达到已完成的状态） 和该文件已被充分安全存储 （例如，在后端办公系统上） 后,接收应用程序单独执行送达通知基元来返回传递到发件人肯定确认。 作为应用的端到端函数，是客户端和服务器端送达通知基元。 这些共同协作以成功完成文件送达通知。  
  
 送达通知需要服务设计器来建立并强制执行发送方和接收方的文件之间的协议。  
  
## <a name="see-also"></a>请参阅  
 [FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct 适配器送达通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)
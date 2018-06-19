---
title: FileAct 适配器实时本地基元 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef4da4f8-3de2-4d35-8f8a-1e12937e52a1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcc0f1d093d56b8cd4580ef068007d02aab6346f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223069"
---
# <a name="fileact-adapter-real-time-local-primitives"></a>FileAct 适配器实时本地基元
本地基元涉及两条消息，该客户端 SWIFTNet 链接 (SNL) 和本地 FileAct 子系统之间交换。  
  
 下图显示 FileAct 本地基元。  
  
 ![FileAct 本地基元](../../adapters-and-accelerators/fileact-interact/media/67ca0c3b-3c81-401d-87cb-473c68cae63f.gif "67ca0c3b-3c81-401d-87cb-473c68cae63f")  
  
## <a name="get-status-for-a-single-transfer"></a>获得单个传输状态  
 获取状态基元检索有关本地的持久性上下文从一个传输的状态信息。  
  
## <a name="subscribe-to-transfer-events"></a>订阅通知，以便传输事件  
 基于事件的事件中，通过使用订阅事件基元可能接收到渐进式传输状态信息。 每个文件传输可能链接到已命名实体的协商期间调用的事件终结点。 订阅事件基元时，将调用的事件服务器将定向为一个此类事件终结点为其自身的所有事件报告。  
  
 事件服务器可以订阅特征 （不同级别的详细信息，以及不同的事件类型）。  
  
 事件服务器可能会调用该基元多次订阅多个事件终结点。 只能有一个事件服务器可能在给定时间订阅特定事件的任何终结点。 此外，事件服务器可以调用该基元的同一个事件终结点的多个时间，个更改特性。  
  
## <a name="receive-transfer-events"></a>接收传输事件  
 接收传输事件是处理有关传输正在进行中的事件按事件状态信息的基元。 它的响应设置订阅事件基元的订阅中的条款。 可以在传输发送或接收端实现此基元。  
  
## <a name="abort-transfer"></a>中止传输  
 用户应用程序可能中止传输正在进行使用中止基元。 中止基元是可能会执行从发送方或接收方的传输正在进行的基元。 当启动或接受传输时，每个端必须建立用作访问密钥才能从其自身保护传输的传输密钥的选项。 如果对进行传输中建立的传输密钥，则它可能未被终止从该端无需提供中止基元的练习中的传输密钥值。  
  
## <a name="see-also"></a>另请参阅  
 [FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct 适配器传递通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)
---
title: FileAct 适配器实时本地基元 |Microsoft Docs
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
ms.openlocfilehash: ac26a598dad808908b6be1b9fe7ecff3ed1f9f6e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367188"
---
# <a name="fileact-adapter-real-time-local-primitives"></a>FileAct 适配器实时本地基元
本地基元涉及两条消息，该客户端 SWIFTNet 链接 (SNL) 和本地 FileAct 子系统之间交换。  
  
 下图显示了 FileAct 本地基元。  
  
 ![FileAct 本地基元](../../adapters-and-accelerators/fileact-interact/media/67ca0c3b-3c81-401d-87cb-473c68cae63f.gif "67ca0c3b-3c81-401d-87cb-473c68cae63f")  
  
## <a name="get-status-for-a-single-transfer"></a>获取单个传输的状态  
 获取状态基元检索有关本地持久上下文从一个传输的状态信息。  
  
## <a name="subscribe-to-transfer-events"></a>订阅传送事件  
 可能使用的订阅事件基元，基于事件的事件接收渐进式传输状态信息。 每个文件传输可能链接到在协商过程中调用的事件终结点的命名实体。 调用订阅事件基元事件 server 将定向为一个此类事件终结点到其自身的所有事件报告。  
  
 事件服务器可以订阅特征 （不同级别的详细信息，以及不同的事件类型）。  
  
 事件服务器可能会调用该基元多次订阅多个事件终结点。 只能有一个事件服务器可能在某一时刻订阅任何特定事件的终结点。 此外，事件服务器可以调用该基元多次为同一个事件终结点用于更改特征。  
  
## <a name="receive-transfer-events"></a>接收传输事件  
 接收传输事件是处理有关传输正在进行中的事件按事件状态信息的基元。 它的响应通过设置订阅事件基元的订阅中的条款。 可以在传输发送或接收端实现此基元。  
  
## <a name="abort-transfer"></a>中止传输  
 用户应用程序可能会中止传输过程中使用的中止基元。 中止基元是可以从在发送端或传输中进度在接收端实施的基元。 当启动或接受传输时，每一端都有建立可用于保护该传输从其自身的访问密钥作为传送密钥的选项。 如果对传输中进度建立传送密钥，则它可能未被终止从该端无需提供中止基元的练习中的传输密钥值。  
  
## <a name="see-also"></a>请参阅  
 [FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/fileact-adapter-store-and-forward.md)   
 [FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct 适配器送达通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)
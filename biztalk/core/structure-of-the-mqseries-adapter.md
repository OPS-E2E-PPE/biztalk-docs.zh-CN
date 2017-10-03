---
title: "结构 MQSeries 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, MQSeries adapters
- MQSeries adapters, architecture
ms.assetid: d25caf6a-3f93-4164-9c92-489b919a624d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6239b78f0b9bd2c44a314b7ba0ba6ace8f3b78e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="structure-of-the-mqseries-adapter"></a>MQSeries 适配器的结构
MQSeries 适配器由两部分组成： 下运行的适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并将 COM + 应用程序，MQSAgent，适用于 Windows 在 MQSeries 服务器下运行。 下图显示了此关系：  
  
 ![MQSeries 适配器组件](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")  
  
 该适配器可与 MQSAgent 应用程序进行通信。 而 MQSAgent 应用程序又与 MQSeries Server for Windows 进行通信。 如果您在计算机上安装了 MQSeries Server for Windows，则可以将代理与该适配器安装在同一台计算机上。  
  
 该适配器的发送部分向 MQSAgent 发送消息。 MQSAgent 然后，使用**MQPut**，将消息发送到 MQSeries 队列管理器。  
  
 该适配器的接收部分将轮询 MQSAgent 以查看是否有消息。 如果有一条消息，执行 MQSAgent **MQGet**来检索消息。 MQSAgent 包含硬编码三秒等待，以从队列管理器中检索消息。  
  
> [!NOTE]
>  您可以设置该适配器的轮询间隔。 将轮询间隔设置为三秒以下时，等待间隔将设置为轮询间隔。  
  
 发送消息和接收消息两种操作均在事务中进行。 这样，适配器就可以回滚消息，并可重试发送或接收操作。 有关事务的详细信息，请参阅[MQSeries 适配器批处理和事务处理](../core/mqseries-adapter-batching-and-transaction-handling.md)。  
  
 由于适配器工作于多台计算机间，因此，可能会碰到安全方面的问题。 恶意程序可能会假冒代理并捕获数据。 有关增强保护的适配器和代理的详细信息，请参阅[MQSeries 适配器安全](../core/mqseries-adapter-security.md)。  
  
## <a name="see-also"></a>另请参阅  
 [MQSeries 适配器体系结构](../core/mqseries-adapter-architecture.md)   
 [什么是 MQSeries 适配器？](../core/what-is-the-mqseries-adapter.md)
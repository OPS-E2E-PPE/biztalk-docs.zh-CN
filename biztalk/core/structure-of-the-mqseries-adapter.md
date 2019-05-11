---
title: MQSeries 适配器的结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, MQSeries adapters
- MQSeries adapters, architecture
ms.assetid: d25caf6a-3f93-4164-9c92-489b919a624d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21bd7d9dee24e8235aff34a14babd4cc69240c74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379945"
---
# <a name="structure-of-the-mqseries-adapter"></a>MQSeries 适配器的结构
MQSeries 适配器由两部分组成： 下运行的适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 COM + 应用程序，MQSAgent 运行 MQSeries Server for Windows。 下图显示了此关系。  
  
 ![MQSeries 适配器组件](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")  
  
 适配器与 MQSAgent 应用程序进行通信。 MQSAgent 应用程序，反过来，通信与 MQSeries Server for Windows。 如果您安装 MQSeries Server for Windows 的计算机上，可以在该适配器所在的计算机上安装代理。  
  
 该适配器的发送部分向 MQSAgent 发送消息。 MQSAgent 然后，使用**MQPut**，将消息发送到 MQSeries 队列管理器。  
  
 该适配器的接收部分将轮询 MQSAgent 以查看是否有消息。 如果有一条消息，则 MQSAgent 将执行**MQGet**中检索消息。 MQSAgent 包含硬编码三秒等待，以检索该消息从队列管理器。  
  
> [!NOTE]
>  您可以设置该适配器的轮询间隔。 轮询间隔设置为小于三秒后，等待间隔设置为轮询间隔。  
  
 这两个发送和接收消息在事务中进行操作。 这使得适配器可以回滚消息以及可能的重试发送或接收操作。 有关事务的详细信息，请参阅[MQSeries 适配器批处理和事务处理](../core/mqseries-adapter-batching-and-transaction-handling.md)。  
  
 因为适配器可以在多台计算机，所以不可能的安全问题。 恶意程序可能会假冒代理并捕获数据。 有关适配器和代理的增强保护的详细信息，请参阅[MQSeries 适配器安全性](../core/mqseries-adapter-security.md)。  
  
## <a name="see-also"></a>请参阅  
 [MQSeries 适配器体系结构](../core/mqseries-adapter-architecture.md)   
 [MQSeries 适配器概述](../core/what-is-the-mqseries-adapter.md)
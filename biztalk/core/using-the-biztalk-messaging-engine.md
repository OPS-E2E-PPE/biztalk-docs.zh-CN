---
title: 使用 BizTalk 消息引擎 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, Messaging Engine
- adapters, TransportProxy object
- Messaging Engine, adapters
- Messaging Engine, architecture
- TransportProxy object
- Messaging Engine, how to
- architecture, Messaging Engine
- messages, Messaging Engine
ms.assetid: e6b6d1ec-38cd-4721-9673-ae40da003dec
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 598a7030b885057dc7781336c2925f0cb99b17fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395179"
---
# <a name="using-the-biztalk-messaging-engine"></a>使用 BizTalk 消息引擎
下图演示了消息引擎的体系结构。 它显示了其中一条消息是由适配器接收，提交到 BizTalk Server 的方案。  
  
 ![](../core/media/ebiz-prog-messaging1.gif "ebiz_prog_messaging1")  
消息引擎的体系结构  
  
 每个适配器具有其自己的实例**TransportProxy**它使用与消息引擎进行交互的对象。 适配器在以原子方式处理的批处理中执行对消息引擎的工作。 一批是诸如 SubmitMessage、 SuspendMessage 或 DeleteMessage 的集合。  
  
 以下是的适配器将提交到消息引擎的消息的方案的事件序列：  
  
1.  适配器创建新的消息，并将数据流连接到该消息。  
  
2.  适配器从消息引擎获取新批。  
  
3.  该适配器将消息添加到提交的批。  
  
4.  该批提交并在消息引擎线程池上排队等候。  
  
5.  消息引擎线程池开始处理新的批。  
  
6.  在接收管道中处理该消息。  
  
7.  接收管道将生成零个或多个消息。 管道可以使用提供它们不会返回任何错误消息。 接收管道可以生成多条消息;这通常会拆装器组件拆装成多个消息的单个交换。 通常接收管道将已提交的消息规范化为 XML。  
  
8.  如果配置映射，将在映射器中处理由管道生成的消息。  
  
9. 消息将发布到消息代理或 MessageBox 数据库。  
  
10. 消息引擎回调适配器，以通知它的工作批的结果。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [可恢复的交换处理](../core/recoverable-interchange-processing.md)  
  
-   [按序送达消息](../core/ordered-delivery-of-messages.md)  
  
-   [错误处理](../core/error-handling.md)  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何处理大消息](../core/how-biztalk-server-processes-large-messages.md)   
 [引擎性能特征](../core/engine-performance-characteristics.md)   
 [测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [测量引擎的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [使用 Microsoft BizTalk LoadGen 2007 工具](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)
---
title: 使用 BizTalk 消息引擎 |Microsoft 文档
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
ms.openlocfilehash: 701ed3e82eb75b98a948313a99bb4debc65a8cce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288037"
---
# <a name="using-the-biztalk-messaging-engine"></a>使用 BizTalk 消息传送引擎
下图显示了消息引擎的结构。 它显示了一个方案，在该方案中消息由适配器接收，然后提交到 BizTalk Server。  
  
 ![](../core/media/ebiz-prog-messaging1.gif "ebiz_prog_messaging1")  
消息引擎的结构  
  
 每个适配器具有自己的实例**TransportProxy**它使用与消息引擎进行交互的对象。 适配器对消息引擎成批执行操作，这是以原子方式处理的。 批是诸如 SubmitMessage、SuspendMessage 或 DeleteMessage 之类的操作的集合。  
  
 下面是适配器将消息提交到消息引擎的方案的一系列事件：  
  
1.  适配器创建新消息并将数据流连接到该消息。  
  
2.  适配器从消息引擎中获取新批。  
  
3.  适配器将该消息添加到要提交的批中。  
  
4.  该批提交并在消息引擎线程池中排队。  
  
5.  消息引擎线程池开始处理该新批。  
  
6.  在接收管道中处理该消息。  
  
7.  接收管道将生成零个或更多个消息。 只要管道没有返回任何错误，它们就可以使用消息。 接收管道可以生成多个消息；这通常会在拆装器组件将单个交换拆装到多个消息时发生。 接收管道通常会将提交的消息规范化为 XML。  
  
8.  如果配置了映射，则管道生成的消息将在映射器中进行处理。  
  
9. 消息将发布到消息代理或 MessageBox 数据库。  
  
10. 消息引擎回调适配器，以通知它该批操作的结果。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [可恢复的交换处理](../core/recoverable-interchange-processing.md)  
  
-   [消息按序送达](../core/ordered-delivery-of-messages.md)  
  
-   [错误处理](../core/error-handling.md)  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 如何处理大消息](../core/how-biztalk-server-processes-large-messages.md)   
 [引擎性能特征](../core/engine-performance-characteristics.md)   
 [测量的最大可持续引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [用于测量引擎 MST 测试方案](../core/test-scenarios-for-measuring-mst-of-the-engine.md)   
 [使用 Microsoft BizTalk LoadGen 2007 工具](../core/using-the-microsoft-biztalk-loadgen-2007-tool.md)
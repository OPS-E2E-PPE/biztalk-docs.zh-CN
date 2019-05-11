---
title: 低延迟方案 Optimizations2 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19cd78ce-ad7d-4e4b-8188-a63d707905d5
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc6db1f67340092c27eea10f4847fa04b0269dab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396331"
---
# <a name="low-latency-scenario-optimizations"></a>低延迟方案优化
默认情况下，BizTalk Server 进行了优化的吞吐量而不是低延迟。 以下优化可以应用于 BizTalk Server 中，在要求减少了的延迟的情况中。  
  
> [!NOTE]  
>  这些优化将改善延迟，但可能会在执行此操作对总体吞吐量一些费用。  
  
## <a name="increase-the-biztalk-server-host-internal-message-queue-size"></a>增加 BizTalk Server 主机内部消息队列大小  
 每个 BizTalk 主机具有其自己的内部内存中队列。 增加此队列从 100 到 10000，以提高性能的低延迟方案的默认值的大小。 有关修改的内部消息队列大小值的详细信息，请参阅[如何修改资源基于阻止设置](http://go.microsoft.com/fwlink/?LinkID=208366)(http://go.microsoft.com/fwlink/?LinkID=208366) BizTalk Server 文档中。  
  
> [!NOTE]  
>  增加的内部消息队列大小值将增加的主机实例使用的内存。  
  
## <a name="increase-the-biztalk-server-host-in-process-messages"></a>增加 BizTalk Server 主机进程内消息数  
 增加从 1000年到 10,000 的默认值的进程内消息，以提高性能。 有关修改进程内消息的值的详细信息，请参阅[如何修改默认主机阻止设置](http://go.microsoft.com/fwlink/?LinkID=208366)(http://go.microsoft.com/fwlink/?LinkID=208366) BizTalk Server 文档中。  
  
> [!NOTE]  
>  增加的内部消息队列大小值将增加的主机实例使用的内存。  
  
## <a name="optimize-orchestrations-for-low-latency"></a>优化低延迟的业务的流程  
 请遵循中的"建议优化的低延迟方案的业务流程"部分建议[优化业务流程性能](../technical-guides/optimizing-orchestration-performance.md)。  
  
## <a name="configure-polling-intervals"></a>配置轮询间隔  
 使用设置仪表板以跨 BizTalk 组配置给定主机的轮询间隔。 若要更改轮询间隔：  
  
1. 在中**BizTalk Server 管理控制台**，展开**BizTalk Server 管理**，右键单击**BizTalk 组**，然后单击**设置**.  
  
2. 在**BizTalk 设置仪表板**对话框中，在**主机**页上，在**常规**选项卡上，在**轮询间隔**，您将发现**Messaging**并**业务流程**值。 默认情况下，这两个值都设置为 500 毫秒。  
  
   下表列出了我们用于测试 BizTalk 进程内 64 位主机 （RxHost、 TxHost 和 PxHost） 上的轮询值。 若要禁用轮询，可以将轮询间隔设置为一个非常大的数字作为在表中列出。  
  
|服务器主机|消息传送|业务流程|  
|------------------|---------------|-------------------|  
|**RxHost**<br /><br /> 由于我们仅发布传入消息与 BizTalk 消息框通过单向接收位置，因此 RxHost 上不需要轮询 （接收主机）。|200000|200000|  
|**TxHost**<br /><br /> 因为我们只从 BizTalk messagebox 中接收消息传送实例，业务流程轮询 TxHost （发送主机） 上不需要。|50|200000|  
|**PxHost**<br /><br /> 因为我们只从 BizTalk messagebox 中接收的业务流程实例，消息传送轮询上不需要 PxHost （处理主机）。|200000|50|  
  
## <a name="see-also"></a>请参阅  
 [优化 BizTalk Server 性能](../technical-guides/optimizing-biztalk-server-performance.md)
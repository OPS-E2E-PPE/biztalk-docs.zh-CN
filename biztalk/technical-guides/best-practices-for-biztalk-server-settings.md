---
title: "BizTalk Server 设置的最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e62024e1-f502-45a8-932f-edd8460bcf5f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf1f89ced33be6f10ceaae37ccb2c899c4e01eac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-biztalk-server-settings"></a>BizTalk Server 设置的最佳操作
本主题列出了执行的操作的准备情况过程时应遵循的最佳实践[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 **配置消息批处理，以便提高适配器性能**  
  
-   最小化适配器由的组合为一个批处理的多个操作的事务的数。  
  
-   限制基于总批处理，除了邮件计数中的字节数的批次大小。 有关限制的批次大小的详细信息，请参阅[配置批处理提高适配器性能](../technical-guides/configuring-batching-to-improve-adapter-performance.md)。  
  
 **调整大型消息阈值**  
  
-   若要增加吞吐量，增加大消息阈值，这样就降低了大型进行缓冲的消息数为在映射中磁盘。  
  
 **确定需要跟踪在规划过程的信息**  
  
-   应在规划阶段决定你需要跟踪的信息。这样一来，在部署项目后, 你可以设置跟踪选项并限制跟踪的数据为你提供所需的信息的量。  
  
    > [!NOTE]  
    >  有关与跟踪相关的最佳做法的详细信息，请参阅[规划跟踪](../technical-guides/planning-for-tracking.md)本指南中和[运行状况和活动跟踪](http://go.microsoft.com/fwlink/p/?LinkId=154187)(http://go.microsoft.com/fwlink/p/?LinkId=154187)。  
  
 **不跟踪所有消息**  
  
-   我们建议你不跟踪所有消息。 这是因为每次都需要一条消息，BizTalk Server 使该消息的另一个副本。 通过跟踪特定端口，而是可以缩小范围。 这有助于你的系统的性能最大化，并以使数据库整洁。  
  
 **在发送端口上设置跟踪和接收管道上的而不是端口**  
  
-   如果你设置跟踪选项卡上的管道，你还将设置使用管道的每个端口全局跟踪选项。 反过来，这可能会在导致被跟踪比你预期，这将降低系统性能的更多数据。 相反，你可以将端口设置跟踪选项卡上的发送和接收端口。  
  
 **调整限制基于资源使用率**  
  
-   限制在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置默认情况下提供系统的有效保护方式。 监视限制状态以查看限制是否正在进行的性能计数器。 然后仪表亲自，如果基于上限制的资源 （例如，数据库大小或内存使用率） 低于或高于利用。 接下来，调整，限制阈值正常运行或相应地关闭。 有关详细信息，请参阅[调整限制阈值： 何时和为何](http://go.microsoft.com/fwlink/p/?LinkId=154188)(http://go.microsoft.com/fwlink/p/?LinkId=154188)。  
  
 **如有可能使用 PassThruTransmit 管道**  
  
-   如果在将消息发送到其目标之前需要没有文档处理，而不是 XML 发送管道使用 PassThruTransmit 管道。  
  
 **最小化"形状开始和结束"的业务流程的使用情况跟踪事件**  
  
-   虽然跟踪的业务流程形状具有的业务流程调试的明显优势，但其性能和可伸缩性的影响。 **形状开始和结束**跟踪事件可能会导致很大的开销。 最好是尽量减少在较高的吞吐量是必要的生产环境中其使用情况。  
  
    > [!NOTE]  
    >  **调整开始和结束**默认情况下，所有的业务流程上启用跟踪事件。  
  
## <a name="see-also"></a>另请参阅  
 [清单： 配置 BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)
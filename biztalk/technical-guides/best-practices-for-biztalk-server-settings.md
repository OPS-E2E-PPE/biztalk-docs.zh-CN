---
title: BizTalk Server 设置的最佳实践 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e62024e1-f502-45a8-932f-edd8460bcf5f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd3cf2d75db87e82fd0fd012f028a2ad8bc1cc2e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401252"
---
# <a name="best-practices-for-biztalk-server-settings"></a>BizTalk Server 设置的最佳方案
本主题列出了执行的操作准备情况过程应遵循的最佳做法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 **配置消息批处理以提高适配器性能**  
  
- 通过组合多个到单个批处理操作由适配器执行的事务的数量降至最低。  
  
- 限制基于总消息计数除了在批处理中的字节数的批大小。 有关限制批处理大小的详细信息，请参阅[提高适配器性能配置批处理](../technical-guides/configuring-batching-to-improve-adapter-performance.md)。  
  
  **调整大消息阈值**  
  
- 若要增加吞吐量，增加大消息阈值，这样就降低了大型进行缓冲的消息数为在映射期间的磁盘。  
  
  **确定您需要在规划期间跟踪的信息**  
  
- 应在规划阶段确定需要跟踪的信息。这样一来，部署该项目之后, 您可以设置跟踪选项并限制跟踪的数据为你提供所需的信息的量。  
  
  > [!NOTE]  
  >  有关与跟踪相关的最佳做法的详细信息，请参阅[规划跟踪](../technical-guides/planning-for-tracking.md)本指南中并[运行状况与活动跟踪](http://go.microsoft.com/fwlink/p/?LinkId=154187)(http://go.microsoft.com/fwlink/p/?LinkId=154187)。  
  
  **不要跟踪所有消息**  
  
- 我们建议不跟踪所有消息。 这是消息的因为每次访问消息，BizTalk Server 将生成的另一个副本。 而是可以通过跟踪特定端口来缩小范围。 这可以帮助您的系统性能最大化和保持数据库整洁。  
  
  **将发送端口上设置跟踪和接收管道上的而不是端口**  
  
- 如果设置管道的跟踪选项，则还将设置为使用的管道的每个端口全局跟踪选项。 反过来，这可能会在导致被跟踪比你预期，这将降低系统性能的更多数据。 相反，您可以设置跟踪选项上的发送端口和接收端口。  
  
  **调整基于资源使用率的阻止功能**  
  
- 中的阻止行为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]默认提供良好的保护系统配置。 监视限制状态，以查看是否限制发生的性能计数器。 然后自行衡量阻止行为的资源为基础 （例如，数据库大小或内存使用率） 处于过利用。 接下来，调整阻止阈值相应地增减。 有关详细信息，请参阅[调整阻止阈值：何时以及为何](http://go.microsoft.com/fwlink/p/?LinkId=154188)(<http://go.microsoft.com/fwlink/p/?LinkId=154188>)。  
  
  **如果可能，请使用 PassThruTransmit 管道**  
  
- 如果消息发送到其目标之前不需要处理任何文档，而不是 XML 发送管道使用 PassThruTransmit 管道。  
  
  **最小化使用的业务流程"形状开始和结束"跟踪事件**  
  
- 虽然跟踪的业务流程形状的业务流程调试明显的优势，它具有性能和可伸缩性的影响。 **形状开始和结束**跟踪事件可能会导致很大的开销。 最好是尽量减少在较高的吞吐量是必要的生产环境中其使用情况。  
  
  > [!NOTE]  
  >  **形状开始和结束**默认情况下对所有业务流程启用跟踪事件。  
  
## <a name="see-also"></a>请参阅  
 [清单：配置 BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)
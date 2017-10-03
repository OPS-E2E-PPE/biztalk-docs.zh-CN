---
title: "清单： 执行每月性能检查 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa103777-af4d-480d-abc7-3c4718f493c1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3c1c84248fc3f5a7efdcc7e4df3f62b23bfcc82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-performing-monthly-performance-checks"></a>清单： 执行每月性能检查
本主题列出了应遵循按月以避免性能问题的最佳做法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。  
  
|步骤|参考|  
|-----------|---------------|  
|确定需要跟踪在规划过程的信息|应当在计划阶段确定需要跟踪的信息，以便在部署项目后可以设置跟踪选项并限制跟踪的数据量，从而仅为您提供所需的信息。 **注意：**有关与跟踪相关的最佳做法的详细信息，请参阅[规划跟踪](../technical-guides/planning-for-tracking.md)本指南中和[运行状况和活动跟踪](http://go.microsoft.com/fwlink/?LinkId=154187)(http://go.microsoft.com/fwlink/?LinkId = 154187) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档。|  
|不跟踪所有消息|我们建议你不跟踪所有消息，因为每次一条消息接触，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使另一个副本。 通过跟踪特定端口，而是可以缩小范围。 这有助于你的系统的性能最大化，并以使数据库整洁。|  
|不跟踪业务流程的所有事件|跟踪业务流程的所有事件可能会增加 dta_DebugTrace 和 dta_MessageInoutEvents 表的大小。 有关如何禁用跟踪为业务流程的说明，请参阅[禁用跟踪为业务流程](../technical-guides/how-to-disable-tracking.md#BKMK_DisableOrchTracking)。|  
|在发送端口上设置跟踪和接收管道上的而不是端口|如果你设置跟踪选项卡上的管道，你还将设置使用管道的每个端口全局跟踪选项。 反过来，这可能会在导致被跟踪比你预期，这将降低系统性能的更多数据。 相反，你可以将端口设置跟踪选项卡上的发送和接收端口。|  
|调整限制基于资源使用率|限制在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置默认情况下提供系统的有效保护方式。 监视性能计数器限制状态以查看是否限制是否正在进行，然后亲自仪表，如果基于上限制的资源 （例如，数据库大小或内存使用率） 低于或使用过度，，然后调整，限制阈值正常运行，或相应地关闭。 有关详细信息，请参阅[调整限制阈值： 何时和为何](http://go.microsoft.com/fwlink/?LinkId=154188)(http://go.microsoft.com/fwlink/?LinkId=154188)。|  
|如有可能使用 PassThruTransmit 管道|如果在将消息发送到其目标之前需要没有文档处理，而不是 XML 发送管道使用 PassThruTransmit 管道。|  
|各种各样的因素时考虑你调整 BizTalk 跟踪数据库的大小|-当 BizTalk 跟踪数据库的大小调整，可以通过将应变乘数添加到您的计算考虑 SQL Server 因素，如索引大小。<br />-当确定 BizTalk 跟踪数据库中的消息的大小，将添加消息上下文的平均大小到的消息大小如果一点很重要，相比的消息大小。<br />-若要限制 BizTalk 跟踪数据库中的消息的大小，则将提升的属性数目的限制。<br />-如果启用业务流程调试器选项，考虑到每个形状中业务流程的状态保存到 BizTalk 跟踪数据库中。|  
|将硬件解决方案，若要避免磁盘争用应用|若要避免 MessageBox 数据库中的磁盘争用，请执行以下操作：<br /><br /> -使用高速磁盘<br />-部署高速 SAN 上的数据库<br />-分隔 MessageBox 数据库分别放在独立于跟踪数据库的专用服务器<br />-Cpu 向上扩展并将更多的 Cpu 添加到专用的 MessageBox 数据库服务器<br />-将页面文件和/或 MSDTC 日志移到单独的驱动器<br /><br /> 有关如何避免数据库争用的详细信息，请参阅[如何避免磁盘争用](http://go.microsoft.com/fwlink/?LinkId=158809)(http://go.microsoft.com/fwlink/?LinkId=158809)。|  
  
## <a name="see-also"></a>另请参阅  
 [例程性能清单](../technical-guides/routine-performance-checklists.md)   
 [清单： 执行每周性能检查](../technical-guides/checklist-performing-weekly-performance-checks.md)
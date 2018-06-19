---
title: 查找 MST DTA 跟踪的提示和技巧 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d72e4ac-d952-4cff-9a65-491e20945d40
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9faaaf7ebb47ac7ec18d8df6d8cb7c6ebd48d7f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279877"
---
# <a name="tips-and-tricks-for-finding-mst-of-dta-tracking"></a>确定 DTA 跟踪的 MST 的提示与技巧
按照定义，MST 是使用恒负载以可重现方式度量系统性能的基准。 在下面介绍的情形中，了解 MST 将非常有用。  
  
1.  **如果需要从系统的最低延迟**。 超出 MST 将导致系统中出现积压，从而延长消息的延迟时间。 即使积压只是暂时性的，也会立即对延迟时间产生负面影响。 因此，通过了解您的系统 MST，也就可以知道应该实现的绝对最大吞吐量，超出该吞吐量，处理单独消息的延迟时间将会显著延长（例如，根据您的配置，可能会从秒钟一级延长到分钟一级）。  
  
2.  **将与其他系统进行比较时**。 例如，如果您想要验证与其他系统（例如，本主题中的情形、案例研究或您的环境中的其他系统）相比是否实现了预期的 MST；使用稳定的输入度量 MST 将提供可重现的、明确的比较标准。  
  
 但无论如何，度量 MST 可能很耗时。 因此，在您花很大气力去进行度量之前，应该权衡利益。 大多数生产系统都不会经历按 MST 度量的稳定的输入，其负载而是常常随时间变化。 必须在生产前对此负载状况进行最后测试以对系统进行验证。 幸运的是，您可以使用用于度量 MST 的相同技术来评估您的生产负载状况的可持续性。 只需将负载状况保持足够长的时间，以便包括一个或两个 BizTalkDTADb 数据库数据保留时段，然后观察关键性能指标 (KPI)。  
  
 特别要注意的是，应该使用一个空的 BizTalkDTADb 数据库来开始执行您的测试，无论是针对 MST 还是负载状况。 在 BizTalkDTADb 数据库中存储的数据是时间敏感数据；并且，如果数据不是每次测试一开始就再次获取的，则可能会导致测试结果出现偏差。 根据您的数据保留时段，这可能会大幅增加确定 MST 所用的时间。 为了缓解这一问题，在执行测试期间实时调整负载可能有助于更快地关注 MST。  
  
 例如，如果您发现经过了第一个保留时段后，KPI 指示您的系统还有余量来承受更高的吞吐量（例如，磁盘空闲时间仍高于零），则可以渐次增加您的负载并观察结果。 但在通过此方法优化您的 MST 评估后，务必要执行以空的 BizTalkDTADb 数据库开始的测试来验证您的评估。  
  
## <a name="recommendations"></a>建议  
 跟踪中的系统体系结构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]能够跟踪各种信息，并且必须管理和密切监视。 MST 所指示的影响系统性能的最重要因素包括：  
  
-   系统的预期吞吐量。  
  
-   为系统中每个消息和服务实例跟踪的信息量。 这将确定 BizTalkDTADb 数据库大小增加的速度，并且最终确定必须清除 BizTalkDTADb 数据库以避免速度过慢的频率。  
  
-   您希望将数据在 BizTalkDTADb 数据库中保留多长时间，即，数据保留时段。 该时段越长，BizTalkDTADb 数据库就会增长得越大，并且对吞吐量造成影响。  
  
-   您是将 BizTalkDTADb 数据库中的数据存档并且清除，还是只清除以保持 BizTalkDTADb 数据库大小。  
  
 查找对其进行跟踪的最大可持续吞吐量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]涉及三个关键绩效指标：  
  
-   DTAdb 数据文件磁盘子系统的物理磁盘空闲时间。  
  
-   后台处理深度  
  
-   BizTalkDTADbData 深度  
  
 通过监控这三个关键性能指标以便了解以下情况，确定您的系统的 MST 或者您的生产状况吞吐量：  
  
-   稳定的后台处理和 trackingdata 表深度。  
  
-   BizTalkDTADb 数据库数据文件磁盘物理空闲时间接近（但不持续稳定在）零。  
  
 使用 DTA 跟踪功能具有相关的性能影响。  默认跟踪不仅仅可以跟踪在生产中使用解决方案所需的内容，还可以通过提供丰富的问题解决信息，使开发以及初始测试和调试更容易。 因此，我们建议将默认跟踪放在开发和初始测试期间进行。 一旦在 BizTalk 上部署的解决方案稳定并可供生产验证（包括性能测试）后，建议您仔细检查生产中需要跟踪的信息量，以及信息需要保留在 BizTalkDTADb 数据库中的时间长度并相应调整。  
  
 例如，如果无需出于不可否认目的或问题解决目的跟踪消息正文，则不要启用消息正文跟踪。 为了说明这一点，在示例方案中所述[测量 MST DTA 跟踪的测试方案](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)，当消息正文跟踪的跟踪配置的组件已消除，MST 已增加了一倍到 40 个消息/秒。  
  
 此外，需要注意的是，即使发生问题，在许多情况下（但绝非全部情况），无需跟踪消息正文，消息在 MessageBox 数据库中就会被挂起并且可被检索和检查。  
  
 关注系统负载的可持续性：  
  
-   您的系统是否足以不受限制地承受生产负载状况，即使是在一般的维护活动下？  
  
-   如果发生导致系统要承受积压（例如计划内或计划外 BizTalkDTADb 数据库中断）的情况将怎么办？  
  
 最好基于最坏情况的方案设置目标并针对这些目标进行测试。 例如，如果您知道存在定期计划的维护周期并在该期间中 BizTalkDTADb 数据库将脱机，则在执行测试期间模拟这一中断，评估系统能否从导致的积压中恢复。  
  
## <a name="see-also"></a>另请参阅  
 [测量的最大可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [了解 DTA 跟踪性能行为](../core/understanding-dta-tracking-performance-behavior.md)   
 [用于测量 MST DTA 跟踪测试方案](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)   
 [跟踪数据库的大小调整准则](../core/tracking-database-sizing-guidelines.md)
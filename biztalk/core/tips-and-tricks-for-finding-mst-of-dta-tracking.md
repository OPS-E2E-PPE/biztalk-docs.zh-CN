---
title: DTA 跟踪的 Mst 的提示和技巧 |Microsoft Docs
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
ms.openlocfilehash: 56d36b6f6be249820e0e24e2ec76151ab47e620b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298646"
---
# <a name="tips-and-tricks-for-finding-mst-of-dta-tracking"></a>DTA 跟踪的 Mst 的提示和技巧
根据定义，MST 是以可重现方式度量使用常量负载的系统性能的基准。 以下是情况下，了解 MST 时特别有用。  
  
1. **当你需要从系统的最低延迟**。 超出 MST 将导致积压工作中在系统中，从而增加的延迟的消息。 即使积压只是临时的积压工作将会对延迟时间立即和负面影响。 因此，了解您的系统 MST 将告诉您应在单个消息 （例如，从秒到几分钟，具体取决于你的配置） 显著处理增加的延迟之前实现的绝对最大吞吐量。  
  
2. **将与其他系统进行比较时**。 例如，如果你想要验证您获得预期的 MST 相比到另一个系统 （例如，本主题、 案例研究或在你的环境中的另一个系统中的方案）;度量 MST 使用稳定的输入提供了一可重现的、 明确的标准，用于比较。  
  
   不用说，但是，它可以是度量 MST 的耗时。 因此，着手进行测量它之前，应该权衡利益。 大多数生产系统不会遇到的稳定的输入度量 MST，但负载而是随着时间推移而变化。 它是最终必须测试来验证系统在生产前的此负载配置文件。 幸运的是，您可以使用用于度量 MST 评估你的生产负载配置文件的可维持性的相同技术。 只需运行时间不足以包含一个或多个 BizTalkDTADb 数据库数据保留时段的加载配置文件并观察关键性能指标 (KPI)。  
  
   务必要开始在测试运行过程中，是否 MST 还是负载状况，使用一个空的 BizTalkDTADb 数据库操作。 存储在 BizTalkDTADb 数据库中的数据是时间敏感，如果它未重新获取从零开始的每个测试运行，但可能会扭曲结果。 具体取决于你的数据保留时段，这会大大增加找到 MST 所需的时间。 若要缓解此问题，在测试运行期间调整负载"动态"可在更多快地关注 MST。  
  
   例如，如果您发现已通过在第一个保留时段时间，Kpi 指示留有空间用于更高的吞吐量 （例如，磁盘空闲时间是仍高于零），可以以增量方式增加您的负载并观察效果。 但是，优化您以这种方式的 MST 评估后，是必须执行从一个空的 BizTalkDTADb 数据库来验证您的评估开始运行的测试。  
  
## <a name="recommendations"></a>建议  
 跟踪中的系统体系结构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]能够跟踪范围广泛的信息，并必须管理并仔细监视。 由 MST，最将影响您性能的因素是系统的，如下所示：  
  
- 系统所需的吞吐量。  
  
- 每个消息和服务实例在系统中跟踪的信息量。 这将确定 BizTalkDTADb 数据库的大小的增加速度，并最终何种频率 BizTalkDTADb 数据库必须清除以避免落在后面。  
  
- 多长时间，你想要保留在 BizTalkDTADb 数据库中，即，数据保持期窗口的数据。 该时段越长，较大 BizTalkDTADb 数据库将增加，对吞吐量造成影响。  
  
- 将存档的 BizTalkDTADb 数据库数据，以及清除，还是只清除以保持 BizTalkDTADb 数据库大小。  
  
  查找对其进行跟踪的最大可承受吞吐量的过程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]涉及三个关键性能指标：  
  
- 物理磁盘空闲时间 DTAdb 数据文件磁盘子系统。  
  
- 后台处理深度  
  
- BizTalkDTADbData 深度  
  
  查找您的系统的 MST 或通过监视寻找这些三个关键性能指标来验证你的生产状况吞吐量：  
  
- 稳定的后台处理和 trackingdata 表深度。  
  
- BizTalkDTADb 数据库数据文件磁盘物理空闲时间接近，但不是持续稳定，零。  
  
  使用 DTA 跟踪功能具有相关的性能影响。  默认跟踪，不仅仅所需的后一种解决方案是在生产中，但可以进行开发和初始测试和调试变得更容易通过提供丰富的问题解决信息可以跟踪。 因此，我们建议在开发和初始测试期间会保留在默认跟踪。 一旦 BizTalk 上部署的解决方案是稳定且可供生产证书，包括性能测试，则建议您仔细检查需要在生产中，跟踪的信息量和它需要的时间长度保留在 BizTalkDTADb 数据库中并相应地调整。  
  
  例如，如果不需要为任一的不可否认或问题解决目的跟踪消息正文，则不要启用消息正文跟踪。 为了说明这一点，在示例方案中所述[测试方案用于度量 MST 的 DTA 跟踪](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)，当消息正文跟踪的跟踪配置的组件已清除，MST 已增加一倍到 40 个消息/秒。  
  
  此外，请记住，即使出现了问题，在许多 （但不是全部） 情况下，消息在 MessageBox 数据库中挂起并可以检索和检查而无需跟踪消息正文。  
  
  重点放在系统负载的可持续性：  
  
- 您的系统可以承受生产负载状况无限期地甚至与一般的维护活动？  
  
- 如果发生导致系统要承受积压工作，例如计划内或计划外 BizTalkDTADb 数据库中断？  
  
  它是一个好办法设置基于最坏的情况和针对这些目标的测试的目标。 例如，如果您知道存在定期计划内的维护循环将采用 BizTalkDTADb 数据库离线，在测试运行以评估系统能够从生成积压中恢复期间模拟这一中断。  
  
## <a name="see-also"></a>请参阅  
 [测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [了解 DTA 跟踪性能行为](../core/understanding-dta-tracking-performance-behavior.md)   
 [测量 DTA 跟踪的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)   
 [跟踪数据库的大小调整准则](../core/tracking-database-sizing-guidelines.md)
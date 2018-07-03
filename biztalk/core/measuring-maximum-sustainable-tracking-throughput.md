---
title: 测量最大可承受跟踪吞吐量 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35605427-0217-4bdd-8b4a-3e68b3f5f452
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d68d1661a86858b8d2bca1bb067c8fa17ea421e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017057"
---
# <a name="measuring-maximum-sustainable-tracking-throughput"></a>度量最大可承受跟踪吞吐量
将行业解决方案部署到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 平台上之后，应跟踪并监视该系统，以了解以下信息：  
  
- 系统的执行情况  
  
- 可能出现的异常和错误以及出现的原因  
  
- 作为 BizTalk 解决方案实现的业务流程的当前状态  
  
  对许多组织而言，也很重要记录出于不可否认目的流经系统的实际原始消息。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了满足这些要求的两种类型的跟踪功能：  
  
- **数据跟踪和活动 (DTA) 跟踪**。 DTA 将跟踪用户定义的各种消息属性、业务流程调试事件、消息流事件以及服务实例状态。 您可以使用跟踪来查询存储在 BizTalk DTA 跟踪数据库 （BizTalkDTADb） 中的数据。 DTA 跟踪还包括原始消息（称为消息正文）的跟踪，以便防止抵赖和解决问题。  
  
- **业务活动监视 (BAM) 跟踪**。 BAM 将使用用户定义的跟踪配置文件来跟踪业务流程的状态，并将其记录到一组特殊的 BAM 数据库中。  
  
  本主题介绍了 DTA 结构以及确定使用 DTA 的系统可以无限维持的最大可承受吞吐量的系统方法。 尽管 DTA 和 BAM 共享某些结构组件，但本主题仅介绍 DTA 的行为。 有关 BAM 结构的信息，请参阅[业务活动监视 (BAM)](../core/business-activity-monitoring-bam.md)。  
  
## <a name="overview-of-dta-tracking-architecture"></a>DTA 跟踪结构概述  
 消息通过系统时，各种被跟踪的元素（如消息正文、属性和事件）会通过一系列流程和数据库，最终将这些元素写入 BizTalkDTADb 数据库中。 将这些元素写入 BizTalkDTADb 数据库之后，可以使用跟踪来查询被跟踪的信息。 有关设置和使用 BizTalkDTADb 数据库信息和跟踪，请参阅[查看历史记录和跟踪数据](../core/viewing-historical-and-tracked-data.md)。  
  
 为了确保系统具有可持续性并以给定的消息流量无限期运行，被跟踪元素到达 BizTalkDTADb 数据库所通过的路径以及数据库本身需要保持良好的状况。 例如，传输过程中在数据库表中生成的消息或在 DTA 生成的消息会导致未绑定数据库文件的增长，如果未得到正确管理，系统将无法承受。  
  
 因此，我们首先应了解结构和被跟踪信息通过的路径。 这将公开的重要资源和性能指标，必须监视以确定如何跟踪系统与消息流量流经保持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎。  
  
 下图显示了 DTA 跟踪结构和路径的概况：  
  
 ![DTA 跟踪概述](../core/media/dtatrackingoverview.gif "DTATrackingOverview")  
  
 按照图中编号进程的顺序，所有 DTA 跟踪的数据进出 BizTalkDTADb 数据库的过程如下所示：  
  
1. BizTalk Server 运行时进程包括一个称为侦听器的组件。 侦听器的工作是在运行时缓存被跟踪的元素，在下一次 MessageBox 数据库往返过程中（例如，将消息传输到 MessageBox 数据库中）将缓存的元素转发到 MessageBox 数据库。 侦听器通过查看跟踪配置（也称为跟踪配置文件，从管理数据库获取并缓存在每个主机运行时实例中以备侦听器使用）来确定要跟踪的元素。  
  
    如上图所示，向 MessageBox 数据库插入了以下两个数据流：  
  
   - 由 Spool 表表示的数据流  
  
   - 由 TrackingData 表表示的数据流  
  
     被跟踪的消息正文将使用这两个数据流。 即，消息正文本身（将它们视为 blob 数据）通过 Spool 表表示的一组表进行处理。 与消息正文相关联的消息事件（例如消息标识符、跟踪消息正文的时间、与消息正文相关联的实例）通过 TrackingData 表进行处理。 未与消息正文跟踪关联的所有被跟踪元素仅通过 TrackingData 表进行处理。  
  
2. MessageBox 数据库是被跟踪数据的第一站，用于缓存被跟踪的数据，这样，运行时可以继续处理，而不会直接被进一步的跟踪数据处理阻止。  
  
    若要获取跟踪的消息正文 (blob) 传输到 BizTalkDTADb 数据库可以在其中查看并将它们存档到更持久的存储，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]采用了称为 TrackedMessages_Copy_BizTalkMsgBoxDb 的每个 MessageBox 上运行的 SQL 代理作业数据库服务器。 此作业负责将标记为进行跟踪的消息正文复制到 BizTalkDTADb 数据库。  
  
3. 之外消息正文跟踪的数据的所有从 MessageBox 数据库移到 BizTalkDTADb 数据库由一个称为 TDDS 运行中的一个或多个服务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机。 只要通过 BizTalk Server 管理控制台中的主机属性页将主机配置为主机跟踪，TDDS 子服务就会在该主机的每个实例中运行。  
  
4. 除非定期清空 BizTalkDTADb 数据库，否则它将无限增长，最终导致运行问题。 称为 DTA 清除和存档 (BizTalkDTADb) 的 SQL 代理作业可执行清空 BizTalkDTADb 数据库的任务。 默认情况下，此作业每分钟运行一次，清除早于用户所配置时间（例如 24 小时）的所有已完成实例。  
  
    有关详细信息有关 DTA 清除和存档作业，请参阅[如何配置 DTA 清除和存档作业](../core/how-to-configure-the-dta-purge-and-archive-job.md)。  
  
5. 另外，DTA 清除和存档作业还可以将 BizTalkDTADb 数据作为 SQL 备份进行存档，以便更长久地存储和/或脱机查看这些数据。 如果需要查询存档的 BizTalkDTADb 数据，则首先必须在 SQL Server 中将数据还原为新数据库，则可以使用跟踪或 SQL 查询分析器工具查询数据。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [了解 DTA 跟踪性能行为](../core/understanding-dta-tracking-performance-behavior.md)  
  
-   [测量 DTA 跟踪的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)  
  
-   [ DTA 跟踪的 MST 的提示与技巧](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md)  
  
## <a name="see-also"></a>请参阅  
 [跟踪数据库的大小调整准则](../core/tracking-database-sizing-guidelines.md)
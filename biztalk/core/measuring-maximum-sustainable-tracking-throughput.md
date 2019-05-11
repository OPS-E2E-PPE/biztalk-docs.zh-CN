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
ms.openlocfilehash: 7938d0d16459028edb39dd1b73b5a9f2276e0e13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380031"
---
# <a name="measuring-maximum-sustainable-tracking-throughput"></a>度量最大可承受跟踪吞吐量
部署到企业解决方案的行后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]平台，你应跟踪并监视系统，以了解以下：  
  
- 了解系统的执行  
  
- 可能出现哪些异常和错误和原因  
  
- 作为 BizTalk 解决方案实现的业务流程的当前状态  
  
  对许多组织而言，也很重要记录出于不可否认目的流经系统的实际原始消息。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了满足这些要求的两种类型的跟踪功能：  
  
- **数据跟踪和活动 (DTA) 跟踪**。 DTA 跟踪的各种用户定义消息属性、 业务流程调试事件、 消息流事件和服务实例状态。 使用跟踪来查询存储在 BizTalk DTA 跟踪数据库 (BizTalkDTADb) 中的数据。 DTA 跟踪还包括原始消息，称为消息正文，出于不可否认和问题解决目的跟踪。  
  
- **业务活动监视 (BAM) 跟踪**。 BAM 使用用户定义的跟踪配置文件到一组特殊的 BAM 数据库中跟踪业务流程的状态。  
  
  在本主题中，我们介绍了 DTA 结构以及确定使用 DTA 的系统可以无限维持的最大可承受吞吐量的系统方法。 尽管 DTA 和 BAM 共享某些结构组件，但本主题介绍仅 DTA 的行为。 有关 BAM 结构的信息，请参阅[业务活动监视 (BAM)](../core/business-activity-monitoring-bam.md)。  
  
## <a name="overview-of-dta-tracking-architecture"></a>DTA 跟踪体系结构的概述  
 为整个系统的消息流，如消息正文、 属性和事件，各种被跟踪的元素通过一系列的进程，最终导致写入 BizTalkDTADb 数据库的数据库。 元素写入 BizTalkDTADb 数据库之后，可以使用跟踪来查询被跟踪的信息。 有关设置和使用 BizTalkDTADb 数据库信息和跟踪，请参阅[查看历史记录和跟踪数据](../core/viewing-historical-and-tracked-data.md)。  
  
 若要确保系统具有可持续性并以给定的消息流速率，到达 BizTalkDTADb 数据库，以及数据库本身，跟踪元素传递的路径将无限期地运行需要保持正常。 例如，在此过程中，数据库表中或在 DTA，构建的消息可能导致不受限制的数据库文件的增长，将无法承受如果未正确管理。  
  
 因此，让我们首先了解体系结构和跟踪信息通过的途径。 这将公开的重要资源和性能指标，必须监视以确定如何跟踪系统与消息流量流经保持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎。  
  
 下图显示概述 DTA 跟踪结构和路径。  
  
 ![DTA 跟踪概述](../core/media/dtatrackingoverview.gif "DTATrackingOverview")  
  
 在顺序中采用图中的带编号的过程，所有 DTA 都跟踪的数据流入流出 BizTalkDTADb 数据库，如下所示：  
  
1. BizTalk Server 运行时进程包括一个称为侦听器的组件。 侦听器的工作是缓存在运行时被跟踪的元素，并在下一步的 MessageBox 数据库往返转换 （例如，en 队列消息发送给 MessageBox 数据库），转发到 MessageBox 数据库缓存的元素。 侦听器确定要跟踪通过查看跟踪配置 （也称为跟踪配置文件） 从管理数据库中获取并缓存在使用每个主机运行时实例侦听器的元素。  
  
    上图中所示，有两个插入到 MessageBox 数据库中的数据流：  
  
   - 一个由后台处理表  
  
   - 通过 TrackingData 表  
  
     跟踪的消息正文使用这两个流。 也就是说，通过一组由 spool 表表示的表处理消息正文本身 （将它们视为 blob 数据）。 与消息正文的消息事件 （例如，消息标识符时跟踪消息正文，实例消息正文与相关联） 通过 TrackingData 表进行处理。 未与消息正文跟踪关联的所有被跟踪的元素通过 TrackingData 表仅进行处理。  
  
2. MessageBox 数据库仅跟踪的数据的第一站并用于缓存被跟踪的数据，以便在运行时可以继续处理而不会直接被阻止进一步的跟踪数据处理。  
  
    若要获取跟踪的消息正文 (blob) 传输到 BizTalkDTADb 数据库可以在其中查看并将它们存档到更持久的存储，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]采用了称为 TrackedMessages_Copy_BizTalkMsgBoxDb 的每个 MessageBox 上运行的 SQL 代理作业数据库服务器。 它负责将标记为进行到 BizTalkDTADb 数据库的跟踪消息正文复制此作业。  
  
3. 之外消息正文跟踪的数据的所有从 MessageBox 数据库移到 BizTalkDTADb 数据库由一个称为 TDDS 运行中的一个或多个服务[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机。 只要通过 BizTalk Server 管理控制台中的主机属性页情况下，将主机配置为主机跟踪，TDDS 子服务将该主机的每个实例中运行。  
  
4. 除非定期清空 BizTalkDTADb 数据库，它将无限增长最终导致运行问题。 没有名为 DTA 清除和存档 (BizTalkDTADb) 用于执行的清除 BizTalkDTADb 数据库的任务的单个 SQL 代理作业。 默认情况下，此作业每分钟运行一次，并清除所有已完成的实例早于用户所配置时间 （例如，24 小时）。  
  
    有关详细信息有关 DTA 清除和存档作业，请参阅[如何配置 DTA 清除和存档作业](../core/how-to-configure-the-dta-purge-and-archive-job.md)。  
  
5. （可选） DTA 清除和存档作业还可以作为 SQL 备份更长期的存储和/或脱机查看数据的存档的 BizTalkDTADb 数据。 如果需要查询存档的 BizTalkDTADb 数据，必须首先将其还原为 SQL Server 中的新数据库，然后使用跟踪或 SQL 查询分析器来对其进行查询。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [了解 DTA 跟踪性能行为](../core/understanding-dta-tracking-performance-behavior.md)  
  
-   [测量 DTA 跟踪的 MST 的测试方案](../core/test-scenarios-for-measuring-mst-of-dta-tracking.md)  
  
-   [ DTA 跟踪的 MST 的提示与技巧](../core/tips-and-tricks-for-finding-mst-of-dta-tracking.md)  
  
## <a name="see-also"></a>请参阅  
 [跟踪数据库的大小调整准则](../core/tracking-database-sizing-guidelines.md)
---
title: "存档和清除跟踪数据库 BizTalk |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, purging
- BizTalk Server, maintaining
- archiving [Tracking database]
- purging
- Tracking database, maintaining
- Tracking database, archiving
- maintaining, Tracking database
- maintaining, BizTalk Server
ms.assetid: 7014cf31-86e8-4829-8055-056442329009
caps.latest.revision: "37"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8fc75f5218ec7a189d28c7120cf23a3047c1752
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="archiving-and-purging-the-biztalk-tracking-database"></a>存档和清除 BizTalk 跟踪数据库
随着 BizTalk Server 在系统中处理的数据的增加，BizTalk 跟踪 (BizTalkDTADb) 数据库的大小也会持续增长。 不受控制的增长将会降低系统性能，并可能导致跟踪数据解码服务 (TDDS) 出错。 除了一般的跟踪数据之外，跟踪的消息也会在 MessageBox 数据库中累积，导致磁盘性能下降。  
  
 尽管早期版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 附带了用于存档跟踪的消息和消除 BizTalk 跟踪数据库的示例脚本，不过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可使用 DTA 消除和存档作业来自动执行这两个过程。 通过存档和清除 BizTalk 跟踪数据库中的数据，您可以保持一个运行状况良好的系统，并将跟踪数据进行存档以供将来使用。 由于 BizTalk 跟踪数据库存档会随着时间的推移不断累积而占用磁盘空间，因此最好定期将 BizTalk 跟踪数据库存档移至辅助存储空间。  
  
 在清除 BizTalk 跟踪数据库中的数据时，DTA 清除和存档作业将清除不同类型的跟踪信息，例如消息和服务实例信息、业务流程事件信息，以及规则引擎跟踪数据。  
  
 跟踪数据记录的保留时间取决于将跟踪数据插入 BizTalk 跟踪数据库的时间。 DTA 清除和存档作业使用时间戳来持续验证该记录是否早于数据生存时段。 在每一个生存时段之后，将对 BizTalk 跟踪数据库进行存档，并创建一个新的存档文件。 在作业计划指定的每个 SQL Server 代理作业时间间隔之后，将清除在该生存时段之前完成的所有跟踪数据。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用了“软清除”和“硬清除”概念。 软清除用来清除已完成的实例，而硬清除仅用来清除未完成的实例。  
  
 **软清除**  
  
 在 DTA 存档和清除作业中，LiveHours 和 LiveDays 参数之和就是要在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中维护的数据生存时段。 将清除与在此数据生存时段之前完成的实例相关联的所有数据。 默认情况下，不启用 DTA 存档和清除作业。 您必须先进行配置，然后才能启用该作业。  
  
 例如，你可以配置运行每隔 20 分钟，DTA 清除和存档作业，并将设置 LiveHours = 1 且 LiveDays = 0。 第一次此 SQL Server 代理作业运行 (T0)，通过创建存档花跟踪数据库的备份，并且一个条目保存在数据库中为此时间戳。 为了清除跟踪数据，必须保证存档成功。 如果存档成功，则与 1 小时前完成的实例相关联的所有数据都将被清除。 每次运行该作业时，都将清除 1 小时之前完成的数据。 在第 3 次运行时（1 小时后），将创建一个新的存档，它包含在前 1 小时内插入跟踪数据库的所有实例的数据。  
  
 为了与上面的示例相匹配，需要在 DTA 清除和存档作业中配置清除和存档的步骤，代码如下：  
  
```  
exec dtasp_BackupAndPurgeTrackingDatabase  
1, --@nLiveHours 1,   
0, --@nLiveDays   
1, --@nHardDeleteDays   
‘\\server\backup’, --@nvcFolder   
null, --@nvcValidatingServer   
0 --@fForceBackup Soft purge process  
```  
  
 最后一次备份的时间戳存储在 BizTalk 跟踪数据库中，以确保只清除上一存档中已有的数据。 为了增加可靠性，存档按大约 10 分钟的间隔依次重叠。 下图显示了基于上述示例的软清除过程。 请注意，存档和清除任务无需同时进行。  
  
 **软清除过程**  
  
 ![软清除进程](../core/media/archivingandpurging.gif "archivingandpurging")  
  
 **硬清除**  
  
 由于软清除只清除与已完成的实例相关联的数据，因此，如果存在许多无限期运行的循环实例，则跟踪数据库将会增长，并且这些实例将永远无法清除。 使用硬清除日期可以清除指定时间间隔之前的所有信息，只有指示服务存在的信息除外。 设置硬清除使用 **@nHardDeleteDays** 中 DTA 存档和清除作业步骤中的参数存档和清除。 硬清除设置应始终大于软清除设置。 换而言之，  **@nHardDeleteDays** 应大于的总和 **@nLiveHours** 和 **@nLiveDays** 。  
  
 存档和清除所包括的功能如下表所述：  
  
|功能|Description|  
|-------------|-----------------|  
|硬清除|使用该功能，可以配置一个时间间隔来清除指定日期之前的示例信息。|  
|将跟踪的消息复制到跟踪数据库|使用“CopyTrackedMessageToDTA”选项，可以直接将跟踪的消息从 MessageBox 服务器复制到 BizTalk 跟踪数据库中。 使用 DTA 清除和存档作业清除数据时，要求进行此操作。|  
|存档验证|使用该功能，可以选择设置一个辅助数据库服务器，以便在创建存档时对其进行验证。|  
|多个 BizTalk 跟踪数据库版本的跟踪支持|这使您能够将跟踪支持与 [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] 和 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] 数据库存档一起使用。|  
|减少跟踪数据|在不减少生成的任何跟踪信息的情况下，显著减少存储的跟踪数据的数量。 这样可以降低跟踪数据库的增长速度。|  
|更快的跟踪操作，对数据库架构进行了显著优化|使您可以使用跟踪任务在大型数据库中查找消息和服务实例；已对此功能进行了显著优化。|  
  
> [!NOTE]
>  如果存在通过清除 BizTalk 跟踪数据库暂时得以解决的性能问题，并且希望对 BizTalk 进行控制以便不再收集跟踪信息，则可能要考虑禁用全局跟踪功能。 有关禁用全局跟踪功能的信息，请参阅“如何禁用全局跟踪”。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [清单： 存档和清除 BizTalk 跟踪数据库](../core/checklist-archiving-and-purging-the-biztalk-tracking-database.md)  
  
-   [如何配置用于存档和清除数据从跟踪数据库 BizTalk BTS_BACKUP_USERS 角色](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)  
  
-   [如何配置 DTA 清除和存档作业](../core/how-to-configure-the-dta-purge-and-archive-job.md)  
  
-   [如何从 BizTalk 跟踪数据库清除数据](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [如何从 BizTalk 跟踪数据库手动清除数据](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [如何启用自动存档验证](../core/how-to-enable-automatic-archive-validation.md)  
  
-   [如何将跟踪的消息复制到跟踪数据库 BizTalk](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)  
  
-   [提高了存档和清除过程的性能](../core/improving-the-performance-of-the-archiving-and-purging-process.md)  
  
-   [如何关闭全局跟踪](../core/how-to-turn-off-global-tracking.md)
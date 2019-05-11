---
title: 存档和清除跟踪数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7014cf31-86e8-4829-8055-056442329009
caps.latest.revision: 37
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99d1d1e65ff943c2a677abc5e71fea4248955f73
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358972"
---
# <a name="archive-and-purge-the-biztalkdtadb-database"></a>存档和清除 BizTalkDTADb 数据库

## <a name="overview"></a>概述
当 BizTalk Server 处理越来越多的数据，你的系统上，BizTalk 跟踪 (BizTalkDTADb) 数据库将不断增长的大小。 受控制的增长会降低系统性能，并且可能会生成错误中跟踪数据解码服务 (TDDS)。 除了常规的跟踪数据，系统可能还会跟踪的消息累积在 MessageBox 数据库中，从而导致磁盘性能下降。  
  
BizTalk Server 会自动将这两个进程使用 DTA 清除和存档作业。 通过存档和清除 BizTalk 跟踪数据库中的数据，你可以保持系统正常运行，以及将存档以供将来使用的跟踪数据。 BizTalk 跟踪数据库存档累积一段时间，占用磁盘空间，因为它是移动到辅助存储定期存档 BizTalk 跟踪数据库的一个好办法。  
  
 当 BizTalk 跟踪数据库中清除数据时，DTA 清除和存档作业清除不同类型的跟踪信息，例如消息和服务实例信息、 业务流程事件信息和规则引擎跟踪数据。  
  
 跟踪数据插入到 BizTalk 跟踪数据库的跟踪数据记录基于时间的期限。 DTA 清除和存档作业使用时间戳来持续验证记录是否早于数据生存时段。 每一个生存时段之后存档 BizTalk 跟踪数据库并创建一个新的存档文件。 指定作业计划的每个 SQL Server 代理作业时间间隔，在完成所有较旧的跟踪数据不是该生存时段都将被清除。  
  
 BizTalk Server 使用软清除和硬清除的概念。 软清除用来清除已完成的实例，而硬清除仅用来清除未完成的实例。  
  
## <a name="soft-purge"></a>软清除
  
 在 DTA 存档和清除作业中，LiveHours 和 LiveDays 参数之和是想要维护 BizTalk Server 环境中的数据生存时段。 清除与数据的保留时间超过此生存时段的已完成实例相关联的所有数据。 默认情况下不启用 DTA 存档和清除作业。 您必须首先配置，然后启用该作业。  
  
 例如，可配置 DTA 清除和存档作业来运行每隔 20 分钟，并设置： LiveHours = 1 和 LiveDays = 0。 第一次此 SQL Server 代理作业运行时 (T0)，它将通过创建存档跟踪数据库的备份和具有此时间戳在数据库中保存一个条目。 存档成功才可清除跟踪数据。 如果存档成功，然后清除与在前一小时内完成的实例相关联的所有数据。 每次运行作业时，将清除 1 小时之前已完成的数据。 (1 小时后） 第三个运行时，被创建新的存档，其中包含已插入到跟踪数据库中的最后一小时段的所有实例的数据。  
  
 下面是如何将配置存档和清除与示例匹配 DTA 清除和存档作业中步骤：  
  
```  
exec dtasp_BackupAndPurgeTrackingDatabase  
1, --@nLiveHours 1,   
0, --@nLiveDays   
1, --@nHardDeleteDays   
‘\\server\backup’, --@nvcFolder   
null, --@nvcValidatingServer   
0 --@fForceBackup Soft purge process  
```  
  
 上次备份的时间戳存储在 BizTalk 跟踪数据库中，并确保在上一存档中是否只清除数据。 为了增加可靠性，存档按大约 10 分钟重叠。 下图中，基于上述示例中，显示了软清除过程。 请注意，存档和清除任务确实不一定会出现在同一时间。  
  
 **软清除过程**  
  
 ![软清除过程](../core/media/archivingandpurging.gif "archivingandpurging")  
  
## <a name="hard-purge"></a>硬清除
  
 由于软清除只清除与已完成的实例，如果您具有无限期运行的多个循环实例，然后跟踪数据库会增长，并且这些实例将永远无法清除关联的数据。 硬清除日期可以早于指定的间隔清除除外，该值指示服务存在的信息的所有信息。 设置硬清除使用<strong>@nHardDeleteDays</strong>中存档和清除参数在 DTA 存档和清除作业步骤。 硬清除设置应始终大于软清除设置。 换而言之， <strong>@nHardDeleteDays</strong>应大于的总和<strong>@nLiveHours</strong>并<strong>@nLiveDays</strong>。  
  
 存档和清除包括下表中所述的功能：  
  
|功能|Description|  
|-------------|-----------------|  
|硬清除|可以配置一个时间间隔来清除早于指定日期的不完整实例的信息。|  
|将跟踪的消息复制到跟踪数据库|使用 copytrackedmessagetodta 选项，则可直接复制跟踪的消息从 MessageBox 服务器到 BizTalk 跟踪数据库。 这是为了清除数据使用 DTA 清除和存档作业所必需的。|  
|存档验证|可以选择性地设置辅助数据库服务器来验证存档，因为它们创建。|  
|跟踪对多个 BizTalk 跟踪数据库版本的支持|使您可以使用跟踪支持与 BizTalk Server 数据库存档。|  
|减少跟踪数据|极大地减少了跟踪数据存储而不会降低生成任何跟踪信息的量。 这会导致在跟踪数据库的速度较慢增长。|  
|更快的跟踪操作，在数据库架构进行了显著优化|使你可以使用跟踪任务在大型数据库; 查找消息和服务实例此功能已显著优化。|  
  
> [!NOTE]
>  如果您遇到暂时解决通过清除 BizTalk 跟踪数据库的性能问题，并且你想要配置 BizTalk，不再收集跟踪信息，你可能想要考虑禁用全局跟踪。 请参阅[禁用全局跟踪](../core/how-to-turn-off-global-tracking.md)。  
  
## <a name="next-steps"></a>后续步骤
  
-   [清单：存档和清除 BizTalk 跟踪数据库](../core/checklist-archiving-and-purging-the-biztalk-tracking-database.md)  
  
-   [配置 BTS_BACKUP_USERS 角色以存档和清除 BizTalk 跟踪数据库中的数据](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)  
  
-   [配置 DTA 清除和存档作业](../core/how-to-configure-the-dta-purge-and-archive-job.md)  
  
-   [从 BizTalk 跟踪数据库中清除数据](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [从 BizTalk 跟踪数据库中手动清除数据](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [启用自动存档验证](../core/how-to-enable-automatic-archive-validation.md)  
  
-   [将跟踪的消息复制到 BizTalk 跟踪数据库](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)  
  
-   [提高存档和清除进程的性能](../core/improving-the-performance-of-the-archiving-and-purging-process.md)  
  
-   [禁用全局跟踪](../core/how-to-turn-off-global-tracking.md)
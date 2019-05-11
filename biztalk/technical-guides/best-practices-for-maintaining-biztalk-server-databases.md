---
title: 维护 BizTalk Server 数据库的最佳实践 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93333f41-ee83-4b64-b381-66584a7d5551
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 259bc2d01401341e3cd8e7fb928fa373dfecfa3e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242684"
---
# <a name="best-practices-for-maintaining-biztalk-server-databases"></a>维护 BizTalk Server 数据库的最佳做法
本主题列出了维护的一些最佳做法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。  
  
- 请确保 SQL Server 代理正在运行的 SQL Server 上。 在 SQL Server 代理停止后，不能运行负责数据库维护的内置 BizTalk SQL Server 代理作业。 此行为会导致数据库增长，这种增长可能导致性能问题。 有关监视 SQL Server 代理作业的信息，请参阅[监视 SQL Server 代理作业](../technical-guides/monitoring-sql-server-agent-jobs.md)。  
  
- 请确保 SQL Server LDF 和 MDF 文件是不同的驱动器上。 具有的 LDF 和 MDF 文件 BizTalkMsgBoxDb 和 BizTalkDTADb 数据库所在的驱动器上可能会导致磁盘争用。  
  
- 不要启用消息正文跟踪，不需要的功能。 通常情况下，你可能想要启用消息正文跟踪开发和对解决方案进行故障排除时。 如果是这样，请确保禁用消息正文跟踪完成后。 如果保留消息正文跟踪的启用，BizTalk Server 数据库增长。 如果你有业务需求要求您启用消息正文跟踪，确认**TrackedMessages_Copy_BizTalkMsgBoxDb**并**DTA 清除和存档**运行 SQL Server 代理作业已成功。  
  
- 通常情况下，较小的事务日志会导致更好的性能。 若要减小事务日志，配置**备份 BizTalk Server**更频繁地运行 SQL Server 代理作业。 有关详细信息，请参阅[BizTalk Server 数据库优化白皮书](http://go.microsoft.com/fwlink/?LinkId=153594)(http://go.microsoft.com/fwlink/?LinkId=153594)。  
  
- 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最佳做法分析器 (BPA) 来评估现有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。 BPA 执行许多与数据库相关的检查。 您可以下载中的 BizTalk Server Best Practices Analyzer 工具[BizTalk Server Best Practices Analyzer 工具](http://go.microsoft.com/fwlink/?LinkId=83317)(<http://go.microsoft.com/fwlink/?LinkId=83317>)。  
  
## <a name="see-also"></a>请参阅  
 [清单：维护和故障排除 BizTalk Server 数据库](~/technical-guides/checklist-maintaining-and-troubleshooting-biztalk-server-databases.md)   
 [大量增长的 BizTalk Server 数据库表](../technical-guides/large-growing-biztalk-server-database-tables.md)
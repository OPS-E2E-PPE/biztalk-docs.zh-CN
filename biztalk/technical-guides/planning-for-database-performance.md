---
title: "为数据库性能规划 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7212fa37-88e0-4b5f-af97-c72063357645
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1338088acc91a45572ae1b49131d99f6c58cb739
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-database-performance"></a>规划数据库性能
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是极数据库密集型应用程序可能需要最多 13 不同数据库中 Microsoft 创建[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 数据库密集型的性质，因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它是至关重要的一点是你选择的适当版本和版本的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，将容纳[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 若要运行的计算机的性能优化[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]该 house[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请遵循本主题中和在的建议[BizTalk Server 数据库优化](http://go.microsoft.com/fwlink/?LinkID=101578)白皮书 ([http://go.microsoft.com/fwlink/?LinkID=101578](http://go.microsoft.com/fwlink/?LinkID=101578))。  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]数据库必须安装在任何一个[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]或[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]。  
  
> [!NOTE]  
>  虽然为其他版本的编写这份白皮书[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，你可以使用的相同建议[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]和[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]  /  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]。  
  
## <a name="considerations-for-sql-server-editions"></a>SQL Server 版本的注意事项  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库应配置为在尽可能的专用 SQL Server 实例上运行。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库密集型应用程序，因此分离[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机承载的 SQL Server 计算机和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库将提高性能，应予以考虑在生产中的最佳实践[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境.  
  
 各种版本的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]提供不同的功能，这可能会影响性能的你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 例如，在高负载情况下可用数数据库可用于的 32 位版本的锁[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]可能超过，这是对 BizTalk 解决方案的性能造成不利影响。 请考虑存放在 64 位版本的 SQL Server 上你 MessageBox 的数据库，如果你在测试环境中遇到"超出锁"错误。 在 64 位版本的 SQL Server 上，可用锁定的数目将大大增加。  
  
 请考虑下面当决定在数据库引擎功能的表将需要为您的 BizTalk 环境。 对于小规模的解决方案，例如，运行时[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]分支版本[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]  /  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] Workgroup Edition 可能满足住房[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。 对于大比例，需要群集的企业级解决方案支持，BizTalk 日志传送支持，或 Analysis Services 支持，则你将需要[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]  /  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] Enterprise 版本到内部[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库。  
  
|版本和版本的 SQL Server|64 位支持|多实例支持|群集的支持|Analysis Services|  
|---------------------------------------|---------------------|-----------------------------|------------------------|-----------------------|  
|SQL Server 2008 SP1 / SQL Server 2008 R2 企业版|是|是|是|是|  
|[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] / [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]Standard Edition|是|是|是 （2 个节点）|是|  
|[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)] / [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]Workgroup Edition|是|是|“否”|是|  
  
> [!NOTE]  
>  BAM RTA 需要[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]  /  [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] Enterprise Edition。  
  
 有关的各个版本支持的功能的完整列表[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]，请参阅[支持的版本的 SQL Server 2008 R2 功能](http://go.microsoft.com/fwlink/?LinkId=151940)([http://go.microsoft.com/fwlink/?LinkId = 151940](http://go.microsoft.com/fwlink/?LinkId=151940)) 中[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]文档。
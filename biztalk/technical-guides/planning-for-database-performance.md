---
title: 规划数据库性能 |Microsoft 文档
ms.custom: ''
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7212fa37-88e0-4b5f-af97-c72063357645
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 878320cf7c6a5762626087964033430afcf611cf
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009502"
---
# <a name="planning-for-database-performance"></a>规划数据库性能

## <a name="overview"></a>概述
Microsoft BizTalk Server 是极数据库密集型应用程序，可能需要 Microsoft SQL Server 中最多 13 个单独的数据库的创建。 由于 BizTalk Server 的数据库密集型特性，它是一点的至关重要是一点的你选择的适当版本和将承载 BizTalk Server 数据库的 SQL server 的版本。 若要优化承载 BizTalk Server 数据库的计算机运行 SQL Server 的性能，请按照本主题中和在的建议[BizTalk Server 数据库优化](optimizing-database-performance.md)。
  

> [!NOTE]  
>  尽管本指南针对其他版本的 BizTalk Server 和 SQL Server 编写的你可以对较新版本使用相同的建议。
  
## <a name="considerations-for-sql-server-editions"></a>SQL Server 版本的注意事项  
 BizTalk Server 数据库应配置为在尽可能的专用 SQL Server 实例上运行。 BizTalk Server 是数据库密集型应用程序，因此单独的 BizTalk Server 计算机和承载 BizTalk Server 数据库的 SQL Server 计算机将改进性能，以及应考虑在生产 BizTalk Server 中的最佳实践环境。  
  
 各种版本的 SQL Server 提供不同的功能，这可能会影响你的 BizTalk 服务器环境的性能。 例如，在高负载情况下可用于 SQL Server 的 32 位版本的可用的数据库锁的数目可能超过，这是对 BizTalk 解决方案的性能造成不利影响。 请考虑存放在 64 位版本的 SQL Server 上你 MessageBox 的数据库，如果你在测试环境中遇到"超出锁"错误。 在 64 位版本的 SQL Server 上，可用锁定的数目将大大增加。  
  
 请考虑下面当决定在数据库引擎功能的表将需要为您的 BizTalk 环境。 对于小规模解决方案，例如当运行 BizTalk Server 分支版，SQL Server Workgroup Edition 可能是够用的用于容纳 BizTalk Server 数据库。 大比例，需要群集的支持，企业级解决方案为 BizTalk 日志传送的支持或 Analysis Services 支持，则你需要以承载数据库的 SQL Server Enterprise Edition。  
  
|版本的 SQL Server|64 位支持|多实例支持|群集的支持|Analysis Services|  
|---|---|---|---|---|  
|SQL Server Enterprise Edition|是|是|是|是|  
|SQL Server Standard Edition|是|是|是 （2 个节点）|是|  
|SQL Server Workgroup Edition|是|是|“否”|是|  
  
> [!NOTE]  
>  BAM RTA 需要 SQL Server Enterprise Edition。  
  
 有关各个版本支持的功能的完整列表，请参阅[支持的 SQL Server 的版本功能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)。
---
title: 规划数据库性能 |Microsoft Docs
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
ms.openlocfilehash: cbbf9c072289b177779ed8ae3a991f58b9f26efe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394611"
---
# <a name="planning-for-database-performance"></a>规划数据库性能

## <a name="overview"></a>概述
Microsoft BizTalk Server 是极其数据库密集型应用程序可能要求的 Microsoft SQL Server 中最多 13 个单独的数据库创建的。 由于 BizTalk Server 的数据库密集型性质，它是至关重要的任务选择适当的版本和版本的 SQL Server 来存放 BizTalk Server 数据库问题。 若要优化运行 SQL Server 的计算机承载 BizTalk Server 数据库的性能，请按照建议在本主题并在[BizTalk Server 数据库优化](optimizing-database-performance.md)。
  

> [!NOTE]  
>  虽然本指南针对其他版本的 BizTalk Server 和 SQL Server 编写的您可能可以较新版本使用相同的建议。
  
## <a name="considerations-for-sql-server-editions"></a>SQL Server 版本的注意事项  
 应将 BizTalk Server 数据库配置为只要有可能的专用 SQL Server 实例上运行。 BizTalk Server 是数据库密集型应用程序，因此，分离的 BizTalk Server 计算机和承载 BizTalk Server 数据库的 SQL Server 计算机将提高性能，应考虑生产 BizTalk Server 中的最佳做法环境。  
  
 各种版本的 SQL Server 提供不同的功能，这可能会影响 BizTalk Server 环境的性能。 例如，在高负载情况下是可用于 32 位版本的 SQL Server 的可用的数据库锁的数目可能会被超出，这是对 BizTalk 解决方案的性能造成不利影响。 请考虑保存 MessageBox 数据库上的 SQL Server 的 64 位版本，如果您在测试环境中遇到"内存不足"错误。 可用锁的数目是 64 位版本的 SQL Server 上高得多。  
  
 请考虑下时确定数据库引擎功能的表将需要为您的 BizTalk 环境。 对于小规模的解决方案，例如当运行 BizTalk Server 分支版，SQL Server Workgroup Edition 可以满足用于容纳 BizTalk Server 数据库。 较大的比例，需要群集的支持，企业级解决方案的 BizTalk 日志传送支持或 Analysis Services 支持，则需要 SQL Server Enterprise Edition 来承载数据库。  
  
|版本的 SQL Server|64 位支持|多实例支持|群集的支持|Analysis Services|  
|---|---|---|---|---|  
|SQL Server 企业版|是|是|是|是|  
|SQL Server 标准版|是|是|是 （2 个节点）|是|  
|SQL Server Workgroup Edition|是|是|否|否|  
  
> [!NOTE]  
>  BAM RTA 需要 SQL Server Enterprise Edition。  
  
 有关各个版本支持的功能的完整列表，请参阅[SQL server 各个版本支持的功能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)。
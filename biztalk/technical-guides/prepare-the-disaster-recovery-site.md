---
title: "准备灾难恢复站点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b66f3c8-afe0-4ac0-b925-8f780d14bd4b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2119de8d5f8625943374d262b063491d2dafa6d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-the-disaster-recovery-site"></a>准备灾难恢复站点
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]日志传送有两个受支持的方案。 其中一个是日志传送的所有生产实例上的所有数据库位置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应用于的一个灾难恢复实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 另一种情形是其中日志传送的每个生产实例数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应用于的相应实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在灾难恢复站点。 请注意，它将完全支持，以具有相同数目的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库灾难恢复站点中的实例，因为没有在生产环境中，但在更少的物理服务器上。 此部分提供了这些准备工作的指南。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [准备灾难恢复 SQL 服务器](../technical-guides/preparing-the-disaster-recovery-sql-servers.md)  
  
-   [备份 BAM 分析和跟踪 Analysis Server 数据库](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)  
  
-   [准备灾难恢复 BizTalk 服务器](../technical-guides/preparing-the-disaster-recovery-biztalk-servers.md)  
  
-   [准备应用程序的灾难恢复](../technical-guides/preparing-applications-for-disaster-recovery.md)  
  
-   [如何还原主密钥服务器](../technical-guides/how-to-restore-the-master-secret-server.md)
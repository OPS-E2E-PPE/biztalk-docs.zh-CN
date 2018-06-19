---
title: 准备灾难恢复站点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b66f3c8-afe0-4ac0-b925-8f780d14bd4b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a60be6d04d0f73013f67c5fe8e5b0144357fd1f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008862"
---
# <a name="prepare-the-disaster-recovery-site"></a>准备灾难恢复站点
BizTalk Server 日志传送有两个受支持的方案。 其中一个是日志传送的所有生产实例上的所有数据库位置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应用于的一个灾难恢复实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 另一种情形是其中日志传送的每个生产实例数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应用于的相应实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在灾难恢复站点。 请注意，它将完全支持，以具有相同数目的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库灾难恢复站点中的实例，因为没有在生产环境中，但在更少的物理服务器上。 此部分提供了这些准备工作的指南。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [准备灾难恢复 SQL Server](../technical-guides/preparing-the-disaster-recovery-sql-servers.md)  
  
-   [备份 BAM 分析和跟踪 Analysis Server 数据库](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)  
  
-   [准备灾难恢复 BizTalk Server](../technical-guides/preparing-the-disaster-recovery-biztalk-servers.md)  
  
-   [准备灾难恢复应用程序](../technical-guides/preparing-applications-for-disaster-recovery.md)  
  
-   [如何还原主密钥服务器](../technical-guides/how-to-restore-the-master-secret-server.md)
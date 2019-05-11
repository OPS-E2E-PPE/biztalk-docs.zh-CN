---
title: 准备灾难恢复站点 |Microsoft Docs
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
ms.openlocfilehash: 0b59adfbbb9ae8d995c3518eaa5c7491fa0179a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65252860"
---
# <a name="prepare-the-disaster-recovery-site"></a>准备灾难恢复站点
BizTalk Server 日志传送有两个支持的方案。 一个是日志传送的所有生产实例上所有数据库的位置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应用于的一个灾难恢复实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。 另一种方案是，日志传送数据库的每个生产实例的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应用于的相应实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在灾难恢复站点。 请注意，它将完全支持，具有相同数量的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库灾难恢复站点中的实例，因为没有在生产环境中，但更少的物理服务器上。 此部分提供了这些准备指南。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [准备灾难恢复 SQL Server](../technical-guides/preparing-the-disaster-recovery-sql-servers.md)  
  
-   [备份 BAM 分析和跟踪 Analysis Server 数据库](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)  
  
-   [准备灾难恢复 BizTalk Server](../technical-guides/preparing-the-disaster-recovery-biztalk-servers.md)  
  
-   [准备灾难恢复应用程序](../technical-guides/preparing-applications-for-disaster-recovery.md)  
  
-   [如何还原主密钥服务器](../technical-guides/how-to-restore-the-master-secret-server.md)
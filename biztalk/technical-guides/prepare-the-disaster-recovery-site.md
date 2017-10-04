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
# <a name="prepare-the-disaster-recovery-site"></a><span data-ttu-id="ac99b-102">准备灾难恢复站点</span><span class="sxs-lookup"><span data-stu-id="ac99b-102">Prepare the Disaster Recovery Site</span></span>
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]<span data-ttu-id="ac99b-103">日志传送有两个受支持的方案。</span><span class="sxs-lookup"><span data-stu-id="ac99b-103"> log shipping has two supported scenarios.</span></span> <span data-ttu-id="ac99b-104">其中一个是日志传送的所有生产实例上的所有数据库位置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应用于的一个灾难恢复实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ac99b-104">One is where log shipping for all databases on all production instances of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is applied to a single disaster recovery instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="ac99b-105">另一种情形是其中日志传送的每个生产实例数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]应用于的相应实例[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]在灾难恢复站点。</span><span class="sxs-lookup"><span data-stu-id="ac99b-105">The other scenario is where log shipping for the databases for each production instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] is applied to a corresponding instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] at the disaster recovery site.</span></span> <span data-ttu-id="ac99b-106">请注意，它将完全支持，以具有相同数目的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库灾难恢复站点中的实例，因为没有在生产环境中，但在更少的物理服务器上。</span><span class="sxs-lookup"><span data-stu-id="ac99b-106">Note that it is fully supported to have the same number of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] database instances in the disaster recovery site as there is in production but on fewer physical servers.</span></span> <span data-ttu-id="ac99b-107">此部分提供了这些准备工作的指南。</span><span class="sxs-lookup"><span data-stu-id="ac99b-107">This section provides guidance on these preparations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac99b-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="ac99b-108">In This Section</span></span>  
  
-   [<span data-ttu-id="ac99b-109">准备灾难恢复 SQL 服务器</span><span class="sxs-lookup"><span data-stu-id="ac99b-109">Preparing the Disaster Recovery SQL Servers</span></span>](../technical-guides/preparing-the-disaster-recovery-sql-servers.md)  
  
-   [<span data-ttu-id="ac99b-110">备份 BAM 分析和跟踪 Analysis Server 数据库</span><span class="sxs-lookup"><span data-stu-id="ac99b-110">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)  
  
-   [<span data-ttu-id="ac99b-111">准备灾难恢复 BizTalk 服务器</span><span class="sxs-lookup"><span data-stu-id="ac99b-111">Preparing the Disaster Recovery BizTalk Servers</span></span>](../technical-guides/preparing-the-disaster-recovery-biztalk-servers.md)  
  
-   [<span data-ttu-id="ac99b-112">准备应用程序的灾难恢复</span><span class="sxs-lookup"><span data-stu-id="ac99b-112">Preparing Applications for Disaster Recovery</span></span>](../technical-guides/preparing-applications-for-disaster-recovery.md)  
  
-   [<span data-ttu-id="ac99b-113">如何还原主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="ac99b-113">How to Restore the Master Secret Server</span></span>](../technical-guides/how-to-restore-the-master-secret-server.md)
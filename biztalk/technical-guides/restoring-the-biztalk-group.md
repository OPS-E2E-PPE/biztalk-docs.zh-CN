---
title: 正在还原 BizTalk 组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14a9af44-d6de-49c7-9600-21ece389727f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 938ac612a7a107e30d1a02fb09f9218a22705d13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291268"
---
# <a name="restoring-the-biztalk-group"></a><span data-ttu-id="22c31-102">正在还原 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="22c31-102">Restoring the BizTalk Group</span></span>
<span data-ttu-id="22c31-103">BizTalk 组由的一套[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services 数据库、 SSIS 包和 SQL 代理作业。</span><span class="sxs-lookup"><span data-stu-id="22c31-103">The BizTalk group is represented by the set of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases, SSIS packages, and SQL Agent Jobs.</span></span> <span data-ttu-id="22c31-104">本部分介绍还原 BizTalk 组的过程。</span><span class="sxs-lookup"><span data-stu-id="22c31-104">This section describes the process for restoring the BizTalk group.</span></span>  
  
 <span data-ttu-id="22c31-105">在的需要切换到目标系统 （灾难恢复站点），则必须完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="22c31-105">In the event that a switchover to the destination system (disaster recovery site) is required, the following steps must be completed:</span></span>  
  
1. <span data-ttu-id="22c31-106">还原[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和 Analysis Services 数据库。</span><span class="sxs-lookup"><span data-stu-id="22c31-106">Restore [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and Analysis Services databases.</span></span>  
  
2. <span data-ttu-id="22c31-107">还原 BizTalk Server 运行时服务器和应用程序。</span><span class="sxs-lookup"><span data-stu-id="22c31-107">Restore BizTalk Server runtime servers and applications.</span></span>  
  
   <span data-ttu-id="22c31-108">在灾难恢复站点，在完成这些步骤，建立的 BizTalk 组[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时服务器可以进行配置，并且应用程序可部署到 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="22c31-108">Upon completion of these steps, the BizTalk group has been established at the disaster recovery site, the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime servers can be configured, and the applications can be deployed into the BizTalk group.</span></span> <span data-ttu-id="22c31-109">在本部分中的主题介绍此过程的详细信息。</span><span class="sxs-lookup"><span data-stu-id="22c31-109">The topics in this section cover the details of this process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22c31-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="22c31-110">In This Section</span></span>  
  
-   [<span data-ttu-id="22c31-111">在源系统上停止应用程序处理</span><span class="sxs-lookup"><span data-stu-id="22c31-111">Stopping Application Processing on the Source System</span></span>](../technical-guides/stopping-application-processing-on-the-source-system.md)  
  
-   [<span data-ttu-id="22c31-112">如何在备份 BizTalk Server 作业中还原数据库</span><span class="sxs-lookup"><span data-stu-id="22c31-112">How to Restore Databases in the Backup BizTalk Server Job</span></span>](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)  
  
-   [<span data-ttu-id="22c31-113">还原备份 BizTalk Server 作业中不包含的数据库</span><span class="sxs-lookup"><span data-stu-id="22c31-113">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)
---
title: "还原 BizTalk 组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14a9af44-d6de-49c7-9600-21ece389727f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c12a1deff8fea6d769f138aa34bf6dab269a167f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-the-biztalk-group"></a><span data-ttu-id="6fdf6-102">还原 BizTalk 组</span><span class="sxs-lookup"><span data-stu-id="6fdf6-102">Restoring the BizTalk Group</span></span>
<span data-ttu-id="6fdf6-103">BizTalk 组都由套[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services 数据库、 SSIS 包和 SQL 代理作业。</span><span class="sxs-lookup"><span data-stu-id="6fdf6-103">The BizTalk group is represented by the set of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases, SSIS packages, and SQL Agent Jobs.</span></span> <span data-ttu-id="6fdf6-104">本部分介绍还原 BizTalk 组的过程。</span><span class="sxs-lookup"><span data-stu-id="6fdf6-104">This section describes the process for restoring the BizTalk group.</span></span>  
  
 <span data-ttu-id="6fdf6-105">事件中适配器转换到目标系统 （灾难恢复站点） 是必需的则必须完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6fdf6-105">In the event that a switchover to the destination system (disaster recovery site) is required, the following steps must be completed:</span></span>  
  
1.  <span data-ttu-id="6fdf6-106">还原[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和 Analysis Services 数据库。</span><span class="sxs-lookup"><span data-stu-id="6fdf6-106">Restore [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and Analysis Services databases.</span></span>  
  
2.  <span data-ttu-id="6fdf6-107">还原[!INCLUDE[prague](../includes/prague-md.md)]运行时服务器和应用程序。</span><span class="sxs-lookup"><span data-stu-id="6fdf6-107">Restore [!INCLUDE[prague](../includes/prague-md.md)] runtime servers and applications.</span></span>  
  
 <span data-ttu-id="6fdf6-108">在灾难恢复站点上，在完成这些步骤，建立 BizTalk 组[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以配置运行时服务器，并且可以将应用程序部署到 BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="6fdf6-108">Upon completion of these steps, the BizTalk group has been established at the disaster recovery site, the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime servers can be configured, and the applications can be deployed into the BizTalk group.</span></span> <span data-ttu-id="6fdf6-109">本部分中的主题介绍此过程的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6fdf6-109">The topics in this section cover the details of this process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6fdf6-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="6fdf6-110">In This Section</span></span>  
  
-   [<span data-ttu-id="6fdf6-111">停止处理源系统上的应用程序</span><span class="sxs-lookup"><span data-stu-id="6fdf6-111">Stopping Application Processing on the Source System</span></span>](../technical-guides/stopping-application-processing-on-the-source-system.md)  
  
-   [<span data-ttu-id="6fdf6-112">如何还原备份的 BizTalk Server 作业中的数据库</span><span class="sxs-lookup"><span data-stu-id="6fdf6-112">How to Restore Databases in the Backup BizTalk Server Job</span></span>](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)  
  
-   [<span data-ttu-id="6fdf6-113">还原数据库备份的 BizTalk Server 作业中不包括</span><span class="sxs-lookup"><span data-stu-id="6fdf6-113">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>](../technical-guides/restoring-databases-not-included-in-the-backup-biztalk-server-job.md)
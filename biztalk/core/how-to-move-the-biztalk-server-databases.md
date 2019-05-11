---
title: 将 BizTalk Server 数据库移 |Microsoft Docs
description: 将 BizTalk Server 数据库移到新的服务器，包括停止服务以及使用 SQL Server 代理作业的步骤
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec302e6d-c89d-4fe7-849f-97b5566e8ba4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baa475b4e8e9cbf63cc921451bb7ae19d6857c57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335898"
---
# <a name="how-to-move-the-biztalk-server-databases"></a><span data-ttu-id="5d8c7-103">如何移动 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="5d8c7-103">How to Move the BizTalk Server Databases</span></span>

## <a name="overview"></a><span data-ttu-id="5d8c7-104">概述</span><span class="sxs-lookup"><span data-stu-id="5d8c7-104">Overview</span></span>
<span data-ttu-id="5d8c7-105">可以使用此过程来移动主[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库迁移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-105">You can use this procedure to move the primary [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases to another server.</span></span> <span data-ttu-id="5d8c7-106">此相同的基本过程还可用于移动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库从本地[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]到远程[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]群集。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-106">This same basic procedure can also be used to move the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases from a local [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] to a remote [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] or to a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="5d8c7-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="5d8c7-107">Prerequisites</span></span>  
<span data-ttu-id="5d8c7-108">是的成员的帐户登录[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]sysadmin 固定的服务器角色才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-108">Sign in with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
## <a name="move-steps"></a><span data-ttu-id="5d8c7-109">移动步骤</span><span class="sxs-lookup"><span data-stu-id="5d8c7-109">Move steps</span></span>
  
1. <span data-ttu-id="5d8c7-110">停止所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]服务。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-110">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="5d8c7-111">有关详细信息，请参阅[重新启动 BizTalk Server 服务和关闭的 BizTalk Server](how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-111">For more information, see [Restart BizTalk Server Services, and shut down BizTalk Server](how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>
  
   > [!IMPORTANT]
   >  <span data-ttu-id="5d8c7-112">很重要，确保所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]移动数据库之前停止的服务和作业。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-112">It is critical to make sure that all the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services and jobs are stopped before you move the databases.</span></span>  
  
2. <span data-ttu-id="5d8c7-113">停止 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-113">Stop the IIS service.</span></span>  
  
3. <span data-ttu-id="5d8c7-114">停止 SQL Server 代理服务。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-114">Stop the SQL Server Agent service.</span></span>  
  
4. <span data-ttu-id="5d8c7-115">备份 BizTalk 数据库的数据库备份过程中所述[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-115">Back up the BizTalk databases by following the database backup procedures as described at [Backing Up and Restoring the BizTalk Server Databases](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span></span>  
  
5. <span data-ttu-id="5d8c7-116">还原以下数据库的新服务器上的 BizTalk 数据库还原过程在[如何还原您数据库](../core/how-to-restore-your-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-116">Restore the BizTalk databases on the new server following the database restore procedures at [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span>  
  
6. <span data-ttu-id="5d8c7-117">SQL Server 代理作业下面列出传输到新服务器中所述的脚本[如何备份和还原 SQL 代理作业](../core/how-to-back-up-and-restore-sql-agent-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-117">Script the SQL Server Agent jobs listed below for transfer to the new server, as described at [How to Back Up and Restore SQL Agent Jobs](../core/how-to-back-up-and-restore-sql-agent-jobs.md).</span></span>  <span data-ttu-id="5d8c7-118">若要重新创建作业在新服务器上运行各个脚本。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-118">Run each of the scripts on the new server to recreate the jobs.</span></span>  
  
    <span data-ttu-id="5d8c7-119">若要重新创建作业在新服务器上运行各个脚本。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-119">Run each of the scripts on the new server to recreate the jobs.</span></span> <span data-ttu-id="5d8c7-120">某些作业，如**备份 BizTalk Server (BizTalkMsgBoxDb)** 作业，必须进行重新配置，除非新服务器的文件路径和服务器名称与旧服务器相同。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-120">Certain jobs, such as the **Backup BizTalk Server (BizTalkMsgBoxDb)** job, will have to be reconfigured unless the new server file paths and server name are identical to the old server.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5d8c7-121">此外可以使用 SSIS/DTS**传输作业**任务将作业移动到新服务器，但大多数用户可能会发现它更轻松地使用 SQL Management Studio 作业编写脚本。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-121">You can also use the SSIS/DTS **Transfer Jobs** task to move the jobs to the new server, but most users will probably find it easier to script the jobs using SQL Management Studio.</span></span>  
  
7. <span data-ttu-id="5d8c7-122">除了上一步中所述，脚本编写 SQL Server 代理作业，你必须还编写登录脚本中所述[如何备份和还原 SQL Server 登录名](../core/how-to-back-up-and-restore-sql-server-logins.md)。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-122">In addition to scripting SQL Server Agent jobs as described in the previous step, you must also script logins as described in [How to Back Up and Restore SQL Server Logins](../core/how-to-back-up-and-restore-sql-server-logins.md).</span></span> <span data-ttu-id="5d8c7-123">需要在目标服务器上还原这些登录名。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-123">These logins need to be restored on the destination server.</span></span>  
  
8. <span data-ttu-id="5d8c7-124">还原[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]按照数据库的步骤 9 到 22 英寸[如何还原您数据库](../core/how-to-restore-your-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-124">Restore the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases by following steps 9 through 22 in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="5d8c7-125">此过程用 BizTalk 数据库的新位置更新 BizTalk 管理 (BizTalkMgmtDb) 数据库和注册表。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-125">This procedure updates the BizTalk Management (BizTalkMgmtDb) database and registry with the new location of the BizTalk databases.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5d8c7-126">在中**SampleUpdateInfo.xml**文件中，注释掉除之外的数据库的所有已迁移到新的服务器。</span><span class="sxs-lookup"><span data-stu-id="5d8c7-126">In the **SampleUpdateInfo.xml** file, comment out all of the databases except for those you have moved to the new server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d8c7-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d8c7-127">See Also</span></span>  
 [<span data-ttu-id="5d8c7-128">移动 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="5d8c7-128">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)
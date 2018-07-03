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
ms.openlocfilehash: 7a3509a6a0297b0f58a16cfd3eff1dc29420232b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978902"
---
# <a name="how-to-move-the-biztalk-server-databases"></a><span data-ttu-id="5b6f3-103">如何移动 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="5b6f3-103">How to Move the BizTalk Server Databases</span></span>

## <a name="overview"></a><span data-ttu-id="5b6f3-104">概述</span><span class="sxs-lookup"><span data-stu-id="5b6f3-104">Overview</span></span>
<span data-ttu-id="5b6f3-105">可以使用此过程来将主 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库移动到其他服务器。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-105">You can use this procedure to move the primary [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases to another server.</span></span> <span data-ttu-id="5b6f3-106">还可以使用此基本的相同过程将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库从本地 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 移动到远程 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 或 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 群集。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-106">This same basic procedure can also be used to move the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases from a local [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] to a remote [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] or to a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] cluster.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="5b6f3-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="5b6f3-107">Prerequisites</span></span>  
<span data-ttu-id="5b6f3-108">是的成员的帐户登录[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]sysadmin 固定的服务器角色才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-108">Sign in with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
## <a name="move-steps"></a><span data-ttu-id="5b6f3-109">移动步骤</span><span class="sxs-lookup"><span data-stu-id="5b6f3-109">Move steps</span></span>
  
1. <span data-ttu-id="5b6f3-110">停止所有的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-110">Stop all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services.</span></span> <span data-ttu-id="5b6f3-111">有关详细信息，请参阅[重新启动 BizTalk Server 服务和关闭的 BizTalk Server](how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-111">For more information, see [Restart BizTalk Server Services, and shut down BizTalk Server](how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>
  
   > [!IMPORTANT]
   >  <span data-ttu-id="5b6f3-112">确保在移动数据库之前停止所有的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 服务和作业非常重要。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-112">It is critical to make sure that all the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] services and jobs are stopped before you move the databases.</span></span>  
  
2. <span data-ttu-id="5b6f3-113">停止 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-113">Stop the IIS service.</span></span>  
  
3. <span data-ttu-id="5b6f3-114">停止 SQL Server 代理服务。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-114">Stop the SQL Server Agent service.</span></span>  
  
4. <span data-ttu-id="5b6f3-115">备份 BizTalk 数据库的数据库备份过程中所述[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-the-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-115">Back up the BizTalk databases by following the database backup procedures as described at [Backing Up and Restoring the BizTalk Server Databases](../core/backing-up-and-restoring-the-biztalk-server-databases.md).</span></span>  
  
5. <span data-ttu-id="5b6f3-116">还原以下数据库的新服务器上的 BizTalk 数据库还原过程在[如何还原您数据库](../core/how-to-restore-your-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-116">Restore the BizTalk databases on the new server following the database restore procedures at [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span>  
  
6. <span data-ttu-id="5b6f3-117">SQL Server 代理作业下面列出传输到新服务器中所述的脚本[如何备份和还原 SQL 代理作业](../core/how-to-back-up-and-restore-sql-agent-jobs.md)。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-117">Script the SQL Server Agent jobs listed below for transfer to the new server, as described at [How to Back Up and Restore SQL Agent Jobs](../core/how-to-back-up-and-restore-sql-agent-jobs.md).</span></span>  <span data-ttu-id="5b6f3-118">在新服务器上运行每个脚本以重新创建作业。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-118">Run each of the scripts on the new server to recreate the jobs.</span></span>  
  
    <span data-ttu-id="5b6f3-119">在新服务器上运行每个脚本以重新创建作业。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-119">Run each of the scripts on the new server to recreate the jobs.</span></span> <span data-ttu-id="5b6f3-120">某些作业，如**备份 BizTalk Server (BizTalkMsgBoxDb)** 作业，必须进行重新配置，除非新服务器的文件路径和服务器名称与旧服务器相同。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-120">Certain jobs, such as the **Backup BizTalk Server (BizTalkMsgBoxDb)** job, will have to be reconfigured unless the new server file paths and server name are identical to the old server.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5b6f3-121">此外可以使用 SSIS/DTS**传输作业**任务将作业移动到新服务器，但大多数用户可能会发现它更轻松地使用 SQL Management Studio 作业编写脚本。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-121">You can also use the SSIS/DTS **Transfer Jobs** task to move the jobs to the new server, but most users will probably find it easier to script the jobs using SQL Management Studio.</span></span>  
  
7. <span data-ttu-id="5b6f3-122">除了上一步中所述，脚本编写 SQL Server 代理作业，你必须还编写登录脚本中所述[如何备份和还原 SQL Server 登录名](../core/how-to-back-up-and-restore-sql-server-logins.md)。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-122">In addition to scripting SQL Server Agent jobs as described in the previous step, you must also script logins as described in [How to Back Up and Restore SQL Server Logins](../core/how-to-back-up-and-restore-sql-server-logins.md).</span></span> <span data-ttu-id="5b6f3-123">需要在目标服务器上还原这些登录信息。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-123">These logins need to be restored on the destination server.</span></span>  
  
8. <span data-ttu-id="5b6f3-124">还原[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]按照数据库的步骤 9 到 22 英寸[如何还原您数据库](../core/how-to-restore-your-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-124">Restore the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases by following steps 9 through 22 in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="5b6f3-125">此过程用 BizTalk 数据库的新位置来更新 BizTalk 管理 (BizTalkMgmtDb) 数据库和注册表。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-125">This procedure updates the BizTalk Management (BizTalkMgmtDb) database and registry with the new location of the BizTalk databases.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="5b6f3-126">在中**SampleUpdateInfo.xml**文件中，注释掉除之外的数据库的所有已迁移到新的服务器。</span><span class="sxs-lookup"><span data-stu-id="5b6f3-126">In the **SampleUpdateInfo.xml** file, comment out all of the databases except for those you have moved to the new server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b6f3-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b6f3-127">See Also</span></span>  
 [<span data-ttu-id="5b6f3-128">移动 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="5b6f3-128">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)
---
title: 如何自定义数据库的备份 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- custom databases
- customizing, custom databases
- backing up, custom databases
ms.assetid: 86bebf3c-968e-4fad-9dab-ced1b04aaac7
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba90f39a90e2a80abda1a00214aafec48c6ea419
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387080"
---
# <a name="how-to-back-up-custom-databases"></a><span data-ttu-id="84454-102">如何备份自定义数据库</span><span class="sxs-lookup"><span data-stu-id="84454-102">How to Back Up Custom Databases</span></span>
<span data-ttu-id="84454-103">因为自定义数据库未安装与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则不包含在要进行标记和由备份 BizTalk Server 作业备份的数据库的默认列表。</span><span class="sxs-lookup"><span data-stu-id="84454-103">Because your custom databases are not installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], they are not included in the default list of databases to be marked and backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="84454-104">如果你想要备份自定义数据库的备份 BizTalk Server 作业，必须手动将数据库添加到备份 BizTalk Server 作业。</span><span class="sxs-lookup"><span data-stu-id="84454-104">If you want the Backup BizTalk Server job to back up your custom databases, you must manually add the databases to the Backup BizTalk Server job.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="84454-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="84454-105">Prerequisites</span></span>  
  
1. <span data-ttu-id="84454-106">SQL Server 必须配置为使用完整恢复模式来确保数据完整性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库备份集。</span><span class="sxs-lookup"><span data-stu-id="84454-106">SQL Server must be configured to use the full recovery model to ensure the integrity of data in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backup sets.</span></span>  <span data-ttu-id="84454-107">有关详细信息请参阅[日志传送](../core/log-shipping.md)。</span><span class="sxs-lookup"><span data-stu-id="84454-107">For more information see [Log Shipping](../core/log-shipping.md).</span></span>  
  
2. <span data-ttu-id="84454-108">若要备份自定义数据库，必须使用有权访问每个要备份的数据库用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="84454-108">To back up your custom databases, you must be logged on with a user account that has access to each of the databases you are backing up.</span></span>  
  
    <span data-ttu-id="84454-109">BizTalk Server 包含名为 BTS_BACKUP_USERS，以便你用来备份数据库的用户帐户不需要在 SQL Server 中，除了控制备份过程的主服务器的系统管理员权限的 SQL Server 角色。</span><span class="sxs-lookup"><span data-stu-id="84454-109">BizTalk Server includes a SQL Server role named BTS_BACKUP_USERS so that the user account you use to back up your databases does not require System Administrator permissions within SQL Server, except for the primary server controlling the backup process.</span></span>  
  
    <span data-ttu-id="84454-110">您用来备份数据库的用户帐户进行设置，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="84454-110">When setting up the user account that you are using to back up your databases, note the following:</span></span>  
  
   -   <span data-ttu-id="84454-111">必须创建此用户，一个 SQL Server 登录帐户，并将此用户分配到每个服务器上的 BizTalk BTS_BACKUP_USERS 角色。</span><span class="sxs-lookup"><span data-stu-id="84454-111">You must create a SQL Server logon account for this user, and assign this user to the BizTalk BTS_BACKUP_USERS role on each server.</span></span>  
  
   -   <span data-ttu-id="84454-112">BizTalk Server 备份作业可以配置为在不同于用于 SQL Server 代理服务的用户帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="84454-112">The BizTalk Server backup jobs can be configured to run under a user account that is different than the one used for the SQL Server Agent service.</span></span>  
  
   -   <span data-ttu-id="84454-113">必须配置为域帐户下运行的 SQL Server 代理服务。</span><span class="sxs-lookup"><span data-stu-id="84454-113">You must configure the SQL Server Agent service to run under a domain account.</span></span> <span data-ttu-id="84454-114">如果所有数据库都都在同一计算机上，可以配置 SQL Server 代理以使用本地帐户。</span><span class="sxs-lookup"><span data-stu-id="84454-114">If all databases are on the same computer, you can configure SQL Server Agent to use a local account.</span></span>  
  
### <a name="to-back-up-custom-databases"></a><span data-ttu-id="84454-115">若要备份自定义数据库</span><span class="sxs-lookup"><span data-stu-id="84454-115">To back up custom databases</span></span>  
  
1. <span data-ttu-id="84454-116">生成新的数据库中的对象：</span><span class="sxs-lookup"><span data-stu-id="84454-116">Build the objects in the new database:</span></span>  
  
   - <span data-ttu-id="84454-117">浏览到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema 目录，然后对所有你想要备份的自定义数据库运行 Backup_Setup_All_Procs.sql 和 Backup_Setup_All_Tables.sql。</span><span class="sxs-lookup"><span data-stu-id="84454-117">Browse to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema directory, and then run Backup_Setup_All_Procs.sql and Backup_Setup_All_Tables.sql against all your custom databases that you want to back up.</span></span> <span data-ttu-id="84454-118">这将创建必要的过程、 表和角色并将权限分配给存储过程。</span><span class="sxs-lookup"><span data-stu-id="84454-118">This creates the necessary procedures, table, and role and assigns permissions to the stored procedures.</span></span>  
  
2. <span data-ttu-id="84454-119">执行以下配置：</span><span class="sxs-lookup"><span data-stu-id="84454-119">Perform the following configurations:</span></span>  
  
   -   <span data-ttu-id="84454-120">链接托管到托管新数据库的 SQL server 的 BizTalk 管理数据库的 SQL server。</span><span class="sxs-lookup"><span data-stu-id="84454-120">Link the SQL server that is hosting the BizTalk Management database to the SQL server hosting the new database.</span></span> <span data-ttu-id="84454-121">用于管理 SQL Server 上运行的 SQL Server 代理服务帐户必须是映射到每台计算机上备份的数据库所在的域帐户。</span><span class="sxs-lookup"><span data-stu-id="84454-121">The account used to run the SQL Server Agent service on the management SQL Server must be a domain account that is mapped to each computer holding a database to be backed up.</span></span> <span data-ttu-id="84454-122">如果数据库位于同一台计算机上则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="84454-122">If the databases are on the same computer you can skip this step.</span></span> <span data-ttu-id="84454-123">这是自动完成。</span><span class="sxs-lookup"><span data-stu-id="84454-123">This is done automatically.</span></span>  
  
   -   <span data-ttu-id="84454-124">宿主管理 SQL Server 上运行的 SQL Server 代理服务的帐户的新数据库的 SQL server 上添加一个登录名。</span><span class="sxs-lookup"><span data-stu-id="84454-124">Add a login on the SQL server hosting the new database for the account running the SQL Server Agent service on the Mgmt SQL Server.</span></span> <span data-ttu-id="84454-125">如果数据库位于同一台计算机上则可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="84454-125">If the databases are on the same computer you can skip this step.</span></span>  
  
   -   <span data-ttu-id="84454-126">在上一步中创建的登录名的新数据库中添加用户并将其添加到 BTS_BACKUP_USERS 角色。</span><span class="sxs-lookup"><span data-stu-id="84454-126">Add a user in the new database for the login created in the previous step and add them to the BTS_BACKUP_USERS role.</span></span> <span data-ttu-id="84454-127">此角色创建并授予了所需过程的 Execute 权限的步骤 1 中的脚本。</span><span class="sxs-lookup"><span data-stu-id="84454-127">This role is created and granted Execute permissions on the necessary procedures by the scripts in step 1.</span></span>  
  
3. <span data-ttu-id="84454-128">在 BizTalk 管理 (BizTalkMgmtDb) 数据库中，使用 SQL Server 企业管理器或 SQL Server Management Studio 中，修改**adm_OtherBackupDatabases**表为每个自定义数据库加入一行。</span><span class="sxs-lookup"><span data-stu-id="84454-128">Using SQL Server Enterprise Manager or SQL Server Management Studio, in the BizTalk Management (BizTalkMgmtDb) database, modify the **adm_OtherBackupDatabases** table to include a row for each of your custom databases.</span></span>  
  
4. <span data-ttu-id="84454-129">下表中所示在相应列中键入新的服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="84454-129">Type the new server and database names in the corresponding columns, as shown in the following table.</span></span>  
  
   |<span data-ttu-id="84454-130">“列”</span><span class="sxs-lookup"><span data-stu-id="84454-130">Column</span></span>|<span data-ttu-id="84454-131">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="84454-131">Value</span></span>|  
   |------------|-----------|  
   |<span data-ttu-id="84454-132">DefaultDatabaseName</span><span class="sxs-lookup"><span data-stu-id="84454-132">DefaultDatabaseName</span></span>|<span data-ttu-id="84454-133">自定义数据库的友好名称。</span><span class="sxs-lookup"><span data-stu-id="84454-133">The friendly name of your custom database.</span></span>|  
   |<span data-ttu-id="84454-134">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="84454-134">DatabaseName</span></span>|<span data-ttu-id="84454-135">自定义数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="84454-135">The name of your custom database.</span></span>|  
   |<span data-ttu-id="84454-136">ServerName</span><span class="sxs-lookup"><span data-stu-id="84454-136">ServerName</span></span>|<span data-ttu-id="84454-137">运行 SQL Server 的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="84454-137">The name of the computer running SQL Server.</span></span>|  
   |<span data-ttu-id="84454-138">BTSServerName</span><span class="sxs-lookup"><span data-stu-id="84454-138">BTSServerName</span></span>|<span data-ttu-id="84454-139">BizTalk Server 的名称。</span><span class="sxs-lookup"><span data-stu-id="84454-139">The name of the BizTalk Server.</span></span> <span data-ttu-id="84454-140">不使用此值，但尽管如此，它必须包含值。</span><span class="sxs-lookup"><span data-stu-id="84454-140">This value is not used, but it must contain a value nonetheless.</span></span>|  
  
   <span data-ttu-id="84454-141">在下次运行备份 BizTalk Server 作业，它会将自定义数据库。</span><span class="sxs-lookup"><span data-stu-id="84454-141">The next time you run the Backup BizTalk Server job, it will back up your custom databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84454-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="84454-142">See Also</span></span>  
 <span data-ttu-id="84454-143">[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="84454-143">[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md) </span></span>  
 [<span data-ttu-id="84454-144">有关备份和还原的高级信息</span><span class="sxs-lookup"><span data-stu-id="84454-144">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)
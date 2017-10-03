---
title: "如何备份自定义数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom databases
- customizing, custom databases
- backing up, custom databases
ms.assetid: 86bebf3c-968e-4fad-9dab-ced1b04aaac7
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2993de90de3f7b768cc5368012d1f27f8940a99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-back-up-custom-databases"></a><span data-ttu-id="c486c-102">如何备份自定义数据库</span><span class="sxs-lookup"><span data-stu-id="c486c-102">How to Back Up Custom Databases</span></span>
<span data-ttu-id="c486c-103">由于自定义数据库不随 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起安装，因此它们不包含在可由备份 BizTalk Server 作业进行标记并备份的数据库的默认列表中。</span><span class="sxs-lookup"><span data-stu-id="c486c-103">Because your custom databases are not installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], they are not included in the default list of databases to be marked and backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="c486c-104">如果希望备份 BizTalk Server 作业对自定义数据库进行备份，则必须手动将自定义数据库添加到备份 BizTalk Server 作业中。</span><span class="sxs-lookup"><span data-stu-id="c486c-104">If you want the Backup BizTalk Server job to back up your custom databases, you must manually add the databases to the Backup BizTalk Server job.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c486c-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="c486c-105">Prerequisites</span></span>  
  
1.  <span data-ttu-id="c486c-106">必须配置 SQL Server，使其使用完全恢复模式，以确保 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库备份集中数据的完整性。</span><span class="sxs-lookup"><span data-stu-id="c486c-106">SQL Server must be configured to use the full recovery model to ensure the integrity of data in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database backup sets.</span></span>  <span data-ttu-id="c486c-107">有关详细信息请参阅[日志传送](../core/log-shipping.md)。</span><span class="sxs-lookup"><span data-stu-id="c486c-107">For more information see [Log Shipping](../core/log-shipping.md).</span></span>  
  
2.  <span data-ttu-id="c486c-108">若要备份自定义数据库，登录所用的用户帐户必须有权访问每个要备份的数据库。</span><span class="sxs-lookup"><span data-stu-id="c486c-108">To back up your custom databases, you must be logged on with a user account that has access to each of the databases you are backing up.</span></span>  
  
     <span data-ttu-id="c486c-109">BizTalk Server 包含一个名为 BTS_BACKUP_USERS 的 SQL Server 角色，因此用来备份数据库的用户帐户不需要 SQL Server 中的系统管理员权限，除非是控制备份过程的主服务器。</span><span class="sxs-lookup"><span data-stu-id="c486c-109">BizTalk Server includes a SQL Server role named BTS_BACKUP_USERS so that the user account you use to back up your databases does not require System Administrator permissions within SQL Server, except for the primary server controlling the backup process.</span></span>  
  
     <span data-ttu-id="c486c-110">在设置要用于备份数据库的用户帐户时，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="c486c-110">When setting up the user account that you are using to back up your databases, note the following:</span></span>  
  
    -   <span data-ttu-id="c486c-111">必须为此用户创建一个 SQL Server 登录帐户，并在每个服务器上为此用户分配 BizTalk BTS_BACKUP_USERS 角色。</span><span class="sxs-lookup"><span data-stu-id="c486c-111">You must create a SQL Server logon account for this user, and assign this user to the BizTalk BTS_BACKUP_USERS role on each server.</span></span>  
  
    -   <span data-ttu-id="c486c-112">可以对 BizTalk Server 备份作业进行配置，使其在与 SQL Server 代理服务所用不同的用户帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="c486c-112">The BizTalk Server backup jobs can be configured to run under a user account that is different than the one used for the SQL Server Agent service.</span></span>  
  
    -   <span data-ttu-id="c486c-113">必须将 SQL Server 代理服务配置为在域帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="c486c-113">You must configure the SQL Server Agent service to run under a domain account.</span></span> <span data-ttu-id="c486c-114">如果所有的数据库都在同一台计算机上，则可将 SQL Server 代理配置为使用本地帐户。</span><span class="sxs-lookup"><span data-stu-id="c486c-114">If all databases are on the same computer, you can configure SQL Server Agent to use a local account.</span></span>  
  
### <a name="to-back-up-custom-databases"></a><span data-ttu-id="c486c-115">备份自定义数据库</span><span class="sxs-lookup"><span data-stu-id="c486c-115">To back up custom databases</span></span>  
  
1.  <span data-ttu-id="c486c-116">在新数据库中生成对象：</span><span class="sxs-lookup"><span data-stu-id="c486c-116">Build the objects in the new database:</span></span>  
  
    -   <span data-ttu-id="c486c-117">浏览到 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema 目录，然后对要备份的所有自定义数据库运行 Backup_Setup_All_Procs.sql 和 Backup_Setup_All_Tables.sql。</span><span class="sxs-lookup"><span data-stu-id="c486c-117">Browse to the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Schema directory, and then run Backup_Setup_All_Procs.sql and Backup_Setup_All_Tables.sql against all your custom databases that you want to back up.</span></span> <span data-ttu-id="c486c-118">此操作将创建必需的过程、表和角色，并向存储过程分配权限。</span><span class="sxs-lookup"><span data-stu-id="c486c-118">This creates the necessary procedures, table, and role and assigns permissions to the stored procedures.</span></span>  
  
2.  <span data-ttu-id="c486c-119">执行以下配置：</span><span class="sxs-lookup"><span data-stu-id="c486c-119">Perform the following configurations:</span></span>  
  
    -   <span data-ttu-id="c486c-120">将 BizTalk 管理数据库的宿主 SQL Server 链接到新数据库的宿主 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="c486c-120">Link the SQL server that is hosting the BizTalk Management database to the SQL server hosting the new database.</span></span> <span data-ttu-id="c486c-121">管理 SQL Server 上用来运行 SQL Server 代理服务的帐户必须是域帐户，该帐户应映射到要备份的数据库所在的每台计算机上。</span><span class="sxs-lookup"><span data-stu-id="c486c-121">The account used to run the SQL Server Agent service on the management SQL Server must be a domain account that is mapped to each computer holding a database to be backed up.</span></span> <span data-ttu-id="c486c-122">如果这些数据库在同一台计算机上，则可跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="c486c-122">If the databases are on the same computer you can skip this step.</span></span> <span data-ttu-id="c486c-123">它是自动完成的。</span><span class="sxs-lookup"><span data-stu-id="c486c-123">This is done automatically.</span></span>  
  
    -   <span data-ttu-id="c486c-124">对于管理 SQL Server 上运行 SQL Server 代理服务的帐户，在新数据库的宿主 SQL Server 上为其添加登录名。</span><span class="sxs-lookup"><span data-stu-id="c486c-124">Add a login on the SQL server hosting the new database for the account running the SQL Server Agent service on the Mgmt SQL Server.</span></span> <span data-ttu-id="c486c-125">如果这些数据库在同一台计算机上，则可跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="c486c-125">If the databases are on the same computer you can skip this step.</span></span>  
  
    -   <span data-ttu-id="c486c-126">在新数据库中为上一步创建的登录名添加用户，并将这类用户添加到 BTS_BACKUP_USERS 角色中。</span><span class="sxs-lookup"><span data-stu-id="c486c-126">Add a user in the new database for the login created in the previous step and add them to the BTS_BACKUP_USERS role.</span></span> <span data-ttu-id="c486c-127">步骤 1 中的脚本创建了此角色，并向其授予了所需过程的执行权限。</span><span class="sxs-lookup"><span data-stu-id="c486c-127">This role is created and granted Execute permissions on the necessary procedures by the scripts in step 1.</span></span>  
  
3.  <span data-ttu-id="c486c-128">在 BizTalk 管理 (BizTalkMgmtDb) 数据库中，使用 SQL Server 企业管理器或 SQL Server Management Studio，修改**adm_OtherBackupDatabases**要某一行中包含的每个自定义数据库表。</span><span class="sxs-lookup"><span data-stu-id="c486c-128">Using SQL Server Enterprise Manager or SQL Server Management Studio, in the BizTalk Management (BizTalkMgmtDb) database, modify the **adm_OtherBackupDatabases** table to include a row for each of your custom databases.</span></span>  
  
4.  <span data-ttu-id="c486c-129">根据下表，在相应列中键入新服务器和数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="c486c-129">Type the new server and database names in the corresponding columns, as shown in the following table.</span></span>  
  
    |<span data-ttu-id="c486c-130">列</span><span class="sxs-lookup"><span data-stu-id="c486c-130">Column</span></span>|<span data-ttu-id="c486c-131">值</span><span class="sxs-lookup"><span data-stu-id="c486c-131">Value</span></span>|  
    |------------|-----------|  
    |<span data-ttu-id="c486c-132">DefaultDatabaseName</span><span class="sxs-lookup"><span data-stu-id="c486c-132">DefaultDatabaseName</span></span>|<span data-ttu-id="c486c-133">自定义数据库的友好名称。</span><span class="sxs-lookup"><span data-stu-id="c486c-133">The friendly name of your custom database.</span></span>|  
    |<span data-ttu-id="c486c-134">DatabaseName</span><span class="sxs-lookup"><span data-stu-id="c486c-134">DatabaseName</span></span>|<span data-ttu-id="c486c-135">自定义数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="c486c-135">The name of your custom database.</span></span>|  
    |<span data-ttu-id="c486c-136">ServerName</span><span class="sxs-lookup"><span data-stu-id="c486c-136">ServerName</span></span>|<span data-ttu-id="c486c-137">运行 SQL Server 的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="c486c-137">The name of the computer running SQL Server.</span></span>|  
    |<span data-ttu-id="c486c-138">BTSServerName</span><span class="sxs-lookup"><span data-stu-id="c486c-138">BTSServerName</span></span>|<span data-ttu-id="c486c-139">BizTalk Server 的名称。</span><span class="sxs-lookup"><span data-stu-id="c486c-139">The name of the BizTalk Server.</span></span> <span data-ttu-id="c486c-140">虽然并不使用此值，但它不能为空。</span><span class="sxs-lookup"><span data-stu-id="c486c-140">This value is not used, but it must contain a value nonetheless.</span></span>|  
  
 <span data-ttu-id="c486c-141">下次运行备份 BizTalk Server 作业时，它就会备份自定义数据库了。</span><span class="sxs-lookup"><span data-stu-id="c486c-141">The next time you run the Backup BizTalk Server job, it will back up your custom databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c486c-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c486c-142">See Also</span></span>  
 <span data-ttu-id="c486c-143">[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="c486c-143">[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md) </span></span>  
 [<span data-ttu-id="c486c-144">有关备份和还原的高级的信息</span><span class="sxs-lookup"><span data-stu-id="c486c-144">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)
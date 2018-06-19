---
title: 管理员的 BAM 任务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d9ae9a6-50fa-4f82-8e48-8dffa55c127f
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b35585d4e3b3ed90df983c8a18f6833ce8aa6bf
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008422"
---
# <a name="bam-tasks-for-administrators"></a><span data-ttu-id="77083-102">管理员的 BAM 任务</span><span class="sxs-lookup"><span data-stu-id="77083-102">BAM Tasks for Administrators</span></span>
<span data-ttu-id="77083-103">本主题描述 BAM 管理员在管理 BAM 基础结构时需要执行的典型任务。</span><span class="sxs-lookup"><span data-stu-id="77083-103">This topic describes typical tasks that BAM administrators undertake in managing the BAM infrastructure.</span></span>  
  
## <a name="configuring-bam"></a><span data-ttu-id="77083-104">配置 BAM</span><span class="sxs-lookup"><span data-stu-id="77083-104">Configuring BAM</span></span>  
 <span data-ttu-id="77083-105">BAM 的初始配置进行使用 BizTalk 服务器配置向导。</span><span class="sxs-lookup"><span data-stu-id="77083-105">The initial configuration of BAM is done using the BizTalk Server Configuration Wizard.</span></span> <span data-ttu-id="77083-106">使用该配置向导，管理员可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="77083-106">Using the configuration wizard administrators can:</span></span>  
  
-   <span data-ttu-id="77083-107">启用业务活动监视工具</span><span class="sxs-lookup"><span data-stu-id="77083-107">Enable Business Activity Monitoring tools</span></span>  
  
-   <span data-ttu-id="77083-108">为 BAM 聚合启用 SQL Server Analysis Services</span><span class="sxs-lookup"><span data-stu-id="77083-108">Enable SQL Server Analysis Services for BAM aggregations</span></span>  
  
-   <span data-ttu-id="77083-109">指定 BAM 工具使用的服务器名和数据库</span><span class="sxs-lookup"><span data-stu-id="77083-109">Specify the server name and databases used for BAM tools</span></span>  
  
-   <span data-ttu-id="77083-110">为 BAM 警报启用 SQL Server Notification Services</span><span class="sxs-lookup"><span data-stu-id="77083-110">Enable SQL Server Notification Services for BAM alerts</span></span>  
  
-   <span data-ttu-id="77083-111">指定用于运行 BAM 通知服务的帐户</span><span class="sxs-lookup"><span data-stu-id="77083-111">Specify the account used to run the BAM Notification service</span></span>  
  
-   <span data-ttu-id="77083-112">指定用于发送 BAM 警报的 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="77083-112">Specify the SMTP server that is used to send BAM alerts</span></span>  
  
-   <span data-ttu-id="77083-113">指定用于存储 BAM 警报的文件位置</span><span class="sxs-lookup"><span data-stu-id="77083-113">Specify the file location used to store BAM alerts</span></span>  
  
-   <span data-ttu-id="77083-114">指定 BAM 警报数据库所在的 SQL 服务器的名称</span><span class="sxs-lookup"><span data-stu-id="77083-114">Specify the name of SQL server on which the BAM alerts databases resides</span></span>  
  
-   <span data-ttu-id="77083-115">指定警报数据库名称的前缀</span><span class="sxs-lookup"><span data-stu-id="77083-115">Specify the prefix for alerts database names</span></span>  
  
-   <span data-ttu-id="77083-116">在计算机上启用 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="77083-116">Enable the BAM portal on a computer</span></span>  
  
-   <span data-ttu-id="77083-117">指定用于运行 BAM 门户的 Web Services 帐户</span><span class="sxs-lookup"><span data-stu-id="77083-117">Specify the Web service accounts used to run the BAM portal</span></span>  
  
-   <span data-ttu-id="77083-118">指定可以访问 BAM 门户的 Windows 组</span><span class="sxs-lookup"><span data-stu-id="77083-118">Specify the Windows groups that can access the BAM portal</span></span>  
  
-   <span data-ttu-id="77083-119">指定 BAM 门户网站的位置</span><span class="sxs-lookup"><span data-stu-id="77083-119">Specify the location of the BAM portal Web site</span></span>  
  
 <span data-ttu-id="77083-120">有关使用该配置向导的详细信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="77083-120">For more information about using the configuration wizard see the following topics:</span></span>  
  
-   [<span data-ttu-id="77083-121">配置 BAM 警报</span><span class="sxs-lookup"><span data-stu-id="77083-121">Configure BAM Alerts</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
-   [<span data-ttu-id="77083-122">配置 BAM 工具</span><span class="sxs-lookup"><span data-stu-id="77083-122">Configure BAM Tools</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
-   [<span data-ttu-id="77083-123">配置 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="77083-123">Configure the BAM Portal</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
### <a name="distributed-notification-services---sql-server-2008-r2-only"></a><span data-ttu-id="77083-124">分布式的 Notification Services 的 SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="77083-124">Distributed Notification Services - SQL Server 2008 R2 only</span></span>
<span data-ttu-id="77083-125">如果将 BAM 配置为在分布式环境中运行，则在处理警报和通知时将具有性能优势。</span><span class="sxs-lookup"><span data-stu-id="77083-125">Configuring BAM to run in a distributed environment affords performance benefits when processing alerts and notifications.</span></span> <span data-ttu-id="77083-126">如果要这样配置，则 Notification Services 的提供者、生成者和分发者角色将位于不同的计算机上，因此您必须在多计算机环境中安装 Notification Services。</span><span class="sxs-lookup"><span data-stu-id="77083-126">When you do this, the Provider, Generator, and Distributor roles of Notification Services are on different computers and you must install Notification Services in the multiple computer environment.</span></span>  

> [!NOTE]
> <span data-ttu-id="77083-127">从 SQL Server 2012 开始，BizTalk Server 使用 SQL 数据库邮件。</span><span class="sxs-lookup"><span data-stu-id="77083-127">Starting with SQL Server 2012, BizTalk Server uses SQL Database Mail.</span></span> <span data-ttu-id="77083-128">因此，如果你使用 SQL Server 2012 或更高版本，这不适用于你。</span><span class="sxs-lookup"><span data-stu-id="77083-128">So if you're using SQL Server 2012 or newer, this does not apply to you.</span></span> <span data-ttu-id="77083-129">请参阅[BAM 警报](../install-and-config-guides/prepare-your-computer-for-installation.md#BKMK_BAMAlerts)的指南。</span><span class="sxs-lookup"><span data-stu-id="77083-129">See [BAM Alerts](../install-and-config-guides/prepare-your-computer-for-installation.md#BKMK_BAMAlerts) for guidance.</span></span>
  
##### <a name="to-configure-distributed-notification-services"></a><span data-ttu-id="77083-130">配置分布式 Notification Services</span><span class="sxs-lookup"><span data-stu-id="77083-130">To configure distributed Notification Services</span></span>  
  
1.  <span data-ttu-id="77083-131">安装 SQL Server Notification Services。</span><span class="sxs-lookup"><span data-stu-id="77083-131">Install SQL Server Notification Services.</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="77083-132">SQL Server 中不包括通知服务。</span><span class="sxs-lookup"><span data-stu-id="77083-132">Notification Services is not included in SQL Server.</span></span> <span data-ttu-id="77083-133">通过选择安装 BizTalk Server 时的情况下安装 SQL Server Notification Services **BAM 警报提供程序 SQL Notification Services**选项下**其他软件**上**组件安装**安装向导页。</span><span class="sxs-lookup"><span data-stu-id="77083-133">Install SQL Server Notification Services when you install BizTalk Server by selecting the **BAM Alert Provider for SQL Notification Services** option under **Additional Software** on the **Component Installation** page of the installation wizard.</span></span>  
  
2.  <span data-ttu-id="77083-134">若要创建 BAM 通知运行 C:\Program Files\Microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol 分布式环境中的每台计算机上的服务注册-name bamalerts-服务器\<服务器名称\>-服务-serviceusername \<alertsuseraccount\> -servicepassword \<passwd\>从命令提示符。</span><span class="sxs-lookup"><span data-stu-id="77083-134">To create the BAM notification service on each computer in the distributed environment run C:\Program Files\Microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol register -name bamalerts -server \<server name\> -service -serviceusername \<alertsuseraccount\> -servicepassword \<passwd\> from a command prompt.</span></span>  
  
3.  <span data-ttu-id="77083-135">编辑每台计算机上为分布式 Notification Services 配置的 BAM 基础结构配置文件。</span><span class="sxs-lookup"><span data-stu-id="77083-135">Edit the BAM infrastructure configuration file on each computer being configured for distributed Notifications Serviced.</span></span> <span data-ttu-id="77083-136">若要获取配置文件，请使用**bm.exe get-config FileName:\<输出文件\>** 命令。</span><span class="sxs-lookup"><span data-stu-id="77083-136">To get the configuration file, use the **bm.exe get-config -FileName:\<output file\>** command.</span></span>  
  
4.  <span data-ttu-id="77083-137">编辑配置文件以引用分布式 Notification Services 环境中的服务器：</span><span class="sxs-lookup"><span data-stu-id="77083-137">Edit the configuration file to reference the servers in the distributed Notification services environment:</span></span>  
  
    ```  
    <Property Name="GeneratorServerName">PFIDWYUK</Property>  
    <Property Name="ProviderServerName">PFIDWYUK</Property>  
    <Property Name="DistributorServerName">PFIDWYUK</Property>  
    ```  
  
5.  <span data-ttu-id="77083-138">使用 bm.exe 更新-config FileName:\<配置文件\>更新 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="77083-138">Use the bm.exe update-config -FileName:\<config file\> to update the BAM configuration.</span></span>  
  
6.  <span data-ttu-id="77083-139">重新启动分布式环境中所有计算机上的 Notification Services。</span><span class="sxs-lookup"><span data-stu-id="77083-139">Restart the Notification Services on all the computers in the distributed environment.</span></span>  
  
 <span data-ttu-id="77083-140">在多计算机环境中安装 BAM 的详细信息，请参阅[安装和配置 BAM （业务活动监视） 在多计算机环境中](http://go.microsoft.com/fwlink/p/?LinkID=208597)。</span><span class="sxs-lookup"><span data-stu-id="77083-140">For more information on installing BAM in a multicomputer environment, see [Install and Configure BAM (Business Activity Monitoring) in a Multi-Computer Environment](http://go.microsoft.com/fwlink/p/?LinkID=208597).</span></span>  
  
### <a name="moving-the-bam-primary-import-database"></a><span data-ttu-id="77083-141">移动 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="77083-141">Moving the BAM Primary Import Database</span></span>  
 <span data-ttu-id="77083-142">有时，可能必须移动 BAM 主导入数据库，例如，在升级硬件或扩展操作时。</span><span class="sxs-lookup"><span data-stu-id="77083-142">At some point it may become necessary to move the BAM Primary Import database, such as when you are upgrading hardware or scaling up operations.</span></span> <span data-ttu-id="77083-143">若要移动该数据库，需要执行备份和还原操作。</span><span class="sxs-lookup"><span data-stu-id="77083-143">To move the database you perform a backup and restore operation.</span></span> <span data-ttu-id="77083-144">有关此过程的详细信息，请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。</span><span class="sxs-lookup"><span data-stu-id="77083-144">For more information about this process, see [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
### <a name="working-with-bam-definitions"></a><span data-ttu-id="77083-145">处理 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="77083-145">Working with BAM Definitions</span></span>  
 <span data-ttu-id="77083-146">管理员需要经常处理 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="77083-146">Administrators work closely with BAM definitions.</span></span> <span data-ttu-id="77083-147">用于处理 BAM 定义的主要工具是 BAM 管理实用程序。</span><span class="sxs-lookup"><span data-stu-id="77083-147">The primary tool you use to work with BAM definitions is the BAM Management utility.</span></span> <span data-ttu-id="77083-148">使用此实用程序可以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="77083-148">You can perform the following tasks by using this utility:</span></span>  
  
-   <span data-ttu-id="77083-149">更改活动。</span><span class="sxs-lookup"><span data-stu-id="77083-149">Changing activities.</span></span> <span data-ttu-id="77083-150">你可以使用**部署所有**，**更新所有**，**删除活动**，**和集 actvitywindow** BAM 管理实用程序的命令若要更改你已部署的活动。</span><span class="sxs-lookup"><span data-stu-id="77083-150">You can use the **deploy-all**, **update-all**, **remove-activity**, **and set-actvitywindow** commands of the BAM management utility to change your deployed activities.</span></span>  
  
-   <span data-ttu-id="77083-151">将索引应用于活动表以提高性能。</span><span class="sxs-lookup"><span data-stu-id="77083-151">Applying indexes to activity tables to enhance performance.</span></span> <span data-ttu-id="77083-152">你使用**创建索引**和**删除索引**命令来修改活动的索引。</span><span class="sxs-lookup"><span data-stu-id="77083-152">You use the **create-index** and **delete-index** commands to modify the indexes on activities.</span></span>  
  
-   <span data-ttu-id="77083-153">设置视图的安全性。</span><span class="sxs-lookup"><span data-stu-id="77083-153">Setting security on views.</span></span> <span data-ttu-id="77083-154">你可以使用**添加帐户**和**删除帐户**命令向用户授予访问权限视图。</span><span class="sxs-lookup"><span data-stu-id="77083-154">You can use the **add-account** and **remove-account** commands to grant users access rights to views.</span></span>  
  
-   <span data-ttu-id="77083-155">配置分布式活动导航。</span><span class="sxs-lookup"><span data-stu-id="77083-155">Configuring distributed navigation of activities.</span></span> <span data-ttu-id="77083-156">你使用**启用引用**和**禁用引用**命令来配置的活动的分布式的导航。</span><span class="sxs-lookup"><span data-stu-id="77083-156">You use the **enable-reference** and **disable-reference** commands to configure distributed navigation of activities.</span></span> <span data-ttu-id="77083-157">有关活动的分布式导航的详细信息，请参阅[管理分布式导航的远程活动](../core/managing-distributed-navigation-of-remote-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="77083-157">For more information about the distributed navigation of activities, see [Managing Distributed Navigation of Remote Activities](../core/managing-distributed-navigation-of-remote-activities.md).</span></span>  
  
-   <span data-ttu-id="77083-158">审核更改。</span><span class="sxs-lookup"><span data-stu-id="77083-158">Auditing changes.</span></span> <span data-ttu-id="77083-159">你可以列出对 BAM 动态基础结构使用的更改**获取变更**命令。</span><span class="sxs-lookup"><span data-stu-id="77083-159">You can list changes to the BAM dynamic infrastructure using the **get-changes** command.</span></span>  
  
 <span data-ttu-id="77083-160">可通过 BAM 管理实用程序的所有命令的说明，请参阅[BAM 管理实用工具](../core/bam-management-utility.md)。</span><span class="sxs-lookup"><span data-stu-id="77083-160">For a description of all the commands available through the BAM Management utility, see [BAM Management Utility](../core/bam-management-utility.md).</span></span> <span data-ttu-id="77083-161">有关使用 BAM 管理实用程序来处理 BAM 定义的示例，请参阅[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="77083-161">For examples of using the BAM Management utility to work with BAM definitions, see [Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md).</span></span>  
  
## <a name="configuring-multiple-biztalk-groups-to-reference-a-single-bam-database"></a><span data-ttu-id="77083-162">将多个 BizTalk 组配置为引用单个 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="77083-162">Configuring Multiple BizTalk Groups to Reference a Single BAM Database</span></span>  
 <span data-ttu-id="77083-163">在配置时 BAM 以使用新的或现有的 BizTalk Server 组，可以配置要使用相同的 BAM 数据库供另一个 BizTalk Server 组中已有的组。</span><span class="sxs-lookup"><span data-stu-id="77083-163">When configuring BAM to use either a new or an existing BizTalk Server group, you can configure the group to use the same BAM databases that are already in use by another BizTalk Server group.</span></span>  <span data-ttu-id="77083-164">若要以这种方式配置 BAM，必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="77083-164">To configure BAM in this manner, you must perform the following tasks:</span></span>  
  
-   <span data-ttu-id="77083-165">从现有 BAM 主导入数据库使用 BizTalk 服务器配置向导中获取的配置信息。</span><span class="sxs-lookup"><span data-stu-id="77083-165">Get the configuration information from the existing BAM Primary Import database using the BizTalk Server Configuration Wizard.</span></span> <span data-ttu-id="77083-166">这包括服务器和数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="77083-166">This includes the server and database names.</span></span> <span data-ttu-id="77083-167">请注意复选框的状态。</span><span class="sxs-lookup"><span data-stu-id="77083-167">Note the state of the check boxes.</span></span> <span data-ttu-id="77083-168">确保获取 BAM 工具和 BAM 警报页的配置信息。</span><span class="sxs-lookup"><span data-stu-id="77083-168">Be sure to get the configuration information for both the BAM Tools and BAM Alerts pages.</span></span>  
  
-   <span data-ttu-id="77083-169">为新组配置 BAM，然后输入与已为目标 PIT 配置的信息完全相同的信息。</span><span class="sxs-lookup"><span data-stu-id="77083-169">Configure BAM for the new group, and enter the exact information as configured already for the target PIT.</span></span> <span data-ttu-id="77083-170">为新组输入配置信息时，将使用从现有组收集的所有信息来配置该新组，唯一的不同是必须将 BAM 警报用户保留为空。</span><span class="sxs-lookup"><span data-stu-id="77083-170">When entering the configuration information for the new group you will use all the information collected from the existing group to configure the new group, except the BAM Alerts user, which you must leave blank.</span></span>  
  
## <a name="backing-up-and-restoring-bam"></a><span data-ttu-id="77083-171">Backing Up and Restoring BAM</span><span class="sxs-lookup"><span data-stu-id="77083-171">Backing Up and Restoring BAM</span></span>  
 <span data-ttu-id="77083-172">管理员应当为灾难恢复情况做好准备。</span><span class="sxs-lookup"><span data-stu-id="77083-172">Administrators should plan for disaster recovery situations.</span></span> <span data-ttu-id="77083-173">您应当备份 BAM 分析数据库、跟踪分析数据库、BAM 星型架构数据库、BAM 存档数据库和 BAM 主导入数据库，以便在必须还原它们时提供所需文件。</span><span class="sxs-lookup"><span data-stu-id="77083-173">You should back up the BAM Analysis, Tracking Analysis, BAM Star Schema, BAM Archive, and BAM Primary Import databases to provide for situations in which you must restore them.</span></span>  <span data-ttu-id="77083-174">有关备份和还原的 BAM 数据库的信息，请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。</span><span class="sxs-lookup"><span data-stu-id="77083-174">For information about backing up and restoring the BAM databases, see [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
## <a name="working-with-renamed-servers"></a><span data-ttu-id="77083-175">处理重命名服务器</span><span class="sxs-lookup"><span data-stu-id="77083-175">Working with Renamed Servers</span></span>  
 <span data-ttu-id="77083-176">在重命名服务器或在服务器之间移动 BAM 基础结构后，必须通过更新 Excel 工作簿中的 BAM 定义来更新该工作簿。</span><span class="sxs-lookup"><span data-stu-id="77083-176">When you rename a server or move the BAM infrastructure between servers, you must update the Excel workbook by updating the BAM definitions in that workbook.</span></span>  
  
 <span data-ttu-id="77083-177">您需要更新该工作簿的情况包括：</span><span class="sxs-lookup"><span data-stu-id="77083-177">The scenarios in which you would need to update the workbook include:</span></span>  
  
-   <span data-ttu-id="77083-178">将 BAM 基础结构移动到新数据库的过渡情况。</span><span class="sxs-lookup"><span data-stu-id="77083-178">A staging scenario, in which you move the BAM infrastructure to a new database.</span></span> <span data-ttu-id="77083-179">若要确保 Excel 工作簿仍然能够正常使用，必须重新部署或进行迁移，然后重新更新工作簿。</span><span class="sxs-lookup"><span data-stu-id="77083-179">To ensure that the Excel workbooks are still functional, you must redeploy or migrate and then re-update the workbooks.</span></span>  
  
-   <span data-ttu-id="77083-180">重命名正运行 BizTalk Server 的计算机的情况。</span><span class="sxs-lookup"><span data-stu-id="77083-180">A scenario in which you rename the computer running BizTalk Server.</span></span> <span data-ttu-id="77083-181">这需要更新的 DTS 包和除了更新工作簿的 OLAP 数据源。</span><span class="sxs-lookup"><span data-stu-id="77083-181">This requires updating the DTS packages and OLAP data source in addition to updating the workbook.</span></span>  
  
 <span data-ttu-id="77083-182">更新 Excel 工作簿可以采用两种方法：</span><span class="sxs-lookup"><span data-stu-id="77083-182">There are two approaches you can use to update the Excel workbook:</span></span>  
  
-   <span data-ttu-id="77083-183">从新服务器运行以下 BAM 管理器命令：</span><span class="sxs-lookup"><span data-stu-id="77083-183">Run the following BAM Manager command from the new server:</span></span>  
  
     <span data-ttu-id="77083-184">**bm.exe 更新 livedataworkbook-名称：\<到 update.xls livedata 工作簿\>**</span><span class="sxs-lookup"><span data-stu-id="77083-184">**bm.exe update-livedataworkbook -Name:\<livedata workbook to update.xls\>**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="77083-185">你还可以指定新的服务器名称和/或 BAM 主导入数据库名称： **bm.exe 更新 livedataworkbook-名称：\<livedata 工作簿变为 update.xls\> [-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="77083-185">You can also specify the new server name and/or BAM Primary Import database name: **bm.exe update-livedataworkbook -Name:\<livedata workbook to update.xls\> [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
-   <span data-ttu-id="77083-186">也可以在 Excel 中更新 Excel 工作簿：</span><span class="sxs-lookup"><span data-stu-id="77083-186">Alternatively, you can update the Excel workbook from within Excel:</span></span>  
  
    1.  <span data-ttu-id="77083-187">打开要更新的工作簿。</span><span class="sxs-lookup"><span data-stu-id="77083-187">Open the workbook you want to update.</span></span>  
  
    2.  <span data-ttu-id="77083-188">从 BAM 菜单上，单击**BAM 数据库连接**。</span><span class="sxs-lookup"><span data-stu-id="77083-188">From the BAM menu, click **BAM Db Connection**.</span></span>  
  
    3.  <span data-ttu-id="77083-189">输入新的服务器名和 BAM 主导入数据库名。</span><span class="sxs-lookup"><span data-stu-id="77083-189">Enter the new server name and BAM Primary Import database name.</span></span>  
  
## <a name="managing-alerts"></a><span data-ttu-id="77083-190">管理警报</span><span class="sxs-lookup"><span data-stu-id="77083-190">Managing Alerts</span></span>  
 <span data-ttu-id="77083-191">管理员可以以几种方式管理警报：</span><span class="sxs-lookup"><span data-stu-id="77083-191">Administrators can manage alerts in a several ways:</span></span>  
  
 <span data-ttu-id="77083-192">您可以使用 BAM 管理实用程序来部署和删除警报。</span><span class="sxs-lookup"><span data-stu-id="77083-192">You can use the BAM Management utility to deploy and remove alerts.</span></span> <span data-ttu-id="77083-193">还可以使用该实用程序来添加和删除订阅，以及启用和禁用警报。</span><span class="sxs-lookup"><span data-stu-id="77083-193">You can also use the utility to add and remove subscriptions, as well as to enable and disable alerts.</span></span> <span data-ttu-id="77083-194">有关使用 BAM 管理实用程序的详细信息，请参阅[BAM 管理实用工具](../core/bam-management-utility.md)，[管理 BAM 安全](../core/managing-bam-security.md)，和[管理 BAM 定义](../core/managing-bam-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="77083-194">For more information about using the BAM Management utility, see [BAM Management Utility](../core/bam-management-utility.md), [Managing BAM Security](../core/managing-bam-security.md), and [Managing BAM Definitions](../core/managing-bam-definitions.md).</span></span>  
  
 <span data-ttu-id="77083-195">您还可以通过 BAM 门户来创建和删除警报。</span><span class="sxs-lookup"><span data-stu-id="77083-195">You can also create and remove alerts through the BAM portal.</span></span>  <span data-ttu-id="77083-196">有关创建使用 BAM 门户警报的信息，请参阅[BAM 门户中的活动搜索](../core/activity-searches-in-the-bam-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="77083-196">For information about creating alerts using the BAM portal, see [Activity Searches in the BAM Portal](../core/activity-searches-in-the-bam-portal.md).</span></span>  
  
### <a name="cleaning-up-the-alerts-chronicle-table"></a><span data-ttu-id="77083-197">清理 Alerts Chronicle 表</span><span class="sxs-lookup"><span data-stu-id="77083-197">Cleaning up the Alerts Chronicle table</span></span>  
 <span data-ttu-id="77083-198">如果配置 BAM 警报，则为创建的每个活动视图都创建一个 SQL 作业。</span><span class="sxs-lookup"><span data-stu-id="77083-198">If BAM alerts are configured, a SQL job is created for each activity view that is created.</span></span> <span data-ttu-id="77083-199">将使用以下模板命名该作业：</span><span class="sxs-lookup"><span data-stu-id="77083-199">The job will be named using the following template:</span></span>  
  
 <span data-ttu-id="77083-200">bam_\<视图名称\>_\<活动视图\>_DelAlertHistJob</span><span class="sxs-lookup"><span data-stu-id="77083-200">bam_\<View Name\>_\<Activity View\>_DelAlertHistJob</span></span>  
  
 <span data-ttu-id="77083-201">此作业负责清除审核数据的指定实例警报\<活动视图\>Bam_Metadata_AlertChronicle 表中。</span><span class="sxs-lookup"><span data-stu-id="77083-201">This job cleans up auditing data for the instance alerts for the specified \<Activity View\> in the Bam_Metadata_AlertChronicle table.</span></span> <span data-ttu-id="77083-202">如果您对特定的活动视图定义了实例警报，则每次触发警报时，就会向该表添加一个新行。</span><span class="sxs-lookup"><span data-stu-id="77083-202">If you have defined instance alerts on the particular activity view, a new row will be added to this table every time the alert is fired.</span></span>  
  
 <span data-ttu-id="77083-203">您可以手动运行此作业以便清理该表，或者可以根据您的应用程序或环境的需要计划此作业的运行时间。</span><span class="sxs-lookup"><span data-stu-id="77083-203">You can run this job manually to clean up the table or schedule it to run according to the need of your application or environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77083-204">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77083-204">See Also</span></span>  
 [<span data-ttu-id="77083-205">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="77083-205">Managing BAM</span></span>](../core/managing-bam.md)
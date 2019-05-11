---
title: 管理员的 BAM 任务 |Microsoft Docs
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
ms.openlocfilehash: 2a7a6ba4459cbe5b9c92c20859b414ec6e694c59
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530541"
---
# <a name="bam-tasks-for-administrators"></a><span data-ttu-id="bd371-102">管理员的 BAM 任务</span><span class="sxs-lookup"><span data-stu-id="bd371-102">BAM Tasks for Administrators</span></span>
<span data-ttu-id="bd371-103">本主题描述 BAM 管理员在管理 BAM 基础结构时需要执行的典型任务。</span><span class="sxs-lookup"><span data-stu-id="bd371-103">This topic describes typical tasks that BAM administrators undertake in managing the BAM infrastructure.</span></span>  
  
## <a name="configuring-bam"></a><span data-ttu-id="bd371-104">配置 BAM</span><span class="sxs-lookup"><span data-stu-id="bd371-104">Configuring BAM</span></span>  
 <span data-ttu-id="bd371-105">进行 BAM 的初始配置使用 BizTalk Server 配置向导。</span><span class="sxs-lookup"><span data-stu-id="bd371-105">The initial configuration of BAM is done using the BizTalk Server Configuration Wizard.</span></span> <span data-ttu-id="bd371-106">使用配置向导，管理员可以：</span><span class="sxs-lookup"><span data-stu-id="bd371-106">Using the configuration wizard administrators can:</span></span>  
  
- <span data-ttu-id="bd371-107">启用业务活动监视工具</span><span class="sxs-lookup"><span data-stu-id="bd371-107">Enable Business Activity Monitoring tools</span></span>  
  
- <span data-ttu-id="bd371-108">启用 SQL Server Analysis Services 为 BAM 聚合</span><span class="sxs-lookup"><span data-stu-id="bd371-108">Enable SQL Server Analysis Services for BAM aggregations</span></span>  
  
- <span data-ttu-id="bd371-109">指定的服务器名称和数据库用于 BAM 工具</span><span class="sxs-lookup"><span data-stu-id="bd371-109">Specify the server name and databases used for BAM tools</span></span>  
  
- <span data-ttu-id="bd371-110">启用 BAM 警报的 SQL Server Notification Services</span><span class="sxs-lookup"><span data-stu-id="bd371-110">Enable SQL Server Notification Services for BAM alerts</span></span>  
  
- <span data-ttu-id="bd371-111">指定用于运行 BAM 通知服务的帐户</span><span class="sxs-lookup"><span data-stu-id="bd371-111">Specify the account used to run the BAM Notification service</span></span>  
  
- <span data-ttu-id="bd371-112">指定用于发送 BAM 警报的 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="bd371-112">Specify the SMTP server that is used to send BAM alerts</span></span>  
  
- <span data-ttu-id="bd371-113">指定用于存储 BAM 警报文件位置</span><span class="sxs-lookup"><span data-stu-id="bd371-113">Specify the file location used to store BAM alerts</span></span>  
  
- <span data-ttu-id="bd371-114">指定所在的 SQL server 的 BAM 警报数据库名称</span><span class="sxs-lookup"><span data-stu-id="bd371-114">Specify the name of SQL server on which the BAM alerts databases resides</span></span>  
  
- <span data-ttu-id="bd371-115">指定警报数据库名称的前缀</span><span class="sxs-lookup"><span data-stu-id="bd371-115">Specify the prefix for alerts database names</span></span>  
  
- <span data-ttu-id="bd371-116">启用 BAM 门户的计算机上</span><span class="sxs-lookup"><span data-stu-id="bd371-116">Enable the BAM portal on a computer</span></span>  
  
- <span data-ttu-id="bd371-117">指定用于运行 BAM 门户的 Web 服务帐户</span><span class="sxs-lookup"><span data-stu-id="bd371-117">Specify the Web service accounts used to run the BAM portal</span></span>  
  
- <span data-ttu-id="bd371-118">指定可以访问 BAM 门户的 Windows 组</span><span class="sxs-lookup"><span data-stu-id="bd371-118">Specify the Windows groups that can access the BAM portal</span></span>  
  
- <span data-ttu-id="bd371-119">指定 BAM 门户网站上的位置</span><span class="sxs-lookup"><span data-stu-id="bd371-119">Specify the location of the BAM portal Web site</span></span>  
  
  <span data-ttu-id="bd371-120">有关使用配置向导的详细信息请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="bd371-120">For more information about using the configuration wizard see the following topics:</span></span>  
  
- [<span data-ttu-id="bd371-121">配置 BAM 警报</span><span class="sxs-lookup"><span data-stu-id="bd371-121">Configure BAM Alerts</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
- [<span data-ttu-id="bd371-122">配置 BAM 工具</span><span class="sxs-lookup"><span data-stu-id="bd371-122">Configure BAM Tools</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
- [<span data-ttu-id="bd371-123">配置 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="bd371-123">Configure the BAM Portal</span></span>](../install-and-config-guides/configure-biztalk-server.md)  
  
### <a name="distributed-notification-services---sql-server-2008-r2-only"></a><span data-ttu-id="bd371-124">分布式的 Notification Services-仅限 SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="bd371-124">Distributed Notification Services - SQL Server 2008 R2 only</span></span>
<span data-ttu-id="bd371-125">处理警报和通知时，配置 BAM 以在分布式环境中运行具有性能优势。</span><span class="sxs-lookup"><span data-stu-id="bd371-125">Configuring BAM to run in a distributed environment affords performance benefits when processing alerts and notifications.</span></span> <span data-ttu-id="bd371-126">时执行此操作时，通知服务的提供程序、 生成器和分发服务器角色上不同的计算机，并且必须在多计算机环境中安装 Notification Services。</span><span class="sxs-lookup"><span data-stu-id="bd371-126">When you do this, the Provider, Generator, and Distributor roles of Notification Services are on different computers and you must install Notification Services in the multiple computer environment.</span></span>  

> [!NOTE]
> <span data-ttu-id="bd371-127">从 SQL Server 2012 开始，BizTalk Server 使用 SQL Database Mail。</span><span class="sxs-lookup"><span data-stu-id="bd371-127">Starting with SQL Server 2012, BizTalk Server uses SQL Database Mail.</span></span> <span data-ttu-id="bd371-128">因此，如果要使用 SQL Server 2012 或更高版本，这不适用于您。</span><span class="sxs-lookup"><span data-stu-id="bd371-128">So if you're using SQL Server 2012 or newer, this does not apply to you.</span></span> <span data-ttu-id="bd371-129">请参阅[BAM 警报](../install-and-config-guides/prepare-your-computer-for-installation.md#BKMK_BAMAlerts)有关的指南。</span><span class="sxs-lookup"><span data-stu-id="bd371-129">See [BAM Alerts](../install-and-config-guides/prepare-your-computer-for-installation.md#BKMK_BAMAlerts) for guidance.</span></span>
  
##### <a name="to-configure-distributed-notification-services"></a><span data-ttu-id="bd371-130">若要配置分布式的 Notification Services</span><span class="sxs-lookup"><span data-stu-id="bd371-130">To configure distributed Notification Services</span></span>  
  
1. <span data-ttu-id="bd371-131">安装 SQL Server Notification Services。</span><span class="sxs-lookup"><span data-stu-id="bd371-131">Install SQL Server Notification Services.</span></span> 
  
   > [!NOTE]
   >  <span data-ttu-id="bd371-132">SQL Server 中不包括通知服务。</span><span class="sxs-lookup"><span data-stu-id="bd371-132">Notification Services is not included in SQL Server.</span></span> <span data-ttu-id="bd371-133">通过选择安装 BizTalk Server 时安装 SQL Server Notification Services**用于 SQL Notification Services 的 BAM 警报提供程序**下**其他软件**上**组件安装**安装向导页。</span><span class="sxs-lookup"><span data-stu-id="bd371-133">Install SQL Server Notification Services when you install BizTalk Server by selecting the **BAM Alert Provider for SQL Notification Services** option under **Additional Software** on the **Component Installation** page of the installation wizard.</span></span>  
  
2. <span data-ttu-id="bd371-134">若要创建 BAM 通知服务运行 C:\Program Files\Microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol 在分布式环境中的每台计算机上注册的名称 bamalerts-server\<服务器名称\>-服务-serviceusername\<警报用户帐户\>-servicepassword \<passwd\>从命令提示符。</span><span class="sxs-lookup"><span data-stu-id="bd371-134">To create the BAM notification service on each computer in the distributed environment run C:\Program Files\Microsoft SQL Server\90\NotificationServices\9.0.242\bin\nscontrol register -name bamalerts -server \<server name\> -service -serviceusername \<alertsuseraccount\> -servicepassword \<passwd\> from a command prompt.</span></span>  
  
3. <span data-ttu-id="bd371-135">编辑 BAM 基础结构配置文件配置为分布式通知提供服务的每台计算机上。</span><span class="sxs-lookup"><span data-stu-id="bd371-135">Edit the BAM infrastructure configuration file on each computer being configured for distributed Notifications Serviced.</span></span> <span data-ttu-id="bd371-136">若要获取配置文件，请使用**bm.exe 获取配置-FileName:\<输出文件\>** 命令。</span><span class="sxs-lookup"><span data-stu-id="bd371-136">To get the configuration file, use the **bm.exe get-config -FileName:\<output file\>** command.</span></span>  
  
4. <span data-ttu-id="bd371-137">编辑配置文件以引用分布式 Notification services 环境中的服务器：</span><span class="sxs-lookup"><span data-stu-id="bd371-137">Edit the configuration file to reference the servers in the distributed Notification services environment:</span></span>  
  
   ```  
   <Property Name="GeneratorServerName">PFIDWYUK</Property>  
   <Property Name="ProviderServerName">PFIDWYUK</Property>  
   <Property Name="DistributorServerName">PFIDWYUK</Property>  
   ```  
  
5. <span data-ttu-id="bd371-138">使用 bm.exe 更新-config-FileName:\<配置文件\>更新 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="bd371-138">Use the bm.exe update-config -FileName:\<config file\> to update the BAM configuration.</span></span>  
  
6. <span data-ttu-id="bd371-139">在分布式环境中重新启动的所有计算机上的 Notification Services。</span><span class="sxs-lookup"><span data-stu-id="bd371-139">Restart the Notification Services on all the computers in the distributed environment.</span></span>  
  
   <span data-ttu-id="bd371-140">在多计算机环境中安装 BAM 的详细信息，请参阅[安装并配置 BAM （业务活动监视） 在多计算机环境中](http://go.microsoft.com/fwlink/p/?LinkID=208597)。</span><span class="sxs-lookup"><span data-stu-id="bd371-140">For more information on installing BAM in a multicomputer environment, see [Install and Configure BAM (Business Activity Monitoring) in a Multi-Computer Environment](http://go.microsoft.com/fwlink/p/?LinkID=208597).</span></span>  
  
### <a name="moving-the-bam-primary-import-database"></a><span data-ttu-id="bd371-141">移动 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="bd371-141">Moving the BAM Primary Import Database</span></span>  
 <span data-ttu-id="bd371-142">在某些时候，它可能需要移动 BAM 主导入数据库，例如升级硬件或扩展操作。</span><span class="sxs-lookup"><span data-stu-id="bd371-142">At some point it may become necessary to move the BAM Primary Import database, such as when you are upgrading hardware or scaling up operations.</span></span> <span data-ttu-id="bd371-143">若要将数据库移动您执行备份和还原操作。</span><span class="sxs-lookup"><span data-stu-id="bd371-143">To move the database you perform a backup and restore operation.</span></span> <span data-ttu-id="bd371-144">有关此过程的详细信息，请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。</span><span class="sxs-lookup"><span data-stu-id="bd371-144">For more information about this process, see [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
### <a name="working-with-bam-definitions"></a><span data-ttu-id="bd371-145">处理 BAM 定义</span><span class="sxs-lookup"><span data-stu-id="bd371-145">Working with BAM Definitions</span></span>  
 <span data-ttu-id="bd371-146">管理员需要经常处理 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="bd371-146">Administrators work closely with BAM definitions.</span></span> <span data-ttu-id="bd371-147">用于处理 BAM 定义的主要工具是 BAM 管理实用程序。</span><span class="sxs-lookup"><span data-stu-id="bd371-147">The primary tool you use to work with BAM definitions is the BAM Management utility.</span></span> <span data-ttu-id="bd371-148">可以使用此实用程序来执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="bd371-148">You can perform the following tasks by using this utility:</span></span>  
  
- <span data-ttu-id="bd371-149">更改活动。</span><span class="sxs-lookup"><span data-stu-id="bd371-149">Changing activities.</span></span> <span data-ttu-id="bd371-150">可以使用**部署全部**，**更新全部**，**删除活动**，**和集 actvitywindow** BAM 管理实用程序的命令若要更改已部署的活动。</span><span class="sxs-lookup"><span data-stu-id="bd371-150">You can use the **deploy-all**, **update-all**, **remove-activity**, **and set-actvitywindow** commands of the BAM management utility to change your deployed activities.</span></span>  
  
- <span data-ttu-id="bd371-151">将索引应用于活动表以提高性能。</span><span class="sxs-lookup"><span data-stu-id="bd371-151">Applying indexes to activity tables to enhance performance.</span></span> <span data-ttu-id="bd371-152">您使用**创建索引**并**删除索引**命令来修改活动上的索引。</span><span class="sxs-lookup"><span data-stu-id="bd371-152">You use the **create-index** and **delete-index** commands to modify the indexes on activities.</span></span>  
  
- <span data-ttu-id="bd371-153">在视图上设置安全性。</span><span class="sxs-lookup"><span data-stu-id="bd371-153">Setting security on views.</span></span> <span data-ttu-id="bd371-154">可以使用**添加帐户**并**删除帐户**命令，授予用户访问视图的权限。</span><span class="sxs-lookup"><span data-stu-id="bd371-154">You can use the **add-account** and **remove-account** commands to grant users access rights to views.</span></span>  
  
- <span data-ttu-id="bd371-155">配置分布式的活动导航。</span><span class="sxs-lookup"><span data-stu-id="bd371-155">Configuring distributed navigation of activities.</span></span> <span data-ttu-id="bd371-156">您使用**启用引用**并**禁用引用**命令以配置分布式的活动导航。</span><span class="sxs-lookup"><span data-stu-id="bd371-156">You use the **enable-reference** and **disable-reference** commands to configure distributed navigation of activities.</span></span> <span data-ttu-id="bd371-157">有关分布式活动导航的详细信息，请参阅[管理分布式导航的远程活动](../core/managing-distributed-navigation-of-remote-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="bd371-157">For more information about the distributed navigation of activities, see [Managing Distributed Navigation of Remote Activities](../core/managing-distributed-navigation-of-remote-activities.md).</span></span>  
  
- <span data-ttu-id="bd371-158">审核更改。</span><span class="sxs-lookup"><span data-stu-id="bd371-158">Auditing changes.</span></span> <span data-ttu-id="bd371-159">可以列出对 BAM 动态基础结构使用的更改**get 更改**命令。</span><span class="sxs-lookup"><span data-stu-id="bd371-159">You can list changes to the BAM dynamic infrastructure using the **get-changes** command.</span></span>  
  
  <span data-ttu-id="bd371-160">可通过 BAM 管理实用程序的所有命令的说明，请参阅[BAM 管理实用程序](../core/bam-management-utility.md)。</span><span class="sxs-lookup"><span data-stu-id="bd371-160">For a description of all the commands available through the BAM Management utility, see [BAM Management Utility](../core/bam-management-utility.md).</span></span> <span data-ttu-id="bd371-161">有关使用 BAM 管理实用程序来处理 BAM 定义的示例，请参阅[管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="bd371-161">For examples of using the BAM Management utility to work with BAM definitions, see [Managing the BAM Dynamic Infrastructure](../core/managing-the-bam-dynamic-infrastructure.md).</span></span>  
  
## <a name="configuring-multiple-biztalk-groups-to-reference-a-single-bam-database"></a><span data-ttu-id="bd371-162">配置多个 BizTalk 组，以引用单个 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="bd371-162">Configuring Multiple BizTalk Groups to Reference a Single BAM Database</span></span>  
 <span data-ttu-id="bd371-163">在配置 BAM 以使用新的或现有的 BizTalk Server 组，可以配置要使用已在由另一个 BizTalk Server 组使用的 BAM 数据库的组。</span><span class="sxs-lookup"><span data-stu-id="bd371-163">When configuring BAM to use either a new or an existing BizTalk Server group, you can configure the group to use the same BAM databases that are already in use by another BizTalk Server group.</span></span>  <span data-ttu-id="bd371-164">若要以这种方式配置 BAM，必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="bd371-164">To configure BAM in this manner, you must perform the following tasks:</span></span>  
  
-   <span data-ttu-id="bd371-165">从使用 BizTalk Server 配置向导在现有 BAM 主导入数据库中获取的配置信息。</span><span class="sxs-lookup"><span data-stu-id="bd371-165">Get the configuration information from the existing BAM Primary Import database using the BizTalk Server Configuration Wizard.</span></span> <span data-ttu-id="bd371-166">这包括服务器和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="bd371-166">This includes the server and database names.</span></span> <span data-ttu-id="bd371-167">请注意复选框的状态。</span><span class="sxs-lookup"><span data-stu-id="bd371-167">Note the state of the check boxes.</span></span> <span data-ttu-id="bd371-168">请确保获取 BAM 工具和 BAM 警报页的配置信息。</span><span class="sxs-lookup"><span data-stu-id="bd371-168">Be sure to get the configuration information for both the BAM Tools and BAM Alerts pages.</span></span>  
  
-   <span data-ttu-id="bd371-169">BAM 配置为新组，并输入已配置为目标 PIT 的准确信息。</span><span class="sxs-lookup"><span data-stu-id="bd371-169">Configure BAM for the new group, and enter the exact information as configured already for the target PIT.</span></span> <span data-ttu-id="bd371-170">输入新组的配置信息时将使用从现有组收集的所有信息来配置新的组，除了 BAM 警报用户，必须将保留为空。</span><span class="sxs-lookup"><span data-stu-id="bd371-170">When entering the configuration information for the new group you will use all the information collected from the existing group to configure the new group, except the BAM Alerts user, which you must leave blank.</span></span>  
  
## <a name="backing-up-and-restoring-bam"></a><span data-ttu-id="bd371-171">Backing Up and Restoring BAM</span><span class="sxs-lookup"><span data-stu-id="bd371-171">Backing Up and Restoring BAM</span></span>  
 <span data-ttu-id="bd371-172">管理员应规划灾难恢复情况。</span><span class="sxs-lookup"><span data-stu-id="bd371-172">Administrators should plan for disaster recovery situations.</span></span> <span data-ttu-id="bd371-173">您应备份 BAM 分析、 跟踪分析、 BAM 星型架构、 BAM 存档和 BAM 主导入数据库以便为在其中你必须将它们还原的情况下提供。</span><span class="sxs-lookup"><span data-stu-id="bd371-173">You should back up the BAM Analysis, Tracking Analysis, BAM Star Schema, BAM Archive, and BAM Primary Import databases to provide for situations in which you must restore them.</span></span>  <span data-ttu-id="bd371-174">有关备份和还原 BAM 数据库的信息，请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。</span><span class="sxs-lookup"><span data-stu-id="bd371-174">For information about backing up and restoring the BAM databases, see [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
## <a name="working-with-renamed-servers"></a><span data-ttu-id="bd371-175">处理重命名服务器</span><span class="sxs-lookup"><span data-stu-id="bd371-175">Working with Renamed Servers</span></span>  
 <span data-ttu-id="bd371-176">当您重命名服务器或服务器之间移动 BAM 基础结构时，必须通过更新该工作簿中的 BAM 定义来更新 Excel 工作簿。</span><span class="sxs-lookup"><span data-stu-id="bd371-176">When you rename a server or move the BAM infrastructure between servers, you must update the Excel workbook by updating the BAM definitions in that workbook.</span></span>  
  
 <span data-ttu-id="bd371-177">需要更新工作簿的方案包括：</span><span class="sxs-lookup"><span data-stu-id="bd371-177">The scenarios in which you would need to update the workbook include:</span></span>  
  
- <span data-ttu-id="bd371-178">过渡的方案，为新的数据库移动 BAM 基础结构。</span><span class="sxs-lookup"><span data-stu-id="bd371-178">A staging scenario, in which you move the BAM infrastructure to a new database.</span></span> <span data-ttu-id="bd371-179">若要确保 Excel 工作簿仍正常工作，必须重新部署或迁移，然后重新更新工作簿。</span><span class="sxs-lookup"><span data-stu-id="bd371-179">To ensure that the Excel workbooks are still functional, you must redeploy or migrate and then re-update the workbooks.</span></span>  
  
- <span data-ttu-id="bd371-180">重命名运行 BizTalk Server 的计算机方案。</span><span class="sxs-lookup"><span data-stu-id="bd371-180">A scenario in which you rename the computer running BizTalk Server.</span></span> <span data-ttu-id="bd371-181">这需要更新 DTS 包和 OLAP 数据源，除了更新工作簿。</span><span class="sxs-lookup"><span data-stu-id="bd371-181">This requires updating the DTS packages and OLAP data source in addition to updating the workbook.</span></span>  
  
  <span data-ttu-id="bd371-182">有两种方法可用于更新 Excel 工作簿：</span><span class="sxs-lookup"><span data-stu-id="bd371-182">There are two approaches you can use to update the Excel workbook:</span></span>  
  
- <span data-ttu-id="bd371-183">从新的服务器上运行以下 BAM 管理器命令：</span><span class="sxs-lookup"><span data-stu-id="bd371-183">Run the following BAM Manager command from the new server:</span></span>  
  
   <span data-ttu-id="bd371-184">**bm.exe 更新 livedataworkbook-名称：\<update.xls 到实时数据工作簿\>**</span><span class="sxs-lookup"><span data-stu-id="bd371-184">**bm.exe update-livedataworkbook -Name:\<livedata workbook to update.xls\>**</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="bd371-185">您还可以指定新的服务器名称和/或 BAM 主导入数据库名称： **bm.exe 更新 livedataworkbook-名称：\<update.xls 到实时数据工作簿\>[-Server:\<server\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="bd371-185">You can also specify the new server name and/or BAM Primary Import database name: **bm.exe update-livedataworkbook -Name:\<livedata workbook to update.xls\> [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
- <span data-ttu-id="bd371-186">或者，你可以更新 Excel 工作簿从 Excel 内：</span><span class="sxs-lookup"><span data-stu-id="bd371-186">Alternatively, you can update the Excel workbook from within Excel:</span></span>  
  
  1.  <span data-ttu-id="bd371-187">打开你想要更新工作的簿。</span><span class="sxs-lookup"><span data-stu-id="bd371-187">Open the workbook you want to update.</span></span>  
  
  2.  <span data-ttu-id="bd371-188">从 BAM 菜单中，单击**BAM 数据库连接**。</span><span class="sxs-lookup"><span data-stu-id="bd371-188">From the BAM menu, click **BAM Db Connection**.</span></span>  
  
  3.  <span data-ttu-id="bd371-189">输入新的服务器名称和 BAM 主导入数据库名称。</span><span class="sxs-lookup"><span data-stu-id="bd371-189">Enter the new server name and BAM Primary Import database name.</span></span>  
  
## <a name="managing-alerts"></a><span data-ttu-id="bd371-190">管理警报</span><span class="sxs-lookup"><span data-stu-id="bd371-190">Managing Alerts</span></span>  
 <span data-ttu-id="bd371-191">管理员可以管理警报以几种方式：</span><span class="sxs-lookup"><span data-stu-id="bd371-191">Administrators can manage alerts in a several ways:</span></span>  
  
 <span data-ttu-id="bd371-192">可以使用 BAM 管理实用程序来部署和删除警报。</span><span class="sxs-lookup"><span data-stu-id="bd371-192">You can use the BAM Management utility to deploy and remove alerts.</span></span> <span data-ttu-id="bd371-193">此外可以使用该实用程序来添加和删除订阅，以及启用和禁用警报。</span><span class="sxs-lookup"><span data-stu-id="bd371-193">You can also use the utility to add and remove subscriptions, as well as to enable and disable alerts.</span></span> <span data-ttu-id="bd371-194">有关使用 BAM 管理实用程序的详细信息，请参阅[BAM 管理实用程序](../core/bam-management-utility.md)，[管理 BAM 安全性](../core/managing-bam-security.md)，并[管理 BAM 定义](../core/managing-bam-definitions.md)。</span><span class="sxs-lookup"><span data-stu-id="bd371-194">For more information about using the BAM Management utility, see [BAM Management Utility](../core/bam-management-utility.md), [Managing BAM Security](../core/managing-bam-security.md), and [Managing BAM Definitions](../core/managing-bam-definitions.md).</span></span>  
  
 <span data-ttu-id="bd371-195">您还可以创建和删除通过 BAM 门户的警报。</span><span class="sxs-lookup"><span data-stu-id="bd371-195">You can also create and remove alerts through the BAM portal.</span></span>  <span data-ttu-id="bd371-196">有关创建使用 BAM 门户的警报的信息，请参阅[BAM 门户中的活动搜索](../core/activity-searches-in-the-bam-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="bd371-196">For information about creating alerts using the BAM portal, see [Activity Searches in the BAM Portal](../core/activity-searches-in-the-bam-portal.md).</span></span>  
  
### <a name="cleaning-up-the-alerts-chronicle-table"></a><span data-ttu-id="bd371-197">清理 Alerts Chronicle 表</span><span class="sxs-lookup"><span data-stu-id="bd371-197">Cleaning up the Alerts Chronicle table</span></span>  
 <span data-ttu-id="bd371-198">如果配置 BAM 警报，是为创建每个活动视图创建一个 SQL 作业。</span><span class="sxs-lookup"><span data-stu-id="bd371-198">If BAM alerts are configured, a SQL job is created for each activity view that is created.</span></span> <span data-ttu-id="bd371-199">该作业将使用以下模板命名为：</span><span class="sxs-lookup"><span data-stu-id="bd371-199">The job will be named using the following template:</span></span>  
  
 <span data-ttu-id="bd371-200">bam_\<视图名称\>_\<活动视图\>_DelAlertHistJob</span><span class="sxs-lookup"><span data-stu-id="bd371-200">bam_\<View Name\>_\<Activity View\>_DelAlertHistJob</span></span>  
  
 <span data-ttu-id="bd371-201">此作业清理审核数据为指定的实例警报\<活动视图\>为 Bam_Metadata_AlertChronicle 表中。</span><span class="sxs-lookup"><span data-stu-id="bd371-201">This job cleans up auditing data for the instance alerts for the specified \<Activity View\> in the Bam_Metadata_AlertChronicle table.</span></span> <span data-ttu-id="bd371-202">如果在特定的活动视图上定义了实例警报，新行将添加到此表每次触发警报。</span><span class="sxs-lookup"><span data-stu-id="bd371-202">If you have defined instance alerts on the particular activity view, a new row will be added to this table every time the alert is fired.</span></span>  
  
 <span data-ttu-id="bd371-203">可以运行此作业手动清除的表，或者计划运行根据应用程序或环境的需求。</span><span class="sxs-lookup"><span data-stu-id="bd371-203">You can run this job manually to clean up the table or schedule it to run according to the need of your application or environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd371-204">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd371-204">See Also</span></span>  
 [<span data-ttu-id="bd371-205">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="bd371-205">Managing BAM</span></span>](../core/managing-bam.md)
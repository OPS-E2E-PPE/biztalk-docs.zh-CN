---
title: 如何更新对 BAM Notification Services 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM], restoring
- Notification Services Application database [BAM], updating references
- restoring, BAM
- NS$instance_name service Notification Services Application database [BAM], NS$instance_name service
- restoring [BAM], updating references
- BAM, restoring
- restoring [BAM], Notification Services Application database
- restoring [BAM], NS$instance_name service
ms.assetid: b007fdc2-2e74-4eef-b4c3-43689e9f2180
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 712e43b5220b6836d80d49953e159c878f40ca79
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978278"
---
# <a name="how-to-update-references-to-the-bam-notification-services-databases"></a><span data-ttu-id="3b60f-102">如何更新对 BAM Notification Services 数据库的引用</span><span class="sxs-lookup"><span data-stu-id="3b60f-102">How to Update References to the BAM Notification Services Databases</span></span>
<span data-ttu-id="3b60f-103">执行完将业务活动监视 (BAM) Notification Services 数据库还原到目标系统所需的步骤后，必须在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组中运行 Notification Services (NSservice.exe) 的所有计算机上重新注册 Notification Services。</span><span class="sxs-lookup"><span data-stu-id="3b60f-103">After you perform the steps necessary to restore the Business Activity Monitoring (BAM) Notification Services databases to the destination system, you must re-register the Notification Service on all computers in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group that are running Notification Services (NSservice.exe).</span></span> <span data-ttu-id="3b60f-104">这样可使 Notification Services 连接到新位置上的数据库。</span><span class="sxs-lookup"><span data-stu-id="3b60f-104">This enables Notification Services to connect to the databases in their new location.</span></span>  
  
 <span data-ttu-id="3b60f-105">注册 Notification Services 实例后会创建 NS$instance_name 服务，在本地服务器上创建性能计数器，并将信息添加到注册表中。</span><span class="sxs-lookup"><span data-stu-id="3b60f-105">Registering an instance of Notification Services creates the NS$instance_name service, creates performance counters on the local server, and adds information to the registry.</span></span> <span data-ttu-id="3b60f-106">必须在以下服务器上注册该实例：</span><span class="sxs-lookup"><span data-stu-id="3b60f-106">You must register the instance on the following servers:</span></span>  
  
- <span data-ttu-id="3b60f-107">运行 NS$instance_name 服务的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="3b60f-107">Each server that runs the NS$instance_name service.</span></span> <span data-ttu-id="3b60f-108">运行事件提供程序宿主、生成器和分发服务器组件的服务。</span><span class="sxs-lookup"><span data-stu-id="3b60f-108">The service runs the event provider host, generator, and distributor components.</span></span> <span data-ttu-id="3b60f-109">对于扩展配置，则为在多个服务器上运行的服务。</span><span class="sxs-lookup"><span data-stu-id="3b60f-109">For scaled-out configurations, the service runs on multiple servers.</span></span>  
  
- <span data-ttu-id="3b60f-110">运行订阅管理应用程序的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="3b60f-110">Each server that runs a subscription management application.</span></span> <span data-ttu-id="3b60f-111">如果订阅管理应用程序在自己的服务器上运行，则注册该实例时不会创建 NS$instance_name 服务。</span><span class="sxs-lookup"><span data-stu-id="3b60f-111">If the subscription management application runs on its own server, do not create the NS$instance_name service when registering the instance.</span></span>  
  
- <span data-ttu-id="3b60f-112">运行独立事件提供程序的所有服务器。</span><span class="sxs-lookup"><span data-stu-id="3b60f-112">Each server that runs an independent event provider.</span></span> <span data-ttu-id="3b60f-113">如果独立事件提供程序在它自己的服务器上或数据库服务器上运行，则注册该实例时不会创建 NS$instance_name 服务。</span><span class="sxs-lookup"><span data-stu-id="3b60f-113">If the independent event provider runs on its own server or the database server, do not create the NS$instance_name service when registering the instance.</span></span>  
  
  <span data-ttu-id="3b60f-114">如果数据库服务器不同时运行 Notification Services 实例或客户端组件，则不会在此服务器上注册该实例。</span><span class="sxs-lookup"><span data-stu-id="3b60f-114">If the database server does not also run the Notification Services instance or the client components, do not register the instance on this server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3b60f-115">必要條件</span><span class="sxs-lookup"><span data-stu-id="3b60f-115">Prerequisites</span></span>  
  
-   <span data-ttu-id="3b60f-116">必须以 Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="3b60f-116">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
-   <span data-ttu-id="3b60f-117">将要还原 BAM Notification Services 数据库的计算机上必须安装 SQL Notification Services 的业务活动监视 (BAM) 警报提供程序。</span><span class="sxs-lookup"><span data-stu-id="3b60f-117">The Business Activity Monitoring (BAM) Alert Provider for SQL Notification Services must be installed on the computer where you are restoring the BAM Notification Services databases.</span></span>  
  
### <a name="to-update-references-to-the-bam-notification-services-databases-sql-server-2008-r2sp1"></a><span data-ttu-id="3b60f-118">更新对 BAM Notification Services 数据库的引用 (SQL Server 2008 R2/SP1)</span><span class="sxs-lookup"><span data-stu-id="3b60f-118">To update references to the BAM Notification Services databases (SQL Server 2008 R2/SP1)</span></span>  
  
1. <span data-ttu-id="3b60f-119">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3b60f-119">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="3b60f-120">在命令提示符下，导航到以下目录：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="3b60f-120">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
3. <span data-ttu-id="3b60f-121">类型： **bm.exe get-config –**</span><span class="sxs-lookup"><span data-stu-id="3b60f-121">Type: **bm.exe get-config –filename:config.xml**</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="3b60f-122">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="3b60f-122">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
4. <span data-ttu-id="3b60f-123">打开在步骤 2 中创建的 xml 文件以获取必须重新注册 Notification Services 的计算机列表。</span><span class="sxs-lookup"><span data-stu-id="3b60f-123">Open the xml file created in step 2 to obtain the list of the computers on which you must re-register Notification Services.</span></span>  
  
    <span data-ttu-id="3b60f-124">中列出了计算机名称**\<属性名称\=\>** 中的参数**\<DeploymentUnit 名称 ="Alert"\>** xml 文件的部分：</span><span class="sxs-lookup"><span data-stu-id="3b60f-124">The computer names are listed in the **\<Property Name\=\>** parameters in the **\<DeploymentUnit Name="Alert"\>** section of the xml file:</span></span>  
  
   ```  
   -<DeploymentUnit Name="Alert">  
   <Property Name="GeneratorServerName" />  
   <Property Name="ProviderServerName" />  
   <Property Name="DistributorServerName" />  
     </DeploymentUnit>  
   ```  
  
5. <span data-ttu-id="3b60f-125">在 xml 文件列出的每台计算机上，停止 NS 服务，然后注销 Notification Services 实例：</span><span class="sxs-lookup"><span data-stu-id="3b60f-125">On each computer listed in the xml file, stop the NS service and then unregister an instance of Notification Services:</span></span>  
  
   1.  <span data-ttu-id="3b60f-126">单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，单击**配置工具**，然后单击**Notification Services 命令提示符下**。</span><span class="sxs-lookup"><span data-stu-id="3b60f-126">Click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
   2.  <span data-ttu-id="3b60f-127">在命令提示符处，键入： **net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="3b60f-127">At the command prompt, type: **net stop NS$BamAlerts**</span></span>  
  
   3.  <span data-ttu-id="3b60f-128">键入以下命令，注销该实例：</span><span class="sxs-lookup"><span data-stu-id="3b60f-128">Type the following command to unregister the instance:</span></span>  
  
        <span data-ttu-id="3b60f-129">**nscontrol unregister-name BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="3b60f-129">**nscontrol unregister  -name BamAlerts**</span></span>  
  
        <span data-ttu-id="3b60f-130">注销实例会删除注册表项、NS$instance_name 服务（如果存在），还会删除该服务的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="3b60f-130">Unregistering an instance removes the registry entries, removes the NS$instance_name service (if present), and deletes the performance counters for the service.</span></span>  
  
6. <span data-ttu-id="3b60f-131">重新注册 Notification Service：</span><span class="sxs-lookup"><span data-stu-id="3b60f-131">Re-register the Notification Service:</span></span>  
  
   1.  <span data-ttu-id="3b60f-132">单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，单击**配置工具**，然后单击**Notification Services 命令提示符下**。</span><span class="sxs-lookup"><span data-stu-id="3b60f-132">Click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
   2.  <span data-ttu-id="3b60f-133">在命令提示符处，键入： **nscontrol register-name BamAlerts-server**  *\<ServerName\>***-服务-serviceusername"*** \<ServiceUserName\>***"-servicepassword"***\<ServicePassword\>* * *"**</span><span class="sxs-lookup"><span data-stu-id="3b60f-133">At the command prompt, type: **nscontrol register -name BamAlerts -server** *\<ServerName\>***-service -serviceusername "***\<ServiceUserName\>***" -servicepassword "***\<ServicePassword\>***"**</span></span>  
  
        <span data-ttu-id="3b60f-134">这样可使 Notification Services 登录到正确的数据库（此信息由 nscontrol 在服务所在计算机的注册表中维护）。</span><span class="sxs-lookup"><span data-stu-id="3b60f-134">This enables Notification Services to log on to the correct database (this information is maintained in the registry of the service machine by nscontrol).</span></span>  
  
       > [!IMPORTANT]
       >  <span data-ttu-id="3b60f-135">请记得使用新的 Notification Services 数据库服务器 **-服务器**选项时重新注册该服务。</span><span class="sxs-lookup"><span data-stu-id="3b60f-135">Remember to use the new Notification Services databases server in the **-server** option when re-registering the service.</span></span> <span data-ttu-id="3b60f-136">此外，新的 Notification Services 服务使用的用户名应与旧名称相同。</span><span class="sxs-lookup"><span data-stu-id="3b60f-136">In addition, you should use the same user name for the new Notification Services service as the old one.</span></span>  
  
7. <span data-ttu-id="3b60f-137">在承载 BAM 门户的计算机，单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，单击**配置工具**，然后单击**Notification Services 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="3b60f-137">On the computer that hosts the BAM portal, click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Notification Services Command Prompt**.</span></span>  
  
8. <span data-ttu-id="3b60f-138">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="3b60f-138">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="3b60f-139">**net stop NS$ BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="3b60f-139">**net stop NS$BamAlerts**</span></span>  
  
9. <span data-ttu-id="3b60f-140">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="3b60f-140">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="3b60f-141">**nscontrol unregister-name BamAlerts**</span><span class="sxs-lookup"><span data-stu-id="3b60f-141">**nscontrol unregister  -name BamAlerts**</span></span>  
  
10. <span data-ttu-id="3b60f-142">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="3b60f-142">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="3b60f-143">**nscontrol register-名称***\<BamAlerts\>***-server**  *\<NotificationServicesDatabaseServer    \>*</span><span class="sxs-lookup"><span data-stu-id="3b60f-143">**nscontrol register  -name**  *\<BamAlerts\>*  **-server** *\<NotificationServicesDatabaseServer\>*</span></span>  
  
11. <span data-ttu-id="3b60f-144">在命令提示符处，键入： **net start NS$ BamAlerts**。</span><span class="sxs-lookup"><span data-stu-id="3b60f-144">At the command prompt, type: **net start NS$BamAlerts**.</span></span>  
  
12. <span data-ttu-id="3b60f-145">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3b60f-145">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="3b60f-146">在命令提示符下，导航到以下目录：[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking。</span><span class="sxs-lookup"><span data-stu-id="3b60f-146">At the command prompt, navigate to the following directory: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.</span></span>  
  
14. <span data-ttu-id="3b60f-147">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="3b60f-147">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="3b60f-148">**bm.exe 更新配置 –FileName:config.xml**</span><span class="sxs-lookup"><span data-stu-id="3b60f-148">**bm.exe update-config –FileName:config.xml**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3b60f-149">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="3b60f-149">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b60f-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b60f-150">See Also</span></span>  
 [<span data-ttu-id="3b60f-151">备份和还原 BAM</span><span class="sxs-lookup"><span data-stu-id="3b60f-151">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)
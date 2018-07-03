---
title: 如何在 NLB 群集上配置 BAM 门户，转到工作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96c04fde-dc12-42fb-9193-aa74819fe880
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adc423fc74cd504f79a1106d196868df20faf974
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994462"
---
# <a name="how-to-configure-the-bam-portal-to-work-on-an-nlb-cluster"></a><span data-ttu-id="35067-102">如何配置要在 NLB 群集上使用的 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="35067-102">How to Configure the BAM Portal to Work on an NLB Cluster</span></span>
<span data-ttu-id="35067-103">可以将 BAM 门户配置为在网络负载平衡 (NLB) 群集中使用。</span><span class="sxs-lookup"><span data-stu-id="35067-103">The BAM portal can be configured to work in a network load balancing (NLB) cluster.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="35067-104">BAM 门户*仅*在 32 位模式下运行。</span><span class="sxs-lookup"><span data-stu-id="35067-104">BAM Portal *only* runs in 32-bit mode.</span></span> <span data-ttu-id="35067-105">如果 IIS 安装在 64 位计算机上，请确认在 32 位模式下启用了 ASP.NET 2.0。</span><span class="sxs-lookup"><span data-stu-id="35067-105">If IIS is installed on a 64-bit machine, then confirm ASP.NET 2.0 is enabled in 32-bit mode.</span></span> <span data-ttu-id="35067-106">若要执行此操作，请打开 IIS 管理器中，打开**应用程序池**，选择应用程序池 (BAMAppPool)，然后单击**高级设置**。</span><span class="sxs-lookup"><span data-stu-id="35067-106">To do this, open IIS Manager, open **Application Pool**, select the application pool (BAMAppPool), and then click **Advanced Settings**.</span></span> <span data-ttu-id="35067-107">在“启用 32 位应用程序”中，选择 **True**。</span><span class="sxs-lookup"><span data-stu-id="35067-107">In **Enable 32-bit applications**, select **True**.</span></span>  
>   
>  <span data-ttu-id="35067-108">有关其他 BAM 门户要求，请参阅[规划 BAM 门户](../core/planning-for-the-bam-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="35067-108">For additional BAM Portal requirements, see [Planning for the BAM Portal](../core/planning-for-the-bam-portal.md).</span></span>  
  
### <a name="to-prepare-to-configure-bam-portal-on-an-nlb-cluster"></a><span data-ttu-id="35067-109">准备在 NLB 群集上配置 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="35067-109">To prepare to configure BAM portal on an NLB cluster</span></span>  
  
1.  <span data-ttu-id="35067-110">在第一台计算机上安装并配置门户。</span><span class="sxs-lookup"><span data-stu-id="35067-110">Install and configure the portal on the first computer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35067-111">只在第一台计算机上配置门户。</span><span class="sxs-lookup"><span data-stu-id="35067-111">You only configure the portal on the first computer.</span></span> <span data-ttu-id="35067-112">你可以选择在群集中的其他计算机上启用 BAM 门户，但只在第一台计算机上进行配置。</span><span class="sxs-lookup"><span data-stu-id="35067-112">You have the option of enabling the BAM portal on other the other computers in the cluster, but the configuration is done only on the first computer.</span></span>  
  
2.  <span data-ttu-id="35067-113">在所有要包括在 NLB 群集中的计算机上安装门户组件，然后将群集中的其他计算机加入到已配置门户的计算机的 BizTalk 组中。</span><span class="sxs-lookup"><span data-stu-id="35067-113">Install the portal components on all the computers to be included in the NLB cluster, and then join the other computers in the cluster to the BizTalk group of the computer on which the portal is configured.</span></span> <span data-ttu-id="35067-114">必须启用 BizTalk 组并加入相应组。</span><span class="sxs-lookup"><span data-stu-id="35067-114">You must enable the BizTalk groups and join the appropriate group.</span></span>  
  
3.  <span data-ttu-id="35067-115">选择为安装门户的计算机配置的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="35067-115">Select the BizTalk Management database configured for the computer on which the portal is installed.</span></span>  
  
4.  <span data-ttu-id="35067-116">创建 NLB 群集。</span><span class="sxs-lookup"><span data-stu-id="35067-116">Create the NLB cluster.</span></span> <span data-ttu-id="35067-117">有关如何创建和管理网络负载平衡群集的详细信息，请参阅"创建和管理网络负载平衡群集"处[ http://go.microsoft.com/fwlink/?LinkId=56206 ](http://go.microsoft.com/fwlink/?LinkId=56206)。</span><span class="sxs-lookup"><span data-stu-id="35067-117">For more information about how to create and manage network load balancing clusters, see "Create and Manage Network Load Balancing Clusters" at [http://go.microsoft.com/fwlink/?LinkId=56206](http://go.microsoft.com/fwlink/?LinkId=56206).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35067-118">继续操作之前，应该确认 NLB 群集在 BizTalk Server 上下文以外工作正常。</span><span class="sxs-lookup"><span data-stu-id="35067-118">You should confirm that your NLB cluster is working properly outside of the BizTalk Server context before continuing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35067-119">若要设置基于硬件的 NLB，请参阅硬件提供商的文档。</span><span class="sxs-lookup"><span data-stu-id="35067-119">To set up hardware-based NLB, refer to your hardware provider's documentation.</span></span>  
  
### <a name="to-update-the-bam-configuration-to-reflect-the-location-of-the-cluster"></a><span data-ttu-id="35067-120">更新 BAM 配置以反映群集的位置</span><span class="sxs-lookup"><span data-stu-id="35067-120">To update the BAM configuration to reflect the location of the cluster</span></span>  
  
1. <span data-ttu-id="35067-121">使用 BAM 管理实用程序获得当前 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="35067-121">Use the BAM Management Utility to get the current BAM configuration.</span></span> <span data-ttu-id="35067-122">若要执行此操作，请单击**启动**，单击**运行**，然后键入[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm get-config-filename: Myconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="35067-122">To do this, click **Start**, click **Run**, and type [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm get-config -FileName:MyConfig.xml.</span></span>  
  
2. <span data-ttu-id="35067-123">将本地主机名换为 NLB 群集的名称。</span><span class="sxs-lookup"><span data-stu-id="35067-123">Replace the local host name with the name of the NLB cluster.</span></span> <span data-ttu-id="35067-124">若要执行此操作，请单击**启动**，单击**运行**，然后键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\MyConfig.xml。</span><span class="sxs-lookup"><span data-stu-id="35067-124">To do this, click **Start**, click **Run**, and type notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\MyConfig.xml.</span></span>  
  
3. <span data-ttu-id="35067-125">仅对于基于硬件的 NLB，验证配置文件具有以下内容：</span><span class="sxs-lookup"><span data-stu-id="35067-125">For hardware-based NLB only, verify the configuration file has the following:</span></span>  
  
   ```  
   <GlobalProperty Name="BAMVRoot">  
   http://<NLB IP Address>:portname/BAM</GlobalProperty>  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="35067-126">在更新基于硬件的 NLB 上的 BAM 配置时，不必执行步骤 4 和 5。</span><span class="sxs-lookup"><span data-stu-id="35067-126">Steps 4 and 5 are not necessary when updating the BAM configuration on hardware-based NLB.</span></span>  
  
4. <span data-ttu-id="35067-127">将以下行中的计算机名 (machinename) 改为群集名以指向 NLB 群集：</span><span class="sxs-lookup"><span data-stu-id="35067-127">Modify the following line to point to the NLB cluster by replacing the computer name (machinename) with the cluster name:</span></span>  
  
   ```  
   <GlobalProperty Name=" BAMVRoot">  http://machinename:portname/BAM  
   </GlobalProperty>   
   ```  
  
5. <span data-ttu-id="35067-128">保存新配置。</span><span class="sxs-lookup"><span data-stu-id="35067-128">Save the new configuration.</span></span> <span data-ttu-id="35067-129">若要执行此操作，请单击**启动**，单击**运行**，然后键入[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm 更新-config-filename: Myconfig.xml。</span><span class="sxs-lookup"><span data-stu-id="35067-129">To do this, click **Start**, click **Run**, and type [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\bm update-config -FileName:MyConfig.xml.</span></span>  
  
### <a name="to-edit-the-bam-portal-webconfig-file-to-change-the-bammanagementservice-and-queryservice-urls-to-point-to-the-nlb-server-name-note-this-procedure-is-not-necessary-for-hardware-based-nlb"></a><span data-ttu-id="35067-130">编辑 BAM 门户 web.config 文件中的 BAMmanagementService 和 QueryService URL 使之改为指向 NLB 服务器名。</span><span class="sxs-lookup"><span data-stu-id="35067-130">To edit the BAM portal web.config file to change the BAMmanagementService and QueryService URLs to point to the NLB server name.</span></span> <span data-ttu-id="35067-131">注意： 此过程不是基于硬件的 NLB 所需的。</span><span class="sxs-lookup"><span data-stu-id="35067-131">Note: This procedure is not necessary for hardware-based NLB.</span></span>  
  
1. <span data-ttu-id="35067-132">打开 web.config 文件，使用记事本**启动**，再单击**运行**，键入 notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="35067-132">Open the web.config file using Notepad by clicking **Start**, clicking **Run**, typing notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\web.config, and then clicking **OK**.</span></span>  
  
2. <span data-ttu-id="35067-133">在以下两行中修改其中的计算机名 (machinename) 和端口名，使其指向群集名：</span><span class="sxs-lookup"><span data-stu-id="35067-133">Modify the following computer name (machinename) and the port name in the following two lines to point to the name of name of the cluster:</span></span>  
  
   ```  
   <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
   <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />   
   ```  
  
3. <span data-ttu-id="35067-134">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="35067-134">Save the file.</span></span> <span data-ttu-id="35067-135">若要执行此操作，请单击**文件**，然后单击**保存**记事本的菜单栏上。</span><span class="sxs-lookup"><span data-stu-id="35067-135">To do this, click **File**, and then click **Save** on the Notepad menu bar.</span></span>  
  
### <a name="to-configure-each-additional-computer-in-the-cluster"></a><span data-ttu-id="35067-136">配置群集中的其他计算机</span><span class="sxs-lookup"><span data-stu-id="35067-136">To configure each additional computer in the cluster</span></span>  
  
1. <span data-ttu-id="35067-137">将 web.config 文件复制到群集中每个其他计算机的 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="35067-137">Copy the web.config file to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal folder on each additional computer in the cluster.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="35067-138">在以下步骤对所有引用**Program Files**文件夹将为**Program Files (x86)** 对于 64 位计算机。</span><span class="sxs-lookup"><span data-stu-id="35067-138">In the following steps all references to the **Program Files** folder will be **Program Files (x86)** for 64 bit computers.</span></span>  
   > 
   > [!IMPORTANT]
   >  <span data-ttu-id="35067-139">在以下步骤中，创建虚拟目录时，请进行查看以确保它们与 BizTalk Server 配置在第一台计算机上所创建的三个 BAM 虚拟目录的设置相同。</span><span class="sxs-lookup"><span data-stu-id="35067-139">In the following steps, when you are creating the virtual directories, check to make sure they have the exact settings as the three BAM virtual directories created by the BizTalk Server Configuration on first computer.</span></span> <span data-ttu-id="35067-140">确认文件路径、ASP.NET 版本、目录权限和应用程序池。</span><span class="sxs-lookup"><span data-stu-id="35067-140">Confirm your file paths, the ASP.NET version, your directory permissions, and application pool.</span></span>  <span data-ttu-id="35067-141">使用与你设置第一台计算机时使用的相同的域服务帐户在要设置的计算机上运行 BAMAppPool。</span><span class="sxs-lookup"><span data-stu-id="35067-141">Use the same domain service account to run the BAMAppPool on the computer you are setting up as you used when setting up the first computer.</span></span> <span data-ttu-id="35067-142">确保 BAMAppPool 在所有计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="35067-142">Make sure the BAMAppPool is running on all of the computers.</span></span> <span data-ttu-id="35067-143">你必须复制两个 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="35067-143">There are two web.config files you must copy.</span></span>  
   > 
   >  <span data-ttu-id="35067-144">除 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal 中的 web.config 文件之外，还必须将 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService 和 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMQueryService 中的 web.config 文件复制到此计算机的相同文件夹中。</span><span class="sxs-lookup"><span data-stu-id="35067-144">In addition to the web.config file [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal, you must copy the web.config file in [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMManagementService and [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]BAMPortal\BAMQueryService to the same folders on this computer.</span></span>  
  
2. <span data-ttu-id="35067-145">仅对于基于硬件的 NLB，在以下两行中修改其中的计算机名 (machinename) 和端口名，使其指向群集名：</span><span class="sxs-lookup"><span data-stu-id="35067-145">For hardware-based NLB only, modify the following computer name (machinename) and the port name in the following two lines to point to the name of name of the cluster:</span></span>  
  
   ```  
   <add key="BamQueryWSUrl" value="http://machinename:portname /BAM/BAMQueryService/BamQueryService.asmx" />  
   <add key="BamManagementWSUrl" value=" http://machinename:portname/BAM/BAMManagementService/BamManagementService.asmx" />  
   ```  
  
3. <span data-ttu-id="35067-146">创建一个称为 BAMAppPool 的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="35067-146">Create an application pool called BAMAppPool.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="35067-147">虚拟目录的目录路径应为 %installationfolder%/bamportal、 InstallationFolder%/BamPortal/BAMManagementService，%和 %installationfolder%InstallationFolder%/BamPortal/BAMQueryService。</span><span class="sxs-lookup"><span data-stu-id="35067-147">The directory path for the virtual directories should be %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService, and %InstallationFolder%/BamPortal/BAMQueryService.</span></span>  
  
4. <span data-ttu-id="35067-148">在默认网站下创建名为 BAM 的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="35067-148">Create a virtual directory under the Default Website called BAM.</span></span>  
  
5. <span data-ttu-id="35067-149">将 BAM 虚拟目录的应用程序池更改为 BAMAppPool。</span><span class="sxs-lookup"><span data-stu-id="35067-149">Change the application pool of BAM virtual directory to BAMAppPool.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="35067-150">虚拟目录的目录路径应为 %InstallationFolder%/BamPortal、%InstallationFolder%/BamPortal/BAMManagementService 和 %InstallationFolder%/BamPortal/BAMQueryService。</span><span class="sxs-lookup"><span data-stu-id="35067-150">The directory path for the virtual directories should be %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService and %InstallationFolder%/BamPortal/BAMQueryService.</span></span>  
  
6. <span data-ttu-id="35067-151">在 BAM 下创建名为 BAMManagementService 的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="35067-151">Create a virtual directory called BAMManagementService under BAM.</span></span>  
  
7. <span data-ttu-id="35067-152">将 BAMManagementService 的应用程序池改为 BAMAppPool。</span><span class="sxs-lookup"><span data-stu-id="35067-152">Change the application pool of BAMManagementService to BAMAppPool.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="35067-153">虚拟目录的目录路径应为 %installationfolder%/bamportal、 InstallationFolder%/BamPortal/BAMManagementService，%和 %installationfolder%InstallationFolder%/BamPortal/BAMQueryService。</span><span class="sxs-lookup"><span data-stu-id="35067-153">The directory path for the virtual directories should be %InstallationFolder%/BamPortal, %InstallationFolder%/BamPortal/BAMManagementService, and %InstallationFolder%/BamPortal/BAMQueryService.</span></span>  
  
8. <span data-ttu-id="35067-154">在 BAM 下创建名为 BAMQueryService 的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="35067-154">Create a virtual directory called BAMQueryService under BAM.</span></span>  
  
9. <span data-ttu-id="35067-155">将 BAMQueryService 的应用程序池改为 BAMAppPool。</span><span class="sxs-lookup"><span data-stu-id="35067-155">Change the application pool of BAMQueryService to BAMAppPool.</span></span>  
  
10. <span data-ttu-id="35067-156">在虚拟目录属性 ASP NET 选项卡上，使用 INETMGR 更改 BAM 的版本，使用 BAMMANAGEMENTSERVICE 和 BAMQUERYSERVICE 将应用程序的版本设置为 .NET Framework 4。</span><span class="sxs-lookup"><span data-stu-id="35067-156">Use the INETMGR, located on the virtual directory Properites ASP NET Tab, to change the version for BAM, BAMMANAGEMENTSERVICE, and BAMQUERYSERVICE to set the version of the Applications to .NET Framework 4.</span></span>  
  
11. <span data-ttu-id="35067-157">运行 aspnet_setreg.exe -k:"SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\identity" -u:BAMWebServiceAccount  -p:Password。</span><span class="sxs-lookup"><span data-stu-id="35067-157">Run aspnet_setreg.exe -k:"SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\identity" -u:BAMWebServiceAccount  -p:Password.</span></span>  <span data-ttu-id="35067-158">此处指定的帐户是 BAM 管理 Web Services 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="35067-158">The account specified here is the BAM Management Web Service User account.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="35067-159">BAM 门户*仅*在 32 位模式下运行。</span><span class="sxs-lookup"><span data-stu-id="35067-159">BAM Portal *only* runs in 32-bit mode.</span></span> <span data-ttu-id="35067-160">如果 IIS 安装在 64 位计算机上，必须在 32 位模式下启用 ASP.NET 2.0。</span><span class="sxs-lookup"><span data-stu-id="35067-160">If IIS is installed on a 64-bit machine, ASP.NET 2.0 must be enabled in 32-bit mode.</span></span> <span data-ttu-id="35067-161">若要执行此操作，请打开 IIS 管理器中，打开**应用程序池**，选择应用程序池 (BAMAppPool)，然后单击**高级设置**。</span><span class="sxs-lookup"><span data-stu-id="35067-161">To do this, open IIS Manager, open **Application Pool**, select the application pool (BAMAppPool), and then click **Advanced Settings**.</span></span> <span data-ttu-id="35067-162">在“启用 32 位应用程序”中，选择 **True**。</span><span class="sxs-lookup"><span data-stu-id="35067-162">In **Enable 32-bit applications**, select **True**.</span></span>  
    >   
    >  <span data-ttu-id="35067-163">[规划 BAM 门户](../core/planning-for-the-bam-portal.md)列出了其他要求。</span><span class="sxs-lookup"><span data-stu-id="35067-163">[Planning for the BAM Portal](../core/planning-for-the-bam-portal.md) lists additional requirements.</span></span>  
  
12. <span data-ttu-id="35067-164">运行 SubInACL，为 Web Services 上的应用程序池用户设置读 ACL。SubInACL 是一个命令行工具，使用它可以使管理员获取有关文件、注册表项和服务的安全信息，并将此信息从一个用户传递到另一个用户，从本地传递到全局，从一个组传递到另一个组，以及从一个域传递到另一个域。</span><span class="sxs-lookup"><span data-stu-id="35067-164">Set the read ACLs for the AppPool user on WebServices by running SubInACL, a command-line tool that enables administrators to obtain security information about files, registry keys, and services, and to transfer this information from user to user, from local or global group to group, and from domain to domain.</span></span>  
  
13. <span data-ttu-id="35067-165">下载从 SubInAcl [ http://go.microsoft.com/fwlink/?LinkId=61990 ](http://go.microsoft.com/fwlink/?LinkId=61990)。</span><span class="sxs-lookup"><span data-stu-id="35067-165">Download SubInAcl from [http://go.microsoft.com/fwlink/?LinkId=61990](http://go.microsoft.com/fwlink/?LinkId=61990).</span></span>  
  
14. <span data-ttu-id="35067-166">打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="35067-166">Open a command prompt.</span></span> <span data-ttu-id="35067-167">若要执行此操作，请单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="35067-167">To do this, click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
15. <span data-ttu-id="35067-168">在命令提示符下键入以下内容： subinacl.exe /subkeyreg"HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices""/ 授予 = 网络服务 = R"</span><span class="sxs-lookup"><span data-stu-id="35067-168">Type the following at the command prompt: subinacl.exe /subkeyreg "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices" "/grant=Network Service=R"</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35067-169">此命令的目的是授予 BAM 应用程序池用户读取访问权限 SOFTWAREMicrosoftBizTalk Server3.0BAMWebServicesidentity 注册表项。</span><span class="sxs-lookup"><span data-stu-id="35067-169">The purpose of this command is to grant the BAM Application Pool user read access to the SOFTWAREMicrosoftBizTalk Server3.0BAMWebServicesidentity registry key.</span></span> <span data-ttu-id="35067-170">由于默认情况下，IIS 对应用程序池使用网络服务，因此本示例使用网络服务。</span><span class="sxs-lookup"><span data-stu-id="35067-170">The example uses Network Service since it is the default used by IIS for Application Pool.</span></span> <span data-ttu-id="35067-171">如果你不想使用默认的 IIS 设置，则应该替换你的部署所使用的应用程序池用户。</span><span class="sxs-lookup"><span data-stu-id="35067-171">If you do not use the default IIS settings, you should substitute the application pool user that your deployment uses.</span></span>  
  
16. <span data-ttu-id="35067-172">在命令提示符下键入以下内容： subinacl.exe /keyreg"HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0""/ 授予 =\<WebService 帐户\>"</span><span class="sxs-lookup"><span data-stu-id="35067-172">Type the following at the command prompt: subinacl.exe /keyreg "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk Server\3.0" "/grant=\<BAM WebService Account\>”</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35067-173">此命令的目的是向 BAM 管理 Web Services 用户帐户授予读取 SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\Identity 注册表项的权限。</span><span class="sxs-lookup"><span data-stu-id="35067-173">The purpose of this command is to grant the BAM Management Web Service User account read access to the SOFTWARE\Microsoft\BizTalk Server\3.0\BAM\WebServices\Identity registry key.</span></span>  
  
17. <span data-ttu-id="35067-174">验证应用程序池用于运行 BAMManagement Web 服务的身份具有对 ASPNET_SETREG 键的读访问权限。</span><span class="sxs-lookup"><span data-stu-id="35067-174">Verify that the identity that the application pool that the BAMManagement Web service runs under has read access to the ASPNET_SETREG key.</span></span>  
  
18. <span data-ttu-id="35067-175">使用“计算机管理”管理员工具向 IIS Worker Process 组 (IIS_WPG) 和 SharePoint services 组 (STS_WPG) 添加 BAM 管理 Web Services 用户和 BAM 应用程序池帐户。</span><span class="sxs-lookup"><span data-stu-id="35067-175">Use the Computer Management administrator tool to add the BAM Management Web service user and the BAM application pool user account to the IIS Worker Process Group (IIS_WPG) and SharePoint services group (STS_WPG).</span></span>  
  
19. <span data-ttu-id="35067-176">为应用程序池和 Web 服务用户的临时 ASP.NET 文件夹上设置权限： c:\windows\system32\cacls"%windir%\Microsoft.NET\Framework\ v2.0。\<最小版本号\>\Temporary ASP.NET Files"/T /E /G \<WebService 帐户\>: F</span><span class="sxs-lookup"><span data-stu-id="35067-176">Set the permissions on the temporary ASP.NET folders for the applications pool and Web service users: c:\windows\system32\cacls "%windir%\Microsoft.NET\Framework\ v2.0.\<min version number\>\Temporary ASP.NET Files" /T /E /G \<BAM WebService Account\>:F</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="35067-177">你要同时向 BAM 管理 Web Services 用户帐户和 BAM 应用程序池用户帐户授予权限。</span><span class="sxs-lookup"><span data-stu-id="35067-177">You grant access to both the BAM Management Web Service User account and the BAM App Pool User account.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35067-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="35067-178">See Also</span></span>  
 [<span data-ttu-id="35067-179">管理 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="35067-179">Managing the BAM Portal</span></span>](../core/managing-the-bam-portal.md)
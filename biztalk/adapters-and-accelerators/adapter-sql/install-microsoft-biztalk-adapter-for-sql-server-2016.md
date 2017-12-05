---
title: "安装 Microsoft BizTalk Adapter for SQL Server-2016年 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcc6b94e-1cac-4b90-8567-05b33caa9bf3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bab2a1edc7f3f19a8f76a041472a8c6d01b7743d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2016"></a><span data-ttu-id="b85e2-102">安装 Microsoft BizTalk Adapter for SQL Server-2016</span><span class="sxs-lookup"><span data-stu-id="b85e2-102">Install Microsoft BizTalk Adapter for SQL Server - 2016</span></span>
<span data-ttu-id="b85e2-103">安装[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]附带[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-103">Install the [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] included with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span>

 <span data-ttu-id="b85e2-104">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可以与使用：</span><span class="sxs-lookup"><span data-stu-id="b85e2-104">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used with:</span></span>  
  
-   <span data-ttu-id="b85e2-105">.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="b85e2-105">A .NET application</span></span>  
  
-   <span data-ttu-id="b85e2-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b85e2-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
 <span data-ttu-id="b85e2-107">所需的软件基于如何使用适配器，而异。</span><span class="sxs-lookup"><span data-stu-id="b85e2-107">Based on how you use the adapters, the required software varies.</span></span>  
 
  
<a name="BKMK_prereq_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a><span data-ttu-id="b85e2-108">.NET 应用程序中使用该适配器时的先决条件</span><span class="sxs-lookup"><span data-stu-id="b85e2-108">Prerequisites when using the adapter with a .NET Application</span></span>  
<span data-ttu-id="b85e2-109">要在其中编写.NET 应用程序使用的计算机上安装以下软件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-109">Install the following software on the computer where you are writing .NET applications that consume the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="b85e2-110">列出的顺序安装软件。</span><span class="sxs-lookup"><span data-stu-id="b85e2-110">Install the software in the order as listed.</span></span>  

||
|---|
|<span data-ttu-id="b85e2-111">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b85e2-111">- Windows Server 2016</span></span> <br /><span data-ttu-id="b85e2-112">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b85e2-112">- Windows Server 2012 R2</span></span> <br /><span data-ttu-id="b85e2-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b85e2-113">- Windows 10</span></span> <br /><span data-ttu-id="b85e2-114">-Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b85e2-114">- Windows 8.1</span></span>    |
|<span data-ttu-id="b85e2-115">.NET Framework 4.6.*x*</span><span class="sxs-lookup"><span data-stu-id="b85e2-115">.NET Framework 4.6.*x*</span></span>|
|<span data-ttu-id="b85e2-116">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="b85e2-116">Visual Studio 2015</span></span>|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|
|<span data-ttu-id="b85e2-117">SQL Server 客户端库。</span><span class="sxs-lookup"><span data-stu-id="b85e2-117">SQL Server client libraries.</span></span> <span data-ttu-id="b85e2-118">请参阅[受支持的版本](#BKMK_SuppLOB)（本主题中）。</span><span class="sxs-lookup"><span data-stu-id="b85e2-118">See the [supported versions](#BKMK_SuppLOB) (in this topic).</span></span>|

<a name="BKMK_prereq_BTS"></a>     
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a><span data-ttu-id="b85e2-119">与 BizTalk Server 使用适配器时的先决条件</span><span class="sxs-lookup"><span data-stu-id="b85e2-119">Prerequisites when using the adapter with BizTalk Server</span></span>  
<span data-ttu-id="b85e2-120">如果使用的在计算机上安装以下软件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-120">Install the following software on the computer where you are using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b85e2-121">按列出的顺序安装软件。</span><span class="sxs-lookup"><span data-stu-id="b85e2-121">Install the software in the order listed.</span></span>  

||
|---|
|<span data-ttu-id="b85e2-122">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b85e2-122">- Windows Server 2016</span></span> <br /><span data-ttu-id="b85e2-123">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b85e2-123">- Windows Server 2012 R2</span></span> <br /><span data-ttu-id="b85e2-124">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b85e2-124">- Windows 10</span></span> <br /><span data-ttu-id="b85e2-125">-Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b85e2-125">- Windows 8.1</span></span>    |
|<span data-ttu-id="b85e2-126">.NET Framework 4.6.*x*</span><span class="sxs-lookup"><span data-stu-id="b85e2-126">.NET Framework 4.6.*x*</span></span>|
|<span data-ttu-id="b85e2-127">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="b85e2-127">Visual Studio 2015</span></span>|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="b85e2-128">安装[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]为[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-128">Install the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="b85e2-129">若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-129">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>|
|[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|
|<span data-ttu-id="b85e2-130">SQL Server 客户端库。</span><span class="sxs-lookup"><span data-stu-id="b85e2-130">SQL Server client libraries.</span></span> <span data-ttu-id="b85e2-131">请参阅[受支持的版本](#BKMK_SuppLOB)（本主题中）。</span><span class="sxs-lookup"><span data-stu-id="b85e2-131">See the [supported versions](#BKMK_SuppLOB) (in this topic).</span></span>|

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a><span data-ttu-id="b85e2-132">支持的 SQL Server 版本和客户端库</span><span class="sxs-lookup"><span data-stu-id="b85e2-132">Supported SQL Server versions and client libraries</span></span>  
 <span data-ttu-id="b85e2-133">下面的部分介绍支持的 SQL Server 版本和客户端所需的库[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-133">The following section presents the supported SQL Server versions and the client libraries required by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
-   <span data-ttu-id="b85e2-134">**支持的服务器版本**: SQL Server 2016、 SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="b85e2-134">**Supported server versions**: SQL Server 2016, SQL Server 2014</span></span>
  
-   <span data-ttu-id="b85e2-135">**支持的客户端版本**: Microsoft[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]捆绑包连接到 SQL Server 所需的客户端 Dll。</span><span class="sxs-lookup"><span data-stu-id="b85e2-135">**Supported client versions**: Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] bundles the client DLLs required to connect to SQL Server.</span></span> <span data-ttu-id="b85e2-136">不需要显式安装在计算机上的任何客户端 Dll。</span><span class="sxs-lookup"><span data-stu-id="b85e2-136">You do not need to explicitly install any client DLLs on your computer.</span></span>  
  
-   <span data-ttu-id="b85e2-137">**所需驱动程序**:</span><span class="sxs-lookup"><span data-stu-id="b85e2-137">**Required drivers**:</span></span>  
  
    -   <span data-ttu-id="b85e2-138">如果你使用随 SQL Server 版本，例如，Geography，Udt 请确保以下 Dll 计算机上存在其中你使用该适配器在 SQL Server 上执行操作。</span><span class="sxs-lookup"><span data-stu-id="b85e2-138">If you use the UDTs shipped with the SQL Server versions, for example, Geography, make sure the following DLLs are present on the computer where you use the adapter to perform operations on SQL Server.</span></span> <span data-ttu-id="b85e2-139">例如，如果你创建 BizTalk 项目，在 SQL Server 上执行操作，这些 Dll 必须存在于运行 BizTalk Server 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="b85e2-139">For example, if you create BizTalk projects to perform operations on SQL Server, these DLLs must be present on the computer where BizTalk Server is running.</span></span>  
  
        -   <span data-ttu-id="b85e2-140">请确保 Microsoft.SqlServer.Types.dll 已添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="b85e2-140">Make sure Microsoft.SqlServer.Types.dll is added to the GAC.</span></span>  
  
        -   <span data-ttu-id="b85e2-141">确保 SqlServerSpatial.dll System32 文件夹中可用。</span><span class="sxs-lookup"><span data-stu-id="b85e2-141">Make sure SqlServerSpatial.dll is available in the System32 folder.</span></span>  
  
         <span data-ttu-id="b85e2-142">可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-基本**和**管理工具 – 完整**中**功能选择**向导页。</span><span class="sxs-lookup"><span data-stu-id="b85e2-142">You can install these DLLs on the computer by running the SQL Server setup and selecting **Management Tools – Basic** and **Management Tools – Complete** in the **Feature Selection** page of the wizard.</span></span>  
  
    -   <span data-ttu-id="b85e2-143">如果你使用该适配器上的 FILESTREAM 数据类型的列执行操作，请确保已安装的 SQL 客户端连接 SDK。</span><span class="sxs-lookup"><span data-stu-id="b85e2-143">If you use the adapter to perform operations on columns of FILESTREAM data types, make sure you have SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="b85e2-144">你可以通过运行 SQL Server 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。</span><span class="sxs-lookup"><span data-stu-id="b85e2-144">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="b85e2-145">适配器使用 sqlncli10.dll，安装 SQL 客户端连接 SDK，与执行 FILESTREAM 操作。</span><span class="sxs-lookup"><span data-stu-id="b85e2-145">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  
  
    -   <span data-ttu-id="b85e2-146">如果在 SQL Server 中创建你自己的 Udt，请确保 Udt 的相应程序集添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="b85e2-146">If you create your own UDTs in SQL Server, make sure the respective assemblies for the UDTs are added to the GAC.</span></span>  
  
<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a><span data-ttu-id="b85e2-147">64 位支持</span><span class="sxs-lookup"><span data-stu-id="b85e2-147">64-bit support</span></span> 

<span data-ttu-id="b85e2-148">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可以在一个 32 位或 64 位主机实例中运行。</span><span class="sxs-lookup"><span data-stu-id="b85e2-148">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can run in a 32-bit or 64-bit host instance.</span></span>

 <span data-ttu-id="b85e2-149">有关受支持的安装方案的 32 位和 64 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[32 位和 64 位安装方案](#BKMK_Install_Scenarios)（本主题中）。</span><span class="sxs-lookup"><span data-stu-id="b85e2-149">For information about the supported installation scenarios for the 32-bit and 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see  [32-bit and 64-bit install scenarios](#BKMK_Install_Scenarios) (in this topic).</span></span>
  
<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a><span data-ttu-id="b85e2-150">安装 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="b85e2-150">Install the SQL adapter</span></span>  
 <span data-ttu-id="b85e2-151">请确保已在安装之前安装的先决条件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-151">Make sure you have the prerequisites installed before installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="b85e2-152">请参阅[.NET 系统必备组件](#BKMK_prereq_NET)（本主题中），或[BizTalk Server 先决条件](#BKMK_prereq_BTS)（本主题中）。</span><span class="sxs-lookup"><span data-stu-id="b85e2-152">See [.NET prerequisites](#BKMK_prereq_NET) (in this topic), or [BizTalk Server prerequisites](#BKMK_prereq_BTS) (in this topic).</span></span>
  
 <span data-ttu-id="b85e2-153">你可以安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="b85e2-153">You can install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="b85e2-154">**在交互模式中**使用安装向导</span><span class="sxs-lookup"><span data-stu-id="b85e2-154">**In interactive mode** using the setup wizard</span></span>
  
-   <span data-ttu-id="b85e2-155">**在静默模式下**命令行中使用 msiexec</span><span class="sxs-lookup"><span data-stu-id="b85e2-155">**In silent mode** using msiexec in the command line</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b85e2-156">必须在其中安装的计算机上具有管理特权[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，不管是否使用向导或命令行安装。</span><span class="sxs-lookup"><span data-stu-id="b85e2-156">You must have administrative privileges on the computer where you install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], irrespective of whether you are installing by using the wizard or the command line.</span></span>    

### <a name="BKMK_Install_Scenarios"></a><span data-ttu-id="b85e2-157">32 位和 64 位安装方案</span><span class="sxs-lookup"><span data-stu-id="b85e2-157">32-bit and 64-bit install scenarios</span></span>
 <span data-ttu-id="b85e2-158">与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可用于：</span><span class="sxs-lookup"><span data-stu-id="b85e2-158">With [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used for:</span></span>  
  
-   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="b85e2-159">设计时 （在生成操作的元数据）。</span><span class="sxs-lookup"><span data-stu-id="b85e2-159"> design time (when generating metadata for operations).</span></span>  
  
-   <span data-ttu-id="b85e2-160">BizTalk Server 管理控制台 （用于创建的物理端口） 的设计时。</span><span class="sxs-lookup"><span data-stu-id="b85e2-160">BizTalk Server Administration console design time (for creating physical ports).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b85e2-161">BizTalk Server 管理控制台将作为 32 位 Microsoft 管理控制台 (MMC) 应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="b85e2-161">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  
  
-   <span data-ttu-id="b85e2-162">BizTalk 运行时 （发送和接收消息时从 LOB 应用程序）。</span><span class="sxs-lookup"><span data-stu-id="b85e2-162">BizTalk run time (when sending and receiving messages from LOB applications).</span></span>  
  
 <span data-ttu-id="b85e2-163">你可以安装在同一台计算机或不同计算机上执行所有这些任务的位置。</span><span class="sxs-lookup"><span data-stu-id="b85e2-163">You can have an installation where you perform all these tasks on the same computer or different computers.</span></span> <span data-ttu-id="b85e2-164">因为同时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和 BizTalk MMC 是 32 位进程，则必须安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]你想要执行的设计时任务的计算机上。</span><span class="sxs-lookup"><span data-stu-id="b85e2-164">Because both [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on the computer where you want to perform the design-time tasks.</span></span> <span data-ttu-id="b85e2-165">安装支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 32 位和 64 位平台上。</span><span class="sxs-lookup"><span data-stu-id="b85e2-165">The following scenarios are supported for installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on 32-bit and 64-bit platforms.</span></span>  
  
#### <a name="32-bit-install-scenarios"></a><span data-ttu-id="b85e2-166">32 位安装方案</span><span class="sxs-lookup"><span data-stu-id="b85e2-166">32-bit install scenarios</span></span>  
 <span data-ttu-id="b85e2-167">在安装时支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 32 位平台上。</span><span class="sxs-lookup"><span data-stu-id="b85e2-167">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 32-bit platform.</span></span>  
  
|<span data-ttu-id="b85e2-168">Visual Studio 设计时</span><span class="sxs-lookup"><span data-stu-id="b85e2-168">Visual Studio design time</span></span>|<span data-ttu-id="b85e2-169">BizTalk MMC 设计时</span><span class="sxs-lookup"><span data-stu-id="b85e2-169">BizTalk MMC design time</span></span>|<span data-ttu-id="b85e2-170">BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="b85e2-170">BizTalk run time</span></span>|<span data-ttu-id="b85e2-171">Visual Studio 设计时和/或 BizTalk MMC 设计时 + BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="b85e2-171">Visual Studio design time and/or  BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="b85e2-172">-安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-172">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-173">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-173">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-174">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="b85e2-174">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="b85e2-175">-安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-175">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-176">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-176">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-177">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="b85e2-177">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="b85e2-178">-安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-178">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-179">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-179">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-180">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="b85e2-180">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="b85e2-181">-安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-181">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-182">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-182">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-183">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="b85e2-183">- Install 32-bit client and other required DLLs.</span></span>|  
  
#### <a name="64-bit-install-scenarios"></a><span data-ttu-id="b85e2-184">64 位安装方案</span><span class="sxs-lookup"><span data-stu-id="b85e2-184">64-bit install scenarios</span></span>  
 <span data-ttu-id="b85e2-185">在安装时支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 64 位平台上。</span><span class="sxs-lookup"><span data-stu-id="b85e2-185">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 64-bit platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b85e2-186">你想要使用的设计时任务执行的任何计算机上[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或者 BizTalk MMC 中，则必须安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-186">On any computer where you want to perform design-time tasks using either [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
|<span data-ttu-id="b85e2-187">Visual Studio 设计时</span><span class="sxs-lookup"><span data-stu-id="b85e2-187">Visual Studio design time</span></span>|<span data-ttu-id="b85e2-188">BizTalk MMC 设计时</span><span class="sxs-lookup"><span data-stu-id="b85e2-188">BizTalk MMC design time</span></span>|<span data-ttu-id="b85e2-189">BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="b85e2-189">BizTalk run time</span></span>|<span data-ttu-id="b85e2-190">Visual Studio 设计时和/或 BizTalk MMC 设计时 + BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="b85e2-190">Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="b85e2-191">-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-191">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-192">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-192">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-193">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="b85e2-193">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="b85e2-194">-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-194">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-195">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-195">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-196">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="b85e2-196">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="b85e2-197">**对于 32 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="b85e2-197">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="b85e2-198">-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-198">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-199">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-199">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-200">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="b85e2-200">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="b85e2-201">**对于 64 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="b85e2-201">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="b85e2-202">-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-202">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-203">-安装 64 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-203">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-204">-安装 64 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="b85e2-204">- Install 64-bit client and other required DLLs.</span></span>|<span data-ttu-id="b85e2-205">**对于 32 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="b85e2-205">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="b85e2-206">-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-206">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-207">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-207">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-208">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="b85e2-208">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="b85e2-209">**对于 64 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="b85e2-209">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="b85e2-210">-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-210">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-211">-安装 64 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-211">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-212">-安装 64 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="b85e2-212">- Install 64-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="b85e2-213">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-213">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="b85e2-214">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="b85e2-214">- Install 32-bit client and other required DLLs.</span></span>|  
  
<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-adapter-in-interactive-mode"></a><span data-ttu-id="b85e2-215">在交互模式中安装适配器</span><span class="sxs-lookup"><span data-stu-id="b85e2-215">Install the adapter in interactive mode</span></span>  
<span data-ttu-id="b85e2-216">完成以下步骤以安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用安装向导。</span><span class="sxs-lookup"><span data-stu-id="b85e2-216">Complete the following steps to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the setup wizard.</span></span>  
  
1.  <span data-ttu-id="b85e2-217">运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="b85e2-217">Run the installer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b85e2-218">如果你正在安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]上虚拟机，安装向导可能不会继续超出了通知，安装程序正在检查可用磁盘空间的对话框。</span><span class="sxs-lookup"><span data-stu-id="b85e2-218">If you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a virtual machine, the setup wizard might not proceed beyond a dialog box informing that the setup is checking for available disk space.</span></span> <span data-ttu-id="b85e2-219">在这种情况下，我们建议你使用的无提示安装选项。</span><span class="sxs-lookup"><span data-stu-id="b85e2-219">In such cases, we recommend that you use the silent installation option.</span></span> <span data-ttu-id="b85e2-220">有关详细信息，请参阅[在静默模式下安装 SQL 适配器](#BKMK_SilentInst)（本主题中）。</span><span class="sxs-lookup"><span data-stu-id="b85e2-220">For more information, see [Install the SQL adapter in silent mode](#BKMK_SilentInst) (in this topic).</span></span>
  
2.  <span data-ttu-id="b85e2-221">阅读欢迎屏幕上的信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-221">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="b85e2-222">阅读并接受最终用户许可协议 (EULA)，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-222">Read and accept the end-user license agreement (EULA), and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="b85e2-223">在**目标文件夹**对话框框中，指定你想要安装的位置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，单击**下一步**，然后单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-223">In the **Destination Folder** dialog box, specify the location where you want to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], click **Next**, and then click **Install**.</span></span>  
  
5.  <span data-ttu-id="b85e2-224">在**客户体验改善计划**对话框框中，指定是否想要注册的客户体验改善计划 (CEIP)。</span><span class="sxs-lookup"><span data-stu-id="b85e2-224">In the **Customer Experience Improvement Program** dialog box, specify whether you would like to enroll for the Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="b85e2-225">有关 CEIP 的一部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，您将与 Microsoft 共享的下列数据：</span><span class="sxs-lookup"><span data-stu-id="b85e2-225">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="b85e2-226">与你正在其安装的计算机硬件相关的数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-226">Data related to the computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    -   <span data-ttu-id="b85e2-227">与你用来连接使用的 SQL Server 版本相关的数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-227">Data related to the SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
     <span data-ttu-id="b85e2-228">指定你选择和单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-228">Specify your choice and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b85e2-229">你始终可以更改您的首选项有关在修复模式下运行安装程序，从控制面板注册 CEIP。</span><span class="sxs-lookup"><span data-stu-id="b85e2-229">You can always change your preference regarding enrolling for CEIP by running the Setup in Repair mode from the Control Panel.</span></span>  
  
6.  <span data-ttu-id="b85e2-230">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-230">Click **Finish**.</span></span>  
  
<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="b85e2-231">在无提示模式下安装 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="b85e2-231">Install the SQL adapter in silent mode</span></span> 
<span data-ttu-id="b85e2-232">完成以下步骤来执行的无提示安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用`msiexec`命令。</span><span class="sxs-lookup"><span data-stu-id="b85e2-232">Complete the following steps to do a silent installation of [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the `msiexec` command.</span></span>  
  
1.  <span data-ttu-id="b85e2-233">打开命令提示符，并导航到你有安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="b85e2-233">Open a command prompt, and navigate to the folder where you have the installer.</span></span>  
  
2.  <span data-ttu-id="b85e2-234">运行以下命令以安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b85e2-234">Run the following command to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b85e2-235">若要执行无提示安装在基于 x64 的平台上，在以下命令，将替换为 SqlAdapterSetup64.msi SqlAdapterSetup.msi。</span><span class="sxs-lookup"><span data-stu-id="b85e2-235">To perform silent installation on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn  
    ```  
  
     <span data-ttu-id="b85e2-236">你还可以选择注册 CEIP 的无提示安装的一部分。</span><span class="sxs-lookup"><span data-stu-id="b85e2-236">You can also choose to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="b85e2-237">有关 CEIP 的一部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，您将与 Microsoft 共享的下列数据：</span><span class="sxs-lookup"><span data-stu-id="b85e2-237">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="b85e2-238">你正在其安装的计算机硬件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-238">The computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    -   <span data-ttu-id="b85e2-239">你要用于连接使用的 SQL Server 版本[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-239">The SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
     <span data-ttu-id="b85e2-240">若要注册 CEIP，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b85e2-240">To enroll for CEIP, run the following command:</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
    ```  
  
     <span data-ttu-id="b85e2-241">默认情况下，选项为 false。</span><span class="sxs-lookup"><span data-stu-id="b85e2-241">By default, the option is false.</span></span>  
  
     <span data-ttu-id="b85e2-242">有关详细信息`msiexec`命令中，键入`msiexec`上的命令行和按`ENTER`，或请参阅[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)。</span><span class="sxs-lookup"><span data-stu-id="b85e2-242">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a><span data-ttu-id="b85e2-243">安装后任务</span><span class="sxs-lookup"><span data-stu-id="b85e2-243">Post-installation tasks</span></span>  
  
<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a><span data-ttu-id="b85e2-244">注册绑定</span><span class="sxs-lookup"><span data-stu-id="b85e2-244">Register the bindings</span></span>  
<span data-ttu-id="b85e2-245">完成这些步骤*仅*如果安装向导无法在 machine.config 文件中注册的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="b85e2-245">Complete these steps *only* if the setup wizard fails to register the adapter bindings in the machine.config file.</span></span>  
  
1.  <span data-ttu-id="b85e2-246">导航到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b85e2-246">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="b85e2-247">例如，在 32 位平台上，machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="b85e2-247">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
2.  <span data-ttu-id="b85e2-248">打开使用文本编辑器的文件。</span><span class="sxs-lookup"><span data-stu-id="b85e2-248">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="b85e2-249">若要注册的适配器绑定：</span><span class="sxs-lookup"><span data-stu-id="b85e2-249">To register the adapter bindings:</span></span>  
  
    1.  <span data-ttu-id="b85e2-250">搜索的元素"的 system.serviceModel"和其下添加以下：</span><span class="sxs-lookup"><span data-stu-id="b85e2-250">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="b85e2-251">搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="b85e2-251">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="b85e2-252">添加以下节"bindingElementExtensions"节点下。</span><span class="sxs-lookup"><span data-stu-id="b85e2-252">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="b85e2-253">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="b85e2-253">For the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="b85e2-254">搜索"bindingExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="b85e2-254">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="b85e2-255">添加以下节"bindingExtensions"节点下。</span><span class="sxs-lookup"><span data-stu-id="b85e2-255">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="b85e2-256">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="b85e2-256">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b85e2-257">有关如何确定的公钥的信息，请参阅[确定的公钥和版本](#BKMK_PubKey)。</span><span class="sxs-lookup"><span data-stu-id="b85e2-257">For information about how to determine the public key, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="b85e2-258">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b85e2-258">Save and close the machine.config file.</span></span>  
  
<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a><span data-ttu-id="b85e2-259">确定的公钥和版本</span><span class="sxs-lookup"><span data-stu-id="b85e2-259">Determining the Public Key and Version</span></span>  
<span data-ttu-id="b85e2-260">完成以下步骤来确定的公钥和版本[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-260">Complete the following steps to determine the public key and version for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
1.  <span data-ttu-id="b85e2-261">导航到 Windows 目录中，通常 C:\WINDOWS\assembly。</span><span class="sxs-lookup"><span data-stu-id="b85e2-261">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="b85e2-262">右键单击该 DLL 为其您希望将公钥，，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-262">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="b85e2-263">下表列出的 Dll 的名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-263">The following table lists the name of the DLLs for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    |<span data-ttu-id="b85e2-264">适配器</span><span class="sxs-lookup"><span data-stu-id="b85e2-264">Adapter</span></span>|<span data-ttu-id="b85e2-265">DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="b85e2-265">Name of the DLL</span></span>|  
    |---|---|  
    |[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]|<span data-ttu-id="b85e2-266">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="b85e2-266">Microsoft.Adapters.Sql.dll</span></span>|  
  
3.  <span data-ttu-id="b85e2-267">上**常规**选项卡上，针对值**Public Key Token**标签指定 DLL 的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="b85e2-267">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="b85e2-268">同样，针对值**版本**标签指定的 dll 的版本号。</span><span class="sxs-lookup"><span data-stu-id="b85e2-268">Similarly, the value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="b85e2-269">复制公钥，，然后单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-269">Copy the public key, and then click **Cancel**.</span></span>  
  
<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a><span data-ttu-id="b85e2-270">更新或更改 SQL 适配器安装</span><span class="sxs-lookup"><span data-stu-id="b85e2-270">Update or change the SQL adapter installation</span></span>  
 <span data-ttu-id="b85e2-271">执行以下步骤以修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="b85e2-271">Perform the following steps to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span> <span data-ttu-id="b85e2-272">请确保你具有[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装之前您运行安装向导以修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="b85e2-272">Make sure you have the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installed before you run the setup wizard to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span>  
  
 <span data-ttu-id="b85e2-273">你可以修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="b85e2-273">You can modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the following two ways:</span></span>  
  
-   <span data-ttu-id="b85e2-274">**在交互模式中**通过运行安装向导。</span><span class="sxs-lookup"><span data-stu-id="b85e2-274">**In interactive mode** by running the setup wizard.</span></span>  
  
-   <span data-ttu-id="b85e2-275">**在静默模式下**通过使用命令行。</span><span class="sxs-lookup"><span data-stu-id="b85e2-275">**In silent mode** by using the command line.</span></span>  
  
#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a><span data-ttu-id="b85e2-276">更新 SQL 适配器安装在交互模式中</span><span class="sxs-lookup"><span data-stu-id="b85e2-276">Update the SQL Adapter installation in interactive mode</span></span>  
  
1.  <span data-ttu-id="b85e2-277">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-277">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="b85e2-278">在 Control Panel 中，双击**程序和功能**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-278">In Control Panel, double-click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="b85e2-279">在**程序和功能**窗口中，选择**用于 SQL Server 的 Microsoft BizTalk Adapter**，然后单击**更改**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-279">In the **Programs and Features** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Change**.</span></span>  
  
4.  <span data-ttu-id="b85e2-280">阅读欢迎屏幕上的信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-280">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="b85e2-281">在**更改、 修复或删除安装**对话框中，单击**修复**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-281">In the **Change, repair, or remove installation** dialog box, click **Repair**.</span></span>  
  
6.  <span data-ttu-id="b85e2-282">在**准备好修复 Microsoft BizTalk Adapter for SQL Server**对话框中，单击**修复**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-282">In the **Ready to repair Microsoft BizTalk Adapter for SQL Server** dialog box, click **Repair**.</span></span>  
  
7.  <span data-ttu-id="b85e2-283">如果需要，更改你的首选项有关选择加入的 CEIP，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-283">If required, change your preferences regarding opting for CEIP, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="b85e2-284">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-284">Click **Finish**.</span></span>  
  
#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a><span data-ttu-id="b85e2-285">更新 SQL 适配器安装在静默模式下</span><span class="sxs-lookup"><span data-stu-id="b85e2-285">Update the SQL Adapter installation in silent mode</span></span>  
  
1.  <span data-ttu-id="b85e2-286">打开命令提示符，并导航到的根目录下[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="b85e2-286">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="b85e2-287">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b85e2-287">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b85e2-288">若要修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装在静默模式下，在基于 x64 的平台上，在以下命令，将替换为 SqlAdapterSetup64.msi SqlAdapterSetup.msi。</span><span class="sxs-lookup"><span data-stu-id="b85e2-288">To modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn /f  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b85e2-289">修改时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在静默模式下的安装，不能更改用于选择加入或退出 CEIP 首选项。</span><span class="sxs-lookup"><span data-stu-id="b85e2-289">While modifying the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="b85e2-290">首选项将保持不变按照您指定在安装期间，即使您显式将 CEIP_OPTIN 设置为 true 或 false。</span><span class="sxs-lookup"><span data-stu-id="b85e2-290">The preferences will remain the same as you specified during the installation, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  
  
     <span data-ttu-id="b85e2-291">有关详细信息`msiexec`命令类型`msiexec`上的命令行和按`ENTER`，或请参阅[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)。</span><span class="sxs-lookup"><span data-stu-id="b85e2-291">For more information about the `msiexec` command type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a><span data-ttu-id="b85e2-292">卸载或删除 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="b85e2-292">Uninstall or remove the SQL Adapter</span></span>  
 <span data-ttu-id="b85e2-293">执行以下步骤以删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从您的计算机。</span><span class="sxs-lookup"><span data-stu-id="b85e2-293">Perform the following steps to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from your computer.</span></span> <span data-ttu-id="b85e2-294">请确保你具有[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装在运行安装向导以删除之前[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-294">Make sure you have the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installed before you run the setup wizard to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="b85e2-295">你可以删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="b85e2-295">You can remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="b85e2-296">**在交互模式中**通过运行安装向导。</span><span class="sxs-lookup"><span data-stu-id="b85e2-296">**In interactive mode** by running the setup wizard.</span></span>  
  
-   <span data-ttu-id="b85e2-297">**在静默模式下**通过使用命令行。</span><span class="sxs-lookup"><span data-stu-id="b85e2-297">**In silent mode** by using the command line.</span></span>  
  
#### <a name="uninstall-the-sql-adapter-in-interactive-mode"></a><span data-ttu-id="b85e2-298">卸载 SQL 适配器在交互模式中</span><span class="sxs-lookup"><span data-stu-id="b85e2-298">Uninstall the SQL Adapter in interactive mode</span></span>  
  
1.  <span data-ttu-id="b85e2-299">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-299">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="b85e2-300">在 Control Panel 中，双击**程序和功能**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-300">In Control Panel, double-click  **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="b85e2-301">在**添加或删除程序**窗口中，选择**用于 SQL Server 的 Microsoft BizTalk Adapter**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-301">In the **Add or Remove Programs** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Remove**.</span></span>  
  
4.  <span data-ttu-id="b85e2-302">在对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="b85e2-302">In the dialog box, click **Yes**.</span></span>  
  
#### <a name="uninstall-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="b85e2-303">卸载 SQL 适配器在静默模式下</span><span class="sxs-lookup"><span data-stu-id="b85e2-303">Uninstall the SQL Adapter in silent mode</span></span>  
  
1.  <span data-ttu-id="b85e2-304">打开命令提示符，并导航到的根目录下[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="b85e2-304">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="b85e2-305">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b85e2-305">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b85e2-306">若要删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在静默模式下，在基于 x64 的平台上，在以下命令，将替换为 SqlAdapterSetup64.msi SqlAdapterSetup.msi。</span><span class="sxs-lookup"><span data-stu-id="b85e2-306">To remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /x SqlAdapterSetup.msi /qn  
    ```  
  
     <span data-ttu-id="b85e2-307">此命令删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从计算机。</span><span class="sxs-lookup"><span data-stu-id="b85e2-307">This command removes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from the computer.</span></span>  
  
     <span data-ttu-id="b85e2-308">有关详细信息`msiexec`命令中，键入`msiexec`上的命令行和按`ENTER`，或请参阅[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)。</span><span class="sxs-lookup"><span data-stu-id="b85e2-308">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a><span data-ttu-id="b85e2-309">卸载后任务</span><span class="sxs-lookup"><span data-stu-id="b85e2-309">Post-uninstall task</span></span>  
 <span data-ttu-id="b85e2-310">如果[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序无法删除适配器绑定，同时删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，则必须手动删除它们。</span><span class="sxs-lookup"><span data-stu-id="b85e2-310">If the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] setup fails to remove the adapter bindings while removing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must remove them manually.</span></span> <span data-ttu-id="b85e2-311">以下部分介绍如何手动删除的绑定[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b85e2-311">The following section describes how to manually remove the bindings for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
<span data-ttu-id="b85e2-312">完成这些步骤*仅*如果安装向导无法从 machine.config 文件中删除适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="b85e2-312">Complete these steps *only* if the setup wizard fails to remove the adapter bindings from the machine.config file.</span></span>  
  
1.  <span data-ttu-id="b85e2-313">导航到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b85e2-313">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="b85e2-314">例如，在 32 位平台上，machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="b85e2-314">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
    -   <span data-ttu-id="b85e2-315">对 Microsoft.NET Framework 3.5 SP1， \<*版本*\>是.NET Framework 版本 v2.0.50727。</span><span class="sxs-lookup"><span data-stu-id="b85e2-315">For Microsoft .NET Framework 3.5 SP1, \<*version*\> is the version v2.0.50727 of the .NET Framework.</span></span>  
  
    -   <span data-ttu-id="b85e2-316">Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]， \<*版本*\>是.NET Framework 版本 v4.0.30319。</span><span class="sxs-lookup"><span data-stu-id="b85e2-316">For Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \<*version*\> is the version v4.0.30319 of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="b85e2-317">打开使用文本编辑器的文件。</span><span class="sxs-lookup"><span data-stu-id="b85e2-317">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="b85e2-318">删除适配器绑定注册：</span><span class="sxs-lookup"><span data-stu-id="b85e2-318">To remove the adapter binding registration:</span></span>  
  
    1.  <span data-ttu-id="b85e2-319">搜索的元素"的 system.serviceModel"，然后删除该元素从以下：</span><span class="sxs-lookup"><span data-stu-id="b85e2-319">Search for the element "system.serviceModel" and remove the following from under the element:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  <span data-ttu-id="b85e2-320">搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="b85e2-320">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="b85e2-321">删除"bindingElementExtensions"节点下的以下部分。</span><span class="sxs-lookup"><span data-stu-id="b85e2-321">Remove the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="b85e2-322">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="b85e2-322">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="b85e2-323">搜索"bindingExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="b85e2-323">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="b85e2-324">删除"bindingExtensions"节点下的以下部分。</span><span class="sxs-lookup"><span data-stu-id="b85e2-324">Remove the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="b85e2-325">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="b85e2-325">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  <span data-ttu-id="b85e2-326">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="b85e2-326">Save and close the machine.config file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b85e2-327">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b85e2-327">See also</span></span>
[<span data-ttu-id="b85e2-328">安装 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="b85e2-328">Install the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[<span data-ttu-id="b85e2-329">了解用于 SQL Server 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="b85e2-329">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)
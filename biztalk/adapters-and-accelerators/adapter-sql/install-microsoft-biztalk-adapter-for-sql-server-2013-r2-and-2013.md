---
title: 安装 Microsoft BizTalk Adapter for SQL Server-2013 R2 和 2013年 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56c31d0d-783b-41ee-8265-56c9547e9dca
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af91ae787d5800738865980609bb86f96a73bfb8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967859"
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2013-r2-and-2013"></a><span data-ttu-id="51fa5-102">安装 Microsoft BizTalk Adapter for SQL Server-2013 R2 和 2013</span><span class="sxs-lookup"><span data-stu-id="51fa5-102">Install Microsoft BizTalk Adapter for SQL Server - 2013 R2 and 2013</span></span>
<span data-ttu-id="51fa5-103">安装[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]附带[!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)]，或包含[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]2013年。</span><span class="sxs-lookup"><span data-stu-id="51fa5-103">Install the [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] included with [!INCLUDE[bts2013r2_md](../../includes/bts2013r2-md.md)], or included with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 2013.</span></span>

 <span data-ttu-id="51fa5-104">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可以与使用：</span><span class="sxs-lookup"><span data-stu-id="51fa5-104">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used with:</span></span>  
  
-   <span data-ttu-id="51fa5-105">.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="51fa5-105">A .NET application</span></span>  
  
-   <span data-ttu-id="51fa5-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51fa5-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
 <span data-ttu-id="51fa5-107">所需的软件基于如何使用适配器，而异。</span><span class="sxs-lookup"><span data-stu-id="51fa5-107">Based on how you use the adapters, the required software varies.</span></span>  
 
<a name="BKMK_Prereqs_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a><span data-ttu-id="51fa5-108">.NET 应用程序中使用该适配器时的先决条件</span><span class="sxs-lookup"><span data-stu-id="51fa5-108">Prerequisites when using the adapter with a .NET Application</span></span>  
<span data-ttu-id="51fa5-109">要在其中编写.NET 应用程序使用的计算机上安装以下软件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-109">Install the following software on the computer where you are writing .NET applications that consume the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="51fa5-110">列出的顺序安装软件。</span><span class="sxs-lookup"><span data-stu-id="51fa5-110">Install the software in the order as listed.</span></span>  

|<span data-ttu-id="51fa5-111">2013 R2</span><span class="sxs-lookup"><span data-stu-id="51fa5-111">2013 R2</span></span>|<span data-ttu-id="51fa5-112">2013</span><span class="sxs-lookup"><span data-stu-id="51fa5-112">2013</span></span>|  
|---|---|  
|[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]|<span data-ttu-id="51fa5-113">Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51fa5-113">Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]</span></span>|  
|<span data-ttu-id="51fa5-114">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="51fa5-114">Visual Studio 2013</span></span>|<span data-ttu-id="51fa5-115">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="51fa5-115">Visual Studio 2012</span></span>|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|  
|<span data-ttu-id="51fa5-116">SQL Server 客户端库。</span><span class="sxs-lookup"><span data-stu-id="51fa5-116">The SQL Server client libraries.</span></span> <span data-ttu-id="51fa5-117">实例时都提供 SQL Server 登录名。</span><span class="sxs-lookup"><span data-stu-id="51fa5-117">.</span></span>|<span data-ttu-id="51fa5-118">SQL Server 客户端库...</span><span class="sxs-lookup"><span data-stu-id="51fa5-118">The SQL Server client libraries..</span></span>|  

<a name="BKMK_Prereqs_BTS"></a>    
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a><span data-ttu-id="51fa5-119">与 BizTalk Server 使用适配器时的先决条件</span><span class="sxs-lookup"><span data-stu-id="51fa5-119">Prerequisites when using the adapter with BizTalk Server</span></span>  
<span data-ttu-id="51fa5-120">将使用你在计算机上安装以下软件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-120">Install the following software on the computer where you will be using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="51fa5-121">我们建议以下列出的相同顺序安装软件。</span><span class="sxs-lookup"><span data-stu-id="51fa5-121">We recommend installing the software in the same order as listed here.</span></span>  
 
 |<span data-ttu-id="51fa5-122">2013 R2</span><span class="sxs-lookup"><span data-stu-id="51fa5-122">2013 R2</span></span>|<span data-ttu-id="51fa5-123">2013</span><span class="sxs-lookup"><span data-stu-id="51fa5-123">2013</span></span>|  
|---|---|  
|[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]|<span data-ttu-id="51fa5-124">Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51fa5-124">Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]</span></span>|  
|<span data-ttu-id="51fa5-125">Visual Studio 2013</span><span class="sxs-lookup"><span data-stu-id="51fa5-125">Visual Studio 2013</span></span>|<span data-ttu-id="51fa5-126">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="51fa5-126">Visual Studio 2012</span></span>|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="51fa5-127">安装[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]为[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-127">Install the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="51fa5-128">若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-128">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="51fa5-129">安装[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]为[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-129">Install the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="51fa5-130">若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-130">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>|  
|<span data-ttu-id="51fa5-131">BizTalk Server 2013 R2</span><span class="sxs-lookup"><span data-stu-id="51fa5-131">BizTalk Server 2013 R2</span></span>|<span data-ttu-id="51fa5-132">BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="51fa5-132">BizTalk Server 2013</span></span>|  
|<span data-ttu-id="51fa5-133">SQL Server 客户端库。</span><span class="sxs-lookup"><span data-stu-id="51fa5-133">The SQL Server client libraries.</span></span> |<span data-ttu-id="51fa5-134">SQL Server 客户端库。</span><span class="sxs-lookup"><span data-stu-id="51fa5-134">The SQL Server client libraries.</span></span> |  

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a><span data-ttu-id="51fa5-135">支持的 SQL Server 版本和客户端库</span><span class="sxs-lookup"><span data-stu-id="51fa5-135">Supported SQL Server versions and client libraries</span></span>  
 <span data-ttu-id="51fa5-136">下面的部分介绍支持的 SQL Server 版本和客户端所需的库[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-136">The following section presents the supported SQL Server versions and the client libraries required by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
-   <span data-ttu-id="51fa5-137">**支持的服务器版本**: SQL Server 2005、 SQL Server 2008 SP1、 SQL Server 2008 R2、 SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="51fa5-137">**Supported server versions**: SQL Server 2005, SQL Server 2008 SP1, SQL Server 2008 R2, SQL Server 2012</span></span>  
  
-   <span data-ttu-id="51fa5-138">**支持的客户端版本**: Microsoft[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]捆绑包连接到 SQL Server 所需的客户端 Dll。</span><span class="sxs-lookup"><span data-stu-id="51fa5-138">**Supported client versions**: Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] bundles the client DLLs required to connect to SQL Server.</span></span> <span data-ttu-id="51fa5-139">不需要显式安装在计算机上的任何客户端 Dll。</span><span class="sxs-lookup"><span data-stu-id="51fa5-139">You do not need to explicitly install any client DLLs on your computer.</span></span>  
  
-   <span data-ttu-id="51fa5-140">**所需驱动程序**:</span><span class="sxs-lookup"><span data-stu-id="51fa5-140">**Required drivers**:</span></span>  
  
    -   <span data-ttu-id="51fa5-141">如果你使用随 SQL Server 版本，例如，Geography，Udt 请确保以下 Dll 计算机上存在其中你使用该适配器在 SQL Server 上执行操作。</span><span class="sxs-lookup"><span data-stu-id="51fa5-141">If you use the UDTs shipped with the SQL Server versions, for example, Geography, make sure the following DLLs are present on the computer where you use the adapter to perform operations on SQL Server.</span></span> <span data-ttu-id="51fa5-142">例如，如果你创建 BizTalk 项目，在 SQL Server 上执行操作，这些 Dll 必须存在于运行 BizTalk Server 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="51fa5-142">For example, if you create BizTalk projects to perform operations on SQL Server, these DLLs must be present on the computer where BizTalk Server is running.</span></span>  
  
        -   <span data-ttu-id="51fa5-143">请确保 Microsoft.SqlServer.Types.dll 已添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="51fa5-143">Make sure Microsoft.SqlServer.Types.dll is added to the GAC.</span></span>  
  
        -   <span data-ttu-id="51fa5-144">确保 SqlServerSpatial.dll System32 文件夹中可用。</span><span class="sxs-lookup"><span data-stu-id="51fa5-144">Make sure SqlServerSpatial.dll is available in the System32 folder.</span></span>  
  
         <span data-ttu-id="51fa5-145">可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-基本**和**管理工具 – 完整**中**功能选择**向导页。</span><span class="sxs-lookup"><span data-stu-id="51fa5-145">You can install these DLLs on the computer by running the SQL Server setup and selecting **Management Tools – Basic** and **Management Tools – Complete** in the **Feature Selection** page of the wizard.</span></span>  
  
    -   <span data-ttu-id="51fa5-146">如果你使用该适配器上的 FILESTREAM 数据类型的列执行操作，请确保已安装的 SQL 客户端连接 SDK。</span><span class="sxs-lookup"><span data-stu-id="51fa5-146">If you use the adapter to perform operations on columns of FILESTREAM data types, make sure you have SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="51fa5-147">你可以通过运行 SQL Server 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。</span><span class="sxs-lookup"><span data-stu-id="51fa5-147">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="51fa5-148">适配器使用 sqlncli10.dll，安装 SQL 客户端连接 SDK，与执行 FILESTREAM 操作。</span><span class="sxs-lookup"><span data-stu-id="51fa5-148">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  
  
    -   <span data-ttu-id="51fa5-149">如果在 SQL Server 中创建你自己的 Udt，请确保 Udt 的相应程序集添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="51fa5-149">If you create your own UDTs in SQL Server, make sure the respective assemblies for the UDTs are added to the GAC.</span></span>  
  
<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a><span data-ttu-id="51fa5-150">64 位支持</span><span class="sxs-lookup"><span data-stu-id="51fa5-150">64-bit support</span></span> 

<span data-ttu-id="51fa5-151">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可以在一个 32 位或 64 位主机实例中运行。</span><span class="sxs-lookup"><span data-stu-id="51fa5-151">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can run in a 32-bit or 64-bit host instance.</span></span>

 <span data-ttu-id="51fa5-152">有关的 32 位和 64 位的受支持的安装方案的详细信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-152">For more information about the supported installation scenarios for the 32-bit and 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)],.</span></span> 
  
<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a><span data-ttu-id="51fa5-153">安装 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="51fa5-153">Install the SQL Adapter</span></span>  
 <span data-ttu-id="51fa5-154">请确保已在安装之前安装的先决条件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-154">Make sure you have the prerequisites installed before installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="51fa5-155">你可以安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="51fa5-155">You can install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="51fa5-156">**在交互模式中**使用安装向导</span><span class="sxs-lookup"><span data-stu-id="51fa5-156">**In interactive mode** using the setup wizard</span></span>  
  
-   <span data-ttu-id="51fa5-157">**在静默模式下**命令中使用 msiexec 链接</span><span class="sxs-lookup"><span data-stu-id="51fa5-157">**In silent mode** using msiexec in the command lin</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="51fa5-158">必须将在其中安装的计算机上具有管理特权[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，不管是否使用向导或命令行安装。</span><span class="sxs-lookup"><span data-stu-id="51fa5-158">You must have administrative privileges on the computer where you will install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], irrespective of whether you are installing by using the wizard or the command line.</span></span>  
  
<a name="BKMK_Install_Scenarios"></a>   
### <a name="32-bit-and-64-bit-install-scenarios"></a><span data-ttu-id="51fa5-159">32 位和 64 位安装方案</span><span class="sxs-lookup"><span data-stu-id="51fa5-159">32-bit and 64-bit install scenarios</span></span>
 <span data-ttu-id="51fa5-160">与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可用于：</span><span class="sxs-lookup"><span data-stu-id="51fa5-160">With [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used for:</span></span>  
  
-   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="51fa5-161">设计时 （在生成操作的元数据）。</span><span class="sxs-lookup"><span data-stu-id="51fa5-161"> design time (when generating metadata for operations).</span></span>  
  
-   <span data-ttu-id="51fa5-162">BizTalk Server 管理控制台 （用于创建的物理端口） 的设计时。</span><span class="sxs-lookup"><span data-stu-id="51fa5-162">BizTalk Server Administration console design time (for creating physical ports).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51fa5-163">BizTalk Server 管理控制台将作为 32 位 Microsoft 管理控制台 (MMC) 应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="51fa5-163">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  
  
-   <span data-ttu-id="51fa5-164">BizTalk 运行时 （发送和接收消息时从 LOB 应用程序）。</span><span class="sxs-lookup"><span data-stu-id="51fa5-164">BizTalk run time (when sending and receiving messages from LOB applications).</span></span>  
  
 <span data-ttu-id="51fa5-165">你可以安装在同一台计算机或不同计算机上执行所有这些任务的位置。</span><span class="sxs-lookup"><span data-stu-id="51fa5-165">You can have an installation where you perform all these tasks on the same computer or different computers.</span></span> <span data-ttu-id="51fa5-166">因为同时[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和 BizTalk MMC 是 32 位进程，则必须安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]你想要执行的设计时任务的计算机上。</span><span class="sxs-lookup"><span data-stu-id="51fa5-166">Because both [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on the computer where you want to perform the design-time tasks.</span></span> <span data-ttu-id="51fa5-167">安装支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 32 位和 64 位平台上。</span><span class="sxs-lookup"><span data-stu-id="51fa5-167">The following scenarios are supported for installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on 32-bit and 64-bit platforms.</span></span>  
  
#### <a name="install-scenarios-on-a-32-bit-platform"></a><span data-ttu-id="51fa5-168">在 32 位平台上安装方案</span><span class="sxs-lookup"><span data-stu-id="51fa5-168">Install scenarios on a 32-bit platform</span></span>  
 <span data-ttu-id="51fa5-169">在安装时支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 32 位平台上。</span><span class="sxs-lookup"><span data-stu-id="51fa5-169">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 32-bit platform.</span></span>  
  
|<span data-ttu-id="51fa5-170">Visual Studio 设计时</span><span class="sxs-lookup"><span data-stu-id="51fa5-170">Visual Studio design time</span></span>|<span data-ttu-id="51fa5-171">BizTalk MMC 设计时</span><span class="sxs-lookup"><span data-stu-id="51fa5-171">BizTalk MMC design time</span></span>|<span data-ttu-id="51fa5-172">BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="51fa5-172">BizTalk run time</span></span>|<span data-ttu-id="51fa5-173">Visual Studio 设计时和/或 BizTalk MMC 设计时 + BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="51fa5-173">Visual Studio design time and/or  BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="51fa5-174">-安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-174">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-175">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-175">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-176">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="51fa5-176">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="51fa5-177">-安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-177">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-178">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-178">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-179">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="51fa5-179">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="51fa5-180">-安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-180">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-181">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-181">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-182">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="51fa5-182">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="51fa5-183">-安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-183">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-184">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-184">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-185">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="51fa5-185">- Install 32-bit client and other required DLLs.</span></span>|  
  
#### <a name="install-scenarios-on-a-64-bit-platform"></a><span data-ttu-id="51fa5-186">在 64 位平台上安装方案</span><span class="sxs-lookup"><span data-stu-id="51fa5-186">Install scenarios on a 64-bit platform</span></span>  
 <span data-ttu-id="51fa5-187">在安装时支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 64 位平台上。</span><span class="sxs-lookup"><span data-stu-id="51fa5-187">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 64-bit platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51fa5-188">你想要使用的设计时任务执行的任何计算机上[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或者 BizTalk MMC 中，则必须安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-188">On any computer where you want to perform design-time tasks using either [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
|<span data-ttu-id="51fa5-189">Visual Studio 设计时</span><span class="sxs-lookup"><span data-stu-id="51fa5-189">Visual Studio design time</span></span>|<span data-ttu-id="51fa5-190">BizTalk MMC 设计时</span><span class="sxs-lookup"><span data-stu-id="51fa5-190">BizTalk MMC design time</span></span>|<span data-ttu-id="51fa5-191">BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="51fa5-191">BizTalk run time</span></span>|<span data-ttu-id="51fa5-192">Visual Studio 设计时和/或 BizTalk MMC 设计时 + BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="51fa5-192">Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="51fa5-193">-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-193">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-194">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-194">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-195">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="51fa5-195">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="51fa5-196">-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-196">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-197">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-197">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-198">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="51fa5-198">- Install 32-bit client and other required DLLs.</span></span>|<span data-ttu-id="51fa5-199">**对于 32 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="51fa5-199">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="51fa5-200">-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-200">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-201">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-201">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-202">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="51fa5-202">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="51fa5-203">**对于 64 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="51fa5-203">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="51fa5-204">-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-204">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-205">-安装 64 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-205">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-206">-安装 64 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="51fa5-206">- Install 64-bit client and other required DLLs.</span></span>|<span data-ttu-id="51fa5-207">**对于 32 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="51fa5-207">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="51fa5-208">-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-208">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-209">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-209">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-210">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="51fa5-210">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="51fa5-211">**对于 64 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="51fa5-211">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="51fa5-212">-安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-212">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-213">-安装 64 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-213">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-214">-安装 64 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="51fa5-214">- Install 64-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="51fa5-215">-安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-215">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="51fa5-216">-安装 32 位客户端和其他必要的 Dll。</span><span class="sxs-lookup"><span data-stu-id="51fa5-216">- Install 32-bit client and other required DLLs.</span></span>|  
  
<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-sql-adapter-in-interactive-mode"></a><span data-ttu-id="51fa5-217">在交互模式中安装 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="51fa5-217">Install the SQL Adapter in interactive mode</span></span>  
 
1.  <span data-ttu-id="51fa5-218">运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="51fa5-218">Run the installer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51fa5-219">如果你正在安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]上虚拟机，安装向导可能不会继续超出了通知，安装程序正在检查可用磁盘空间的对话框。</span><span class="sxs-lookup"><span data-stu-id="51fa5-219">If you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a virtual machine, the setup wizard might not proceed beyond a dialog box informing that the setup is checking for available disk space.</span></span> <span data-ttu-id="51fa5-220">在这种情况下，我们建议你使用的无提示安装选项。</span><span class="sxs-lookup"><span data-stu-id="51fa5-220">In such cases, we recommend that you use the silent installation option.</span></span>   
  
2.  <span data-ttu-id="51fa5-221">阅读欢迎屏幕上的信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-221">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="51fa5-222">阅读并接受最终用户许可协议 (EULA)，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-222">Read and accept the end-user license agreement (EULA), and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="51fa5-223">在**目标文件夹**对话框框中，指定你想要安装的位置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，单击**下一步**，然后单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-223">In the **Destination Folder** dialog box, specify the location where you want to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], click **Next**, and then click **Install**.</span></span>  
  
5.  <span data-ttu-id="51fa5-224">在**客户体验改善计划**对话框框中，指定是否想要注册的客户体验改善计划 (CEIP)。</span><span class="sxs-lookup"><span data-stu-id="51fa5-224">In the **Customer Experience Improvement Program** dialog box, specify whether you would like to enroll for the Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="51fa5-225">有关 CEIP 的一部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，您将与 Microsoft 共享的下列数据：</span><span class="sxs-lookup"><span data-stu-id="51fa5-225">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="51fa5-226">与你正在其安装的计算机硬件相关的数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-226">Data related to the computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    -   <span data-ttu-id="51fa5-227">与你用来连接使用的 SQL Server 版本相关的数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-227">Data related to the SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
     <span data-ttu-id="51fa5-228">指定你选择和单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-228">Specify your choice and click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51fa5-229">你始终可以更改您的首选项有关在修复模式下运行安装程序，从控制面板注册 CEIP。</span><span class="sxs-lookup"><span data-stu-id="51fa5-229">You can always change your preference regarding enrolling for CEIP by running the Setup in Repair mode from the Control Panel.</span></span>  
  
6.  <span data-ttu-id="51fa5-230">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-230">Click **Finish**.</span></span>  
  
<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="51fa5-231">在无提示模式下安装 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="51fa5-231">Install the SQL adapter in Silent mode</span></span>  
 <span data-ttu-id="51fa5-232">下面的过程演示如何执行无提示安装的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用`msiexec`命令。</span><span class="sxs-lookup"><span data-stu-id="51fa5-232">The following procedure demonstrates how to perform a silent installation of [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the `msiexec` command.</span></span>  
  
1.  <span data-ttu-id="51fa5-233">打开命令提示符，并导航到你有安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="51fa5-233">Open a command prompt, and navigate to the folder where you have the installer.</span></span>  
  
2.  <span data-ttu-id="51fa5-234">运行以下命令以安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="51fa5-234">Run the following command to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51fa5-235">若要执行无提示安装在基于 x64 的平台上，在以下命令，将替换为 SqlAdapterSetup64.msi SqlAdapterSetup.msi。</span><span class="sxs-lookup"><span data-stu-id="51fa5-235">To perform silent installation on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn  
    ```  
  
     <span data-ttu-id="51fa5-236">你还可以选择注册 CEIP 的无提示安装的一部分。</span><span class="sxs-lookup"><span data-stu-id="51fa5-236">You can also choose to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="51fa5-237">有关 CEIP 的一部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，您将与 Microsoft 共享的下列数据：</span><span class="sxs-lookup"><span data-stu-id="51fa5-237">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  
  
    -   <span data-ttu-id="51fa5-238">你正在其安装的计算机硬件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-238">The computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    -   <span data-ttu-id="51fa5-239">你要用于连接使用的 SQL Server 版本[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-239">The SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
     <span data-ttu-id="51fa5-240">若要注册 CEIP，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="51fa5-240">To enroll for CEIP, run the following command:</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
    ```  
  
     <span data-ttu-id="51fa5-241">默认情况下，选项为 false。</span><span class="sxs-lookup"><span data-stu-id="51fa5-241">By default, the option is false.</span></span>  
  
     <span data-ttu-id="51fa5-242">有关详细信息`msiexec`命令中，键入`msiexec`上的命令行和按`ENTER`，或请参阅[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)。</span><span class="sxs-lookup"><span data-stu-id="51fa5-242">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a><span data-ttu-id="51fa5-243">安装后任务</span><span class="sxs-lookup"><span data-stu-id="51fa5-243">Post-installation tasks</span></span>  
  
<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a><span data-ttu-id="51fa5-244">注册绑定</span><span class="sxs-lookup"><span data-stu-id="51fa5-244">Register the Bindings</span></span>  
<span data-ttu-id="51fa5-245">完成这些步骤*仅*如果安装向导无法在 machine.config 文件中注册的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="51fa5-245">Complete these steps *only* if the setup wizard fails to register the adapter bindings in the machine.config file.</span></span>  
  
1.  <span data-ttu-id="51fa5-246">导航到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="51fa5-246">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="51fa5-247">例如，在 32 位平台上，machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="51fa5-247">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
    -   <span data-ttu-id="51fa5-248">对 Microsoft.NET Framework 3.5 SP1， \<*版本*\>是.NET Framework 版本 v2.0.50727。</span><span class="sxs-lookup"><span data-stu-id="51fa5-248">For Microsoft .NET Framework 3.5 SP1, \<*version*\> is the version v2.0.50727 of the .NET Framework.</span></span>  
  
    -   <span data-ttu-id="51fa5-249">Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]， \<*版本*\>是.NET Framework 版本 v4.0.30319。</span><span class="sxs-lookup"><span data-stu-id="51fa5-249">For Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \<*version*\> is the version v4.0.30319 of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="51fa5-250">打开使用文本编辑器的文件。</span><span class="sxs-lookup"><span data-stu-id="51fa5-250">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="51fa5-251">若要注册的适配器绑定：</span><span class="sxs-lookup"><span data-stu-id="51fa5-251">To register the adapter bindings:</span></span>  
  
    1.  <span data-ttu-id="51fa5-252">搜索的元素"的 system.serviceModel"和其下添加以下：</span><span class="sxs-lookup"><span data-stu-id="51fa5-252">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="51fa5-253">搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="51fa5-253">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="51fa5-254">添加以下节"bindingElementExtensions"节点下。</span><span class="sxs-lookup"><span data-stu-id="51fa5-254">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="51fa5-255">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="51fa5-255">For the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="51fa5-256">搜索"bindingExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="51fa5-256">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="51fa5-257">添加以下节"bindingExtensions"节点下。</span><span class="sxs-lookup"><span data-stu-id="51fa5-257">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="51fa5-258">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="51fa5-258">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
      
  
4.  <span data-ttu-id="51fa5-259">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="51fa5-259">Save and close the machine.config file.</span></span>  
  
<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a><span data-ttu-id="51fa5-260">确定的公钥和版本</span><span class="sxs-lookup"><span data-stu-id="51fa5-260">Determining the Public Key and Version</span></span>  
<span data-ttu-id="51fa5-261">完成以下步骤来确定的公钥和版本[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-261">Complete the following steps to determine the public key and version for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
1.  <span data-ttu-id="51fa5-262">导航到 Windows 目录中，通常 C:\WINDOWS\assembly。</span><span class="sxs-lookup"><span data-stu-id="51fa5-262">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="51fa5-263">右键单击该 DLL 为其您希望将公钥，，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-263">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="51fa5-264">下表列出的 Dll 的名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-264">The following table lists the name of the DLLs for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    |<span data-ttu-id="51fa5-265">适配器</span><span class="sxs-lookup"><span data-stu-id="51fa5-265">Adapter</span></span>|<span data-ttu-id="51fa5-266">DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="51fa5-266">Name of the DLL</span></span>|  
    |---|---|  
    |[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]|<span data-ttu-id="51fa5-267">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="51fa5-267">Microsoft.Adapters.Sql.dll</span></span>|  
  
3.  <span data-ttu-id="51fa5-268">上**常规**选项卡上，针对值**Public Key Token**标签指定 DLL 的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="51fa5-268">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="51fa5-269">同样，针对值**版本**标签指定的 dll 的版本号。</span><span class="sxs-lookup"><span data-stu-id="51fa5-269">Similarly, the value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="51fa5-270">复制公钥，，然后单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-270">Copy the public key, and then click **Cancel**.</span></span>  
  
<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a><span data-ttu-id="51fa5-271">更新或更改 SQL 适配器安装</span><span class="sxs-lookup"><span data-stu-id="51fa5-271">Update or change the SQL adapter installation</span></span>  
 <span data-ttu-id="51fa5-272">执行以下步骤以修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="51fa5-272">Perform the following steps to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span> <span data-ttu-id="51fa5-273">请确保你具有[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装之前您运行安装向导以修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="51fa5-273">Make sure you have the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installed before you run the setup wizard to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span>  
  
 <span data-ttu-id="51fa5-274">你可以修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="51fa5-274">You can modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the following two ways:</span></span>  
  
-   <span data-ttu-id="51fa5-275">**在交互模式中**通过运行安装向导。</span><span class="sxs-lookup"><span data-stu-id="51fa5-275">**In interactive mode** by running the setup wizard.</span></span>  
  
-   <span data-ttu-id="51fa5-276">**在静默模式下**通过使用命令行。</span><span class="sxs-lookup"><span data-stu-id="51fa5-276">**In silent mode** by using the command line.</span></span>  
  
#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a><span data-ttu-id="51fa5-277">更新 SQL 适配器安装在交互模式中</span><span class="sxs-lookup"><span data-stu-id="51fa5-277">Update the SQL Adapter installation in interactive mode</span></span>  
  
1.  <span data-ttu-id="51fa5-278">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-278">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="51fa5-279">在 Control Panel 中，双击**程序和功能**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-279">In Control Panel, double-click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="51fa5-280">在**程序和功能**窗口中，选择**用于 SQL Server 的 Microsoft BizTalk Adapter**，然后单击**更改**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-280">In the **Programs and Features** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Change**.</span></span>  
  
4.  <span data-ttu-id="51fa5-281">阅读欢迎屏幕上的信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-281">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="51fa5-282">在**更改、 修复或删除安装**对话框中，单击**修复**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-282">In the **Change, repair, or remove installation** dialog box, click **Repair**.</span></span>  
  
6.  <span data-ttu-id="51fa5-283">在**准备好修复 Microsoft BizTalk Adapter for SQL Server**对话框中，单击**修复**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-283">In the **Ready to repair Microsoft BizTalk Adapter for SQL Server** dialog box, click **Repair**.</span></span>  
  
7.  <span data-ttu-id="51fa5-284">如果需要，更改你的首选项有关选择加入的 CEIP，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-284">If required, change your preferences regarding opting for CEIP, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="51fa5-285">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-285">Click **Finish**.</span></span>  
  
#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a><span data-ttu-id="51fa5-286">更新 SQL 适配器安装在静默模式下</span><span class="sxs-lookup"><span data-stu-id="51fa5-286">Update the SQL Adapter installation in silent mode</span></span>  
  
1.  <span data-ttu-id="51fa5-287">打开命令提示符，并导航到的根目录下[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="51fa5-287">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="51fa5-288">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="51fa5-288">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51fa5-289">若要修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装在静默模式下，在基于 x64 的平台上，在以下命令，将替换为 SqlAdapterSetup64.msi SqlAdapterSetup.msi。</span><span class="sxs-lookup"><span data-stu-id="51fa5-289">To modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /i SqlAdapterSetup.msi /qn /f  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="51fa5-290">修改时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在静默模式下的安装，不能更改用于选择加入或退出 CEIP 首选项。</span><span class="sxs-lookup"><span data-stu-id="51fa5-290">While modifying the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="51fa5-291">首选项将保持不变按照您指定在安装期间，即使您显式将 CEIP_OPTIN 设置为 true 或 false。</span><span class="sxs-lookup"><span data-stu-id="51fa5-291">The preferences will remain the same as you specified during the installation, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  
  
     <span data-ttu-id="51fa5-292">有关详细信息`msiexec`命令中，键入`msiexec`上的命令行和按`ENTER`，或请参阅[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)。</span><span class="sxs-lookup"><span data-stu-id="51fa5-292">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>   
  
<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a><span data-ttu-id="51fa5-293">卸载或删除 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="51fa5-293">Uninstall or remove the SQL Adapter</span></span>  
 <span data-ttu-id="51fa5-294">执行以下步骤以删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从您的计算机。</span><span class="sxs-lookup"><span data-stu-id="51fa5-294">Perform the following steps to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from your computer.</span></span> <span data-ttu-id="51fa5-295">请确保你具有[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装在运行安装向导以删除之前[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-295">Make sure you have the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installed before you run the setup wizard to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="51fa5-296">你可以删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="51fa5-296">You can remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  
  
-   <span data-ttu-id="51fa5-297">**在交互模式中**通过运行安装向导。</span><span class="sxs-lookup"><span data-stu-id="51fa5-297">**In interactive mode** by running the setup wizard.</span></span>  
  
-   <span data-ttu-id="51fa5-298">**在静默模式下**通过使用命令行。</span><span class="sxs-lookup"><span data-stu-id="51fa5-298">**In silent mode** by using the command line.</span></span>  
  
#### <a name="uninstall-in-interactive-mode"></a><span data-ttu-id="51fa5-299">在交互模式中卸载</span><span class="sxs-lookup"><span data-stu-id="51fa5-299">Uninstall in interactive mode</span></span>  
  
1.  <span data-ttu-id="51fa5-300">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-300">Click **Start**, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="51fa5-301">在 Control Panel 中，双击**程序和功能**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-301">In Control Panel, double-click  **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="51fa5-302">在**添加或删除程序**窗口中，选择**用于 SQL Server 的 Microsoft BizTalk Adapter**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-302">In the **Add or Remove Programs** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Remove**.</span></span>  
  
4.  <span data-ttu-id="51fa5-303">在对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="51fa5-303">In the dialog box, click **Yes**.</span></span>  
  
#### <a name="uninstall-in-silent-mode"></a><span data-ttu-id="51fa5-304">在静默模式下卸载</span><span class="sxs-lookup"><span data-stu-id="51fa5-304">Uninstall in silent mode</span></span>  
  
1.  <span data-ttu-id="51fa5-305">打开命令提示符，并导航到的根目录下[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="51fa5-305">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  
  
2.  <span data-ttu-id="51fa5-306">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="51fa5-306">Run the following command:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="51fa5-307">若要删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在静默模式下，在基于 x64 的平台上，在以下命令，将替换为 SqlAdapterSetup64.msi SqlAdapterSetup.msi。</span><span class="sxs-lookup"><span data-stu-id="51fa5-307">To remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  
  
    ```  
    msiexec /x SqlAdapterSetup.msi /qn  
    ```  
  
     <span data-ttu-id="51fa5-308">此命令删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从计算机。</span><span class="sxs-lookup"><span data-stu-id="51fa5-308">This command removes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from the computer.</span></span>  
  
     <span data-ttu-id="51fa5-309">有关详细信息`msiexec`命令中，键入`msiexec`上的命令行和按`ENTER`，或请参阅[https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781)。</span><span class="sxs-lookup"><span data-stu-id="51fa5-309">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  
  
<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a><span data-ttu-id="51fa5-310">卸载后任务</span><span class="sxs-lookup"><span data-stu-id="51fa5-310">Post-uninstall task</span></span>  
 <span data-ttu-id="51fa5-311">如果[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序无法删除适配器绑定，同时删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，则必须手动删除它们。</span><span class="sxs-lookup"><span data-stu-id="51fa5-311">If the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] setup fails to remove the adapter bindings while removing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must remove them manually.</span></span> <span data-ttu-id="51fa5-312">以下部分介绍如何手动删除的绑定[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="51fa5-312">The following section describes how to manually remove the bindings for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
<a name="BKMK_Remove_Binding"></a>   
#### <a name="manually-remove-the-bindings"></a><span data-ttu-id="51fa5-313">手动删除绑定</span><span class="sxs-lookup"><span data-stu-id="51fa5-313">Manually remove the bindings</span></span>  
 <span data-ttu-id="51fa5-314">执行这些步骤*仅*如果安装向导无法从 machine.config 文件中删除适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="51fa5-314">Perform these steps *only* if the setup wizard fails to remove the adapter bindings from the machine.config file.</span></span>  
  
1.  <span data-ttu-id="51fa5-315">导航到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="51fa5-315">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="51fa5-316">例如，在 32 位平台上，machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="51fa5-316">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
    -   <span data-ttu-id="51fa5-317">对 Microsoft.NET Framework 3.5 SP1， \<*版本*\>是.NET Framework 版本 v2.0.50727。</span><span class="sxs-lookup"><span data-stu-id="51fa5-317">For Microsoft .NET Framework 3.5 SP1, \<*version*\> is the version v2.0.50727 of the .NET Framework.</span></span>  
  
    -   <span data-ttu-id="51fa5-318">Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]， \<*版本*\>是.NET Framework 版本 v4.0.30319。</span><span class="sxs-lookup"><span data-stu-id="51fa5-318">For Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \<*version*\> is the version v4.0.30319 of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="51fa5-319">打开使用文本编辑器的文件。</span><span class="sxs-lookup"><span data-stu-id="51fa5-319">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="51fa5-320">删除适配器绑定注册：</span><span class="sxs-lookup"><span data-stu-id="51fa5-320">To remove the adapter binding registration:</span></span>  
  
    1.  <span data-ttu-id="51fa5-321">搜索的元素"的 system.serviceModel"，然后删除该元素从以下：</span><span class="sxs-lookup"><span data-stu-id="51fa5-321">Search for the element "system.serviceModel" and remove the following from under the element:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
  
        ```  
  
    2.  <span data-ttu-id="51fa5-322">搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="51fa5-322">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="51fa5-323">删除"bindingElementExtensions"节点下的以下部分。</span><span class="sxs-lookup"><span data-stu-id="51fa5-323">Remove the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="51fa5-324">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="51fa5-324">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="51fa5-325">搜索"bindingExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="51fa5-325">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="51fa5-326">删除"bindingExtensions"节点下的以下部分。</span><span class="sxs-lookup"><span data-stu-id="51fa5-326">Remove the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="51fa5-327">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="51fa5-327">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
4.  <span data-ttu-id="51fa5-328">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="51fa5-328">Save and close the machine.config file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51fa5-329">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51fa5-329">See also</span></span>
[<span data-ttu-id="51fa5-330">安装 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="51fa5-330">Install the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[<span data-ttu-id="51fa5-331">了解用于 SQL Server 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="51fa5-331">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)
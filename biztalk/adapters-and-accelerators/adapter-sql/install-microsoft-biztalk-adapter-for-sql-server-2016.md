---
title: 安装 Microsoft BizTalk Adapter for SQL Server-2016年 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bcc6b94e-1cac-4b90-8567-05b33caa9bf3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65205828e4ab178a0fec29c37cc1854f6a570242
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966974"
---
# <a name="install-microsoft-biztalk-adapter-for-sql-server---2016"></a><span data-ttu-id="ca2bf-102">安装 Microsoft BizTalk Adapter for SQL Server-2016</span><span class="sxs-lookup"><span data-stu-id="ca2bf-102">Install Microsoft BizTalk Adapter for SQL Server - 2016</span></span>
<span data-ttu-id="ca2bf-103">安装[!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)]附带[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-103">Install the [!INCLUDE[adaptersql_md](../../includes/adaptersql-md.md)] included with [!INCLUDE[bts2016_md](../../includes/bts2016-md.md)].</span></span>

 <span data-ttu-id="ca2bf-104">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可用于：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-104">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used with:</span></span>  

- <span data-ttu-id="ca2bf-105">.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="ca2bf-105">A .NET application</span></span>  

- <span data-ttu-id="ca2bf-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca2bf-106">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span></span>  

  <span data-ttu-id="ca2bf-107">根据如何使用适配器，所需的软件各不相同。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-107">Based on how you use the adapters, the required software varies.</span></span>  


<a name="BKMK_prereq_NET"></a>   
## <a name="prerequisites-when-using-the-adapter-with-a-net-application"></a><span data-ttu-id="ca2bf-108">使用.NET 应用程序中使用适配器时的先决条件</span><span class="sxs-lookup"><span data-stu-id="ca2bf-108">Prerequisites when using the adapter with a .NET Application</span></span>  
<span data-ttu-id="ca2bf-109">要在其中编写的.NET 应用程序使用的计算机上安装以下软件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-109">Install the following software on the computer where you are writing .NET applications that consume the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="ca2bf-110">列出的顺序安装软件。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-110">Install the software in the order as listed.</span></span>  

||
|---|
|<span data-ttu-id="ca2bf-111">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ca2bf-111">- Windows Server 2016</span></span> <br /><span data-ttu-id="ca2bf-112">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ca2bf-112">- Windows Server 2012 R2</span></span> <br /><span data-ttu-id="ca2bf-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ca2bf-113">- Windows 10</span></span> <br /><span data-ttu-id="ca2bf-114">-Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ca2bf-114">- Windows 8.1</span></span>    |
|<span data-ttu-id="ca2bf-115">.NET Framework 4.6.*x*</span><span class="sxs-lookup"><span data-stu-id="ca2bf-115">.NET Framework 4.6.*x*</span></span>|
|<span data-ttu-id="ca2bf-116">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="ca2bf-116">Visual Studio 2015</span></span>|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]|
|<span data-ttu-id="ca2bf-117">SQL Server 客户端库。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-117">SQL Server client libraries.</span></span> <span data-ttu-id="ca2bf-118">请参阅[受支持的版本](#BKMK_SuppLOB)（在本主题中）。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-118">See the [supported versions](#BKMK_SuppLOB) (in this topic).</span></span>|

<a name="BKMK_prereq_BTS"></a>     
## <a name="prerequisites-when-using-the-adapter-with-biztalk-server"></a><span data-ttu-id="ca2bf-119">使用适配器与 BizTalk Server 时的先决条件</span><span class="sxs-lookup"><span data-stu-id="ca2bf-119">Prerequisites when using the adapter with BizTalk Server</span></span>  
<span data-ttu-id="ca2bf-120">： 您正在使用的计算机上安装以下软件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-120">Install the following software on the computer where you are using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="ca2bf-121">按所列顺序安装软件。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-121">Install the software in the order listed.</span></span>  

||
|---|
|<span data-ttu-id="ca2bf-122">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ca2bf-122">- Windows Server 2016</span></span> <br /><span data-ttu-id="ca2bf-123">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ca2bf-123">- Windows Server 2012 R2</span></span> <br /><span data-ttu-id="ca2bf-124">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ca2bf-124">- Windows 10</span></span> <br /><span data-ttu-id="ca2bf-125">-Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ca2bf-125">- Windows 8.1</span></span>    |
|<span data-ttu-id="ca2bf-126">.NET Framework 4.6.*x*</span><span class="sxs-lookup"><span data-stu-id="ca2bf-126">.NET Framework 4.6.*x*</span></span>|
|<span data-ttu-id="ca2bf-127">Visual Studio 2015</span><span class="sxs-lookup"><span data-stu-id="ca2bf-127">Visual Studio 2015</span></span>|
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<br /><br /> <span data-ttu-id="ca2bf-128">安装[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]有关[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]附带[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-128">Install the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] for [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] included with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="ca2bf-129">若要安装，请执行**自定义**(选择**BizTalk Server 外接程序**) 或**完成**安装[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-129">To install, do a **Custom** (select **BizTalk Server Addin**) or **Complete** installation of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span>|
|[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]|
|<span data-ttu-id="ca2bf-130">SQL Server 客户端库。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-130">SQL Server client libraries.</span></span> <span data-ttu-id="ca2bf-131">请参阅[受支持的版本](#BKMK_SuppLOB)（在本主题中）。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-131">See the [supported versions](#BKMK_SuppLOB) (in this topic).</span></span>|

<a name="BKMK_SuppLOB"></a>   
## <a name="supported-sql-server-versions-and-client-libraries"></a><span data-ttu-id="ca2bf-132">支持的 SQL Server 版本和客户端库</span><span class="sxs-lookup"><span data-stu-id="ca2bf-132">Supported SQL Server versions and client libraries</span></span>  
 <span data-ttu-id="ca2bf-133">以下部分提供支持的 SQL Server 版本和客户端所需的库[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-133">The following section presents the supported SQL Server versions and the client libraries required by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

- <span data-ttu-id="ca2bf-134">**支持的服务器版本**: SQL Server 2016、 SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="ca2bf-134">**Supported server versions**: SQL Server 2016, SQL Server 2014</span></span>

- <span data-ttu-id="ca2bf-135">**支持的客户端版本**: Microsoft[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]捆绑包连接到 SQL Server 所需的客户端 Dll。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-135">**Supported client versions**: Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] bundles the client DLLs required to connect to SQL Server.</span></span> <span data-ttu-id="ca2bf-136">不需要在您的计算机上显式安装任何客户端 Dll。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-136">You do not need to explicitly install any client DLLs on your computer.</span></span>  

- <span data-ttu-id="ca2bf-137">**所需的驱动程序**:</span><span class="sxs-lookup"><span data-stu-id="ca2bf-137">**Required drivers**:</span></span>  

  - <span data-ttu-id="ca2bf-138">如果使用 Udt 附带的 SQL Server 版本，例如，地理位置，请确保以下 Dll 计算机上存在其中使用该适配器在 SQL Server 上执行操作。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-138">If you use the UDTs shipped with the SQL Server versions, for example, Geography, make sure the following DLLs are present on the computer where you use the adapter to perform operations on SQL Server.</span></span> <span data-ttu-id="ca2bf-139">例如，如果在 BizTalk 项目，在 SQL Server 上执行操作，这些 Dll 必须在运行 BizTalk Server 的计算机上存在。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-139">For example, if you create BizTalk projects to perform operations on SQL Server, these DLLs must be present on the computer where BizTalk Server is running.</span></span>  

    - <span data-ttu-id="ca2bf-140">请确保 Microsoft.SqlServer.Types.dll 添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-140">Make sure Microsoft.SqlServer.Types.dll is added to the GAC.</span></span>  

    - <span data-ttu-id="ca2bf-141">确保 SqlServerSpatial.dll System32 文件夹中可用。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-141">Make sure SqlServerSpatial.dll is available in the System32 folder.</span></span>  

      <span data-ttu-id="ca2bf-142">可以通过运行 SQL Server 安装程序并选择在计算机上安装这些 Dll**管理工具-Basic**并**管理工具-完整**中**功能选择**向导页。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-142">You can install these DLLs on the computer by running the SQL Server setup and selecting **Management Tools – Basic** and **Management Tools – Complete** in the **Feature Selection** page of the wizard.</span></span>  

  - <span data-ttu-id="ca2bf-143">如果使用适配器来执行对 FILESTREAM 数据类型的列的操作，请确保已安装的 SQL 客户端连接 SDK。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-143">If you use the adapter to perform operations on columns of FILESTREAM data types, make sure you have SQL Client Connectivity SDK installed.</span></span> <span data-ttu-id="ca2bf-144">可以通过运行 SQL Server 安装程序并选择安装 SQL 客户端连接 SDK **SQL 客户端连接 SDK**中**功能选择**向导页。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-144">You can install the SQL Client Connectivity SDK by running the SQL Server setup and selecting **SQL Client Connectivity SDK** in the **Feature Selection** page of the wizard.</span></span> <span data-ttu-id="ca2bf-145">适配器使用 sqlncli10.dll，随 SQL 客户端连接 SDK，用于执行 FILESTREAM 操作。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-145">The adapter uses the sqlncli10.dll, installed with the SQL Client Connectivity SDK, to perform FILESTREAM operations.</span></span>  

  - <span data-ttu-id="ca2bf-146">如果在 SQL Server 中创建你自己的 Udt，请确保对 Udt 的相应程序集添加到 GAC。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-146">If you create your own UDTs in SQL Server, make sure the respective assemblies for the UDTs are added to the GAC.</span></span>  

<a name="BKMK_Compat"></a>   
## <a name="64-bit-support"></a><span data-ttu-id="ca2bf-147">64 位支持</span><span class="sxs-lookup"><span data-stu-id="ca2bf-147">64-bit support</span></span> 

<span data-ttu-id="ca2bf-148">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可以运行的 32 位或 64 位主机实例中。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-148">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can run in a 32-bit or 64-bit host instance.</span></span>

 <span data-ttu-id="ca2bf-149">有关为 32 位和 64 位支持的安装方案的信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[32 位和 64 位安装方案](#BKMK_Install_Scenarios)（在本主题中）。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-149">For information about the supported installation scenarios for the 32-bit and 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see  [32-bit and 64-bit install scenarios](#BKMK_Install_Scenarios) (in this topic).</span></span>

<a name="BKMK_Install_Adap"></a>   
## <a name="install-the-sql-adapter"></a><span data-ttu-id="ca2bf-150">安装 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="ca2bf-150">Install the SQL adapter</span></span>  
 <span data-ttu-id="ca2bf-151">请确保已安装之前安装必备组件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-151">Make sure you have the prerequisites installed before installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="ca2bf-152">请参阅[.NET 系统必备组件](#BKMK_prereq_NET)（在本主题中），或[BizTalk Server 必备组件](#BKMK_prereq_BTS)（在本主题中）。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-152">See [.NET prerequisites](#BKMK_prereq_NET) (in this topic), or [BizTalk Server prerequisites](#BKMK_prereq_BTS) (in this topic).</span></span>

 <span data-ttu-id="ca2bf-153">你可以安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-153">You can install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  

- <span data-ttu-id="ca2bf-154">**在交互模式下**使用安装向导</span><span class="sxs-lookup"><span data-stu-id="ca2bf-154">**In interactive mode** using the setup wizard</span></span>

- <span data-ttu-id="ca2bf-155">**在静默模式下**使用 msiexec 命令行中</span><span class="sxs-lookup"><span data-stu-id="ca2bf-155">**In silent mode** using msiexec in the command line</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="ca2bf-156">必须在其中安装的计算机上具有管理特权[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，不考虑要使用向导或命令行安装。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-156">You must have administrative privileges on the computer where you install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], irrespective of whether you are installing by using the wizard or the command line.</span></span>    

### <a name="BKMK_Install_Scenarios"></a> <span data-ttu-id="ca2bf-157">32 位和 64 位安装方案</span><span class="sxs-lookup"><span data-stu-id="ca2bf-157">32-bit and 64-bit install scenarios</span></span>
 <span data-ttu-id="ca2bf-158">与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，则[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可用于：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-158">With [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used for:</span></span>  

- [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="ca2bf-159"> 设计时 （时生成的操作的元数据）。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-159"> design time (when generating metadata for operations).</span></span>  

- <span data-ttu-id="ca2bf-160">BizTalk Server 管理控制台 （用于创建物理端口） 的设计时。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-160">BizTalk Server Administration console design time (for creating physical ports).</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="ca2bf-161">BizTalk Server 管理控制台作为 32 位 Microsoft 管理控制台 (MMC) 应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-161">BizTalk Server Administration console runs as a 32-bit Microsoft Management Console (MMC) application.</span></span>  

- <span data-ttu-id="ca2bf-162">BizTalk 运行时 （发送和接收消息时的 LOB 应用程序）。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-162">BizTalk run time (when sending and receiving messages from LOB applications).</span></span>  

  <span data-ttu-id="ca2bf-163">您可以安装在同一台计算机或不同的计算机上执行所有这些任务的位置。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-163">You can have an installation where you perform all these tasks on the same computer or different computers.</span></span> <span data-ttu-id="ca2bf-164">因为这两[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]以及 BizTalk MMC 是 32 位进程，你必须安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]你想要执行的设计时任务的计算机上。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-164">Because both [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and BizTalk MMC are 32-bit processes, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on the computer where you want to perform the design-time tasks.</span></span> <span data-ttu-id="ca2bf-165">安装支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在 32 位和 64 位平台上。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-165">The following scenarios are supported for installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on 32-bit and 64-bit platforms.</span></span>  

#### <a name="32-bit-install-scenarios"></a><span data-ttu-id="ca2bf-166">32 位安装方案</span><span class="sxs-lookup"><span data-stu-id="ca2bf-166">32-bit install scenarios</span></span>  
 <span data-ttu-id="ca2bf-167">安装时，支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]32 位平台上。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-167">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 32-bit platform.</span></span>  


|                                                                                                               <span data-ttu-id="ca2bf-168">Visual Studio 设计时</span><span class="sxs-lookup"><span data-stu-id="ca2bf-168">Visual Studio design time</span></span>                                                                                                                |                                                                                                                <span data-ttu-id="ca2bf-169">BizTalk MMC 设计时</span><span class="sxs-lookup"><span data-stu-id="ca2bf-169">BizTalk MMC design time</span></span>                                                                                                                 |                                                                                                                    <span data-ttu-id="ca2bf-170">BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="ca2bf-170">BizTalk run time</span></span>                                                                                                                    |                                                                                      <span data-ttu-id="ca2bf-171">Visual Studio 设计时和/或 BizTalk MMC 设计时间 + BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="ca2bf-171">Visual Studio design time and/or  BizTalk MMC design time + BizTalk run time</span></span>                                                                                      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ca2bf-172">安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-172">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-173">安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-173">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-174">-安装 32 位客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-174">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="ca2bf-175">安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-175">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-176">安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-176">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-177">-安装 32 位客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-177">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="ca2bf-178">安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-178">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-179">安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-179">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-180">-安装 32 位客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-180">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="ca2bf-181">安装 32 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-181">- Install 32-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-182">安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-182">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-183">-安装 32 位客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-183">- Install 32-bit client and other required DLLs.</span></span> |

#### <a name="64-bit-install-scenarios"></a><span data-ttu-id="ca2bf-184">64 位安装方案</span><span class="sxs-lookup"><span data-stu-id="ca2bf-184">64-bit install scenarios</span></span>  
 <span data-ttu-id="ca2bf-185">安装时，支持以下方案[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]64 位平台上。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-185">The following scenarios are supported when installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a 64-bit platform.</span></span>  

> [!NOTE]
>  <span data-ttu-id="ca2bf-186">你想要执行设计时任务使用的任何计算机上[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]BizTalk MMC 中，你必须安装 32 位或[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-186">On any computer where you want to perform design-time tasks using either [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or BizTalk MMC, you must install the 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

|                                                                                                               <span data-ttu-id="ca2bf-187">Visual Studio 设计时</span><span class="sxs-lookup"><span data-stu-id="ca2bf-187">Visual Studio design time</span></span>                                                                                                                |                                                                                                                <span data-ttu-id="ca2bf-188">BizTalk MMC 设计时</span><span class="sxs-lookup"><span data-stu-id="ca2bf-188">BizTalk MMC design time</span></span>                                                                                                                 |                                                                                                                                                                                                                                                                                                   <span data-ttu-id="ca2bf-189">BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="ca2bf-189">BizTalk run time</span></span>                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                                                                    <span data-ttu-id="ca2bf-190">Visual Studio 设计时和/或 BizTalk MMC 设计时间 + BizTalk 运行时</span><span class="sxs-lookup"><span data-stu-id="ca2bf-190">Visual Studio design time and/or BizTalk MMC design time + BizTalk run time</span></span>                                                                                                                                                                                                                                                                                                                                                     |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ca2bf-191">安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-191">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-192">安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-192">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-193">-安装 32 位客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-193">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="ca2bf-194">安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-194">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-195">安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-195">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-196">-安装 32 位客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-196">- Install 32-bit client and other required DLLs.</span></span> | <span data-ttu-id="ca2bf-197">**对于 32 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="ca2bf-197">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="ca2bf-198">安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-198">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-199">安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-199">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-200">-安装 32 位客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-200">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="ca2bf-201">**对于 64 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="ca2bf-201">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="ca2bf-202">安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-202">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-203">安装 64 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-203">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-204">-安装 64 位客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-204">- Install 64-bit client and other required DLLs.</span></span> | <span data-ttu-id="ca2bf-205">**对于 32 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="ca2bf-205">**For a 32-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="ca2bf-206">安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-206">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-207">安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-207">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-208">-安装 32 位客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-208">- Install 32-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="ca2bf-209">**对于 64 位 BizTalk 进程**:</span><span class="sxs-lookup"><span data-stu-id="ca2bf-209">**For a 64-bit BizTalk process**:</span></span><br /><br /> <span data-ttu-id="ca2bf-210">安装 64 位[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-210">- Install 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-211">安装 64 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-211">- Install 64-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-212">-安装 64 位客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-212">- Install 64-bit client and other required DLLs.</span></span><br /><br /> <span data-ttu-id="ca2bf-213">安装 32 位[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-213">- Install 32-bit [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span><br /><br /> <span data-ttu-id="ca2bf-214">-安装 32 位客户端和其他所需的 Dll。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-214">- Install 32-bit client and other required DLLs.</span></span> |

<a name="BKMK_Install_wizard"></a>   
### <a name="install-the-adapter-in-interactive-mode"></a><span data-ttu-id="ca2bf-215">在交互模式下安装适配器</span><span class="sxs-lookup"><span data-stu-id="ca2bf-215">Install the adapter in interactive mode</span></span>  
<span data-ttu-id="ca2bf-216">完成以下步骤来安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用安装向导。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-216">Complete the following steps to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the setup wizard.</span></span>  

1. <span data-ttu-id="ca2bf-217">运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-217">Run the installer.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ca2bf-218">如果您正在安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]虚拟机上安装向导可能无法继续超出了对话框，通知安装程序正在检查的可用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-218">If you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] on a virtual machine, the setup wizard might not proceed beyond a dialog box informing that the setup is checking for available disk space.</span></span> <span data-ttu-id="ca2bf-219">在这种情况下，我们建议你使用的无提示安装选项。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-219">In such cases, we recommend that you use the silent installation option.</span></span> <span data-ttu-id="ca2bf-220">有关详细信息，请参阅[在无提示模式下安装 SQL 适配器](#BKMK_SilentInst)（在本主题中）。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-220">For more information, see [Install the SQL adapter in silent mode](#BKMK_SilentInst) (in this topic).</span></span>

2. <span data-ttu-id="ca2bf-221">阅读欢迎屏幕上的信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-221">Read the information on the Welcome screen, and then click **Next**.</span></span>  

3. <span data-ttu-id="ca2bf-222">阅读并接受最终用户许可协议 (EULA)，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-222">Read and accept the end-user license agreement (EULA), and then click **Next**.</span></span>  

4. <span data-ttu-id="ca2bf-223">在中**目标文件夹**对话框框中，指定你想要安装的位置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，单击**下一步**，然后单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-223">In the **Destination Folder** dialog box, specify the location where you want to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], click **Next**, and then click **Install**.</span></span>  

5. <span data-ttu-id="ca2bf-224">在中**客户体验改善计划**对话框框中，指定是否想要注册的客户体验改善计划 (CEIP)。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-224">In the **Customer Experience Improvement Program** dialog box, specify whether you would like to enroll for the Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="ca2bf-225">有关 CEIP 的一部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，您将与 Microsoft 共享的以下数据：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-225">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  

   - <span data-ttu-id="ca2bf-226">与正在其安装的计算机硬件相关的数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-226">Data related to the computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

   - <span data-ttu-id="ca2bf-227">与用来连接使用的 SQL Server 版本相关的数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-227">Data related to the SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

     <span data-ttu-id="ca2bf-228">指定所选，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-228">Specify your choice and click **OK**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ca2bf-229">你可以随时更改您的首选项有关注册 CEIP 通过从控制面板在修复模式下运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-229">You can always change your preference regarding enrolling for CEIP by running the Setup in Repair mode from the Control Panel.</span></span>  

6. <span data-ttu-id="ca2bf-230">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-230">Click **Finish**.</span></span>  

<a name="BKMK_SilentInst"></a>   
### <a name="install-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="ca2bf-231">在无提示模式下安装 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="ca2bf-231">Install the SQL adapter in silent mode</span></span> 
<span data-ttu-id="ca2bf-232">完成以下步骤，若要执行的无提示安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用`msiexec`命令。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-232">Complete the following steps to do a silent installation of [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the `msiexec` command.</span></span>  

1. <span data-ttu-id="ca2bf-233">打开命令提示符，并导航到你有安装程序文件夹。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-233">Open a command prompt, and navigate to the folder where you have the installer.</span></span>  

2. <span data-ttu-id="ca2bf-234">运行以下命令以安装[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="ca2bf-234">Run the following command to install the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ca2bf-235">若要执行无提示安装在基于 x64 的平台上，在以下命令中，替换为 SqlAdapterSetup.msi SqlAdapterSetup64.msi。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-235">To perform silent installation on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn  
   ```  

    <span data-ttu-id="ca2bf-236">您还可以选择无提示安装的一部分注册 CEIP。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-236">You can also choose to enroll for CEIP as part of the silent installation.</span></span> <span data-ttu-id="ca2bf-237">有关 CEIP 的一部分[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，您将与 Microsoft 共享的以下数据：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-237">As part of CEIP for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you will share the following data with Microsoft:</span></span>  

   - <span data-ttu-id="ca2bf-238">正在其安装的计算机硬件[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-238">The computer hardware on which you are installing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

   - <span data-ttu-id="ca2bf-239">用来连接使用的 SQL Server 版本[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-239">The SQL Server versions you are using to connect using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

     <span data-ttu-id="ca2bf-240">若要注册 CEIP，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-240">To enroll for CEIP, run the following command:</span></span>  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn CEIP_OPTIN=true  
   ```  

    <span data-ttu-id="ca2bf-241">默认情况下，选项为 false。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-241">By default, the option is false.</span></span>  

    <span data-ttu-id="ca2bf-242">有关详细信息`msiexec`命令中，键入`msiexec`上的命令行和按`ENTER`，或参阅[ https://support.microsoft.com/kb/230781 ](https://support.microsoft.com/kb/230781)。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-242">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  

<a name="BKMK_PostInst"></a>   
## <a name="post-installation-tasks"></a><span data-ttu-id="ca2bf-243">安装后任务</span><span class="sxs-lookup"><span data-stu-id="ca2bf-243">Post-installation tasks</span></span>  

<a name="BKMK_Register_Bindings"></a>   
#### <a name="register-the-bindings"></a><span data-ttu-id="ca2bf-244">注册绑定</span><span class="sxs-lookup"><span data-stu-id="ca2bf-244">Register the bindings</span></span>  
<span data-ttu-id="ca2bf-245">完成这些步骤*仅*如果安装向导无法注册适配器绑定在 machine.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-245">Complete these steps *only* if the setup wizard fails to register the adapter bindings in the machine.config file.</span></span>  

1. <span data-ttu-id="ca2bf-246">导航到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-246">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="ca2bf-247">例如，在 32 位平台上，在 machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-247">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

2. <span data-ttu-id="ca2bf-248">打开文件使用文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-248">Open the file using a text editor.</span></span>  

3. <span data-ttu-id="ca2bf-249">若要注册适配器绑定：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-249">To register the adapter bindings:</span></span>  

   1. <span data-ttu-id="ca2bf-250">搜索元素"的 system.serviceModel"并将其下的以下代码添加：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-250">Search for the element "system.serviceModel" and add the following under it:</span></span>  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. <span data-ttu-id="ca2bf-251">搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-251">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="ca2bf-252">添加"bindingElementExtensions"节点下的以下部分。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-252">Add the following section under the "bindingElementExtensions" node.</span></span>  

       <span data-ttu-id="ca2bf-253">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-253">For the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="ca2bf-254">搜索"bindingExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-254">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="ca2bf-255">添加"bindingExtensions"节点下的以下部分。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-255">Add the following section under the "bindingExtensions" node.</span></span>  

       <span data-ttu-id="ca2bf-256">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，添加：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-256">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  <span data-ttu-id="ca2bf-257">有关如何确定的公钥的信息，请参阅[确定公用密钥和版本](#BKMK_PubKey)。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-257">For information about how to determine the public key, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  

4. <span data-ttu-id="ca2bf-258">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-258">Save and close the machine.config file.</span></span>  

<a name="BKMK_PubKey"></a>   
#### <a name="determining-the-public-key-and-version"></a><span data-ttu-id="ca2bf-259">确定公用密钥和版本</span><span class="sxs-lookup"><span data-stu-id="ca2bf-259">Determining the Public Key and Version</span></span>  
<span data-ttu-id="ca2bf-260">完成以下步骤来确定公用密钥和版本[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-260">Complete the following steps to determine the public key and version for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

1. <span data-ttu-id="ca2bf-261">导航到 Windows 目录，通常 C:\WINDOWS\assembly。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-261">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  

2. <span data-ttu-id="ca2bf-262">右键单击的 DLL 为其也希望将公钥，并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-262">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="ca2bf-263">下表列出了的 Dll 名称[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-263">The following table lists the name of the DLLs for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  


   |                              <span data-ttu-id="ca2bf-264">适配器</span><span class="sxs-lookup"><span data-stu-id="ca2bf-264">Adapter</span></span>                              |      <span data-ttu-id="ca2bf-265">DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="ca2bf-265">Name of the DLL</span></span>       |
   |-------------------------------------------------------------------|----------------------------|
   | [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] | <span data-ttu-id="ca2bf-266">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="ca2bf-266">Microsoft.Adapters.Sql.dll</span></span> |


3. <span data-ttu-id="ca2bf-267">上**常规**选项卡上，针对值**公钥标记**标签指定 DLL 的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-267">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="ca2bf-268">同样，针对值**版本**标签指定 dll 的版本号。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-268">Similarly, the value against the **Version** label specifies the version number for the DLL.</span></span>  

4. <span data-ttu-id="ca2bf-269">复制公钥，，然后单击**取消**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-269">Copy the public key, and then click **Cancel**.</span></span>  

<a name="BKMK_Modify_Adap"></a>   
## <a name="update-or-change-the-sql-adapter-installation"></a><span data-ttu-id="ca2bf-270">更新或更改 SQL 适配器安装</span><span class="sxs-lookup"><span data-stu-id="ca2bf-270">Update or change the SQL adapter installation</span></span>  
 <span data-ttu-id="ca2bf-271">执行以下步骤来修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-271">Perform the following steps to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span> <span data-ttu-id="ca2bf-272">请确保你拥有[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装，然后运行安装向导以修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-272">Make sure you have the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installed before you run the setup wizard to modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation.</span></span>  

 <span data-ttu-id="ca2bf-273">您可以修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-273">You can modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the following two ways:</span></span>  

-   <span data-ttu-id="ca2bf-274">**在交互模式下**通过运行安装向导。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-274">**In interactive mode** by running the setup wizard.</span></span>  

-   <span data-ttu-id="ca2bf-275">**在静默模式下**使用命令行。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-275">**In silent mode** by using the command line.</span></span>  

#### <a name="update-the-sql-adapter-installation-in-interactive-mode"></a><span data-ttu-id="ca2bf-276">更新在交互模式下安装 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="ca2bf-276">Update the SQL Adapter installation in interactive mode</span></span>  

1.  <span data-ttu-id="ca2bf-277">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-277">Click **Start**, and then click **Control Panel**.</span></span>  

2.  <span data-ttu-id="ca2bf-278">在控制面板中，双击**程序和功能**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-278">In Control Panel, double-click **Programs and Features**.</span></span>  

3.  <span data-ttu-id="ca2bf-279">在中**程序和功能**窗口中，选择**适用于 SQL Server 的 Microsoft BizTalk 适配器**，然后单击**更改**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-279">In the **Programs and Features** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Change**.</span></span>  

4.  <span data-ttu-id="ca2bf-280">阅读欢迎屏幕上的信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-280">Read the information on the Welcome screen, and then click **Next**.</span></span>  

5.  <span data-ttu-id="ca2bf-281">在中**更改、 修复或删除安装**对话框中，单击**修复**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-281">In the **Change, repair, or remove installation** dialog box, click **Repair**.</span></span>  

6.  <span data-ttu-id="ca2bf-282">在中**准备好修复 for SQL Server 的 Microsoft BizTalk 适配器**对话框中，单击**修复**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-282">In the **Ready to repair Microsoft BizTalk Adapter for SQL Server** dialog box, click **Repair**.</span></span>  

7.  <span data-ttu-id="ca2bf-283">如果需要，更改您的首选项有关选择加入 ceip，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-283">If required, change your preferences regarding opting for CEIP, and then click **OK**.</span></span>  

8.  <span data-ttu-id="ca2bf-284">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-284">Click **Finish**.</span></span>  

#### <a name="update-the-sql-adapter-installation-in-silent-mode"></a><span data-ttu-id="ca2bf-285">更新在静默模式下安装 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="ca2bf-285">Update the SQL Adapter installation in silent mode</span></span>  

1. <span data-ttu-id="ca2bf-286">打开命令提示符，并导航到的根目录下[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-286">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  

2. <span data-ttu-id="ca2bf-287">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-287">Run the following command:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ca2bf-288">若要修改[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在基于 x64 的平台，在以下命令中上, 无提示模式下安装替换 SqlAdapterSetup64.msi SqlAdapterSetup.msi。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-288">To modify the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  

   ```  
   msiexec /i SqlAdapterSetup.msi /qn /f  
   ```  

   > [!IMPORTANT]
   >  <span data-ttu-id="ca2bf-289">修改时[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在静默模式下安装，不能更改首选项的选择加入或退出 CEIP。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-289">While modifying the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installation in the silent mode, you cannot change your preferences for opting in or out of CEIP.</span></span> <span data-ttu-id="ca2bf-290">首选项将保持不变作为安装过程中，指定即使 CEIP_OPTIN 显式设置为 true 或 false。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-290">The preferences will remain the same as you specified during the installation, even if you explicitly set the CEIP_OPTIN to true or false.</span></span>  

    <span data-ttu-id="ca2bf-291">有关详细信息`msiexec`命令类型`msiexec`上的命令行和按`ENTER`，或参阅[ https://support.microsoft.com/kb/230781 ](https://support.microsoft.com/kb/230781)。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-291">For more information about the `msiexec` command type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  

<a name="BKMK_Remove_Adap"></a>   
## <a name="uninstall-or-remove-the-sql-adapter"></a><span data-ttu-id="ca2bf-292">卸载或删除 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="ca2bf-292">Uninstall or remove the SQL Adapter</span></span>  
 <span data-ttu-id="ca2bf-293">执行以下步骤以删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从您的计算机。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-293">Perform the following steps to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from your computer.</span></span> <span data-ttu-id="ca2bf-294">请确保你拥有[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]安装，然后运行安装向导以删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-294">Make sure you have the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installed before you run the setup wizard to remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

 <span data-ttu-id="ca2bf-295">您可以删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以下两种方式：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-295">You can remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in the following two ways:</span></span>  

-   <span data-ttu-id="ca2bf-296">**在交互模式下**通过运行安装向导。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-296">**In interactive mode** by running the setup wizard.</span></span>  

-   <span data-ttu-id="ca2bf-297">**在静默模式下**使用命令行。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-297">**In silent mode** by using the command line.</span></span>  

#### <a name="uninstall-the-sql-adapter-in-interactive-mode"></a><span data-ttu-id="ca2bf-298">卸载在交互模式下的 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="ca2bf-298">Uninstall the SQL Adapter in interactive mode</span></span>  

1.  <span data-ttu-id="ca2bf-299">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-299">Click **Start**, and then click **Control Panel**.</span></span>  

2.  <span data-ttu-id="ca2bf-300">在控制面板中，双击**程序和功能**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-300">In Control Panel, double-click  **Programs and Features**.</span></span>  

3.  <span data-ttu-id="ca2bf-301">在中**添加或删除程序**窗口中，选择**适用于 SQL Server 的 Microsoft BizTalk 适配器**，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-301">In the **Add or Remove Programs** window, select **Microsoft BizTalk Adapter for SQL Server**, and then click **Remove**.</span></span>  

4.  <span data-ttu-id="ca2bf-302">在对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-302">In the dialog box, click **Yes**.</span></span>  

#### <a name="uninstall-the-sql-adapter-in-silent-mode"></a><span data-ttu-id="ca2bf-303">卸载在静默模式下的 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="ca2bf-303">Uninstall the SQL Adapter in silent mode</span></span>  

1. <span data-ttu-id="ca2bf-304">打开命令提示符，并导航到的根目录下[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-304">Open a command prompt, and navigate to the root directory of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] installer.</span></span>  

2. <span data-ttu-id="ca2bf-305">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-305">Run the following command:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="ca2bf-306">若要删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在无提示模式在基于 x64 的平台，在以下命令中，替换为 SqlAdapterSetup.msi SqlAdapterSetup64.msi。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-306">To remove the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in silent mode on an x64-based platform, in the following commands, replace SqlAdapterSetup.msi with SqlAdapterSetup64.msi.</span></span>  

   ```  
   msiexec /x SqlAdapterSetup.msi /qn  
   ```  

    <span data-ttu-id="ca2bf-307">此命令将删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]从计算机。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-307">This command removes the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] from the computer.</span></span>  

    <span data-ttu-id="ca2bf-308">有关详细信息`msiexec`命令中，键入`msiexec`上的命令行和按`ENTER`，或参阅[ https://support.microsoft.com/kb/230781 ](https://support.microsoft.com/kb/230781)。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-308">For more information about the `msiexec` command, type `msiexec` on the command line and press `ENTER`, or see [https://support.microsoft.com/kb/230781](https://support.microsoft.com/kb/230781).</span></span>  

<a name="BKMK_PostRemove"></a>   
### <a name="post-uninstall-task"></a><span data-ttu-id="ca2bf-309">卸载后任务</span><span class="sxs-lookup"><span data-stu-id="ca2bf-309">Post-uninstall task</span></span>  
 <span data-ttu-id="ca2bf-310">如果[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]安装程序无法删除适配器绑定，同时删除[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，您必须手动将其删除。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-310">If the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] setup fails to remove the adapter bindings while removing the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must remove them manually.</span></span> <span data-ttu-id="ca2bf-311">以下部分介绍如何手动删除的绑定[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-311">The following section describes how to manually remove the bindings for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  

<span data-ttu-id="ca2bf-312">完成这些步骤*仅*如果安装向导无法从 machine.config 文件中删除适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-312">Complete these steps *only* if the setup wizard fails to remove the adapter bindings from the machine.config file.</span></span>  

1. <span data-ttu-id="ca2bf-313">导航到计算机上的 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-313">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="ca2bf-314">例如，在 32 位平台上，在 machine.config 位于下\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-314">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

   - <span data-ttu-id="ca2bf-315">用于 Microsoft.NET Framework 3.5 SP1 中， \<*版本*\>是.NET Framework 版本 v2.0.50727。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-315">For Microsoft .NET Framework 3.5 SP1, \<*version*\> is the version v2.0.50727 of the .NET Framework.</span></span>  

   - <span data-ttu-id="ca2bf-316">Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)]， \<*版本*\>是.NET Framework 版本 v4.0.30319。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-316">For Microsoft [!INCLUDE[netfx40_short](../../includes/netfx40-short-md.md)], \<*version*\> is the version v4.0.30319 of the .NET Framework.</span></span>  

2. <span data-ttu-id="ca2bf-317">打开文件使用文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-317">Open the file using a text editor.</span></span>  

3. <span data-ttu-id="ca2bf-318">若要删除适配器绑定注册：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-318">To remove the adapter binding registration:</span></span>  

   1. <span data-ttu-id="ca2bf-319">搜索的元素"的 system.serviceModel"并删除以下从元素下：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-319">Search for the element "system.serviceModel" and remove the following from under the element:</span></span>  

      ```  
      <client>  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  

      ```  

   2. <span data-ttu-id="ca2bf-320">搜索"bindingElementExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-320">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="ca2bf-321">删除"bindingElementExtensions"节点下的以下部分。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-321">Remove the following section under the "bindingElementExtensions" node.</span></span>  

       <span data-ttu-id="ca2bf-322">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-322">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="ca2bf-323">搜索"bindingExtensions"system.serviceModel\extensions 下的元素。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-323">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="ca2bf-324">删除"bindingExtensions"节点下的以下部分。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-324">Remove the following section under the "bindingExtensions" node.</span></span>  

       <span data-ttu-id="ca2bf-325">有关[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，删除：</span><span class="sxs-lookup"><span data-stu-id="ca2bf-325">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], remove:</span></span>  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

4. <span data-ttu-id="ca2bf-326">保存并关闭 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="ca2bf-326">Save and close the machine.config file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ca2bf-327">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca2bf-327">See also</span></span>
[<span data-ttu-id="ca2bf-328">安装 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="ca2bf-328">Install the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/install-the-sql-adapter.md)  
[<span data-ttu-id="ca2bf-329">了解用于 SQL Server 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="ca2bf-329">Understand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)
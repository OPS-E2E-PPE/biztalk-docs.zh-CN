---
title: 配置疑难解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 902e591a-4ff4-4053-b329-0c022f44999a
caps.latest.revision: 37
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed34079f38490b2e48f367c5b73bb3ec9bea4904
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398651"
---
# <a name="troubleshooting-configuration"></a><span data-ttu-id="62060-102">排查配置问题</span><span class="sxs-lookup"><span data-stu-id="62060-102">Troubleshooting Configuration</span></span>
<span data-ttu-id="62060-103">在 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序会在运行的一个或多个计算机上创建数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，将填充带有表、 角色、 数据库和存储过程由[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并部署到运行时期间使用的.NET 程序集BizTalk 管理数据库中。</span><span class="sxs-lookup"><span data-stu-id="62060-103">The Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program creates databases on one or more computers running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], populates the databases with tables, roles, and stored procedures used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and deploys .NET assemblies used during runtime to the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="62060-104">本部分讨论用于解决配置错误的故障排除技术。</span><span class="sxs-lookup"><span data-stu-id="62060-104">This section discusses troubleshooting techniques to resolve configuration errors.</span></span> <span data-ttu-id="62060-105">它还列出了一些常见的配置问题以及如何解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="62060-105">It also lists some common configuration problems and how to resolve these problems.</span></span>  
  
## <a name="configuration-logging"></a><span data-ttu-id="62060-106">配置日志记录</span><span class="sxs-lookup"><span data-stu-id="62060-106">Configuration Logging</span></span>  
 <span data-ttu-id="62060-107">配置程序将详细的信息写入到一个配置日志文件位于运行的计算机的 temp 目录中的默认情况下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="62060-107">The configuration program writes detailed information to a configuration log file which by default is located in the temp directory of the computer running[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="62060-108">若要确定由 TEMP 环境变量打开指定的文件夹，此计算机上的命令提示符下键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="62060-108">To determine the folder that is specified by the TEMP environment variable open a command prompt on this computer, type the following command, and then press ENTER:</span></span>  
  
 <span data-ttu-id="62060-109">**echo %TEMP%**</span><span class="sxs-lookup"><span data-stu-id="62060-109">**echo %TEMP%**</span></span>  
  
 <span data-ttu-id="62060-110">配置日志文件包含执行，这些配置步骤的摘要，以及有关在配置过程中可能发生的任何故障的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="62060-110">The configuration log file contains a summary of the configuration steps performed, as well as diagnostic information about any failures that may occur during the configuration process.</span></span> <span data-ttu-id="62060-111">如果出现配置错误，在诸如记事本之类的文本编辑器中打开配置日志，并检查错误的可能原因的日志文件。</span><span class="sxs-lookup"><span data-stu-id="62060-111">If a configuration error occurs, open the configuration log in a text editor such as Notepad and check the log file for possible causes of the error.</span></span>  
  
## <a name="troubleshooting-tools"></a><span data-ttu-id="62060-112">故障排除工具</span><span class="sxs-lookup"><span data-stu-id="62060-112">Troubleshooting Tools</span></span>  
 <span data-ttu-id="62060-113">使用 SQL Server Profiler、 Filemon 或 Regmon 收集有关配置失败的其他信息。</span><span class="sxs-lookup"><span data-stu-id="62060-113">Use SQL Server Profiler, Filemon, or Regmon to gather additional information about configuration failures.</span></span> <span data-ttu-id="62060-114">有关这些工具的详细信息，请参阅[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="62060-114">For more information about these tools, see [Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="62060-115">已知问题</span><span class="sxs-lookup"><span data-stu-id="62060-115">Known Issues</span></span>  
  
#### <a name="configuration-fails-when-biztalk-server-and-sql-server-are-installed-on-separate-computers"></a><span data-ttu-id="62060-116">当单独的计算机上安装 BizTalk Server 和 SQL Server 时配置失败</span><span class="sxs-lookup"><span data-stu-id="62060-116">Configuration fails when BizTalk Server and SQL Server are installed on separate computers</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="62060-117">问题</span><span class="sxs-lookup"><span data-stu-id="62060-117">Problem</span></span>  
 <span data-ttu-id="62060-118">在尝试配置企业单一登录 (SSO) 组件时，配置将失败并出现错误如下所示：</span><span class="sxs-lookup"><span data-stu-id="62060-118">Configuration fails with errors similar to the following when attempting to configure the Enterprise Single Sign-On (SSO) component:</span></span>  
  
 <span data-ttu-id="62060-119">尝试访问 SSO 数据库时出错。</span><span class="sxs-lookup"><span data-stu-id="62060-119">An error occurred while attempting to access the SSO database.</span></span>  
  
 <span data-ttu-id="62060-120">函数：FieldInfoCreate</span><span class="sxs-lookup"><span data-stu-id="62060-120">Function: FieldInfoCreate</span></span>  
  
 <span data-ttu-id="62060-121">-或-</span><span class="sxs-lookup"><span data-stu-id="62060-121">-or-</span></span>  
  
 <span data-ttu-id="62060-122">未能启用单一登录 (SSO) 服务 （错误代码 0X800706BA）</span><span class="sxs-lookup"><span data-stu-id="62060-122">Failed to enable the Single Sign-On (SSO) Service (error code 0X800706BA)</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="62060-123">原因</span><span class="sxs-lookup"><span data-stu-id="62060-123">Cause</span></span>  
 <span data-ttu-id="62060-124">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]则分布式事务处理协调器 (MSDTC) 事务的上下文下执行配置操作，并且必须可通过 MSDTC 功能安装在不同计算机上这些计算机之间的网络。</span><span class="sxs-lookup"><span data-stu-id="62060-124">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are installed on different computers then the configuration operations are performed under the context of a Distributed Transaction Coordinator (MSDTC) transaction and MSDTC functionality must be available over the network between these computers.</span></span> <span data-ttu-id="62060-125">如果 MSDTC 功能将不可用通过网络运行的计算机之间[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]则会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="62060-125">If MSDTC functionality is not available over the network between the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] then this error can occur.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="62060-126">解决方法</span><span class="sxs-lookup"><span data-stu-id="62060-126">Resolution</span></span>  
 <span data-ttu-id="62060-127">按照中的步骤[MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)以确保通过网络运行的计算机之间的 MSDTC 功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="62060-127">Follow the steps in [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md) to ensure MSDTC functionality over the network between the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
#### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a><span data-ttu-id="62060-128">防病毒软件干扰配置并将导致配置失败</span><span class="sxs-lookup"><span data-stu-id="62060-128">Antivirus software interferes with configuration and causes configuration failures</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="62060-129">问题</span><span class="sxs-lookup"><span data-stu-id="62060-129">Problem</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="62060-130">当防病毒软件错误地确定配置程序是一种病毒时，配置失败。</span><span class="sxs-lookup"><span data-stu-id="62060-130">configuration fails when antivirus software incorrectly determines that the configuration program is a virus.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="62060-131">原因</span><span class="sxs-lookup"><span data-stu-id="62060-131">Cause</span></span>  
 <span data-ttu-id="62060-132">防病毒软件尚未更新以包括[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序作为合法 （非病毒） 程序。</span><span class="sxs-lookup"><span data-stu-id="62060-132">The antivirus software has not been updated to include the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program as a legitimate (non-virus) program.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="62060-133">解决方法</span><span class="sxs-lookup"><span data-stu-id="62060-133">Resolution</span></span>  
 <span data-ttu-id="62060-134">配置防病毒程序识别[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序正在运行时，配置程序作为合法 （非病毒） 程序，否则暂时禁用防病毒软件。</span><span class="sxs-lookup"><span data-stu-id="62060-134">Configure the antivirus program to recognize the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program as a legitimate (non-virus) program or else temporarily disable the antivirus software while the configuration program is running.</span></span>  
  
#### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a><span data-ttu-id="62060-135">配置失败，出现"文件或程序集名称 FileName.dll，或其某个依赖项，未找到"错误</span><span class="sxs-lookup"><span data-stu-id="62060-135">Configuration fails with a "File or assembly name FileName.dll, or one of its dependencies, was not found" error</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="62060-136">问题</span><span class="sxs-lookup"><span data-stu-id="62060-136">Problem</span></span>  
 <span data-ttu-id="62060-137">在配置过程中将显示类似于以下错误：</span><span class="sxs-lookup"><span data-stu-id="62060-137">An error similar to the following is displayed during the configuration process:</span></span>  
  
 <span data-ttu-id="62060-138">无法部署 BizTalk 系统程序集"C:\Program Files\Microsoft\\</span><span class="sxs-lookup"><span data-stu-id="62060-138">Failed to deploy BizTalk system assembly "C:\Program Files\Microsoft\\</span></span>  
  
 <span data-ttu-id="62060-139">BizTalk Server 2009\Microsoft.BizTalk.DefaultPipelines.dll.</span><span class="sxs-lookup"><span data-stu-id="62060-139">BizTalk Server 2009\Microsoft.BizTalk.DefaultPipelines.dll.</span></span> <span data-ttu-id="62060-140">“未指定”</span><span class="sxs-lookup"><span data-stu-id="62060-140">Unspecified</span></span>  
  
 <span data-ttu-id="62060-141">异常：文件或程序集名称 FileName.dll 或其中一个其</span><span class="sxs-lookup"><span data-stu-id="62060-141">exception: File or assembly name FileName .dll, or one of its</span></span>  
  
 <span data-ttu-id="62060-142">依赖项，找不到。</span><span class="sxs-lookup"><span data-stu-id="62060-142">dependencies, was not found.</span></span> <span data-ttu-id="62060-143">文件或程序集名称 FileName.dll 或</span><span class="sxs-lookup"><span data-stu-id="62060-143">File or assembly name FileName .dll, or</span></span>  
  
 <span data-ttu-id="62060-144">其某个依赖项，未找到。"</span><span class="sxs-lookup"><span data-stu-id="62060-144">one of its dependencies, was not found."</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="62060-145">原因</span><span class="sxs-lookup"><span data-stu-id="62060-145">Cause</span></span>  
 <span data-ttu-id="62060-146">如果网络服务帐户运行的计算机上的临时文件夹没有写入权限，可能出现此错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="62060-146">This error can occur if the Network Service account does not have write permissions to the temp folder on the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="62060-147">在配置期间，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置使用 Windows Management Instrumentation (WMI) 将.NET 程序集部署到 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="62060-147">During configuration, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration uses Windows Management Instrumentation (WMI) to deploy .NET assemblies to the BizTalk Management database.</span></span> <span data-ttu-id="62060-148">这些程序集部署到 BizTalk 管理数据库时，WMI 模拟网络服务帐户，因此网络服务帐户必须运行的计算机上的临时文件夹具有写访问权限[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="62060-148">WMI impersonates the Network Service account while deploying these assemblies to the BizTalk Management database and so the Network Service account must have write access to the temp folder on the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="62060-149">解决方法</span><span class="sxs-lookup"><span data-stu-id="62060-149">Resolution</span></span>  
 <span data-ttu-id="62060-150">授予网络服务帐户写入访问权限运行的计算机上的临时文件夹[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并再次运行配置程序。</span><span class="sxs-lookup"><span data-stu-id="62060-150">Grant the Network Service account write access to the temp folder on the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and run the configuration program again.</span></span> <span data-ttu-id="62060-151">若要确定由 TEMP 环境变量指定的文件夹，打开命令提示符在计算机上，键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="62060-151">To determine the folder that is specified by the TEMP environment variable, open a command prompt on the computer, type the following command, and then press ENTER:</span></span>  
  
```  
echo %TEMP%  
```  
  
#### <a name="configuration-of-the-group-fails-if-the-netbios-name-of-the-computer-running-sql-server-exceeds-15-characters"></a><span data-ttu-id="62060-152">如果运行 SQL Server 的计算机的 NetBIOS 名称超过 15 个字符的组的配置将失败</span><span class="sxs-lookup"><span data-stu-id="62060-152">Configuration of the group fails if the NetBIOS name of the computer running SQL Server exceeds 15 characters</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="62060-153">问题</span><span class="sxs-lookup"><span data-stu-id="62060-153">Problem</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="62060-154">组配置失败，并且类似于以下的错误显示在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置日志：</span><span class="sxs-lookup"><span data-stu-id="62060-154">group configuration fails and an error similar to the following is displayed in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration log:</span></span>  
  
 <span data-ttu-id="62060-155">2006-08-29 23:54:00:0902 [WARN] AdminLib GetBTSMessage: hrErr=80070547;</span><span class="sxs-lookup"><span data-stu-id="62060-155">2006-08-29 23:54:00:0902 [WARN] AdminLib GetBTSMessage: hrErr=80070547;</span></span>  
  
 <span data-ttu-id="62060-156">Msg = 无法从域中读取信息的配置</span><span class="sxs-lookup"><span data-stu-id="62060-156">Msg=Configuration information could not be read from the domain</span></span>  
  
 <span data-ttu-id="62060-157">控制器，或者因为计算机不可用，或者是具有访问权限</span><span class="sxs-lookup"><span data-stu-id="62060-157">controller, either because the machine is unavailable, or access has</span></span>  
  
 <span data-ttu-id="62060-158">已拒绝。;</span><span class="sxs-lookup"><span data-stu-id="62060-158">been denied.;</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="62060-159">原因</span><span class="sxs-lookup"><span data-stu-id="62060-159">Cause</span></span>  
 <span data-ttu-id="62060-160">如果运行的计算机命名为 NetBIOS 的长度，会发生此问题[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]超过 15 个字符。</span><span class="sxs-lookup"><span data-stu-id="62060-160">This problem occurs if the length of the NetBIOS name for the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] exceeds 15 characters.</span></span> <span data-ttu-id="62060-161">如果 NetBIOS 名称超过 15 个字符 Windows 然后截断至 15 个字符的 NetBIOS 名称和 NetBIOS 名称将不再匹配的完全限定的域名 (FQDN) 或此计算机的 DNS 名称的第一部分。</span><span class="sxs-lookup"><span data-stu-id="62060-161">If the NetBIOS name exceeds 15 characters then Windows truncates the NetBIOS name to 15 characters and the NetBIOS name will no longer match the first part of the fully qualified domain name (FQDN) or DNS name of this computer.</span></span> <span data-ttu-id="62060-162">如果 NetBIOS 名称不匹配的计算机的 FQDN 的第一部分，组配置将失败。</span><span class="sxs-lookup"><span data-stu-id="62060-162">If the NetBIOS name does not match the first part of the FQDN of the computer, group configuration will fail.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="62060-163">解决方法</span><span class="sxs-lookup"><span data-stu-id="62060-163">Resolution</span></span>  
 <span data-ttu-id="62060-164">更改运行的计算机的 NetBIOS 名称[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]到包含不超过 15 个字符，然后再次运行的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="62060-164">Change the NetBIOS name of the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] to a name with no more than 15 characters and run configuration again.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62060-165">如果您重命名，必须重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="62060-165">You must restart the computer if you rename it.</span></span>  
  
#### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a><span data-ttu-id="62060-166">如果已具有相同的名称，因为指定的数据库的 SQL Server 数据库文件存在于 SQL Server 数据文件夹配置失败</span><span class="sxs-lookup"><span data-stu-id="62060-166">Configuration fails if a SQL Server database file that has the same name as the specified database already exists in the SQL Server data folder</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="62060-167">问题</span><span class="sxs-lookup"><span data-stu-id="62060-167">Problem</span></span>  
 <span data-ttu-id="62060-168">配置失败并出现类似于以下的错误：</span><span class="sxs-lookup"><span data-stu-id="62060-168">Configuration fails with an error similar to the following:</span></span>  
  
 <span data-ttu-id="62060-169">无法设置 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="62060-169">Failed to set up BAM database(s)</span></span>  
  
 <span data-ttu-id="62060-170">无法打开登录 BAMPrimaryImport 中所请求的数据库</span><span class="sxs-lookup"><span data-stu-id="62060-170">Cannot open database requested in login 'BAMPrimaryImport'</span></span>  
  
 <span data-ttu-id="62060-171">登录失败。</span><span class="sxs-lookup"><span data-stu-id="62060-171">Logon fails.</span></span> <span data-ttu-id="62060-172">用户的登录失败*BizTalk\BizTalkUser*</span><span class="sxs-lookup"><span data-stu-id="62060-172">Logon failed for user '*BizTalk\BizTalkUser*'</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="62060-173">原因</span><span class="sxs-lookup"><span data-stu-id="62060-173">Cause</span></span>  
 <span data-ttu-id="62060-174">如果运行的计算机的 \MSSQL\data 文件夹中已存在的.mdf 文件或.ldf 文件，可能出现此错误[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]具有相同的名称为.mdf 文件或.ldf 文件的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序尝试创建。</span><span class="sxs-lookup"><span data-stu-id="62060-174">This error can occur if an .mdf file or an .ldf file already exists in the \MSSQL\data folder of the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that has the same name as the .mdf file or the .ldf file that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program is trying to create.</span></span> <span data-ttu-id="62060-175">为数据库派生自中指定的数据库的名称创建的.mdf 文件和.ldf 文件的名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].mdf 和.ldf 扩展名追加配置程序。</span><span class="sxs-lookup"><span data-stu-id="62060-175">The names of the .mdf file and the .ldf file that are created for the databases are derived from the name of the database that is specified in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program with an .mdf and an .ldf extension appended.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="62060-176">解决方法</span><span class="sxs-lookup"><span data-stu-id="62060-176">Resolution</span></span>  
 <span data-ttu-id="62060-177">若要解决此问题，请使用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="62060-177">To resolve this behavior, use one of the following methods:</span></span>  
  
-   <span data-ttu-id="62060-178">删除任何.mdf 文件或.ldf 文件与要创建的任何数据库的名称匹配的名称。</span><span class="sxs-lookup"><span data-stu-id="62060-178">Delete any .mdf files or .ldf files that have names that match the names of any databases that you are creating.</span></span>  
  
-   <span data-ttu-id="62060-179">选择数据库名称不匹配的任何.mdf 文件或.ldf 文件已存在 SQL server 的 \Program Files\Microsoft SQL Server\MSSQL\data 文件夹中的名称。</span><span class="sxs-lookup"><span data-stu-id="62060-179">Choose database names that do not match the names of any .mdf files or .ldf files that already exist in the \Program Files\Microsoft SQL Server\MSSQL\data folder of your SQL server.</span></span>  
  
#### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a><span data-ttu-id="62060-180">指定本地帐户时，配置在域控制器上失败</span><span class="sxs-lookup"><span data-stu-id="62060-180">Configuration fails on a domain controller when specifying local accounts</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="62060-181">问题</span><span class="sxs-lookup"><span data-stu-id="62060-181">Problem</span></span>  
 <span data-ttu-id="62060-182">运行时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序的域控制器上，如果您为 BizTalkServerApplication 主机或 BizTalkIsolatedHost 主机指定本地组 （例如，BizTalk 主机用户组），则配置失败。</span><span class="sxs-lookup"><span data-stu-id="62060-182">When running the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program on a domain controller, configuration fails if you specified a local group (for example, BizTalk Host Users Group) for either the BizTalkServerApplication host or the BizTalkIsolatedHost host.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="62060-183">原因</span><span class="sxs-lookup"><span data-stu-id="62060-183">Cause</span></span>  
 <span data-ttu-id="62060-184">域控制器会自动将本地 Windows 组视为域 Windows 组 （没有就没有域控制器上的本地 Windows 组）。</span><span class="sxs-lookup"><span data-stu-id="62060-184">A domain controller automatically treats a local Windows group as a domain Windows group (there is no such thing as local Windows group on a domain controller).</span></span> <span data-ttu-id="62060-185">如果您运行配置程序时为主机指定本地 Windows 组，配置将失败时尝试创建[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]组登录。</span><span class="sxs-lookup"><span data-stu-id="62060-185">If you specified a local Windows group for the host while running the configuration program, configuration will fail when trying to create a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] logon for the group.</span></span> <span data-ttu-id="62060-186">当服务器是域控制器时，配置程序不会禁用本地 Windows 组选项。</span><span class="sxs-lookup"><span data-stu-id="62060-186">The configuration program does not disable the local Windows group option when the server is a domain controller.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="62060-187">解决方法</span><span class="sxs-lookup"><span data-stu-id="62060-187">Resolution</span></span>  
 <span data-ttu-id="62060-188">在配置期间创建的主机指定域组。</span><span class="sxs-lookup"><span data-stu-id="62060-188">Specify domain groups for the hosts that are created during configuration.</span></span>  
  
#### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a><span data-ttu-id="62060-189">无法创建 SQL Server 分析数据库，如果已重命名 SQL server 配置</span><span class="sxs-lookup"><span data-stu-id="62060-189">Configuration fails to create SQL Server Analysis database if the SQL server has been renamed</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="62060-190">问题</span><span class="sxs-lookup"><span data-stu-id="62060-190">Problem</span></span>  
 <span data-ttu-id="62060-191">如果已重命名在其安装 SQL Server 分析服务器的计算机，配置程序将失败时尝试创建新的 SQL Server 分析数据库并生成类似于以下错误：</span><span class="sxs-lookup"><span data-stu-id="62060-191">If you have renamed the computer on which you installed SQL Server Analysis Server, the configuration program fails when it tries to create the new SQL Server Analysis database and an error similar to the following is generated:</span></span>  
  
 <span data-ttu-id="62060-192">无法连接到存储库。</span><span class="sxs-lookup"><span data-stu-id="62060-192">Cannot connect to the repository.</span></span>  
  
 <span data-ttu-id="62060-193">Analysis server:\<计算机名称\></span><span class="sxs-lookup"><span data-stu-id="62060-193">Analysis server: \<machine name\></span></span>  
  
 <span data-ttu-id="62060-194">错误：</span><span class="sxs-lookup"><span data-stu-id="62060-194">Error:</span></span>  
  
 <span data-ttu-id="62060-195">'\\\\< 计算机名称\>\MsOLAPRepository$\msmdrep.mdb 不是有效路径。</span><span class="sxs-lookup"><span data-stu-id="62060-195">'\\\\<machine name\>\MsOLAPRepository$\msmdrep.mdb' is not a valid path.</span></span>  
  
 <span data-ttu-id="62060-196">请确保正确拼写路径名称，并且您已</span><span class="sxs-lookup"><span data-stu-id="62060-196">Make sure that you correctly spell the path name and that you are</span></span>  
  
 <span data-ttu-id="62060-197">连接到该文件所驻留的服务器。</span><span class="sxs-lookup"><span data-stu-id="62060-197">connected to the server on which the file resides.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="62060-198">原因</span><span class="sxs-lookup"><span data-stu-id="62060-198">Cause</span></span>  
 <span data-ttu-id="62060-199">配置程序不能确定在其安装 SQL Server 分析服务器的计算机的新名称。</span><span class="sxs-lookup"><span data-stu-id="62060-199">The configuration program is unable to determine the new name of the computer on which you installed SQL Server Analysis Server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="62060-200">解决方法</span><span class="sxs-lookup"><span data-stu-id="62060-200">Resolution</span></span>  
 <span data-ttu-id="62060-201">执行以下手动步骤，以使用新的计算机名更新分析服务器：</span><span class="sxs-lookup"><span data-stu-id="62060-201">Perform the following manual steps to update Analysis Server with the new computer name:</span></span>  
  
1.  <span data-ttu-id="62060-202">单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server**，指向**Analysis Services**，然后单击**分析管理器**。</span><span class="sxs-lookup"><span data-stu-id="62060-202">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Analysis Services**, and then click **Analysis Manager**.</span></span>  
  
2.  <span data-ttu-id="62060-203">在中**分析管理器**导航面板中，双击**分析服务器**节点以将其展开。</span><span class="sxs-lookup"><span data-stu-id="62060-203">In the **Analysis Manager** navigation panel, double-click the **Analysis Servers** node to expand it.</span></span>  
  
3.  <span data-ttu-id="62060-204">右键单击你想要编辑，然后选择的存储库连接字符串服务器**编辑存储库连接字符串**。</span><span class="sxs-lookup"><span data-stu-id="62060-204">Right-click the server with the repository connection string you want to edit, and then select **Edit Repository Connection String**.</span></span>  
  
4.  <span data-ttu-id="62060-205">在中**编辑存储库连接字符串**对话框中，验证此字符串中的服务器名称，它更新为新的计算机名称是否正确。</span><span class="sxs-lookup"><span data-stu-id="62060-205">In the **Edit Repository Connection String** dialog box, verify the server name in this string and update it to the new computer name if it is incorrect.</span></span>  
  
5.  <span data-ttu-id="62060-206">导航到以下位置： \<*安装目录*\>\Program Files\Microsoft Analysis Services\Bin。</span><span class="sxs-lookup"><span data-stu-id="62060-206">Navigate to the following location: \<*installation directory*\>\Program Files\Microsoft Analysis Services\Bin.</span></span>  
  
6.  <span data-ttu-id="62060-207">右键单击**Bin**文件夹，，然后单击**共享和安全**。</span><span class="sxs-lookup"><span data-stu-id="62060-207">Right-click the **Bin** folder, and then click **Sharing and Security**.</span></span> <span data-ttu-id="62060-208">**Bin 属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="62060-208">The **Bin Properties** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="62060-209">在中**Bin 属性**对话框中，单击**共享**选项卡来验证所有联机分析处理 (OLAP) 管理员具有对此文件夹的完全权限。</span><span class="sxs-lookup"><span data-stu-id="62060-209">In the **Bin Properties** dialog box, click the **Sharing** tab to verify that all Online Analytical Processing (OLAP) administrators have full permissions to this folder.</span></span>  
  
#### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a><span data-ttu-id="62060-210">项目将从配置数据库上重新部署程序集从 Visual Studio 中消失</span><span class="sxs-lookup"><span data-stu-id="62060-210">Artifacts Disappear from Configuration Database on Redeployment of Assemblies from Visual Studio</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="62060-211">问题</span><span class="sxs-lookup"><span data-stu-id="62060-211">Problem</span></span>  
 <span data-ttu-id="62060-212">当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]内的项目级重新部署项目[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，包含在项目中引用正在重新部署该项目的所有项目都都消失时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]刷新 MMC。</span><span class="sxs-lookup"><span data-stu-id="62060-212">When a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project is redeployed at the project level within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], all artifacts contained within the project that reference the project being redeployed will appear to vanish when the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MMC is refreshed.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="62060-213">原因</span><span class="sxs-lookup"><span data-stu-id="62060-213">Cause</span></span>  
 <span data-ttu-id="62060-214">为了说明此问题的原因，请考虑下面的示例基于示例用户要重新部署 Maps 项目的 BizTalk Server 解决方案。</span><span class="sxs-lookup"><span data-stu-id="62060-214">To illustrate the cause of this problem, consider the following example based on a sample BizTalk Server solution where a user wants to redeploy the Maps project.</span></span> <span data-ttu-id="62060-215">请注意，编译项目生成单独的程序集。</span><span class="sxs-lookup"><span data-stu-id="62060-215">Note that compiling projects yields individual assemblies.</span></span> <span data-ttu-id="62060-216">用户在进行重新部署之前下, 图指示解决方案的状态。</span><span class="sxs-lookup"><span data-stu-id="62060-216">The following figure indicates the state of the solution before the user does a redeployment.</span></span> <span data-ttu-id="62060-217">项目之间的关系如下所示：</span><span class="sxs-lookup"><span data-stu-id="62060-217">The relationships among the artifacts are as follows:</span></span>  
  
- <span data-ttu-id="62060-218">Orch1、 Orch2、 映射、 管道和架构项目。</span><span class="sxs-lookup"><span data-stu-id="62060-218">Orch1, Orch2, Maps, Pipelines, and Schemas are projects.</span></span>  
  
- <span data-ttu-id="62060-219">Orch1 引用 Maps，后者又引用架构。</span><span class="sxs-lookup"><span data-stu-id="62060-219">Orch1 references Maps, which in turn references Schemas.</span></span>  
  
- <span data-ttu-id="62060-220">Orch2 引用 Schemas。</span><span class="sxs-lookup"><span data-stu-id="62060-220">Orch2 references Schemas.</span></span>  
  
- <span data-ttu-id="62060-221">Pipelines 引用 Schemas。</span><span class="sxs-lookup"><span data-stu-id="62060-221">Pipelines references Schemas.</span></span>  
  
  <span data-ttu-id="62060-222">![](../core/media/bcd-existingbiztalkserversolutionc.gif "bcd_ExistingBizTalkServerSolutionc")</span><span class="sxs-lookup"><span data-stu-id="62060-222">![](../core/media/bcd-existingbiztalkserversolutionc.gif "bcd_ExistingBizTalkServerSolutionc")</span></span>  
  
  <span data-ttu-id="62060-223">如果用户重新部署 Maps 项目使用默认 Visual Studio 项目设置，Orch1、 Orch2 和管道项目将消失下, 图中所示。</span><span class="sxs-lookup"><span data-stu-id="62060-223">If the user redeploys the Maps project using the default Visual Studio project settings, the Orch1, Orch2, and Pipeline artifacts vanish, as shown in the following figure.</span></span>  
  
  <span data-ttu-id="62060-224">![](../core/media/bcd-biztalksolutionwlostartifactsc.gif "bcd_BizTalkSolutionWLostArtifactsc")</span><span class="sxs-lookup"><span data-stu-id="62060-224">![](../core/media/bcd-biztalksolutionwlostartifactsc.gif "bcd_BizTalkSolutionWLostArtifactsc")</span></span>  
  
  <span data-ttu-id="62060-225">重新部署 Maps 是一个两步过程以及取消部署当前已部署的 Maps.dll 程序集，然后部署新的 Maps.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="62060-225">Redeploying Maps is a two-step process of undeploying the currently deployed Maps.dll assembly, and then deploying the new Maps.dll file.</span></span> <span data-ttu-id="62060-226">Visual Studio 重新部署过程的一部分自动执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="62060-226">Visual Studio performs these steps automatically as part of the redeployment process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62060-227">上面的描述不完全正确，因为这些是 Visual Studio 一直执行的步骤因此没有考虑其方式是否适当。</span><span class="sxs-lookup"><span data-stu-id="62060-227">The preceding sentence is not strictly correct because these are steps that Visual Studio always does so there is no notion of it being the proper way.</span></span>  
  
 <span data-ttu-id="62060-228">关键之处在于，为了取消部署 BizTalk Server 程序集[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]必须取消部署所有程序集依赖于该程序集的设置部署标志。</span><span class="sxs-lookup"><span data-stu-id="62060-228">The key point is that in order to undeploy a BizTalk Server assembly, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] has to undeploy all assemblies that are dependent upon that assembly that have the deploy flag set.</span></span> <span data-ttu-id="62060-229">在本示例中，若要执行的重新部署，首先取消部署 BizTalk Server 需要取消部署 Orch1.dll （而它依赖于 Maps.dll）。</span><span class="sxs-lookup"><span data-stu-id="62060-229">In our example, to perform the first undeployment step of the redeployment, BizTalk Server needs to undeploy Orch1.dll (which depends on Maps.dll).</span></span> <span data-ttu-id="62060-230">在取消部署 Maps.dll 的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]还将取消部署 Schemas.dll （假定它已设置部署标志）。</span><span class="sxs-lookup"><span data-stu-id="62060-230">During the undeployment of Maps.dll, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] also undeploys Schemas.dll (assuming it has the deploy flag set).</span></span> <span data-ttu-id="62060-231">为了取消部署 Schemas.dll，Visual Studio 需要取消部署 Orch2.dll 和 Pipelines.dll （这两者都依赖于 Schemas.dll）。</span><span class="sxs-lookup"><span data-stu-id="62060-231">In order to undeploy Schemas.dll, Visual Studio needs to undeploy Orch2.dll and Pipelines.dll (both of which depend on Schemas.dll).</span></span>  
  
 <span data-ttu-id="62060-232">中的存在问题[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]重新部署仅 Maps.dll 以及它所依赖的程序集： 在本例中为 Schemas.dll。</span><span class="sxs-lookup"><span data-stu-id="62060-232">A problem exists in that [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] redeploys only Maps.dll and the assemblies that it depends upon: in this case, Schemas.dll.</span></span> <span data-ttu-id="62060-233">因此，当用户刷新 BizTalk Server MMC，Orch1 和 Orch2，管道程序集似乎消失，但 Maps.dll 和 Schemas.dll 是仍然可见。</span><span class="sxs-lookup"><span data-stu-id="62060-233">So when the user refreshes the BizTalk Server MMC, the Orch1, Orch2, and Pipeline assemblies seem to have vanished, but Maps.dll and Schemas.dll are still visible.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="62060-234">解决方法</span><span class="sxs-lookup"><span data-stu-id="62060-234">Resolution</span></span>  
 <span data-ttu-id="62060-235">主项目 （引用其他项目），请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="62060-235">For the main project (that references other projects) do the following:</span></span>  
  
1.  <span data-ttu-id="62060-236">在解决方案资源管理器，右键单击解决方案节点。</span><span class="sxs-lookup"><span data-stu-id="62060-236">In Solution Explorer, right-click the solution node.</span></span>  
  
2.  <span data-ttu-id="62060-237">单击**属性**以打开**解决方案属性页**对话框。</span><span class="sxs-lookup"><span data-stu-id="62060-237">Click **Properties** to open the **Solution Property Pages** dialog box.</span></span>  
  
3.  <span data-ttu-id="62060-238">单击**配置属性**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="62060-238">Click **Configuration Properties**, and then click **Configuration**.</span></span>  
  
4.  <span data-ttu-id="62060-239">清除**部署**引用的项目的复选框。</span><span class="sxs-lookup"><span data-stu-id="62060-239">Clear the **Deploy** check box for the referenced project.</span></span>  
  
5.  <span data-ttu-id="62060-240">在解决方案资源管理器中执行新的解决方案级部署。</span><span class="sxs-lookup"><span data-stu-id="62060-240">In Solution Explorer, execute a new solution-level deployment.</span></span> <span data-ttu-id="62060-241">若要执行此操作，右键单击解决方案节点，然后单击**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="62060-241">To do this, right-click the solution node and then click **Deploy Solution**.</span></span>  
  
#### <a name="supported-virtual-directory-types"></a><span data-ttu-id="62060-242">支持的虚拟目录类型</span><span class="sxs-lookup"><span data-stu-id="62060-242">Supported Virtual Directory Types</span></span>  
 <span data-ttu-id="62060-243">仅当关联的虚拟目录的类型，导出操作时从业务流程，并尝试执行 MSI 导出引用 Web 服务，将会成功**IIsWebVirtualDir**或**IIsWebDirectory**.</span><span class="sxs-lookup"><span data-stu-id="62060-243">When referencing Web services from an orchestration and attempting to do an MSI export, the export operation will succeed only if the associated virtual directories are of type **IIsWebVirtualDir** or **IIsWebDirectory**.</span></span> <span data-ttu-id="62060-244">**IIsWebVirtualDir**并**IIsWebDirectory**是显示在 IIS 元数据库中的节点类型。</span><span class="sxs-lookup"><span data-stu-id="62060-244">**IIsWebVirtualDir** and **IIsWebDirectory** are the node types that appear in the IIS metabase.</span></span> <span data-ttu-id="62060-245">**IIsWebVirtualDir**是与虚拟目录**路径**指向绝对文件夹的属性。</span><span class="sxs-lookup"><span data-stu-id="62060-245">**IIsWebVirtualDir** is a virtual directory with a **Path** property that points to an absolute file folder.</span></span> <span data-ttu-id="62060-246">**IIsWebDirectory**是一个虚拟目录，而无需**路径**属性，因此指向相对文件夹中，通常的另一个子文件夹**IIsWebVirtualDir**或**IIsWebDirectory**节点。</span><span class="sxs-lookup"><span data-stu-id="62060-246">**IIsWebDirectory** is a virtual directory without a **Path** property and thus refers to a relative file folder, typically a subfolder of another **IIsWebVirtualDir** or **IIsWebDirectory** node.</span></span> <span data-ttu-id="62060-247">这两种类型是通常会出现在元数据库层次结构中用于描述文件夹。</span><span class="sxs-lookup"><span data-stu-id="62060-247">These two types are the ones typically seen in the metabase hierarchy to describe folders.</span></span>  
  
 <span data-ttu-id="62060-248">类型的虚拟目录**IIsConfigObject**不受支持，并且，MSI 导出在此情况下将失败。</span><span class="sxs-lookup"><span data-stu-id="62060-248">Virtual directories of type **IIsConfigObject** are not supported and the MSI export will fail in this case.</span></span> <span data-ttu-id="62060-249">**IIsConfigObject**是 BizTalk Server 无法正确处理任一有效的节点类型的意外元数据库节点类型或相对值的指示正确创建 （并因此而无效） 元数据库条目。</span><span class="sxs-lookup"><span data-stu-id="62060-249">**IIsConfigObject** is an unexpected metabase node type that is either a valid node type that BizTalk Server is not handling properly or an indication of an improperly created (and thus invalid) metabase entry.</span></span> <span data-ttu-id="62060-250">在此情况下 BizTalk Server 将显示一条错误消息类似于以下内容：预期的目录条目"iis: //lm/w3svc/1/root/badvdir/"，类型为 IIsConfigObject。</span><span class="sxs-lookup"><span data-stu-id="62060-250">In this situation BizTalk Server will display an error message something like the following: Unexpected directory entry " IIS://LM/W3SVC/1/ROOT/BadVdir/" of type IIsConfigObject.</span></span>  
  
#### <a name="unable-to-view-group-information-after-removing-stale-logons"></a><span data-ttu-id="62060-251">无法查看组信息删除过时登录后</span><span class="sxs-lookup"><span data-stu-id="62060-251">Unable to view Group information after removing stale logons</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="62060-252">问题</span><span class="sxs-lookup"><span data-stu-id="62060-252">Problem</span></span>  
 <span data-ttu-id="62060-253">如果在配置期间，你会遇到并删除过时登录，你可能无法查看组信息。</span><span class="sxs-lookup"><span data-stu-id="62060-253">If, during configuration, you encounter and delete stale logons, you may not be able to view Group information.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="62060-254">原因</span><span class="sxs-lookup"><span data-stu-id="62060-254">Cause</span></span>  
 <span data-ttu-id="62060-255">这是一个已知的配置问题。</span><span class="sxs-lookup"><span data-stu-id="62060-255">This is a known configuration issue.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="62060-256">解决方法</span><span class="sxs-lookup"><span data-stu-id="62060-256">Resolution</span></span>  
 <span data-ttu-id="62060-257">它可能有助于删除主机 Windows 组登录，然后重新配置。</span><span class="sxs-lookup"><span data-stu-id="62060-257">It may help to delete the Host Windows group logons and then reconfigure.</span></span> <span data-ttu-id="62060-258">如果组信息仍不可用，请联系 Microsoft 产品支持。</span><span class="sxs-lookup"><span data-stu-id="62060-258">If the Group information is still not available, contact Microsoft Product Support.</span></span>  
  
##### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a><span data-ttu-id="62060-259">安装 BizTalk Server 后无法更改计算机名称</span><span class="sxs-lookup"><span data-stu-id="62060-259">Cannot change computer name after BizTalk Server is installed</span></span>  
  
###### <a name="problem"></a><span data-ttu-id="62060-260">问题</span><span class="sxs-lookup"><span data-stu-id="62060-260">Problem</span></span>  
 <span data-ttu-id="62060-261">当您更改运行的计算机上的计算机名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并重新启动 （重启） 计算机，可能会出现错误消息。</span><span class="sxs-lookup"><span data-stu-id="62060-261">When you change the computer name on a computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and you restart (reboot) the computer, error messages may occur.</span></span>  
  
###### <a name="cause"></a><span data-ttu-id="62060-262">原因</span><span class="sxs-lookup"><span data-stu-id="62060-262">Cause</span></span>  
 <span data-ttu-id="62060-263">SQL Server 不支持更改计算机名称，因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]不支持一次更改计算机名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装和配置。</span><span class="sxs-lookup"><span data-stu-id="62060-263">SQL Server does not support changing the computer name, so [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not support changing the computer name once [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed and configured.</span></span>  
  
###### <a name="resolution"></a><span data-ttu-id="62060-264">解决方法</span><span class="sxs-lookup"><span data-stu-id="62060-264">Resolution</span></span>  
 <span data-ttu-id="62060-265">我们建议在安装 BizTalk Server 后不会更改计算机名称。</span><span class="sxs-lookup"><span data-stu-id="62060-265">We recommend that you do not change computer names after you install BizTalk Server.</span></span>
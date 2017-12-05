---
title: "配置疑难解答 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 902e591a-4ff4-4053-b329-0c022f44999a
caps.latest.revision: "37"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e523c5c992ea422e6fe81f3c0d948db7007bcdb1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshooting-configuration"></a><span data-ttu-id="0a203-102">配置疑难解答</span><span class="sxs-lookup"><span data-stu-id="0a203-102">Troubleshooting Configuration</span></span>
<span data-ttu-id="0a203-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序将运行的一个或多个计算机上创建数据库[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]、 填充了表，角色的数据库和存储过程使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，并将部署到运行时期间使用的.NET 程序集BizTalk 管理数据库中。</span><span class="sxs-lookup"><span data-stu-id="0a203-103">The Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program creates databases on one or more computers running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], populates the databases with tables, roles, and stored procedures used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and deploys .NET assemblies used during runtime to the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="0a203-104">本部分讨论用于解决配置错误的疑难解答方法。</span><span class="sxs-lookup"><span data-stu-id="0a203-104">This section discusses troubleshooting techniques to resolve configuration errors.</span></span> <span data-ttu-id="0a203-105">它还列出了某些常见的配置问题以及解决这些问题的方法。</span><span class="sxs-lookup"><span data-stu-id="0a203-105">It also lists some common configuration problems and how to resolve these problems.</span></span>  
  
## <a name="configuration-logging"></a><span data-ttu-id="0a203-106">配置记录</span><span class="sxs-lookup"><span data-stu-id="0a203-106">Configuration Logging</span></span>  
 <span data-ttu-id="0a203-107">配置程序的详细的信息将写入配置日志文件位于默认情况下运行的计算机的临时目录中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0a203-107">The configuration program writes detailed information to a configuration log file which by default is located in the temp directory of the computer running[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0a203-108">若要确定由 TEMP 环境变量指定的文件夹，请在此计算机上打开命令提示符，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="0a203-108">To determine the folder that is specified by the TEMP environment variable open a command prompt on this computer, type the following command, and then press ENTER:</span></span>  
  
 <span data-ttu-id="0a203-109">**echo %TEMP%**</span><span class="sxs-lookup"><span data-stu-id="0a203-109">**echo %TEMP%**</span></span>  
  
 <span data-ttu-id="0a203-110">配置日志文件中包含所执行的配置步骤的摘要，以及在配置过程中可能发生的任何故障的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="0a203-110">The configuration log file contains a summary of the configuration steps performed, as well as diagnostic information about any failures that may occur during the configuration process.</span></span> <span data-ttu-id="0a203-111">如果出现配置错误，请在文本编辑器（如“记事本”）中打开配置日志，然后在日志中检查此错误的可能原因。</span><span class="sxs-lookup"><span data-stu-id="0a203-111">If a configuration error occurs, open the configuration log in a text editor such as Notepad and check the log file for possible causes of the error.</span></span>  
  
## <a name="troubleshooting-tools"></a><span data-ttu-id="0a203-112">疑难解答工具</span><span class="sxs-lookup"><span data-stu-id="0a203-112">Troubleshooting Tools</span></span>  
 <span data-ttu-id="0a203-113">使用 SQL Server Profiler、Filemon 或 Regmon 收集有关配置失败的其他信息。</span><span class="sxs-lookup"><span data-stu-id="0a203-113">Use SQL Server Profiler, Filemon, or Regmon to gather additional information about configuration failures.</span></span> <span data-ttu-id="0a203-114">有关这些工具的详细信息，请参阅[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="0a203-114">For more information about these tools, see [Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="0a203-115">已知问题</span><span class="sxs-lookup"><span data-stu-id="0a203-115">Known Issues</span></span>  
  
#### <a name="configuration-fails-when-biztalk-server-and-sql-server-are-installed-on-separate-computers"></a><span data-ttu-id="0a203-116">当在单独的计算机上安装 BizTalk Server 和 SQL Server 时，配置失败</span><span class="sxs-lookup"><span data-stu-id="0a203-116">Configuration fails when BizTalk Server and SQL Server are installed on separate computers</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0a203-117">问题</span><span class="sxs-lookup"><span data-stu-id="0a203-117">Problem</span></span>  
 <span data-ttu-id="0a203-118">当尝试配置 Enterprise 单一登录 (SSO) 组件时，配置失败并出现如下错误：</span><span class="sxs-lookup"><span data-stu-id="0a203-118">Configuration fails with errors similar to the following when attempting to configure the Enterprise Single Sign-On (SSO) component:</span></span>  
  
 <span data-ttu-id="0a203-119">尝试访问 SSO 数据库时出错。</span><span class="sxs-lookup"><span data-stu-id="0a203-119">An error occurred while attempting to access the SSO database.</span></span>  
  
 <span data-ttu-id="0a203-120">函数： FieldInfoCreate</span><span class="sxs-lookup"><span data-stu-id="0a203-120">Function: FieldInfoCreate</span></span>  
  
 <span data-ttu-id="0a203-121">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0a203-121">-or-</span></span>  
  
 <span data-ttu-id="0a203-122">启用单一登录 (SSO) 服务失败（错误代码 0X800706BA）</span><span class="sxs-lookup"><span data-stu-id="0a203-122">Failed to enable the Single Sign-On (SSO) Service (error code 0X800706BA)</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0a203-123">原因</span><span class="sxs-lookup"><span data-stu-id="0a203-123">Cause</span></span>  
 <span data-ttu-id="0a203-124">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]分布式事务处理协调器 (MSDTC) 事务的上下文中执行的配置操作然后 MSDTC 功能必须可通过不同的计算机上安装这些计算机之间的网络。</span><span class="sxs-lookup"><span data-stu-id="0a203-124">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are installed on different computers then the configuration operations are performed under the context of a Distributed Transaction Coordinator (MSDTC) transaction and MSDTC functionality must be available over the network between these computers.</span></span> <span data-ttu-id="0a203-125">如果 MSDTC 功能将不可用通过运行计算机之间的网络[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]则会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="0a203-125">If MSDTC functionality is not available over the network between the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] then this error can occur.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0a203-126">解决方法</span><span class="sxs-lookup"><span data-stu-id="0a203-126">Resolution</span></span>  
 <span data-ttu-id="0a203-127">按照中的步骤[问题疑难解答与 MSDTC](../core/troubleshooting-problems-with-msdtc.md)确保 MSDTC 功能将通过运行计算机之间的网络[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0a203-127">Follow the steps in [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md) to ensure MSDTC functionality over the network between the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
#### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a><span data-ttu-id="0a203-128">防病毒软件干扰配置并导致配置失败</span><span class="sxs-lookup"><span data-stu-id="0a203-128">Antivirus software interferes with configuration and causes configuration failures</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0a203-129">问题</span><span class="sxs-lookup"><span data-stu-id="0a203-129">Problem</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0a203-130">当防病毒软件未正确确定配置程序是病毒，配置将失败。</span><span class="sxs-lookup"><span data-stu-id="0a203-130"> configuration fails when antivirus software incorrectly determines that the configuration program is a virus.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0a203-131">原因</span><span class="sxs-lookup"><span data-stu-id="0a203-131">Cause</span></span>  
 <span data-ttu-id="0a203-132">防病毒软件尚未更新，因此未将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置程序作为合法（非病毒）程序加入到其中。</span><span class="sxs-lookup"><span data-stu-id="0a203-132">The antivirus software has not been updated to include the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program as a legitimate (non-virus) program.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0a203-133">解决方法</span><span class="sxs-lookup"><span data-stu-id="0a203-133">Resolution</span></span>  
 <span data-ttu-id="0a203-134">配置防病毒程序识别[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序为合法的 （非病毒） 程序，否则暂时禁用防病毒软件配置程序运行时。</span><span class="sxs-lookup"><span data-stu-id="0a203-134">Configure the antivirus program to recognize the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program as a legitimate (non-virus) program or else temporarily disable the antivirus software while the configuration program is running.</span></span>  
  
#### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a><span data-ttu-id="0a203-135">配置失败，并出现错误“找不到文件或程序集名称 FileName.dll，或找不到它的一个依赖项”</span><span class="sxs-lookup"><span data-stu-id="0a203-135">Configuration fails with a "File or assembly name FileName.dll, or one of its dependencies, was not found" error</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0a203-136">问题</span><span class="sxs-lookup"><span data-stu-id="0a203-136">Problem</span></span>  
 <span data-ttu-id="0a203-137">在配置过程中显示如下错误：</span><span class="sxs-lookup"><span data-stu-id="0a203-137">An error similar to the following is displayed during the configuration process:</span></span>  
  
 <span data-ttu-id="0a203-138">无法部署 BizTalk 系统程序集“C:\Program Files\Microsoft\\</span><span class="sxs-lookup"><span data-stu-id="0a203-138">Failed to deploy BizTalk system assembly "C:\Program Files\Microsoft\\</span></span>  
  
 <span data-ttu-id="0a203-139">BizTalk Server 2009\Microsoft.BizTalk.DefaultPipelines.dll。</span><span class="sxs-lookup"><span data-stu-id="0a203-139">BizTalk Server 2009\Microsoft.BizTalk.DefaultPipelines.dll.</span></span> <span data-ttu-id="0a203-140">“未指定”</span><span class="sxs-lookup"><span data-stu-id="0a203-140">Unspecified</span></span>  
  
 <span data-ttu-id="0a203-141">异常： 文件或程序集名称 FileName.dll，或它的一个其</span><span class="sxs-lookup"><span data-stu-id="0a203-141">exception: File or assembly name FileName .dll, or one of its</span></span>  
  
 <span data-ttu-id="0a203-142">或其依存关系之一。</span><span class="sxs-lookup"><span data-stu-id="0a203-142">dependencies, was not found.</span></span> <span data-ttu-id="0a203-143">找不到文件或程序集名称 FileName .dll</span><span class="sxs-lookup"><span data-stu-id="0a203-143">File or assembly name FileName .dll, or</span></span>  
  
 <span data-ttu-id="0a203-144">其依存关系之一。”</span><span class="sxs-lookup"><span data-stu-id="0a203-144">one of its dependencies, was not found."</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0a203-145">原因</span><span class="sxs-lookup"><span data-stu-id="0a203-145">Cause</span></span>  
 <span data-ttu-id="0a203-146">如果网络服务帐户是否没有写入权限运行的计算机上的临时文件夹，会出现此错误[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0a203-146">This error can occur if the Network Service account does not have write permissions to the temp folder on the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0a203-147">在配置过程中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置使用 Windows 管理规范 (WMI) 将 .NET 程序集部署到 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="0a203-147">During configuration, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration uses Windows Management Instrumentation (WMI) to deploy .NET assemblies to the BizTalk Management database.</span></span> <span data-ttu-id="0a203-148">在将这些程序集部署到 BizTalk 管理数据库时，WMI 模拟网络服务帐户，因此，网络服务帐户必须对运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上的临时文件夹具有写权限。</span><span class="sxs-lookup"><span data-stu-id="0a203-148">WMI impersonates the Network Service account while deploying these assemblies to the BizTalk Management database and so the Network Service account must have write access to the temp folder on the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0a203-149">解决方法</span><span class="sxs-lookup"><span data-stu-id="0a203-149">Resolution</span></span>  
 <span data-ttu-id="0a203-150">向网络服务帐户授予对运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上的临时文件夹的写权限，并再次运行配置程序。</span><span class="sxs-lookup"><span data-stu-id="0a203-150">Grant the Network Service account write access to the temp folder on the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and run the configuration program again.</span></span> <span data-ttu-id="0a203-151">若要确定由 TEMP 环境变量指定的文件夹，打开命令提示符的计算机上，键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="0a203-151">To determine the folder that is specified by the TEMP environment variable, open a command prompt on the computer, type the following command, and then press ENTER:</span></span>  
  
```  
echo %TEMP%  
```  
  
#### <a name="configuration-of-the-group-fails-if-the-netbios-name-of-the-computer-running-sql-server-exceeds-15-characters"></a><span data-ttu-id="0a203-152">如果运行 SQL Server 的计算机的 NetBIOS 名称超过 15 个字符，则组的配置失败</span><span class="sxs-lookup"><span data-stu-id="0a203-152">Configuration of the group fails if the NetBIOS name of the computer running SQL Server exceeds 15 characters</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0a203-153">问题</span><span class="sxs-lookup"><span data-stu-id="0a203-153">Problem</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0a203-154">组配置将失败并出现类似于以下的错误显示在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置日志：</span><span class="sxs-lookup"><span data-stu-id="0a203-154"> group configuration fails and an error similar to the following is displayed in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration log:</span></span>  
  
 <span data-ttu-id="0a203-155">2006-08-29 23:54:00:0902 [警告] AdminLib GetBTSMessage: hrErr = 80070547;</span><span class="sxs-lookup"><span data-stu-id="0a203-155">2006-08-29 23:54:00:0902 [WARN] AdminLib GetBTSMessage: hrErr=80070547;</span></span>  
  
 <span data-ttu-id="0a203-156">Msg=Configuration information could not be read from the domain</span><span class="sxs-lookup"><span data-stu-id="0a203-156">Msg=Configuration information could not be read from the domain</span></span>  
  
 <span data-ttu-id="0a203-157">controller, either because the machine is unavailable, or access has</span><span class="sxs-lookup"><span data-stu-id="0a203-157">controller, either because the machine is unavailable, or access has</span></span>  
  
 <span data-ttu-id="0a203-158">been denied.;</span><span class="sxs-lookup"><span data-stu-id="0a203-158">been denied.;</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0a203-159">原因</span><span class="sxs-lookup"><span data-stu-id="0a203-159">Cause</span></span>  
 <span data-ttu-id="0a203-160">如果运行的计算机名称的 NetBIOS 的长度，则会发生此问题[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]超过 15 个字符。</span><span class="sxs-lookup"><span data-stu-id="0a203-160">This problem occurs if the length of the NetBIOS name for the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] exceeds 15 characters.</span></span> <span data-ttu-id="0a203-161">如果 NetBIOS 名称超过 15 个字符，则 Windows 将该 NetBIOS 名称截断至 15 个字符，NetBIOS 名称将不再与此计算机的完全限定域名 (FQDN) 或 DNS 名称的第一部分相符。</span><span class="sxs-lookup"><span data-stu-id="0a203-161">If the NetBIOS name exceeds 15 characters then Windows truncates the NetBIOS name to 15 characters and the NetBIOS name will no longer match the first part of the fully qualified domain name (FQDN) or DNS name of this computer.</span></span> <span data-ttu-id="0a203-162">如果 NetBIOS 名称与计算机的 FQDN 的第一部分不符，组配置将失败。</span><span class="sxs-lookup"><span data-stu-id="0a203-162">If the NetBIOS name does not match the first part of the FQDN of the computer, group configuration will fail.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0a203-163">解决方法</span><span class="sxs-lookup"><span data-stu-id="0a203-163">Resolution</span></span>  
 <span data-ttu-id="0a203-164">更改运行的计算机的 NetBIOS 名称[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]到具有不超过 15 个字符并再次运行的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="0a203-164">Change the NetBIOS name of the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] to a name with no more than 15 characters and run configuration again.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a203-165">如果对其重命名，则必须重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="0a203-165">You must restart the computer if you rename it.</span></span>  
  
#### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a><span data-ttu-id="0a203-166">如果 SQL Server 数据文件夹中已经存在与指定的数据库同名的 SQL Server 数据库文件，则配置将失败</span><span class="sxs-lookup"><span data-stu-id="0a203-166">Configuration fails if a SQL Server database file that has the same name as the specified database already exists in the SQL Server data folder</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0a203-167">问题</span><span class="sxs-lookup"><span data-stu-id="0a203-167">Problem</span></span>  
 <span data-ttu-id="0a203-168">配置失败，并出现如下错误：</span><span class="sxs-lookup"><span data-stu-id="0a203-168">Configuration fails with an error similar to the following:</span></span>  
  
 <span data-ttu-id="0a203-169">无法设置 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="0a203-169">Failed to set up BAM database(s)</span></span>  
  
 <span data-ttu-id="0a203-170">无法打开在登录“BAMPrimaryImport”中请求的数据库</span><span class="sxs-lookup"><span data-stu-id="0a203-170">Cannot open database requested in login 'BAMPrimaryImport'</span></span>  
  
 <span data-ttu-id="0a203-171">登录失败。</span><span class="sxs-lookup"><span data-stu-id="0a203-171">Logon fails.</span></span> <span data-ttu-id="0a203-172">用户登录失败*BizTalk\BizTalkUser*</span><span class="sxs-lookup"><span data-stu-id="0a203-172">Logon failed for user '*BizTalk\BizTalkUser*'</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0a203-173">原因</span><span class="sxs-lookup"><span data-stu-id="0a203-173">Cause</span></span>  
 <span data-ttu-id="0a203-174">如果在运行 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的计算机的 \MSSQL\data 文件夹中已经存在 .mdf 文件或 .ldf 文件，而它们与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置程序正在尝试创建的 .mdf 文件或 .ldf 文件同名，则可能出现此错误。</span><span class="sxs-lookup"><span data-stu-id="0a203-174">This error can occur if an .mdf file or an .ldf file already exists in the \MSSQL\data folder of the computer running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] that has the same name as the .mdf file or the .ldf file that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program is trying to create.</span></span> <span data-ttu-id="0a203-175">为数据库创建的 .mdf 文件和 .ldf 文件的名称派生自在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置程序中指定的数据库的名称（附加 .mdf 和 .ldf 扩展名）。</span><span class="sxs-lookup"><span data-stu-id="0a203-175">The names of the .mdf file and the .ldf file that are created for the databases are derived from the name of the database that is specified in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program with an .mdf and an .ldf extension appended.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0a203-176">解决方法</span><span class="sxs-lookup"><span data-stu-id="0a203-176">Resolution</span></span>  
 <span data-ttu-id="0a203-177">若要解决此行为的问题，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="0a203-177">To resolve this behavior, use one of the following methods:</span></span>  
  
-   <span data-ttu-id="0a203-178">删除其名称与您要创建的任何数据库的名称匹配的任何 .mdf 文件或 .ldf 文件。</span><span class="sxs-lookup"><span data-stu-id="0a203-178">Delete any .mdf files or .ldf files that have names that match the names of any databases that you are creating.</span></span>  
  
-   <span data-ttu-id="0a203-179">选择数据库名称时，确保其与 SQL Server 的 \Program Files\Microsoft SQL Server\MSSQL\data 文件夹中已经存在的任何 .mdf 文件或 .ldf 文件的名称都不匹配。</span><span class="sxs-lookup"><span data-stu-id="0a203-179">Choose database names that do not match the names of any .mdf files or .ldf files that already exist in the \Program Files\Microsoft SQL Server\MSSQL\data folder of your SQL server.</span></span>  
  
#### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a><span data-ttu-id="0a203-180">当指定本地帐户时，域控制器上的配置失败</span><span class="sxs-lookup"><span data-stu-id="0a203-180">Configuration fails on a domain controller when specifying local accounts</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0a203-181">问题</span><span class="sxs-lookup"><span data-stu-id="0a203-181">Problem</span></span>  
 <span data-ttu-id="0a203-182">运行时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置程序在域控制器上，如果你为 BizTalkServerApplication 主机或 BizTalkIsolatedHost 主机指定的本地组 （例如，BizTalk 主机用户组） 的配置将失败。</span><span class="sxs-lookup"><span data-stu-id="0a203-182">When running the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] configuration program on a domain controller, configuration fails if you specified a local group (for example, BizTalk Host Users Group) for either the BizTalkServerApplication host or the BizTalkIsolatedHost host.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0a203-183">原因</span><span class="sxs-lookup"><span data-stu-id="0a203-183">Cause</span></span>  
 <span data-ttu-id="0a203-184">域控制器自动将本地 Windows 组视为域 Windows 组（在域控制器上不存在本地 Windows 组）。</span><span class="sxs-lookup"><span data-stu-id="0a203-184">A domain controller automatically treats a local Windows group as a domain Windows group (there is no such thing as local Windows group on a domain controller).</span></span> <span data-ttu-id="0a203-185">如果在运行配置程序时为主机指定了本地 Windows 组，当您尝试为此组创建 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 登录时，配置将失败。</span><span class="sxs-lookup"><span data-stu-id="0a203-185">If you specified a local Windows group for the host while running the configuration program, configuration will fail when trying to create a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] logon for the group.</span></span> <span data-ttu-id="0a203-186">当服务器是域控制器时，配置程序不禁用本地 Windows 组选项。</span><span class="sxs-lookup"><span data-stu-id="0a203-186">The configuration program does not disable the local Windows group option when the server is a domain controller.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0a203-187">解决方法</span><span class="sxs-lookup"><span data-stu-id="0a203-187">Resolution</span></span>  
 <span data-ttu-id="0a203-188">为在配置过程中创建的主机指定域组。</span><span class="sxs-lookup"><span data-stu-id="0a203-188">Specify domain groups for the hosts that are created during configuration.</span></span>  
  
#### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a><span data-ttu-id="0a203-189">如果尚未重命名 SQL Server，配置将无法创建 SQL Server 分析数据库</span><span class="sxs-lookup"><span data-stu-id="0a203-189">Configuration fails to create SQL Server Analysis database if the SQL server has been renamed</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0a203-190">问题</span><span class="sxs-lookup"><span data-stu-id="0a203-190">Problem</span></span>  
 <span data-ttu-id="0a203-191">如果您已经对安装了 SQL Server 分析服务器的计算机进行了重命名，当配置程序尝试新建 SQL Server 分析数据库时将失败，并且生成如下错误：</span><span class="sxs-lookup"><span data-stu-id="0a203-191">If you have renamed the computer on which you installed SQL Server Analysis Server, the configuration program fails when it tries to create the new SQL Server Analysis database and an error similar to the following is generated:</span></span>  
  
 <span data-ttu-id="0a203-192">无法连接到存储库。</span><span class="sxs-lookup"><span data-stu-id="0a203-192">Cannot connect to the repository.</span></span>  
  
 <span data-ttu-id="0a203-193">分析服务器：\<计算机名称\></span><span class="sxs-lookup"><span data-stu-id="0a203-193">Analysis server: \<machine name\></span></span>  
  
 <span data-ttu-id="0a203-194">Error:</span><span class="sxs-lookup"><span data-stu-id="0a203-194">Error:</span></span>  
  
 <span data-ttu-id="0a203-195">\\\\< 计算机名称\>\MsOLAPRepository$\msmdrep.mdb 不是有效的路径。</span><span class="sxs-lookup"><span data-stu-id="0a203-195">'\\\\<machine name\>\MsOLAPRepository$\msmdrep.mdb' is not a valid path.</span></span>  
  
 <span data-ttu-id="0a203-196">请确保正确拼写路径名称，并且已</span><span class="sxs-lookup"><span data-stu-id="0a203-196">Make sure that you correctly spell the path name and that you are</span></span>  
  
 <span data-ttu-id="0a203-197">并且您已连接到该文件所驻留的服务器。</span><span class="sxs-lookup"><span data-stu-id="0a203-197">connected to the server on which the file resides.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0a203-198">原因</span><span class="sxs-lookup"><span data-stu-id="0a203-198">Cause</span></span>  
 <span data-ttu-id="0a203-199">配置程序无法确定您安装了 SQL Server 分析服务器的计算机的新名称。</span><span class="sxs-lookup"><span data-stu-id="0a203-199">The configuration program is unable to determine the new name of the computer on which you installed SQL Server Analysis Server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0a203-200">解决方法</span><span class="sxs-lookup"><span data-stu-id="0a203-200">Resolution</span></span>  
 <span data-ttu-id="0a203-201">手动执行下列操作，以便用新的计算机名更新分析服务器：</span><span class="sxs-lookup"><span data-stu-id="0a203-201">Perform the following manual steps to update Analysis Server with the new computer name:</span></span>  
  
1.  <span data-ttu-id="0a203-202">单击**启动**，指向**所有程序**，指向**Microsoft SQL Server**，指向**Analysis Services**，然后单击**Analysis Manager**。</span><span class="sxs-lookup"><span data-stu-id="0a203-202">Click **Start**, point to **All Programs**, point to **Microsoft SQL Server**, point to **Analysis Services**, and then click **Analysis Manager**.</span></span>  
  
2.  <span data-ttu-id="0a203-203">在**Analysis Manager**导航面板中，双击**分析服务器**节点以将其展开。</span><span class="sxs-lookup"><span data-stu-id="0a203-203">In the **Analysis Manager** navigation panel, double-click the **Analysis Servers** node to expand it.</span></span>  
  
3.  <span data-ttu-id="0a203-204">右键单击你想要编辑，，然后选择的存储库连接字符串服务器**编辑储存库连接字符串**。</span><span class="sxs-lookup"><span data-stu-id="0a203-204">Right-click the server with the repository connection string you want to edit, and then select **Edit Repository Connection String**.</span></span>  
  
4.  <span data-ttu-id="0a203-205">在**编辑储存库连接字符串**对话框中，验证此字符串中的服务器名称，为新的计算机名称进行更新，如果不正确。</span><span class="sxs-lookup"><span data-stu-id="0a203-205">In the **Edit Repository Connection String** dialog box, verify the server name in this string and update it to the new computer name if it is incorrect.</span></span>  
  
5.  <span data-ttu-id="0a203-206">导航到以下位置： \<*安装目录*\>files\microsoft Analysis Services\Bin。</span><span class="sxs-lookup"><span data-stu-id="0a203-206">Navigate to the following location: \<*installation directory*\>\Program Files\Microsoft Analysis Services\Bin.</span></span>  
  
6.  <span data-ttu-id="0a203-207">右键单击**Bin**文件夹，，然后单击**共享和安全**。</span><span class="sxs-lookup"><span data-stu-id="0a203-207">Right-click the **Bin** folder, and then click **Sharing and Security**.</span></span> <span data-ttu-id="0a203-208">**Bin 属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="0a203-208">The **Bin Properties** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="0a203-209">在**Bin 属性**对话框中，单击**共享**选项卡以验证所有联机分析处理 (OLAP) 管理员具有对此文件夹的完全权限。</span><span class="sxs-lookup"><span data-stu-id="0a203-209">In the **Bin Properties** dialog box, click the **Sharing** tab to verify that all Online Analytical Processing (OLAP) administrators have full permissions to this folder.</span></span>  
  
#### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a><span data-ttu-id="0a203-210">当从 Visual Studio 中重新部署程序集时，项目从配置数据库中消失</span><span class="sxs-lookup"><span data-stu-id="0a203-210">Artifacts Disappear from Configuration Database on Redeployment of Assemblies from Visual Studio</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0a203-211">问题</span><span class="sxs-lookup"><span data-stu-id="0a203-211">Problem</span></span>  
 <span data-ttu-id="0a203-212">当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在项目级别内重新部署项目后[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，项目中包含的所有引用正在重新部署该项目项看起来消失时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]刷新 MMC。</span><span class="sxs-lookup"><span data-stu-id="0a203-212">When a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] project is redeployed at the project level within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], all artifacts contained within the project that reference the project being redeployed will appear to vanish when the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MMC is refreshed.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0a203-213">原因</span><span class="sxs-lookup"><span data-stu-id="0a203-213">Cause</span></span>  
 <span data-ttu-id="0a203-214">为了说明此问题的原因，请看以下示例，此示例基于一个示例 BizTalk Server 解决方案，用户要在此解决方案中重新部署 Maps 项目。</span><span class="sxs-lookup"><span data-stu-id="0a203-214">To illustrate the cause of this problem, consider the following example based on a sample BizTalk Server solution where a user wants to redeploy the Maps project.</span></span> <span data-ttu-id="0a203-215">请注意，对项目进行编译将生成单独的程序集。</span><span class="sxs-lookup"><span data-stu-id="0a203-215">Note that compiling projects yields individual assemblies.</span></span> <span data-ttu-id="0a203-216">下图表示用户在进行重新部署之前，此解决方案的状态。</span><span class="sxs-lookup"><span data-stu-id="0a203-216">The following figure indicates the state of the solution before the user does a redeployment.</span></span> <span data-ttu-id="0a203-217">项目之间的关系如下所示：</span><span class="sxs-lookup"><span data-stu-id="0a203-217">The relationships among the artifacts are as follows:</span></span>  
  
-   <span data-ttu-id="0a203-218">Orch1、Orch2、Maps、Pipelines 和 Schemas 为项目。</span><span class="sxs-lookup"><span data-stu-id="0a203-218">Orch1, Orch2, Maps, Pipelines, and Schemas are projects.</span></span>  
  
-   <span data-ttu-id="0a203-219">Orch1 引用 Maps，而 Maps 引用 Schemas。</span><span class="sxs-lookup"><span data-stu-id="0a203-219">Orch1 references Maps, which in turn references Schemas.</span></span>  
  
-   <span data-ttu-id="0a203-220">Orch2 引用 Schemas。</span><span class="sxs-lookup"><span data-stu-id="0a203-220">Orch2 references Schemas.</span></span>  
  
-   <span data-ttu-id="0a203-221">Pipelines 引用 Schemas。</span><span class="sxs-lookup"><span data-stu-id="0a203-221">Pipelines references Schemas.</span></span>  
  
 <span data-ttu-id="0a203-222">![](../core/media/bcd-existingbiztalkserversolutionc.gif "bcd_ExistingBizTalkServerSolutionc")</span><span class="sxs-lookup"><span data-stu-id="0a203-222">![](../core/media/bcd-existingbiztalkserversolutionc.gif "bcd_ExistingBizTalkServerSolutionc")</span></span>  
  
 <span data-ttu-id="0a203-223">如果用户使用默认的 Visual Studio 项目设置重新部署 Maps 项目，则 Orch1、Orch2 和 Pipeline 项目将消失，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="0a203-223">If the user redeploys the Maps project using the default Visual Studio project settings, the Orch1, Orch2, and Pipeline artifacts vanish, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="0a203-224">![](../core/media/bcd-biztalksolutionwlostartifactsc.gif "bcd_BizTalkSolutionWLostArtifactsc")</span><span class="sxs-lookup"><span data-stu-id="0a203-224">![](../core/media/bcd-biztalksolutionwlostartifactsc.gif "bcd_BizTalkSolutionWLostArtifactsc")</span></span>  
  
 <span data-ttu-id="0a203-225">重新部署 Maps 的过程分为两步，首先取消部署当前已部署的 Maps.dll 程序集，然后部署新的 Maps.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="0a203-225">Redeploying Maps is a two-step process of undeploying the currently deployed Maps.dll assembly, and then deploying the new Maps.dll file.</span></span> <span data-ttu-id="0a203-226">Visual Studio 会重新部署过程的一部分自动执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="0a203-226">Visual Studio performs these steps automatically as part of the redeployment process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a203-227">严格来说，上面的描述并不正确，因为这些是 Visual Studio 一直执行的步骤，因此并没有考虑其方式是否适当。</span><span class="sxs-lookup"><span data-stu-id="0a203-227">The preceding sentence is not strictly correct because these are steps that Visual Studio always does so there is no notion of it being the proper way.</span></span>  
  
 <span data-ttu-id="0a203-228">关键在于，为了取消部署 BizTalk Server 程序集，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 必须取消部署依赖于这一已设置部署标志的程序集的所有程序集。</span><span class="sxs-lookup"><span data-stu-id="0a203-228">The key point is that in order to undeploy a BizTalk Server assembly, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] has to undeploy all assemblies that are dependent upon that assembly that have the deploy flag set.</span></span> <span data-ttu-id="0a203-229">在本例中，要执行重新部署过程的第一个取消部署步骤，BizTalk Server 需要取消部署 Orch1.dll（而它依赖于 Maps.dll）。</span><span class="sxs-lookup"><span data-stu-id="0a203-229">In our example, to perform the first undeployment step of the redeployment, BizTalk Server needs to undeploy Orch1.dll (which depends on Maps.dll).</span></span> <span data-ttu-id="0a203-230">在取消部署 Maps.dll 的过程中，[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 还将取消部署 Schemas.dll（假定它已设置部署标志）。</span><span class="sxs-lookup"><span data-stu-id="0a203-230">During the undeployment of Maps.dll, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] also undeploys Schemas.dll (assuming it has the deploy flag set).</span></span> <span data-ttu-id="0a203-231">为了取消部署 Schemas.dll，Visual Studio 需要取消部署 Orch2.dll 和 Pipelines.dll（这两者都依赖于 Schemas.dll）。</span><span class="sxs-lookup"><span data-stu-id="0a203-231">In order to undeploy Schemas.dll, Visual Studio needs to undeploy Orch2.dll and Pipelines.dll (both of which depend on Schemas.dll).</span></span>  
  
 <span data-ttu-id="0a203-232">问题在于存在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]将重新部署仅 Maps.dll 和它取决于程序集： 在此情况下，Schemas.dll。</span><span class="sxs-lookup"><span data-stu-id="0a203-232">A problem exists in that [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] redeploys only Maps.dll and the assemblies that it depends upon: in this case, Schemas.dll.</span></span> <span data-ttu-id="0a203-233">因此，当用户刷新 BizTalk Server MMC，Orch1、 Orch2，和管道程序集似乎已消失，但 Maps.dll 和 Schemas.dll 仍将可见。</span><span class="sxs-lookup"><span data-stu-id="0a203-233">So when the user refreshes the BizTalk Server MMC, the Orch1, Orch2, and Pipeline assemblies seem to have vanished, but Maps.dll and Schemas.dll are still visible.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0a203-234">解决方法</span><span class="sxs-lookup"><span data-stu-id="0a203-234">Resolution</span></span>  
 <span data-ttu-id="0a203-235">主要项目 （引用其他项目） 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0a203-235">For the main project (that references other projects) do the following:</span></span>  
  
1.  <span data-ttu-id="0a203-236">在解决方案资源管理器中，右键单击解决方案节点。</span><span class="sxs-lookup"><span data-stu-id="0a203-236">In Solution Explorer, right-click the solution node.</span></span>  
  
2.  <span data-ttu-id="0a203-237">单击**属性**以打开**解决方案属性页**对话框。</span><span class="sxs-lookup"><span data-stu-id="0a203-237">Click **Properties** to open the **Solution Property Pages** dialog box.</span></span>  
  
3.  <span data-ttu-id="0a203-238">单击**配置属性**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="0a203-238">Click **Configuration Properties**, and then click **Configuration**.</span></span>  
  
4.  <span data-ttu-id="0a203-239">清除**部署**引用的项目的复选框。</span><span class="sxs-lookup"><span data-stu-id="0a203-239">Clear the **Deploy** check box for the referenced project.</span></span>  
  
5.  <span data-ttu-id="0a203-240">在解决方案资源管理器中，执行新的解决方案级别部署。</span><span class="sxs-lookup"><span data-stu-id="0a203-240">In Solution Explorer, execute a new solution-level deployment.</span></span> <span data-ttu-id="0a203-241">若要执行此操作，右键单击解决方案节点，然后单击**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="0a203-241">To do this, right-click the solution node and then click **Deploy Solution**.</span></span>  
  
#### <a name="supported-virtual-directory-types"></a><span data-ttu-id="0a203-242">支持的虚拟目录类型</span><span class="sxs-lookup"><span data-stu-id="0a203-242">Supported Virtual Directory Types</span></span>  
 <span data-ttu-id="0a203-243">仅当关联的虚拟目录的类型，在导出操作时从业务流程和尝试的操作的 MSI 导出中引用 Web 服务，将会成功**IIsWebVirtualDir**或**IIsWebDirectory**.</span><span class="sxs-lookup"><span data-stu-id="0a203-243">When referencing Web services from an orchestration and attempting to do an MSI export, the export operation will succeed only if the associated virtual directories are of type **IIsWebVirtualDir** or **IIsWebDirectory**.</span></span> <span data-ttu-id="0a203-244">**IIsWebVirtualDir**和**IIsWebDirectory**是显示在 IIS 元数据库中的节点类型。</span><span class="sxs-lookup"><span data-stu-id="0a203-244">**IIsWebVirtualDir** and **IIsWebDirectory** are the node types that appear in the IIS metabase.</span></span> <span data-ttu-id="0a203-245">**IIsWebVirtualDir**是使用的虚拟目录**路径**指向绝对文件文件夹的属性。</span><span class="sxs-lookup"><span data-stu-id="0a203-245">**IIsWebVirtualDir** is a virtual directory with a **Path** property that points to an absolute file folder.</span></span> <span data-ttu-id="0a203-246">**IIsWebDirectory**而不是虚拟目录**路径**属性，并因此将路由到相对文件文件夹，通常的另一个子文件夹**IIsWebVirtualDir**或**IIsWebDirectory**节点。</span><span class="sxs-lookup"><span data-stu-id="0a203-246">**IIsWebDirectory** is a virtual directory without a **Path** property and thus refers to a relative file folder, typically a subfolder of another **IIsWebVirtualDir** or **IIsWebDirectory** node.</span></span> <span data-ttu-id="0a203-247">这两种类型是元数据库层次中用于描述文件夹的常见类型。</span><span class="sxs-lookup"><span data-stu-id="0a203-247">These two types are the ones typically seen in the metabase hierarchy to describe folders.</span></span>  
  
 <span data-ttu-id="0a203-248">类型的虚拟目录**IIsConfigObject**不支持和 MSI 导出将会在这种情况下失败。</span><span class="sxs-lookup"><span data-stu-id="0a203-248">Virtual directories of type **IIsConfigObject** are not supported and the MSI export will fail in this case.</span></span> <span data-ttu-id="0a203-249">**IIsConfigObject**意外元数据库节点类型，是一个有效的节点类型不正确处理 BizTalk Server 或不正确创建 （并因此无效） 元数据库条目的相对值。</span><span class="sxs-lookup"><span data-stu-id="0a203-249">**IIsConfigObject** is an unexpected metabase node type that is either a valid node type that BizTalk Server is not handling properly or an indication of an improperly created (and thus invalid) metabase entry.</span></span> <span data-ttu-id="0a203-250">在此情况下，BizTalk 服务器会显示一条错误消息类似于以下内容： 类型为 IIsConfigObject 意外的目录项"IIS://LM/W3SVC/1/ROOT/BadVdir/"。</span><span class="sxs-lookup"><span data-stu-id="0a203-250">In this situation BizTalk Server will display an error message something like the following: Unexpected directory entry " IIS://LM/W3SVC/1/ROOT/BadVdir/" of type IIsConfigObject.</span></span>  
  
#### <a name="unable-to-view-group-information-after-removing-stale-logons"></a><span data-ttu-id="0a203-251">删除过时登录后无法查看组信息</span><span class="sxs-lookup"><span data-stu-id="0a203-251">Unable to view Group information after removing stale logons</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="0a203-252">问题</span><span class="sxs-lookup"><span data-stu-id="0a203-252">Problem</span></span>  
 <span data-ttu-id="0a203-253">如果在配置过程中遇到过时登录并删除它们，您可能无法查看组信息。</span><span class="sxs-lookup"><span data-stu-id="0a203-253">If, during configuration, you encounter and delete stale logons, you may not be able to view Group information.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="0a203-254">原因</span><span class="sxs-lookup"><span data-stu-id="0a203-254">Cause</span></span>  
 <span data-ttu-id="0a203-255">这是一个已知的配置问题。</span><span class="sxs-lookup"><span data-stu-id="0a203-255">This is a known configuration issue.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="0a203-256">解决方法</span><span class="sxs-lookup"><span data-stu-id="0a203-256">Resolution</span></span>  
 <span data-ttu-id="0a203-257">删除主机 Windows 组登录，然后重新配置，这种方法可能奏效。</span><span class="sxs-lookup"><span data-stu-id="0a203-257">It may help to delete the Host Windows group logons and then reconfigure.</span></span> <span data-ttu-id="0a203-258">如果组信息仍然不可用，请联系 Microsoft 产品支持人员。</span><span class="sxs-lookup"><span data-stu-id="0a203-258">If the Group information is still not available, contact Microsoft Product Support.</span></span>  
  
##### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a><span data-ttu-id="0a203-259">安装 BizTalk Server 后将无法更改计算机名称</span><span class="sxs-lookup"><span data-stu-id="0a203-259">Cannot change computer name after BizTalk Server is installed</span></span>  
  
###### <a name="problem"></a><span data-ttu-id="0a203-260">问题</span><span class="sxs-lookup"><span data-stu-id="0a203-260">Problem</span></span>  
 <span data-ttu-id="0a203-261">当您在运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机上更改计算机名称，并重新启动计算机时，可能会出现错误消息。</span><span class="sxs-lookup"><span data-stu-id="0a203-261">When you change the computer name on a computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and you restart (reboot) the computer, error messages may occur.</span></span>  
  
###### <a name="cause"></a><span data-ttu-id="0a203-262">原因</span><span class="sxs-lookup"><span data-stu-id="0a203-262">Cause</span></span>  
 <span data-ttu-id="0a203-263">SQL Server 不支持更改计算机名称，因此在安装和配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 不支持更改计算机名称。</span><span class="sxs-lookup"><span data-stu-id="0a203-263">SQL Server does not support changing the computer name, so [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] does not support changing the computer name once [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed and configured.</span></span>  
  
###### <a name="resolution"></a><span data-ttu-id="0a203-264">解决方法</span><span class="sxs-lookup"><span data-stu-id="0a203-264">Resolution</span></span>  
 <span data-ttu-id="0a203-265">我们建议您在安装 BizTalk Server 后不要更改计算机名称。</span><span class="sxs-lookup"><span data-stu-id="0a203-265">We recommend that you do not change computer names after you install BizTalk Server.</span></span>
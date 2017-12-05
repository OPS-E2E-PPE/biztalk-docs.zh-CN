---
title: "已知的安装问题 |Microsoft 文档"
description: "已知的问题和常见问题和解决方法时安装和配置 BizTalk Server"
ms.custom: 
ms.date: 11/30/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4d0e707-6b9e-49e1-9f17-19b3bac1229e
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90217a4e80df6f017b451dd7c40f6a1dfe3898ac
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="troubleshoot-biztalk-server-setup"></a><span data-ttu-id="bb6f8-103">BizTalk Server 安装程序疑难解答</span><span class="sxs-lookup"><span data-stu-id="bb6f8-103">Troubleshoot BizTalk Server Setup</span></span>

## <a name="introduction"></a><span data-ttu-id="bb6f8-104">简介</span><span class="sxs-lookup"><span data-stu-id="bb6f8-104">Introduction</span></span>  
 <span data-ttu-id="bb6f8-105">本疑难解答指南列出已知的问题，以及安装 BizTalk Server 时可能遇到的最常见问题。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-105">This Troubleshooting Guide lists  known issues as well as the most common problems you may encounter while installing BizTalk Server.</span></span> <span data-ttu-id="bb6f8-106">本指南还包括自定义操作，提供有关 Windows Server 徽标计划的 BizTalk Server 认证的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-106">This guide also includes Custom actions which provides details about BizTalk Server certification for the Windows Server logo program.</span></span>  <span data-ttu-id="bb6f8-107">它提供你的 BizTalk Server 安装程序操作过程中可能会执行的自定义操作的列表。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-107">It provides you a list of custom actions that might be performed during BizTalk Server Setup operation.</span></span>  
  
## <a name="review-install-steps"></a><span data-ttu-id="bb6f8-108">查看安装步骤</span><span class="sxs-lookup"><span data-stu-id="bb6f8-108">Review install steps</span></span>  
<span data-ttu-id="bb6f8-109">绝大部分 BizTalk Server 安装问题出现的原因为在安装 BizTalk Server 前未正确准备 BizTalk Server 计算机，或是在尝试新的安装前之前没有完全卸载以前的 BizTalk Server 安装。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-109">The majority of BizTalk Server setup problems occur because the BizTalk Server computer was not properly prepared before BizTalk Server was installed, or a previous installation of BizTalk Server was not fully uninstalled before a new installation was attempted.</span></span>  
  
<span data-ttu-id="bb6f8-110">查看两个检查表，下面，你还可以在 BizTalk Server 安装指南，以确保您的计算机正确配置以支持 BizTalk Server 中找到。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-110">Review the two checklists below, which you can also find in the BizTalk Server Installation Guides, to ensure that your computer(s) are properly configured to support BizTalk Server.</span></span> <span data-ttu-id="bb6f8-111">如果在检查该信息之后，您的安装仍然无法成功完成，本文档其他部分中的疑难解答提示可能会有所帮助。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-111">If, after reviewing this information, your setup still does not succeed, the troubleshooting tips in the rest of this document may be useful.</span></span>  
  
1. <span data-ttu-id="bb6f8-112">安装必备软件和程序：</span><span class="sxs-lookup"><span data-stu-id="bb6f8-112">Install prerequisite software and programs:</span></span>

    * [<span data-ttu-id="bb6f8-113">BizTalk Server 2016</span><span class="sxs-lookup"><span data-stu-id="bb6f8-113">BizTalk Server 2016</span></span>](set-up-and-install-prerequisites-for-biztalk-server-2016.md)
    * [<span data-ttu-id="bb6f8-114">BizTalk Server 2013 R2 和 2013</span><span class="sxs-lookup"><span data-stu-id="bb6f8-114">BizTalk Server 2013 R2 & 2013</span></span>](prepare-your-computer-for-installation.md)

2. <span data-ttu-id="bb6f8-115">安装和配置 BizTalk Server:</span><span class="sxs-lookup"><span data-stu-id="bb6f8-115">Install and configure BizTalk Server:</span></span>  

    1. <span data-ttu-id="bb6f8-116">安装 BizTalk Server: [BizTalk 2016](install-biztalk-server-2016.md) ， [BizTalk 2013 R2 / 2013年](install-biztalk-server-2013-and-2013-r2.md)</span><span class="sxs-lookup"><span data-stu-id="bb6f8-116">Install BizTalk Server: [BizTalk 2016](install-biztalk-server-2016.md) , [BizTalk 2013 R2 / 2013](install-biztalk-server-2013-and-2013-r2.md)</span></span>  
    2. <span data-ttu-id="bb6f8-117">[配置](configure-biztalk-server.md)BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="bb6f8-117">[Configure](configure-biztalk-server.md) BizTalk Server</span></span>
    3. [<span data-ttu-id="bb6f8-118">后配置步骤</span><span class="sxs-lookup"><span data-stu-id="bb6f8-118">Post-configuration steps</span></span>](post-configuration-steps-to-optimize-your-environment.md)
  
## <a name="some-edias2-artifacts-are-still-active-after-unconfiguring"></a><span data-ttu-id="bb6f8-119">某些 EDI/AS2 项目仍处于活动状态后未配置</span><span class="sxs-lookup"><span data-stu-id="bb6f8-119">Some EDI/AS2 artifacts are still active after unconfiguring</span></span>  
  
<span data-ttu-id="bb6f8-120">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-120">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-121">后取消配置 BizTalk Server 中，与 EDI 某些 BizTalk 服务器项目的 BizTalk EDI/AS2 功能和 AS2 处理将仍然处于活动状态的 BizTalk 组配置的上下文中。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-121">After you unconfigure the BizTalk EDI/AS2 feature of BizTalk Server, some BizTalk Server artifacts related to EDI and AS2 processing will still be active in the context of the BizTalk group configuration.</span></span> <span data-ttu-id="bb6f8-122">这些项目将包括 EDI 和 AS2 管道以及批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-122">These artifacts will include EDI and AS2 pipelines and the batching orchestration.</span></span> <span data-ttu-id="bb6f8-123">因此，即使在取消对 BizTalk EDI/AS2 功能的配置后，您仍然能够执行基本的 EDI 和 AS2 处理。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-123">As a result, you will still be able to perform basic EDI and AS2 processing even after unconfiguring the BizTalk EDI/AS2 feature.</span></span>  
  
<span data-ttu-id="bb6f8-124">**可能的原因** </span><span class="sxs-lookup"><span data-stu-id="bb6f8-124">**Cause** </span></span>  
 <span data-ttu-id="bb6f8-125">存在与 EDI 和 AS2 处理关联的活动端口。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-125">There are active ports associated with EDI and AS2 processing.</span></span> <span data-ttu-id="bb6f8-126">某些项目在这些端口保持活动时会继续工作。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-126">Some artifacts will continue to function while these ports remain active.</span></span>  
  
<span data-ttu-id="bb6f8-127">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-127">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-128">若要禁用所有 EDI/AS2 项目，应禁用、停止或删除与 EDI 和 AS2 处理关联的端口。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-128">To disable all EDI/AS2 artifacts, you should disable, stop, or delete the ports associated with EDI and AS2 processing.</span></span>  
  
## <a name="after-renaming-biztalk-or-sql-server-computer-the-configuration-wizard-fails"></a><span data-ttu-id="bb6f8-129">重命名后 BizTalk 或 SQL Server 的计算机，则配置向导将失败</span><span class="sxs-lookup"><span data-stu-id="bb6f8-129">After renaming BizTalk or SQL Server computer, the Configuration Wizard fails</span></span>  
  
<span data-ttu-id="bb6f8-130">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-130">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-131">此问题的表现方式有多种：</span><span class="sxs-lookup"><span data-stu-id="bb6f8-131">This problem may manifest itself in several ways:</span></span>  
  
-   <span data-ttu-id="bb6f8-132">配置管理器可以正确加载“概述”页，但是在尝试配置功能时，屏幕中不显示功能选项。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-132">The configuration manager will load the Overview page correctly, but when attempting to configure a feature, the feature options do not display on the screen.</span></span>  
  
-   <span data-ttu-id="bb6f8-133">配置向导无法连接到 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-133">The configuration wizard cannot connect to the SQL Server.</span></span>  
  
-   <span data-ttu-id="bb6f8-134">尝试使用“取消对所有功能的配置”时仅取消了对部分功能而不是所有功能的配置。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-134">Attempting to Unconfigure All unconfigures some features, but not all.</span></span>  
  
<span data-ttu-id="bb6f8-135">**可能的原因** </span><span class="sxs-lookup"><span data-stu-id="bb6f8-135">**Cause** </span></span>  
 <span data-ttu-id="bb6f8-136">BizTalk Server 配置存储了计算机的网络名称。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-136">The BizTalk Server configuration stores the computer network name.</span></span> <span data-ttu-id="bb6f8-137">在计算机重命名后，configuration manager 和配置向导找不到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-137">When the computer is renamed, the configuration manager and configuration wizard cannot locate the BizTalk Server.</span></span> <span data-ttu-id="bb6f8-138">如果在对 BizTalk Server 进行配置之后重命名了 SQL Server 计算机，将会出现类似的问题。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-138">A similar problem will occur if the SQL Server computer is renamed after BizTalk Server is configured.</span></span>  
  
<span data-ttu-id="bb6f8-139">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-139">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-140">请不要重命名 BizTalk Server 计算机或 SQL Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-140">Do not rename the BizTalk Server computer or the SQL Server computer.</span></span> <span data-ttu-id="bb6f8-141">如果必须对服务器进行重命名，请取消对所有 BizTalk 功能的配置，然后再重命名计算机。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-141">If a server must be renamed, unconfigure all BizTalk features before renaming the computer.</span></span> <span data-ttu-id="bb6f8-142">在重命名计算机后，请重新配置 BizTalk Server 功能。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-142">After renaming the computer, reconfigure BizTalk Server features.</span></span>  
  
## <a name="business-rules-configuration-wizard-fails"></a><span data-ttu-id="bb6f8-143">业务规则配置向导将失败</span><span class="sxs-lookup"><span data-stu-id="bb6f8-143">Business Rules Configuration Wizard fails</span></span>  
  
<span data-ttu-id="bb6f8-144">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-144">**Problem**</span></span>  
  
-   <span data-ttu-id="bb6f8-145">业务规则配置向导失败，并显示错误“某些组件的配置失败，这些组件未应用任何设置”。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-145">The Business Rules Configuration Wizard fails with the error “Configuration failed for some components and no settings were applied for those components.”</span></span>  
  
-   <span data-ttu-id="bb6f8-146">在已为其成功配置业务规则引擎的 BizTalk Server 计算机上，规则引擎更新服务启动失败并且不能手动启动。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-146">On BizTalk Server computers for which the Business Rules Engine has already been successfully configured, the Rules Engine Update service fails to start and cannot be started manually.</span></span>  
  
<span data-ttu-id="bb6f8-147">出现此问题时，可能会在 BizTalk Server 计算机的应用程序日志中生成与下面类似的错误：</span><span class="sxs-lookup"><span data-stu-id="bb6f8-147">When this problem occurs, an error similar to the following may be generated in the BizTalk Server computer Application log:</span></span>  
  
```  
Service could not be started. : System.Net.Sockets.SocketException (10061): No connection could be made because the target machine actively refused it ::1:3132  
  
```  
  
<span data-ttu-id="bb6f8-148">**可能的原因** </span><span class="sxs-lookup"><span data-stu-id="bb6f8-148">**Cause** </span></span>  
 <span data-ttu-id="bb6f8-149">Microsoft 恶意软件防护中心发布上 9，2010 年 3 月来解决从 SettingsModifier:Win32 可能威胁的更新的签名文件 / PossibleHostsFileHijack。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-149">The Microsoft Malware Protection Center released an updated signature file on March 9th, 2010 to address a possible threat from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="bb6f8-150">此更新的签名文件可能导致 Microsoft 恶意软件检测软件（例如 Windows Defender）更新本地 HOSTS 文件，以缓解来自 SettingsModifier:Win32/PossibleHostsFileHijack 的威胁。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-150">This updated signature file can cause Microsoft Malware Detection software such as Windows Defender to update the local HOSTS file to mitigate threats from SettingsModifier:Win32/PossibleHostsFileHijack.</span></span> <span data-ttu-id="bb6f8-151">由于这些更改，BizTalk Server 规则引擎更新服务可能启动失败。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-151">As a result of these changes, the BizTalk Server Rules Engine Update service may fail to start.</span></span>  
  
<span data-ttu-id="bb6f8-152">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-152">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-153">更新本地 HOSTS 文件以包括以下行：</span><span class="sxs-lookup"><span data-stu-id="bb6f8-153">Update the local HOSTS file to include the following line:</span></span>  
  
```  
127.0.0.1         localhost  
```  
  
 <span data-ttu-id="bb6f8-154">HOSTS 文件位于 %systemroot%\drivers\etc\ 目录中。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-154">The HOSTS file is located in the %systemroot%\drivers\etc\ directory.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb6f8-155">请参阅更新，以从的地址可能发生的威胁的 Microsoft 恶意软件防护中心签名[SettingsModifier:Win32 / PossibleHostsFileHijack](http://go.microsoft.com/fwlink/?LinkId=146221)。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-155">See the Microsoft Malware Protection Center signature update that addresses a possible threat from [SettingsModifier:Win32/PossibleHostsFileHijack](http://go.microsoft.com/fwlink/?LinkId=146221).</span></span>  
  
## <a name="configuration-logging"></a><span data-ttu-id="bb6f8-156">配置记录</span><span class="sxs-lookup"><span data-stu-id="bb6f8-156">Configuration Logging</span></span>  
 <span data-ttu-id="bb6f8-157">配置程序将写入配置日志文件位于默认情况下运行 BizTalk Server 的计算机的临时目录中的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-157">The configuration program writes detailed information to a configuration log file which by default is located in the temp directory of the computer running BizTalk Server.</span></span> <span data-ttu-id="bb6f8-158">若要确定由 TEMP 环境变量指定的文件夹，请在此计算机上打开命令提示符，键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="bb6f8-158">To determine the folder that is specified by the TEMP environment variable open a command prompt on this computer, type the following command, and then press ENTER:</span></span>  
  
 <span data-ttu-id="bb6f8-159">**echo %TEMP%**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-159">**echo %TEMP%**</span></span>  
  
 <span data-ttu-id="bb6f8-160">配置日志文件中包含所执行的配置步骤的摘要，以及在配置过程中可能发生的任何故障的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-160">The configuration log file contains a summary of the configuration steps performed, as well as diagnostic information about any failures that may occur during the configuration process.</span></span> <span data-ttu-id="bb6f8-161">如果出现配置错误，请在文本编辑器（如“记事本”）中打开配置日志，然后在日志中检查此错误的可能原因。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-161">If a configuration error occurs, open the configuration log in a text editor such as Notepad and check the log file for possible causes of the error.</span></span>  
  
## <a name="troubleshooting-tools"></a><span data-ttu-id="bb6f8-162">疑难解答工具</span><span class="sxs-lookup"><span data-stu-id="bb6f8-162">Troubleshooting Tools</span></span>  
 <span data-ttu-id="bb6f8-163">使用 SQL Server Profiler、Filemon 或 Regmon 收集有关配置失败的其他信息。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-163">Use SQL Server Profiler, Filemon, or Regmon to gather additional information about configuration failures.</span></span> <span data-ttu-id="bb6f8-164">请参阅[用于故障排除工具和实用程序](../core/tools-and-utilities-to-use-for-troubleshooting.md)。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-164">See [Tools and Utilities to use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md).</span></span>  
  
### <a name="configuration-fails-when-biztalk-and-sql-are-installed-on-separate-computers"></a><span data-ttu-id="bb6f8-165">单独的计算机上安装 BizTalk 和 SQL 时，配置将会失败</span><span class="sxs-lookup"><span data-stu-id="bb6f8-165">Configuration fails when BizTalk and SQL are installed on separate computers</span></span>  
  
<span data-ttu-id="bb6f8-166">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-166">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-167">当尝试配置 Enterprise 单一登录 (SSO) 组件时，配置失败并出现如下错误：</span><span class="sxs-lookup"><span data-stu-id="bb6f8-167">Configuration fails with errors similar to the following when attempting to configure the Enterprise Single Sign-On (SSO) component:</span></span>  
  
```
An error occurred while attempting to access the SSO database.  
Function: FieldInfoCreate  
```
  
 <span data-ttu-id="bb6f8-168">- 或 -</span><span class="sxs-lookup"><span data-stu-id="bb6f8-168">-or-</span></span>  
  
```Failed to enable the Single Sign-On (SSO) Service (error code 0X800706BA)```  
  
<span data-ttu-id="bb6f8-169">**可能的原因**  </span><span class="sxs-lookup"><span data-stu-id="bb6f8-169">**Cause**  </span></span>  
 <span data-ttu-id="bb6f8-170">如果在不同计算机上安装 BizTalk Server 和 SQL Server 的 Microsoft 分布式事务处理协调器 (MSDTC) 事务的上下文中执行的配置操作然后 MSDTC 功能必须可通过这些计算机之间的网络。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-170">If BizTalk Server and SQL Server are installed on different computers, then the configuration operations are performed under the context of a Microsoft Distributed Transaction Coordinator (MSDTC) transaction and MSDTC functionality must be available over the network between these computers.</span></span> <span data-ttu-id="bb6f8-171">如果通过运行 BizTalk Server 和 SQL Server 的计算机之间的网络 MSDTC 功能不可用，可能发生此错误。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-171">If MSDTC functionality is not available over the network between the computers running BizTalk Server and SQL Server, then this error can occur.</span></span>  
  
<span data-ttu-id="bb6f8-172">**解决方法**  </span><span class="sxs-lookup"><span data-stu-id="bb6f8-172">**Resolution**  </span></span>  
<span data-ttu-id="bb6f8-173">使用[问题疑难解答与 MSDTC](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues)确保 MSDTC 功能将通过运行 BizTalk Server 和 SQL Server 的计算机之间的网络。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-173">Use [Troubleshooting Problems with MSDTC](https://support.microsoft.com/help/306843/how-to-troubleshoot-ms-dtc-firewall-issues) to ensure MSDTC functionality over the network between the computers running BizTalk Server and SQL Server.</span></span>  
  
### <a name="antivirus-software-interferes-with-configuration-and-causes-configuration-failures"></a><span data-ttu-id="bb6f8-174">防病毒软件干扰配置并导致配置失败</span><span class="sxs-lookup"><span data-stu-id="bb6f8-174">Antivirus software interferes with configuration and causes configuration failures</span></span>  
  
<span data-ttu-id="bb6f8-175">**问题** </span><span class="sxs-lookup"><span data-stu-id="bb6f8-175">**Problem** </span></span>  
 <span data-ttu-id="bb6f8-176">当防病毒软件未正确确定配置程序是病毒，BizTalk Server 配置将失败。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-176">BizTalk Server configuration fails when antivirus software incorrectly determines that the configuration program is a virus.</span></span>  
  
<span data-ttu-id="bb6f8-177">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-177">**Cause**</span></span>  
 <span data-ttu-id="bb6f8-178">防病毒软件尚未更新为包括为合法的 （非病毒） 程序的 BizTalk Server 配置程序。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-178">The antivirus software has not been updated to include the BizTalk Server configuration program as a legitimate (non-virus) program.</span></span>  
  
<span data-ttu-id="bb6f8-179">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-179">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-180">配置防病毒程序来将 BizTalk Server 配置程序识别为合法的 （非病毒） 程序或者暂时禁用防病毒软件配置程序运行时。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-180">Configure the antivirus program to recognize the BizTalk Server configuration program as a legitimate (non-virus) program or else temporarily disable the antivirus software while the configuration program is running.</span></span>  
  
### <a name="configuration-fails-with-a-file-or-assembly-name-filenamedll-or-one-of-its-dependencies-was-not-found-error"></a><span data-ttu-id="bb6f8-181">配置失败，并出现错误“找不到文件或程序集名称 FileName.dll，或找不到它的一个依赖项”</span><span class="sxs-lookup"><span data-stu-id="bb6f8-181">Configuration fails with a "File or assembly name FileName.dll, or one of its dependencies, was not found" error</span></span>  
  
<span data-ttu-id="bb6f8-182">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-182">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-183">在配置过程中显示如下错误：</span><span class="sxs-lookup"><span data-stu-id="bb6f8-183">An error similar to the following is displayed during the configuration process:</span></span>  
  
 <span data-ttu-id="bb6f8-184">无法部署 BizTalk 系统程序集"C:\Program Files\Microsoft\BizTalk Server 20xx\Microsoft.BizTalk.DefaultPipelines.dll。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-184">Failed to deploy BizTalk system assembly "C:\Program Files\Microsoft\BizTalk Server 20xx\Microsoft.BizTalk.DefaultPipelines.dll.</span></span> <span data-ttu-id="bb6f8-185">未指定的异常： 未找到文件或程序集名称 FileName.dll，或其依赖项之一。"</span><span class="sxs-lookup"><span data-stu-id="bb6f8-185">Unspecified exception: File or assembly name FileName .dll, or one of its dependencies, was not found."</span></span>  
  
<span data-ttu-id="bb6f8-186">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-186">**Cause**</span></span>  
 <span data-ttu-id="bb6f8-187">如果网络服务帐户没有写入权限的临时文件夹运行 BizTalk Server 的计算机上，可能出现此错误。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-187">This error can occur if the Network Service account does not have write permissions to the temp folder on the computer running BizTalk Server.</span></span> <span data-ttu-id="bb6f8-188">在配置期间，BizTalk Server 配置使用 Windows Management Instrumentation (WMI) 将.NET 程序集部署到 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-188">During configuration, BizTalk Server configuration uses Windows Management Instrumentation (WMI) to deploy .NET assemblies to the BizTalk Management database.</span></span> <span data-ttu-id="bb6f8-189">WMI 将这些程序集部署到 BizTalk 管理数据库时模拟的网络服务帐户，因此网络服务帐户必须具有写入访问权限运行 BizTalk Server 的计算机上的临时文件夹。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-189">WMI impersonates the Network Service account while deploying these assemblies to the BizTalk Management database and so the Network Service account must have write access to the temp folder on the computer running BizTalk Server.</span></span>  
  
<span data-ttu-id="bb6f8-190">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-190">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-191">授予对运行 BizTalk Server 的计算机上的临时文件夹的网络服务帐户写入访问权限，然后重新运行配置程序。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-191">Grant the Network Service account write access to the temp folder on the computer running BizTalk Server and run the configuration program again.</span></span> <span data-ttu-id="bb6f8-192">若要确定由 TEMP 环境变量指定的文件夹，打开命令提示符的计算机上，键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="bb6f8-192">To determine the folder that is specified by the TEMP environment variable, open a command prompt on the computer, type the following command, and then press ENTER:</span></span>  
  
```  
echo %TEMP%  
```  
  
### <a name="configuration-fails-if-a-sql-server-database-file-that-has-the-same-name-as-the-specified-database-already-exists-in-the-sql-server-data-folder"></a><span data-ttu-id="bb6f8-193">如果 SQL Server 数据文件夹中已经存在与指定的数据库同名的 SQL Server 数据库文件，则配置将失败</span><span class="sxs-lookup"><span data-stu-id="bb6f8-193">Configuration fails if a SQL Server database file that has the same name as the specified database already exists in the SQL Server data folder</span></span>  
  
#### <a name="problem"></a><span data-ttu-id="bb6f8-194">问题</span><span class="sxs-lookup"><span data-stu-id="bb6f8-194">Problem</span></span>  
 <span data-ttu-id="bb6f8-195">配置失败，并出现如下错误：</span><span class="sxs-lookup"><span data-stu-id="bb6f8-195">Configuration fails with an error similar to the following:</span></span>  
  
```
Failed to set up BAM database(s)  
  
Cannot open database requested in login 'BAMPrimaryImport'  
  
Logon fails. Logon failed for user '*BizTalk\BizTalkUser*'  
```
  
<span data-ttu-id="bb6f8-196">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-196">**Cause**</span></span>  
 <span data-ttu-id="bb6f8-197">如果.mdf 文件，会出现此错误，或运行具有.mdf 文件或 BizTalk Server 配置程序尝试创建的.ldf 文件的名称相同的 SQL Server 的计算机的 \MSSQL\data 文件夹中已存在的.ldf 文件。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-197">This error can occur if an .mdf file or an .ldf file already exists in the \MSSQL\data folder of the computer running SQL Server that has the same name as the .mdf file or the .ldf file that the BizTalk Server configuration program is trying to create.</span></span> <span data-ttu-id="bb6f8-198">为数据库创建的.mdf 文件和.ldf 文件的名称派生而来的数据库的.mdf 和.ldf 扩展名追加与 BizTalk Server 配置程序中指定的名称。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-198">The names of the .mdf file and the .ldf file that are created for the databases are derived from the name of the database that is specified in the BizTalk Server configuration program with an .mdf and an .ldf extension appended.</span></span>  
  
<span data-ttu-id="bb6f8-199">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-199">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-200">若要解决此行为的问题，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="bb6f8-200">To resolve this behavior, use one of the following methods:</span></span>  
  
-   <span data-ttu-id="bb6f8-201">删除其名称与您要创建的任何数据库的名称匹配的任何 .mdf 文件或 .ldf 文件。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-201">Delete any .mdf files or .ldf files that have names that match the names of any databases that you are creating.</span></span>  
  
-   <span data-ttu-id="bb6f8-202">选择数据库名称时，确保其与 SQL Server 的 \Program Files\Microsoft SQL Server\MSSQL\data 文件夹中已经存在的任何 .mdf 文件或 .ldf 文件的名称都不匹配。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-202">Choose database names that do not match the names of any .mdf files or .ldf files that already exist in the \Program Files\Microsoft SQL Server\MSSQL\data folder of your SQL server.</span></span>  
  
### <a name="configuration-fails-on-a-domain-controller-when-specifying-local-accounts"></a><span data-ttu-id="bb6f8-203">当指定本地帐户时，域控制器上的配置失败</span><span class="sxs-lookup"><span data-stu-id="bb6f8-203">Configuration fails on a domain controller when specifying local accounts</span></span>  
  
<span data-ttu-id="bb6f8-204">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-204">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-205">在运行 BizTalk Server 配置程序时的域控制器上，配置有 BizTalkServerApplication 主机或 BizTalkIsolatedHost 主机失败如果指定的本地组 （例如，BizTalk 主机用户组）。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-205">When running the BizTalk Server configuration program on a domain controller, configuration fails if you specified a local group (for example, BizTalk Host Users Group) for either the BizTalkServerApplication host or the BizTalkIsolatedHost host.</span></span>  
  
<span data-ttu-id="bb6f8-206">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-206">**Cause**</span></span>  
 <span data-ttu-id="bb6f8-207">域控制器自动将本地 Windows 组视为域 Windows 组（在域控制器上不存在本地 Windows 组）。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-207">A domain controller automatically treats a local Windows group as a domain Windows group (there is no such thing as local Windows group on a domain controller).</span></span> <span data-ttu-id="bb6f8-208">如果运行配置程序时为主机指定本地 Windows 组，则配置会失败时尝试创建组的 SQL Server 登录。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-208">If you specified a local Windows group for the host while running the configuration program, configuration will fail when trying to create a SQL Server logon for the group.</span></span> <span data-ttu-id="bb6f8-209">当服务器是域控制器时，配置程序不禁用本地 Windows 组选项。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-209">The configuration program does not disable the local Windows group option when the server is a domain controller.</span></span>  
  
<span data-ttu-id="bb6f8-210">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-210">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-211">为在配置过程中创建的主机指定域组。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-211">Specify domain groups for the hosts that are created during configuration.</span></span>  
  
### <a name="configuration-fails-to-create-sql-server-analysis-database-if-the-sql-server-has-been-renamed"></a><span data-ttu-id="bb6f8-212">如果尚未重命名 SQL Server，配置将无法创建 SQL Server 分析数据库</span><span class="sxs-lookup"><span data-stu-id="bb6f8-212">Configuration fails to create SQL Server Analysis database if the SQL server has been renamed</span></span>  
  
<span data-ttu-id="bb6f8-213">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-213">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-214">如果您已经对安装了 SQL Server 分析服务器的计算机进行了重命名，当配置程序尝试新建 SQL Server 分析数据库时将失败，并且生成如下错误：</span><span class="sxs-lookup"><span data-stu-id="bb6f8-214">If you have renamed the computer on which you installed SQL Server Analysis Server, the configuration program fails when it tries to create the new SQL Server Analysis database and an error similar to the following is generated:</span></span>  

```  
 Cannot connect to the repository.  
  
 Analysis server: <machine name\>  
  
 Error:  
  
 '\\\\<machine name\>\MsOLAPRepository$\msmdrep.mdb' is not a valid path.  
  
 Make sure that you correctly spell the path name and that you are  
  
 connected to the server on which the file resides.  
```
  
<span data-ttu-id="bb6f8-215">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-215">**Cause**</span></span>  
 <span data-ttu-id="bb6f8-216">配置程序无法确定您安装了 SQL Server 分析服务器的计算机的新名称。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-216">The configuration program is unable to determine the new name of the computer on which you installed SQL Server Analysis Server.</span></span>  
  
<span data-ttu-id="bb6f8-217">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-217">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-218">手动执行下列操作，以便用新的计算机名更新分析服务器：</span><span class="sxs-lookup"><span data-stu-id="bb6f8-218">Perform the following manual steps to update Analysis Server with the new computer name:</span></span>  
  
1.  <span data-ttu-id="bb6f8-219">在 SQL 服务器上，打开**Microsoft SQL Server**，选择**Analysis Services**，然后单击**Analysis Manager**。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-219">On the SQL Server, open **Microsoft SQL Server**, select **Analysis Services**, and then click **Analysis Manager**.</span></span>  
  
2.  <span data-ttu-id="bb6f8-220">在**Analysis Manager**导航面板中，双击**分析服务器**节点以将其展开。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-220">In the **Analysis Manager** navigation panel, double-click the **Analysis Servers** node to expand it.</span></span>  
  
3.  <span data-ttu-id="bb6f8-221">右键单击你想要编辑，，然后选择的存储库连接字符串服务器**编辑储存库连接字符串**。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-221">Right-click the server with the repository connection string you want to edit, and then select **Edit Repository Connection String**.</span></span>  
  
4.  <span data-ttu-id="bb6f8-222">在**编辑储存库连接字符串**对话框中，验证此字符串中的服务器名称，为新的计算机名称进行更新，如果不正确。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-222">In the **Edit Repository Connection String** dialog box, verify the server name in this string and update it to the new computer name if it is incorrect.</span></span>  
  
5.  <span data-ttu-id="bb6f8-223">导航到以下位置： <*安装目录*> files\microsoft Analysis Services\Bin。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-223">Navigate to the following location: <*installation directory*>\Program Files\Microsoft Analysis Services\Bin.</span></span>  
  
6.  <span data-ttu-id="bb6f8-224">右键单击**Bin**文件夹，，然后单击**共享和安全**。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-224">Right-click the **Bin** folder, and then click **Sharing and Security**.</span></span> <span data-ttu-id="bb6f8-225">**Bin 属性**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-225">The **Bin Properties** dialog box appears.</span></span>  
  
7.  <span data-ttu-id="bb6f8-226">在**Bin 属性**对话框中，单击**共享**选项卡以验证所有联机分析处理 (OLAP) 管理员具有对此文件夹的完全权限。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-226">In the **Bin Properties** dialog box, click the **Sharing** tab to verify that all Online Analytical Processing (OLAP) administrators have full permissions to this folder.</span></span>  
  
### <a name="artifacts-disappear-from-configuration-database-on-redeployment-of-assemblies-from-visual-studio"></a><span data-ttu-id="bb6f8-227">从配置数据库消失上的 Visual Studio 中的程序集的重新部署的项目</span><span class="sxs-lookup"><span data-stu-id="bb6f8-227">Artifacts disappear from Configuration Database on redeployment of assemblies from Visual Studio</span></span>  
  
<span data-ttu-id="bb6f8-228">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-228">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-229">当 BizTalk 服务器项目重新部署后在 Visual Studio 中的项目级引用正在重新部署项目看起来消失时刷新 BizTalk Server MMC 项目中包含的所有项目。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-229">When a BizTalk Server project is redeployed at the project level within Visual Studio, all artifacts contained within the project that reference the project being redeployed will appear to vanish when the BizTalk Server MMC is refreshed.</span></span>  
  
<span data-ttu-id="bb6f8-230">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-230">**Cause**</span></span>  
 <span data-ttu-id="bb6f8-231">为了说明此问题的原因，请看以下示例，此示例基于一个示例 BizTalk Server 解决方案，用户要在此解决方案中重新部署 Maps 项目。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-231">To illustrate the cause of this problem, consider the following example based on a sample BizTalk Server solution where a user wants to redeploy the Maps project.</span></span> <span data-ttu-id="bb6f8-232">请注意，对项目进行编译将生成单独的程序集。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-232">Note that compiling projects yields individual assemblies.</span></span> <span data-ttu-id="bb6f8-233">下图表示用户在进行重新部署之前，此解决方案的状态。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-233">The following figure indicates the state of the solution before the user does a redeployment.</span></span> <span data-ttu-id="bb6f8-234">项目之间的关系如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb6f8-234">The relationships among the artifacts are as follows:</span></span>  
  
-   <span data-ttu-id="bb6f8-235">Orch1、Orch2、Maps、Pipelines 和 Schemas 为项目。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-235">Orch1, Orch2, Maps, Pipelines, and Schemas are projects.</span></span>  
  
-   <span data-ttu-id="bb6f8-236">Orch1 引用 Maps，而 Maps 引用 Schemas。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-236">Orch1 references Maps, which in turn references Schemas.</span></span>  
  
-   <span data-ttu-id="bb6f8-237">Orch2 引用 Schemas。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-237">Orch2 references Schemas.</span></span>  
  
-   <span data-ttu-id="bb6f8-238">Pipelines 引用 Schemas。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-238">Pipelines references Schemas.</span></span>  
  
![bcd_ExistingBizTalkServerSolutionc](../install-and-config-guides/media/bcd_ExistingBizTalkServerSolutionc.gif)  
  
<span data-ttu-id="bb6f8-240">如果用户使用默认的 Visual Studio 项目设置重新部署 Maps 项目，则 Orch1、Orch2 和 Pipeline 项目将消失，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-240">If the user redeploys the Maps project using the default Visual Studio project settings, the Orch1, Orch2, and Pipeline artifacts vanish, as shown in the following figure.</span></span>  
  
![bcd_BizTalkSolutionWLostArtifactsc](../install-and-config-guides/media/bcd_BizTalkSolutionWLostArtifactsc.gif)  
  
 <span data-ttu-id="bb6f8-242">重新部署 Maps 的过程分为两步，首先取消部署当前已部署的 Maps.dll 程序集，然后部署新的 Maps.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-242">Redeploying Maps is a two-step process of undeploying the currently deployed Maps.dll assembly, and then deploying the new Maps.dll file.</span></span> <span data-ttu-id="bb6f8-243">Visual Studio 会重新部署过程的一部分自动执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-243">Visual Studio performs these steps automatically as part of the redeployment process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb6f8-244">严格来说，上面的描述并不正确，因为这些是 Visual Studio 一直执行的步骤，因此并没有考虑其方式是否适当。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-244">The preceding sentence is not strictly correct because these are steps that Visual Studio always does so there is no notion of it being the proper way.</span></span>  
  
 <span data-ttu-id="bb6f8-245">关键之处在于，若要取消部署的 BizTalk Server 程序集，Visual Studio 必须取消部署的所有程序集依赖于该程序集，将部署标志设置。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-245">The key point is that in order to undeploy a BizTalk Server assembly, Visual Studio has to undeploy all assemblies that are dependent upon that assembly that have the deploy flag set.</span></span> <span data-ttu-id="bb6f8-246">在本例中，要执行重新部署过程的第一个取消部署步骤，BizTalk Server 需要取消部署 Orch1.dll（而它依赖于 Maps.dll）。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-246">In our example, to perform the first undeployment step of the redeployment, BizTalk Server needs to undeploy Orch1.dll (which depends on Maps.dll).</span></span> <span data-ttu-id="bb6f8-247">期间的 Maps.dll 取消部署，Visual Studio 还取消部署 Schemas.dll （假设它已将部署标志设）。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-247">During the undeployment of Maps.dll, Visual Studio also undeploys Schemas.dll (assuming it has the deploy flag set).</span></span> <span data-ttu-id="bb6f8-248">为了取消部署 Schemas.dll，Visual Studio 需要取消部署 Orch2.dll 和 Pipelines.dll（这两者都依赖于 Schemas.dll）。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-248">In order to undeploy Schemas.dll, Visual Studio needs to undeploy Orch2.dll and Pipelines.dll (both of which depend on Schemas.dll).</span></span>  
  
 <span data-ttu-id="bb6f8-249">只有 Maps.dll 和它取决于程序集，将重新部署 Visual Studio，因为存在问题： 在此情况下，Schemas.dll。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-249">A problem exists in that Visual Studio redeploys only Maps.dll and the assemblies that it depends upon: in this case, Schemas.dll.</span></span> <span data-ttu-id="bb6f8-250">因此，当用户刷新 BizTalk Server MMC，Orch1、 Orch2，和管道程序集似乎已消失，但 Maps.dll 和 Schemas.dll 仍将可见。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-250">So when the user refreshes the BizTalk Server MMC, the Orch1, Orch2, and Pipeline assemblies seem to have vanished, but Maps.dll and Schemas.dll are still visible.</span></span>  
  
<span data-ttu-id="bb6f8-251">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-251">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-252">主要项目 （引用其他项目） 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bb6f8-252">For the main project (that references other projects) do the following:</span></span>  
  
1.  <span data-ttu-id="bb6f8-253">在解决方案资源管理器中，右键单击解决方案节点。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-253">In Solution Explorer, right-click the solution node.</span></span>  
  
2.  <span data-ttu-id="bb6f8-254">单击**属性**以打开**解决方案属性页**对话框。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-254">Click **Properties** to open the **Solution Property Pages** dialog box.</span></span>  
  
3.  <span data-ttu-id="bb6f8-255">单击**配置属性**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-255">Click **Configuration Properties**, and then click **Configuration**.</span></span>  
  
4.  <span data-ttu-id="bb6f8-256">清除**部署**引用的项目的复选框。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-256">Clear the **Deploy** check box for the referenced project.</span></span>  
  
5.  <span data-ttu-id="bb6f8-257">在解决方案资源管理器中，执行新的解决方案级别部署。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-257">In Solution Explorer, execute a new solution-level deployment.</span></span> <span data-ttu-id="bb6f8-258">若要执行此操作，右键单击解决方案节点，然后单击**部署解决方案**。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-258">To do this, right-click the solution node and then click **Deploy Solution**.</span></span>  
  
### <a name="supported-virtual-directory-types"></a><span data-ttu-id="bb6f8-259">支持的虚拟目录类型</span><span class="sxs-lookup"><span data-stu-id="bb6f8-259">Supported Virtual Directory Types</span></span>  
 <span data-ttu-id="bb6f8-260">仅当关联的虚拟目录的类型，在导出操作时从业务流程和尝试的操作的 MSI 导出中引用 Web 服务，将会成功**IIsWebVirtualDir**或**IIsWebDirectory**.</span><span class="sxs-lookup"><span data-stu-id="bb6f8-260">When referencing Web services from an orchestration and attempting to do an MSI export, the export operation will succeed only if the associated virtual directories are of type **IIsWebVirtualDir** or **IIsWebDirectory**.</span></span> <span data-ttu-id="bb6f8-261">**IIsWebVirtualDir**和**IIsWebDirectory**是显示在 IIS 元数据库中的节点类型。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-261">**IIsWebVirtualDir** and **IIsWebDirectory** are the node types that appear in the IIS metabase.</span></span> <span data-ttu-id="bb6f8-262">**IIsWebVirtualDir**是使用的虚拟目录**路径**指向绝对文件文件夹的属性。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-262">**IIsWebVirtualDir** is a virtual directory with a **Path** property that points to an absolute file folder.</span></span> <span data-ttu-id="bb6f8-263">**IIsWebDirectory**而不是虚拟目录**路径**属性，并因此将路由到相对文件文件夹，通常的另一个子文件夹**IIsWebVirtualDir**或**IIsWebDirectory**节点。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-263">**IIsWebDirectory** is a virtual directory without a **Path** property and thus refers to a relative file folder, typically a subfolder of another **IIsWebVirtualDir** or **IIsWebDirectory** node.</span></span> <span data-ttu-id="bb6f8-264">这两种类型是元数据库层次中用于描述文件夹的常见类型。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-264">These two types are the ones typically seen in the metabase hierarchy to describe folders.</span></span>  
  
 <span data-ttu-id="bb6f8-265">类型的虚拟目录**IIsConfigObject**不支持和 MSI 导出将会在这种情况下失败。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-265">Virtual directories of type **IIsConfigObject** are not supported and the MSI export will fail in this case.</span></span> <span data-ttu-id="bb6f8-266">**IIsConfigObject**意外元数据库节点类型，是一个有效的节点类型不正确处理 BizTalk Server 或不正确创建 （并因此无效） 元数据库条目的相对值。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-266">**IIsConfigObject** is an unexpected metabase node type that is either a valid node type that BizTalk Server is not handling properly or an indication of an improperly created (and thus invalid) metabase entry.</span></span> <span data-ttu-id="bb6f8-267">在此情况下，BizTalk 服务器会显示一条错误消息类似于以下内容： 类型为 IIsConfigObject 意外的目录项"IIS://LM/W3SVC/1/ROOT/BadVdir/"。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-267">In this situation BizTalk Server will display an error message something like the following: Unexpected directory entry " IIS://LM/W3SVC/1/ROOT/BadVdir/" of type IIsConfigObject.</span></span>  
  
### <a name="unable-to-view-group-information-after-removing-stale-logons"></a><span data-ttu-id="bb6f8-268">删除过时登录后无法查看组信息</span><span class="sxs-lookup"><span data-stu-id="bb6f8-268">Unable to view Group information after removing stale logons</span></span>  
  
<span data-ttu-id="bb6f8-269">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-269">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-270">如果在配置过程中遇到过时登录并删除它们，您可能无法查看组信息。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-270">If, during configuration, you encounter and delete stale logons, you may not be able to view Group information.</span></span>  
  
<span data-ttu-id="bb6f8-271">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-271">**Cause**</span></span>  
 <span data-ttu-id="bb6f8-272">这是一个已知的配置问题。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-272">This is a known configuration issue.</span></span>  
  
<span data-ttu-id="bb6f8-273">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-273">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-274">删除主机 Windows 组登录，然后重新配置，这种方法可能奏效。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-274">It may help to delete the Host Windows group logons and then reconfigure.</span></span> <span data-ttu-id="bb6f8-275">如果组信息仍然不可用，请联系 Microsoft 产品支持人员。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-275">If the Group information is still not available, contact Microsoft Product Support.</span></span>  
  
### <a name="cannot-change-computer-name-after-biztalk-server-is-installed"></a><span data-ttu-id="bb6f8-276">安装 BizTalk Server 后将无法更改计算机名称</span><span class="sxs-lookup"><span data-stu-id="bb6f8-276">Cannot change computer name after BizTalk Server is installed</span></span>  
  
<span data-ttu-id="bb6f8-277">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-277">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-278">当你更改运行 BizTalk Server 的计算机上的计算机名称并重新启动 （重启） 计算机，错误消息可能会出现。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-278">When you change the computer name on a computer running BizTalk Server, and you restart (reboot) the computer, error messages may occur.</span></span>  
  
<span data-ttu-id="bb6f8-279">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-279">**Cause**</span></span>  
 <span data-ttu-id="bb6f8-280">SQL Server 不支持更改计算机名称，因此 BizTalk Server 不支持更改计算机名称后安装并配置 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-280">SQL Server does not support changing the computer name, so BizTalk Server does not support changing the computer name once BizTalk Server is installed and configured.</span></span>  
  
<span data-ttu-id="bb6f8-281">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-281">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-282">我们建议您在安装 BizTalk Server 后不要更改计算机名称。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-282">We recommend that you do not change computer names after you install BizTalk Server.</span></span>  
  
### <a name="known-issues-with-enterprise-single-sign-on"></a><span data-ttu-id="bb6f8-283">与企业单一登录有关的已知问题</span><span class="sxs-lookup"><span data-stu-id="bb6f8-283">Known Issues with Enterprise Single Sign-On</span></span>  
 <span data-ttu-id="bb6f8-284">该部分介绍了可能与企业单一登录 (SSO) 有关的安装和配置问题。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-284">This section describes setup and configuration problems that may be related to Enterprise Single Sign-On (SSO).</span></span>  
  
##### <a name="entsso-service-fails-to-start"></a><span data-ttu-id="bb6f8-285">ENTSSO 服务启动失败</span><span class="sxs-lookup"><span data-stu-id="bb6f8-285">ENTSSO Service fails to start</span></span>  
  
<span data-ttu-id="bb6f8-286">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-286">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-287">ENTSSO 服务启动失败。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-287">The ENTSSO service fails to start.</span></span>  
  
<span data-ttu-id="bb6f8-288">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-288">**Cause**</span></span>  
 <span data-ttu-id="bb6f8-289">如果 ENTSSO 服务没有在有效的 SSO 管理员帐户下运行，将无法启动。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-289">If the ENTSSO service is not running under a valid SSO Administrator account, it will fail to start.</span></span>  
  
<span data-ttu-id="bb6f8-290">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-290">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-291">请为 ENTSSO 服务指定有效的 SSO 管理员帐户，然后从服务控制管理器 (SCM) 管理单元重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-291">Specify a valid SSO administrator account for the ENTSSO Service and restart the service from Services Control Manager (SCM) snap-in.</span></span>  
  
##### <a name="biztalk-services-dependent-on-the-enterprise-single-sign-on-service-entsso-fail-to-start-after-a-reboot"></a><span data-ttu-id="bb6f8-292">依赖于企业单一登录服务 (ENTSSO) 的 BizTalk Services 未能在重新启动后启动</span><span class="sxs-lookup"><span data-stu-id="bb6f8-292">BizTalk Services dependent on the Enterprise Single Sign-On Service (ENTSSO) fail to start after a reboot</span></span>  
  
<span data-ttu-id="bb6f8-293">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-293">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-294">BTSSvc$BizTalkServerApplication 依赖于企业单一登录服务 (ENTSSO)，且在重新启动之后的启动过程中可能超时。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-294">BTSSvc$BizTalkServerApplication has a dependency on the Enterprise Single Sign-On Service (ENTSSO) and may timeout during start up after a reboot.</span></span>  
  
<span data-ttu-id="bb6f8-295">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-295">**Cause**</span></span>  
 <span data-ttu-id="bb6f8-296">企业单一登录服务可能需要约 3 分钟时间才能启动。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-296">The Enterprise Single Sign-On Service may take around 3 minutes to start.</span></span>  
  
<span data-ttu-id="bb6f8-297">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-297">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-298">通过“自动(延迟的启动)”启动类型选项配置“BizTalk 服务 BizTalk 组: BizTalkServerApplication”服务。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-298">Configure the “BizTalk Service BizTalk Group: BizTalkServerApplication” service with the Automatic (Delayed Start) startup type option.</span></span> <span data-ttu-id="bb6f8-299">这将在所有自动服务完成其启动例程后开始启动服务。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-299">This will initiate the start of the service after all Automatic services have completed their startup routines.</span></span>  
  
##### <a name="cannot-access-an-affiliate-application"></a><span data-ttu-id="bb6f8-300">无法访问关联应用程序</span><span class="sxs-lookup"><span data-stu-id="bb6f8-300">Cannot access an affiliate application</span></span>  
  
<span data-ttu-id="bb6f8-301">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-301">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-302">如果与关联应用程序关联的应用程序管理员帐户无效，则企业单一登录禁用关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-302">The Enterprise Single Sign-On service disables an affiliate application if the application administrator account associated with it is not valid.</span></span>  
  
<span data-ttu-id="bb6f8-303">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-303">**Cause**</span></span>  
 <span data-ttu-id="bb6f8-304">SSO 应用程序管理员帐户无效。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-304">The SSO application administrator account is not valid.</span></span>  
  
<span data-ttu-id="bb6f8-305">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-305">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-306">在创建关联应用程序之前，请确保 SSO 应用程序管理员帐户有效。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-306">Ensure that the SSO application administrator account is valid before you create an affiliate application.</span></span> <span data-ttu-id="bb6f8-307">然后，您必须使关联应用程序能够使用该应用程序。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-307">You must then enable the affiliate application to use the application.</span></span>  
  
##### <a name="rpc-error-occurs-when-connecting-to-a-client-computer"></a><span data-ttu-id="bb6f8-308">如果连接到客户端计算机会出现 RPC 错误</span><span class="sxs-lookup"><span data-stu-id="bb6f8-308">RPC error occurs when connecting to a client computer</span></span>  
  
<span data-ttu-id="bb6f8-309">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-309">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-310">当你运行命令如**ssomanage-displayapp** *< applicationname\>*，其中计算机尝试连接到远程的 SSO 服务器以检索信息，你收到以下错误： 错误： 0x800706BA: RPC 服务器不可用。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-310">When you run a command such as **ssomanage -displayapp** *<applicationname\>*, where the computer attempt to connect to a remote SSO Server to retrieve the information, you receive the following error: ERROR: 0x800706BA: The RPC server is unavailable.</span></span>  
  
<span data-ttu-id="bb6f8-311">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-311">**Cause**</span></span>  
 <span data-ttu-id="bb6f8-312">当您指定了错误的服务器信息时，或者当 SSO 服务在远程服务器上不可用时，会发生此错误。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-312">This error occurs when you specify the wrong server information, or when the SSO Service is not available on the remote server.</span></span>  
  
<span data-ttu-id="bb6f8-313">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-313">**Resolution**</span></span>  
  
-   <span data-ttu-id="bb6f8-314">按照中的步骤[设置 SSO 服务器](../core/how-to-set-the-sso-server.md)若要确保你连接到正确的 SSO 服务器。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-314">Follow the steps in [Set the SSO Server](../core/how-to-set-the-sso-server.md) to make sure you are connected to the correct SSO Server.</span></span>  
  
-   <span data-ttu-id="bb6f8-315">确保 SSO 服务已启用并且运行在您要连接到的 SSO 服务器中。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-315">Make sure the SSO Service is enabled and running in the SSO Server to which you are connecting.</span></span>  
  
##### <a name="master-secret-is-missing-or-corrupt"></a><span data-ttu-id="bb6f8-316">主密钥已丢失或损坏</span><span class="sxs-lookup"><span data-stu-id="bb6f8-316">Master Secret is missing or corrupt</span></span>  
  
<span data-ttu-id="bb6f8-317">**问题**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-317">**Problem**</span></span>  
 <span data-ttu-id="bb6f8-318">缺少主密钥，或者主密钥已损坏。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-318">The master secret is missing or corrupt.</span></span> <span data-ttu-id="bb6f8-319">主密钥通常在配置期间生成。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-319">It normally generates during configuration.</span></span> <span data-ttu-id="bb6f8-320">如果缺少该密钥，当企业单一登录服务启动时事件日志中便会显示下列消息之一。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-320">If the secret is missing, one of the following messages will display in the event log as the Enterprise Single Sign-On service starts.</span></span>  
  
```
MessageId=10520  
Severity=Warning  
SSO_WARN_NO_SECRETS  
MessageId=10565  
Severity=Error  
SSO_ERROR_SECRET_VALIDATE_FAILED  
MessageId=10521  
Severity=Error  
SSO_ERROR_SECRETS_NOT_LOADED  
```

<span data-ttu-id="bb6f8-321">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-321">**Cause**</span></span>  
 <span data-ttu-id="bb6f8-322">如果企业单一登录服务 (SSO) 在某个服务帐户下运行时生成密钥，又更改了该服务帐户，则可能出现此问题。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-322">This problem can occur if a secret is generated while the Enterprise Single Sign-On service (SSO) was running under one service account, and then the service account was changed.</span></span> <span data-ttu-id="bb6f8-323">但是，该密钥以加密的形式存储在注册表中，并且使用基于此服务帐户标识（ENTSSO 在该帐户下运行）的密钥进行加密。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-323">The secret is stored in the registry in encrypted form, and is encrypted using a key based on the identity of the service account (which ENTSSO runs under).</span></span>  
  
<span data-ttu-id="bb6f8-324">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bb6f8-324">**Resolution**</span></span>  
 <span data-ttu-id="bb6f8-325">将 ENTSSO 在其下运行的服务帐户更改为创建主密钥时的原始服务帐户。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-325">Change the service account ENTSSO is running under to the original service account when the master secret was created.</span></span>  
  
1.  <span data-ttu-id="bb6f8-326">备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-326">Back up the master secret.</span></span> <span data-ttu-id="bb6f8-327">请参阅[备份主密钥](../core/how-to-back-up-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-327">See [Back Up the Master Secret](../core/how-to-back-up-the-master-secret.md).</span></span>  
  
2.  <span data-ttu-id="bb6f8-328">停止企业单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-328">Stop Enterprise Single Sign-On Services.</span></span>  
  
3.  <span data-ttu-id="bb6f8-329">更改服务帐户。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-329">Change the service account.</span></span>  
  
4.  <span data-ttu-id="bb6f8-330">重新启动 SSO，并忽略有关受损密钥的任何事件日志错误。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-330">Restart SSO and ignore any event log errors about a corrupted secret.</span></span>  
  
5.  <span data-ttu-id="bb6f8-331">还原主密钥。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-331">Restore the master secret.</span></span> <span data-ttu-id="bb6f8-332">请参阅[还原主密钥](../core/how-to-restore-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-332">See [Restore the Master Secret](../core/how-to-restore-the-master-secret.md).</span></span>  
  
### <a name="custom-action"></a><span data-ttu-id="bb6f8-333">自定义操作</span><span class="sxs-lookup"><span data-stu-id="bb6f8-333">Custom Action</span></span>  
 <span data-ttu-id="bb6f8-334">本主题提供有关 Windows Server 徽标程序适用于 BizTalk Server 认证的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-334">This topic provides details about BizTalk Server certification for the Windows Server logo program.</span></span> <span data-ttu-id="bb6f8-335">在 BizTalk Server 安装操作期间可能执行以下自定义操作。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-335">The following custom actions might be performed during BizTalk Server Setup operations.</span></span>  
  
|<span data-ttu-id="bb6f8-336">自定义操作</span><span class="sxs-lookup"><span data-stu-id="bb6f8-336">Custom action</span></span>|<span data-ttu-id="bb6f8-337">Description</span><span class="sxs-lookup"><span data-stu-id="bb6f8-337">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="bb6f8-338">ReadComplusData</span><span class="sxs-lookup"><span data-stu-id="bb6f8-338">ReadComplusData</span></span>|<span data-ttu-id="bb6f8-339">阅读自定义 COM+ 表、创建 XML 文档并将其保存在 Complus_XML_Data 属性中。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-339">Reads custom COM+ tables, creates XML document, and saves it in the Complus_XML_Data property.</span></span>|  
|<span data-ttu-id="bb6f8-340">SchedXmlConfig</span><span class="sxs-lookup"><span data-stu-id="bb6f8-340">SchedXmlConfig</span></span>|<span data-ttu-id="bb6f8-341">用于配置具有 RFID 数据的计算机。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-341">Used for configuring machines having RFID data.</span></span>|  
|<span data-ttu-id="bb6f8-342">CheckBaseEDI</span><span class="sxs-lookup"><span data-stu-id="bb6f8-342">CheckBaseEDI</span></span>|<span data-ttu-id="bb6f8-343">检查是否存在旧版本的 EDI</span><span class="sxs-lookup"><span data-stu-id="bb6f8-343">Checks the presence of an old version of EDI</span></span>|  
|<span data-ttu-id="bb6f8-344">CheckMQSeries</span><span class="sxs-lookup"><span data-stu-id="bb6f8-344">CheckMQSeries</span></span>|<span data-ttu-id="bb6f8-345">检查是否存在 MQSeries</span><span class="sxs-lookup"><span data-stu-id="bb6f8-345">Checks the presence of MQSeries</span></span>|  
|<span data-ttu-id="bb6f8-346">CheckNET30Vista</span><span class="sxs-lookup"><span data-stu-id="bb6f8-346">CheckNET30Vista</span></span>|<span data-ttu-id="bb6f8-347">检查是否存在 WCF</span><span class="sxs-lookup"><span data-stu-id="bb6f8-347">Checks the presence of WCF</span></span>|  
|<span data-ttu-id="bb6f8-348">CheckWSSV3SP1</span><span class="sxs-lookup"><span data-stu-id="bb6f8-348">CheckWSSV3SP1</span></span>|<span data-ttu-id="bb6f8-349">检查是否存在 Windows SharePoint Services 3.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-349">Checks the presence of Windows SharePoint Services 3.0 SP1.</span></span>|  
|<span data-ttu-id="bb6f8-350">CheckWSSV4</span><span class="sxs-lookup"><span data-stu-id="bb6f8-350">CheckWSSV4</span></span>|<span data-ttu-id="bb6f8-351">检查是否存在 Windows SharePoint Services 4</span><span class="sxs-lookup"><span data-stu-id="bb6f8-351">Checks the presence of Windows SharePoint Services 4</span></span>|  
|<span data-ttu-id="bb6f8-352">GetFrameworkPath</span><span class="sxs-lookup"><span data-stu-id="bb6f8-352">GetFrameworkPath</span></span>|<span data-ttu-id="bb6f8-353">在包含 Microsoft .Net framework 4 和 2.0 的安装路径的安装程序中设置安装程序属性。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-353">Sets installer properties in the installer that holds installation path to Microsoft .Net framework 4 and 2.0.</span></span>|  
|<span data-ttu-id="bb6f8-354">Set_BAMClientExcelDir</span><span class="sxs-lookup"><span data-stu-id="bb6f8-354">Set_BAMClientExcelDir</span></span>|<span data-ttu-id="bb6f8-355">创建一个 Excel 应用程序对象，以设置一个用于包含安装程序中 Microsoft Office 库路径的属性。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-355">Creates an Excel application object for setting a property to hold the Microsoft Office library path in the installer.</span></span>|  
|<span data-ttu-id="bb6f8-356">Set_CurrentUser</span><span class="sxs-lookup"><span data-stu-id="bb6f8-356">Set_CurrentUser</span></span>|<span data-ttu-id="bb6f8-357">设置当前用户的域\用户名信息</span><span class="sxs-lookup"><span data-stu-id="bb6f8-357">Sets domain\username information of the current user</span></span>|  
|<span data-ttu-id="bb6f8-358">ViewInstallGuide</span><span class="sxs-lookup"><span data-stu-id="bb6f8-358">ViewInstallGuide</span></span>|<span data-ttu-id="bb6f8-359">从安装源目录启动 BizTalk Server 安装指南。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-359">Launches the BizTalk Server installation guide from the installation source directory.</span></span>|  
|<span data-ttu-id="bb6f8-360">CA_CheckSTSLanguage</span><span class="sxs-lookup"><span data-stu-id="bb6f8-360">CA_CheckSTSLanguage</span></span>|<span data-ttu-id="bb6f8-361">当 WSS 和 BizTalk 的语言集相同时设置 STS_Language_Property 属性。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-361">Sets STS_Language_Property property when the language set for WSS and BizTalk are same.</span></span>|  
|<span data-ttu-id="bb6f8-362">CA_CleanupRegistry</span><span class="sxs-lookup"><span data-stu-id="bb6f8-362">CA_CleanupRegistry</span></span>|<span data-ttu-id="bb6f8-363">卸载 BizTalk Server 时，会清除在 BizTalk Server 配置期间创建的注册表项。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-363">When you uninstall BizTalk Server, it cleans the registry entries that were created during BizTalk Server configuration.</span></span>|  
|<span data-ttu-id="bb6f8-364">CA_CleanupRegistry_OldProducts</span><span class="sxs-lookup"><span data-stu-id="bb6f8-364">CA_CleanupRegistry_OldProducts</span></span>|<span data-ttu-id="bb6f8-365">清除属于旧版本的 BizTalk Server 的注册表项以及 BizTalk Server 的全新安装不需要的注册表项。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-365">Cleans the registry entries that belong to an older version of BizTalk Server and are not required for a fresh installation of BizTalk Server.</span></span>|  
|<span data-ttu-id="bb6f8-366">CA_RemovePatches</span><span class="sxs-lookup"><span data-stu-id="bb6f8-366">CA_RemovePatches</span></span>|<span data-ttu-id="bb6f8-367">卸载 BizTalk Server 时删除 Microsoft BizTalk Server 更新。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-367">Removes Microsoft BizTalk Server updates when you uninstall BizTalk Server.</span></span>|  
|<span data-ttu-id="bb6f8-368">CA_ResolveWellKnownNames</span><span class="sxs-lookup"><span data-stu-id="bb6f8-368">CA_ResolveWellKnownNames</span></span>|<span data-ttu-id="bb6f8-369">使用熟知的名称创建安装程序属性，并为这些属性分配相应的 SID。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-369">Creates installer properties with well-known names and assigns them their corresponding SID.</span></span>|  
|<span data-ttu-id="bb6f8-370">CA_SaveTargetVSVersionToRegistry</span><span class="sxs-lookup"><span data-stu-id="bb6f8-370">CA_SaveTargetVSVersionToRegistry</span></span>|<span data-ttu-id="bb6f8-371">将 TargetVSVersion_Property 属性设置为受支持版本的 Visual Studio 的值。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-371">Sets a TargetVSVersion_Property property to the value of a supported version of Visual Studio.</span></span>|  
|<span data-ttu-id="bb6f8-372">CA_StopServices</span><span class="sxs-lookup"><span data-stu-id="bb6f8-372">CA_StopServices</span></span>|<span data-ttu-id="bb6f8-373">停止 IISAdmin、规则引擎更新和 EDI 子系统服务。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-373">Stops IISAdmin, Rules Engine Update and EDI Subsystem services.</span></span>|  
|<span data-ttu-id="bb6f8-374">CleanupUsersKeys</span><span class="sxs-lookup"><span data-stu-id="bb6f8-374">CleanupUsersKeys</span></span>|<span data-ttu-id="bb6f8-375">从 HKEY_CURRENT_USER 注册表项中删除与 BizTalk Server 相关的项。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-375">Removes BizTalk Server related entries from the HKEY_CURRENT_USER registry key.</span></span>|  
|<span data-ttu-id="bb6f8-376">DevEnvRunning</span><span class="sxs-lookup"><span data-stu-id="bb6f8-376">DevEnvRunning</span></span>|<span data-ttu-id="bb6f8-377">检查 Visual Studio 是否正在运行</span><span class="sxs-lookup"><span data-stu-id="bb6f8-377">Checks whether Visual Studio is running</span></span>|  
|<span data-ttu-id="bb6f8-378">ValidateINSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="bb6f8-378">ValidateINSTALLDIR</span></span>|<span data-ttu-id="bb6f8-379">验证 BizTalk Server 安装目录格式</span><span class="sxs-lookup"><span data-stu-id="bb6f8-379">Validates BizTalk Server installation directory format</span></span>|  
|<span data-ttu-id="bb6f8-380">StartHostInstances</span><span class="sxs-lookup"><span data-stu-id="bb6f8-380">StartHostInstances</span></span>|<span data-ttu-id="bb6f8-381">启动 BizTalk Server 主机实例。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-381">Starts BizTalk Server Host Instances.</span></span>|  
|<span data-ttu-id="bb6f8-382">StopHostInstances</span><span class="sxs-lookup"><span data-stu-id="bb6f8-382">StopHostInstances</span></span>|<span data-ttu-id="bb6f8-383">停止 BizTalk Server 主机实例。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-383">Stops BizTalk Server Host Instances.</span></span>|  
|<span data-ttu-id="bb6f8-384">MQSUnConfig</span><span class="sxs-lookup"><span data-stu-id="bb6f8-384">MQSUnConfig</span></span>|<span data-ttu-id="bb6f8-385">对于未配置的 MQSeries 代理启动 MQSeries 配置向导。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-385">Launches MQSeries Configuration wizard for un-configuring MQSeries agent.</span></span>|  
|<span data-ttu-id="bb6f8-386">LaunchConfigFmk</span><span class="sxs-lookup"><span data-stu-id="bb6f8-386">LaunchConfigFmk</span></span>|<span data-ttu-id="bb6f8-387">启动 BizTalk Server 配置向导</span><span class="sxs-lookup"><span data-stu-id="bb6f8-387">Launches BizTalk Server Configuration Wizard</span></span>|  
|<span data-ttu-id="bb6f8-388">CHKASPNET</span><span class="sxs-lookup"><span data-stu-id="bb6f8-388">CHKASPNET</span></span>|<span data-ttu-id="bb6f8-389">检查 ASP.NET 的安装状态</span><span class="sxs-lookup"><span data-stu-id="bb6f8-389">Checks the install state of ASP.NET</span></span>|  
|<span data-ttu-id="bb6f8-390">CHKIIS</span><span class="sxs-lookup"><span data-stu-id="bb6f8-390">CHKIIS</span></span>|<span data-ttu-id="bb6f8-391">检查 IIS 的安装状态</span><span class="sxs-lookup"><span data-stu-id="bb6f8-391">Checks the install state of IIS</span></span>|  
|<span data-ttu-id="bb6f8-392">TBExpired</span><span class="sxs-lookup"><span data-stu-id="bb6f8-392">TBExpired</span></span>|<span data-ttu-id="bb6f8-393">检查 BizTalk Server TimeBomb 是否已过期</span><span class="sxs-lookup"><span data-stu-id="bb6f8-393">Checks if the BizTalk Server TimeBomb has expired</span></span>|  
|<span data-ttu-id="bb6f8-394">BrandSKU</span><span class="sxs-lookup"><span data-stu-id="bb6f8-394">BrandSKU</span></span>|<span data-ttu-id="bb6f8-395">对依赖于 SKU 安装的 BizTalk Server timebomb 的值进行更新。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-395">Updates the value of BizTalk Server timebomb which depends on SKU installation.</span></span>|  
|<span data-ttu-id="bb6f8-396">CA_ERROR</span><span class="sxs-lookup"><span data-stu-id="bb6f8-396">CA_ERROR</span></span>|<span data-ttu-id="bb6f8-397">返回安装故障</span><span class="sxs-lookup"><span data-stu-id="bb6f8-397">Returns installation failure</span></span>|  
|<span data-ttu-id="bb6f8-398">InstallComplus</span><span class="sxs-lookup"><span data-stu-id="bb6f8-398">InstallComplus</span></span>|<span data-ttu-id="bb6f8-399">安装 Complus 应用程序和组件。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-399">Installs Complus applications and components.</span></span>|  
|<span data-ttu-id="bb6f8-400">BAM_Add_Perf_Silent</span><span class="sxs-lookup"><span data-stu-id="bb6f8-400">BAM_Add_Perf_Silent</span></span>|<span data-ttu-id="bb6f8-401">安装 BAM 的性能计数器</span><span class="sxs-lookup"><span data-stu-id="bb6f8-401">Installs performance counters for BAM</span></span>|  
|<span data-ttu-id="bb6f8-402">RegsvcsApplicationDeployment</span><span class="sxs-lookup"><span data-stu-id="bb6f8-402">RegsvcsApplicationDeployment</span></span>|<span data-ttu-id="bb6f8-403">在 BizTalk 部署 COM+ 应用程序 DLL 上运行 Regsvcs.exe（.NET 服务安装工具）</span><span class="sxs-lookup"><span data-stu-id="bb6f8-403">Runs Regsvcs.exe (.NET Services Installation Tool) on BizTalk Deployment COM+ application DLLs</span></span>|  
|<span data-ttu-id="bb6f8-404">RegsvcsDeployment</span><span class="sxs-lookup"><span data-stu-id="bb6f8-404">RegsvcsDeployment</span></span>|<span data-ttu-id="bb6f8-405">在 DLL 上运行 Regsvcs.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-405">Runs Regsvcs.exe on DLLs</span></span>|  
|<span data-ttu-id="bb6f8-406">RegsvcsMQSAdapter</span><span class="sxs-lookup"><span data-stu-id="bb6f8-406">RegsvcsMQSAdapter</span></span>|<span data-ttu-id="bb6f8-407">在 DLL 上运行 Regsvcs.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-407">Runs Regsvcs.exe on DLLs</span></span>|  
|<span data-ttu-id="bb6f8-408">RegsvcsSQLAdapter</span><span class="sxs-lookup"><span data-stu-id="bb6f8-408">RegsvcsSQLAdapter</span></span>|<span data-ttu-id="bb6f8-409">在 DLL 上运行 Regsvcs.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-409">Runs Regsvcs.exe on DLLs</span></span>|  
|<span data-ttu-id="bb6f8-410">WMI_Add_MSBTS_Silent</span><span class="sxs-lookup"><span data-stu-id="bb6f8-410">WMI_Add_MSBTS_Silent</span></span>|<span data-ttu-id="bb6f8-411">向 WMI 注册 BizTalk Server 命名空间和类。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-411">Registers BizTalk Server namespace and classes to WMI.</span></span>|  
|<span data-ttu-id="bb6f8-412">LaunchConfigFmk_SlashUP</span><span class="sxs-lookup"><span data-stu-id="bb6f8-412">LaunchConfigFmk_SlashUP</span></span>|<span data-ttu-id="bb6f8-413">取消对 BizTalk Server 的配置</span><span class="sxs-lookup"><span data-stu-id="bb6f8-413">Un-configures BizTalk Server</span></span>|  
|<span data-ttu-id="bb6f8-414">CleanupComplus</span><span class="sxs-lookup"><span data-stu-id="bb6f8-414">CleanupComplus</span></span>|<span data-ttu-id="bb6f8-415">卸载 Complus 应用程序和组件。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-415">Uninstalls Complus Applications and components.</span></span>|  
|<span data-ttu-id="bb6f8-416">RemoveSKU</span><span class="sxs-lookup"><span data-stu-id="bb6f8-416">RemoveSKU</span></span>|<span data-ttu-id="bb6f8-417">删除 BizTalk Server TimeBomb 数据。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-417">Removes BizTalk Server TimeBomb data.</span></span>|  
|<span data-ttu-id="bb6f8-418">BAM_Remove_Perf</span><span class="sxs-lookup"><span data-stu-id="bb6f8-418">BAM_Remove_Perf</span></span>|<span data-ttu-id="bb6f8-419">卸载 BAM 的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-419">Uninstalls performance counters for BAM.</span></span>|  
|<span data-ttu-id="bb6f8-420">LoadBTSCounters</span><span class="sxs-lookup"><span data-stu-id="bb6f8-420">LoadBTSCounters</span></span>|<span data-ttu-id="bb6f8-421">加载 BizTalk Server 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-421">Loads BizTalk Server performance counters.</span></span>|  
|<span data-ttu-id="bb6f8-422">RegisterBtprojExtn</span><span class="sxs-lookup"><span data-stu-id="bb6f8-422">RegisterBtprojExtn</span></span>|<span data-ttu-id="bb6f8-423">注册 BizTalk 项目文件 (.btproj) 扩展。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-423">Registers BizTalk project file (.btproj) extension.</span></span>|  
|<span data-ttu-id="bb6f8-424">UnRegisterBtprojExtn</span><span class="sxs-lookup"><span data-stu-id="bb6f8-424">UnRegisterBtprojExtn</span></span>|<span data-ttu-id="bb6f8-425">注销 BizTalk 项目文件 (.btproj) 扩展。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-425">Un-registers BizTalk project file (.btproj) extension.</span></span>|  
|<span data-ttu-id="bb6f8-426">UnRegsvcsApplicationDeployment</span><span class="sxs-lookup"><span data-stu-id="bb6f8-426">UnRegsvcsApplicationDeployment</span></span>|<span data-ttu-id="bb6f8-427">卸载 BizTalk Server 时在某些 DLL 上运行 Regsvcs.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-427">Runs Regsvcs.exe on certain DLLs when you uninstall BizTalk Server</span></span>|  
|<span data-ttu-id="bb6f8-428">UnRegsvcsDeployment</span><span class="sxs-lookup"><span data-stu-id="bb6f8-428">UnRegsvcsDeployment</span></span>|<span data-ttu-id="bb6f8-429">卸载 BizTalk Server 时在某些 DLL 上运行 Regsvcs.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-429">Runs Regsvcs.exe on certain DLLs when you uninstall BizTalk Server</span></span>|  
|<span data-ttu-id="bb6f8-430">UnRegsvcsMQSAdapter</span><span class="sxs-lookup"><span data-stu-id="bb6f8-430">UnRegsvcsMQSAdapter</span></span>|<span data-ttu-id="bb6f8-431">卸载 BizTalk Server 时在某些 DLL 上运行 Regsvcs.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-431">Runs Regsvcs.exe on certain DLLs when you uninstall BizTalk Server</span></span>|  
|<span data-ttu-id="bb6f8-432">UnRegsvcsSQLAdapter</span><span class="sxs-lookup"><span data-stu-id="bb6f8-432">UnRegsvcsSQLAdapter</span></span>|<span data-ttu-id="bb6f8-433">卸载 BizTalk Server 时在某些 DLL 上运行 Regsvcs.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-433">Runs Regsvcs.exe on certain DLLs when you uninstall BizTalk Server</span></span>|  
|<span data-ttu-id="bb6f8-434">UnloadBTSCounters</span><span class="sxs-lookup"><span data-stu-id="bb6f8-434">UnloadBTSCounters</span></span>|<span data-ttu-id="bb6f8-435">卸载 BizTalk Server 性能计数器。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-435">Unloads BizTalk Server performance counters.</span></span>|  
|<span data-ttu-id="bb6f8-436">WMI_Remove_MSBTS</span><span class="sxs-lookup"><span data-stu-id="bb6f8-436">WMI_Remove_MSBTS</span></span>|<span data-ttu-id="bb6f8-437">从 WMI 中删除 BizTalk Server 命名空间。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-437">Removes BizTalk Server namespace from WMI.</span></span>|  
|<span data-ttu-id="bb6f8-438">RegisterComsvcs</span><span class="sxs-lookup"><span data-stu-id="bb6f8-438">RegisterComsvcs</span></span>|<span data-ttu-id="bb6f8-439">在 comsvcs.dll 上无提示地运行 regsvr32.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-439">Runs regsvr32.exe on comsvcs.dll silently.</span></span>|  
|<span data-ttu-id="bb6f8-440">DevenvSetupUninstall</span><span class="sxs-lookup"><span data-stu-id="bb6f8-440">DevenvSetupUninstall</span></span>|<span data-ttu-id="bb6f8-441">运行 DevEnv.exe/Setup/resetskippkgs。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-441">Runs DevEnv.exe /Setup/resetskippkgs.</span></span>|  
|<span data-ttu-id="bb6f8-442">RollbackComplus</span><span class="sxs-lookup"><span data-stu-id="bb6f8-442">RollbackComplus</span></span>|<span data-ttu-id="bb6f8-443">回滚 Complus 应用程序和组件的安装。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-443">Rollbacks the installation of Complus applications and components.</span></span>|  
|<span data-ttu-id="bb6f8-444">ResRegsvcsMQSAdapter</span><span class="sxs-lookup"><span data-stu-id="bb6f8-444">ResRegsvcsMQSAdapter</span></span>|<span data-ttu-id="bb6f8-445">对给定二进制文件运行 regsvcs.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-445">Runs regsvcs.exe on a given binary</span></span>|  
|<span data-ttu-id="bb6f8-446">ResRegsvcsSQLAdapter</span><span class="sxs-lookup"><span data-stu-id="bb6f8-446">ResRegsvcsSQLAdapter</span></span>|<span data-ttu-id="bb6f8-447">对给定二进制文件运行 regsvcs.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-447">Runs regsvcs.exe on a given binary</span></span>|  
|<span data-ttu-id="bb6f8-448">RestoreRegsvcsApplicationDeployment</span><span class="sxs-lookup"><span data-stu-id="bb6f8-448">RestoreRegsvcsApplicationDeployment</span></span>|<span data-ttu-id="bb6f8-449">在 Microsoft.BizTalk.ApplicationDeployment.Engine.dll 后追加框架的路径。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-449">Appends the path of framework with Microsoft.BizTalk.ApplicationDeployment.Engine.dll.</span></span>|  
|<span data-ttu-id="bb6f8-450">RestoreRegsvcsDeployment</span><span class="sxs-lookup"><span data-stu-id="bb6f8-450">RestoreRegsvcsDeployment</span></span>|<span data-ttu-id="bb6f8-451">在 Microsoft.BizTalk.ApplicationDeployment.Engine.dll 后追加框架的路径。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-451">Appends the path of framework with Microsoft.BizTalk.ApplicationDeployment.Engine.dll.</span></span>|  
|<span data-ttu-id="bb6f8-452">BrandSKURollback</span><span class="sxs-lookup"><span data-stu-id="bb6f8-452">BrandSKURollback</span></span>|<span data-ttu-id="bb6f8-453">在发生安装失败时，回滚注册的 SKU 信息。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-453">Rollbacks registered SKU information if installation failure occurs.</span></span>|  
|<span data-ttu-id="bb6f8-454">CA_RestartServices_rollback</span><span class="sxs-lookup"><span data-stu-id="bb6f8-454">CA_RestartServices_rollback</span></span>|<span data-ttu-id="bb6f8-455">重新启动停止的服务。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-455">Restarts the stopped services.</span></span>|  
|<span data-ttu-id="bb6f8-456">RemoveSKURollback</span><span class="sxs-lookup"><span data-stu-id="bb6f8-456">RemoveSKURollback</span></span>|<span data-ttu-id="bb6f8-457">更新注册表中的 SKU 值。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-457">Updates the SKU values from the registry.</span></span>|  
|<span data-ttu-id="bb6f8-458">BAM_Res_Perf_Silent</span><span class="sxs-lookup"><span data-stu-id="bb6f8-458">BAM_Res_Perf_Silent</span></span>|<span data-ttu-id="bb6f8-459">在无提示安装过程中将 Microsoft.BizTalk.Bam.EventObservation.dll 注册为 BAM 性能计数器 DLL。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-459">Registers Microsoft.BizTalk.Bam.EventObservation.dll as the BAM performance counter DLLs during silent installation.</span></span>|  
|<span data-ttu-id="bb6f8-460">BAM_Rollback_Perf</span><span class="sxs-lookup"><span data-stu-id="bb6f8-460">BAM_Rollback_Perf</span></span>|<span data-ttu-id="bb6f8-461">注销作为 BAM 性能计数器 DLL 的 Microsoft.BizTalk.Bam.EventObservation.dll</span><span class="sxs-lookup"><span data-stu-id="bb6f8-461">Unregisters  Microsoft.BizTalk.Bam.EventObservation.dll as the BAM performance counter DLL</span></span>|  
|<span data-ttu-id="bb6f8-462">RBKRegsvcsMQSAdapter</span><span class="sxs-lookup"><span data-stu-id="bb6f8-462">RBKRegsvcsMQSAdapter</span></span>|<span data-ttu-id="bb6f8-463">对给定二进制文件运行 regsvcs.exe。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-463">Runs regsvcs.exe on a given binary.</span></span>|  
|<span data-ttu-id="bb6f8-464">RBKRegsvcsSQLAdapter</span><span class="sxs-lookup"><span data-stu-id="bb6f8-464">RBKRegsvcsSQLAdapter</span></span>|<span data-ttu-id="bb6f8-465">对给定二进制文件运行 regsvcs.exe。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-465">Runs regsvcs.exe on a given binary.</span></span>|  
|<span data-ttu-id="bb6f8-466">RestoreBTSCounters</span><span class="sxs-lookup"><span data-stu-id="bb6f8-466">RestoreBTSCounters</span></span>|<span data-ttu-id="bb6f8-467">还原包含性能计数器 .ini 文件名的属性。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-467">Restores the property with the performance counter .ini file name.</span></span>|  
|<span data-ttu-id="bb6f8-468">RollbackBTSCounters</span><span class="sxs-lookup"><span data-stu-id="bb6f8-468">RollbackBTSCounters</span></span>|<span data-ttu-id="bb6f8-469">运行命令 unlodctr BTSSvc.3.0。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-469">Runs command unlodctr BTSSvc.3.0.</span></span>|  
|<span data-ttu-id="bb6f8-470">RollbackRegsvcsApplicationDeployment</span><span class="sxs-lookup"><span data-stu-id="bb6f8-470">RollbackRegsvcsApplicationDeployment</span></span>|<span data-ttu-id="bb6f8-471">设置 [FrameworkPath] &#124;[INSTALLDIR]对于失败的安装方案的 Microsoft.BizTalk.ApplicationDeployment.Engine.dll。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-471">Sets up [FrameworkPath]&#124;[INSTALLDIR]Microsoft.BizTalk.ApplicationDeployment.Engine.dll for the failed installation scenarios.</span></span>|  
|<span data-ttu-id="bb6f8-472">RollbackRegsvcsDeployment</span><span class="sxs-lookup"><span data-stu-id="bb6f8-472">RollbackRegsvcsDeployment</span></span>|<span data-ttu-id="bb6f8-473">在卸载/回滚方案过程中调用 regsvcs.exe。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-473">Invokes regsvcs.exe during uninstall/rollback scenarios.</span></span>|  
|<span data-ttu-id="bb6f8-474">WMI_Restore_MSBTS_Silent</span><span class="sxs-lookup"><span data-stu-id="bb6f8-474">WMI_Restore_MSBTS_Silent</span></span>|<span data-ttu-id="bb6f8-475">调用 mofcomp 以注册 WMI 架构</span><span class="sxs-lookup"><span data-stu-id="bb6f8-475">Calls mofcomp to register WMI schemas</span></span>|  
|<span data-ttu-id="bb6f8-476">WMI_Rollback_MSBTS</span><span class="sxs-lookup"><span data-stu-id="bb6f8-476">WMI_Rollback_MSBTS</span></span>|<span data-ttu-id="bb6f8-477">从 WMI 中删除 BizTalk Server 命名空间。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-477">Removes BizTalk Server namespace from WMI.</span></span>|  
|<span data-ttu-id="bb6f8-478">CA_RestartServices_commit</span><span class="sxs-lookup"><span data-stu-id="bb6f8-478">CA_RestartServices_commit</span></span>|<span data-ttu-id="bb6f8-479">重新启动停止的服务</span><span class="sxs-lookup"><span data-stu-id="bb6f8-479">Restarts the stopped services</span></span>|  
|<span data-ttu-id="bb6f8-480">DevenvSetup</span><span class="sxs-lookup"><span data-stu-id="bb6f8-480">DevenvSetup</span></span>|<span data-ttu-id="bb6f8-481">在 BizTalk Server 安装/卸载过程中都运行 DevEnv.exe /Setup /resetskippkgs。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-481">Runs DevEnv.exe /Setup /resetskippkgs both during BizTalk Server install/uninstall process.</span></span>|  
|<span data-ttu-id="bb6f8-482">ExecXmlConfig</span><span class="sxs-lookup"><span data-stu-id="bb6f8-482">ExecXmlConfig</span></span>|<span data-ttu-id="bb6f8-483">用于 machine.config 进行配置更改以便获得与 RFID 相关的数据。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-483">Used to make configuration changes to machine.config for RFID related data.</span></span>|  
|<span data-ttu-id="bb6f8-484">ExecXmlConfigRollback</span><span class="sxs-lookup"><span data-stu-id="bb6f8-484">ExecXmlConfigRollback</span></span>|<span data-ttu-id="bb6f8-485">用于 machine.config 进行配置更改以便获得与 RFID 相关的数据。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-485">Used to make configuration changes to machine.config for RFID related data.</span></span>|  
  
#### <a name="running-biztalk-components"></a><span data-ttu-id="bb6f8-486">运行 BizTalk 组件</span><span class="sxs-lookup"><span data-stu-id="bb6f8-486">Running BizTalk Components</span></span>  
 <span data-ttu-id="bb6f8-487">下表列出了必须使用管理权限或最高可用权限运行的 BizTalk 组件。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-487">The following table lists BizTalk components that must be run using administrative privileges or with highest available privilege.</span></span>  
  
|<span data-ttu-id="bb6f8-488">文件夹路径</span><span class="sxs-lookup"><span data-stu-id="bb6f8-488">Folder path</span></span>|<span data-ttu-id="bb6f8-489">文件名</span><span class="sxs-lookup"><span data-stu-id="bb6f8-489">File name</span></span>|<span data-ttu-id="bb6f8-490">用户特权</span><span class="sxs-lookup"><span data-stu-id="bb6f8-490">User privileges</span></span>|  
|-----------------|---------------|---------------------|  
|<span data-ttu-id="bb6f8-491">\Program 文件 (x86) \common shared\Help 9\Microsoft 文档资源管理器 2008年</span><span class="sxs-lookup"><span data-stu-id="bb6f8-491">\Program Files (x86)\Common Files\Microsoft shared\Help 9\Microsoft Document Explorer 2008</span></span>|<span data-ttu-id="bb6f8-492">Install.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-492">Install.exe</span></span>|<span data-ttu-id="bb6f8-493">最高可用权限</span><span class="sxs-lookup"><span data-stu-id="bb6f8-493">Highest available privilege</span></span>|  
|<span data-ttu-id="bb6f8-494">\Program files (x86) \Microsoft BizTalk Server*你的版本*</span><span class="sxs-lookup"><span data-stu-id="bb6f8-494">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="bb6f8-495">BTSHatApp.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-495">BTSHatApp.exe</span></span>|<span data-ttu-id="bb6f8-496">最高可用权限</span><span class="sxs-lookup"><span data-stu-id="bb6f8-496">Highest available privilege</span></span>|  
|<span data-ttu-id="bb6f8-497">\Program files (x86) \Microsoft BizTalk Server*你的版本*</span><span class="sxs-lookup"><span data-stu-id="bb6f8-497">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="bb6f8-498">BTSMMCLauncher.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-498">BTSMMCLauncher.exe</span></span>|<span data-ttu-id="bb6f8-499">最高可用权限</span><span class="sxs-lookup"><span data-stu-id="bb6f8-499">Highest available privilege</span></span>|  
|<span data-ttu-id="bb6f8-500">\Program files (x86) \Microsoft BizTalk Server*你的版本*</span><span class="sxs-lookup"><span data-stu-id="bb6f8-500">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="bb6f8-501">BtsWcfServicePublishingWizard.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-501">BtsWcfServicePublishingWizard.exe</span></span>|<span data-ttu-id="bb6f8-502">最高可用权限</span><span class="sxs-lookup"><span data-stu-id="bb6f8-502">Highest available privilege</span></span>|  
|<span data-ttu-id="bb6f8-503">\Program files (x86) \Microsoft BizTalk Server*你的版本*</span><span class="sxs-lookup"><span data-stu-id="bb6f8-503">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="bb6f8-504">BTSWebSvcWiz.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-504">BTSWebSvcWiz.exe</span></span>|<span data-ttu-id="bb6f8-505">最高可用权限</span><span class="sxs-lookup"><span data-stu-id="bb6f8-505">Highest available privilege</span></span>|  
|<span data-ttu-id="bb6f8-506">\Program files (x86) \Microsoft BizTalk Server*你的版本*</span><span class="sxs-lookup"><span data-stu-id="bb6f8-506">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="bb6f8-507">Configuration.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-507">Configuration.exe</span></span>|<span data-ttu-id="bb6f8-508">最高可用权限</span><span class="sxs-lookup"><span data-stu-id="bb6f8-508">Highest available privilege</span></span>|  
|<span data-ttu-id="bb6f8-509">\Program files (x86) \Microsoft BizTalk Server*你的版本*</span><span class="sxs-lookup"><span data-stu-id="bb6f8-509">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="bb6f8-510">REDeployWiz.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-510">REDeployWiz.exe</span></span>|<span data-ttu-id="bb6f8-511">最高可用权限</span><span class="sxs-lookup"><span data-stu-id="bb6f8-511">Highest available privilege</span></span>|  
|<span data-ttu-id="bb6f8-512">\Program files (x86) \Microsoft BizTalk Server*你的版本*</span><span class="sxs-lookup"><span data-stu-id="bb6f8-512">\Program Files (x86)\Microsoft BizTalk Server *your version*</span></span>|<span data-ttu-id="bb6f8-513">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-513">Setup.exe</span></span>|<span data-ttu-id="bb6f8-514">管理权限</span><span class="sxs-lookup"><span data-stu-id="bb6f8-514">Administrative privilege</span></span>|  
|<span data-ttu-id="bb6f8-515">\Program files (x86) \Microsoft BizTalk Server*你版本*\XSD Schema\EDI</span><span class="sxs-lookup"><span data-stu-id="bb6f8-515">\Program Files (x86)\Microsoft BizTalk Server *your version*\XSD Schema\EDI</span></span>|<span data-ttu-id="bb6f8-516">MicrosoftEdiXSDTemplates.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-516">MicrosoftEdiXSDTemplates.exe</span></span>|<span data-ttu-id="bb6f8-517">Self-extracting .exe 文件。</span><span class="sxs-lookup"><span data-stu-id="bb6f8-517">Self-extracting .exe file.</span></span>|  
|<span data-ttu-id="bb6f8-518">\Program 文件 (x86) \Microsoft UDDI Services\config</span><span class="sxs-lookup"><span data-stu-id="bb6f8-518">\Program Files (x86)\Microsoft UDDI Services\config</span></span>|<span data-ttu-id="bb6f8-519">Configuration .exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-519">Configuration .exe</span></span>|<span data-ttu-id="bb6f8-520">管理权限</span><span class="sxs-lookup"><span data-stu-id="bb6f8-520">Administrative privilege</span></span>|  
|<span data-ttu-id="bb6f8-521">Files\ Microsoft BizTalk RFID\bin</span><span class="sxs-lookup"><span data-stu-id="bb6f8-521">\Program Files\ Microsoft BizTalk RFID\bin</span></span>|<span data-ttu-id="bb6f8-522">BTSMMCLauncher.exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-522">BTSMMCLauncher.exe</span></span>|<span data-ttu-id="bb6f8-523">最高可用权限</span><span class="sxs-lookup"><span data-stu-id="bb6f8-523">Highest available privilege</span></span>|  
|<span data-ttu-id="bb6f8-524">Files\microsoft BizTalk RFID\BREConfi 配置</span><span class="sxs-lookup"><span data-stu-id="bb6f8-524">\Program Files\Microsoft BizTalk RFID\BREConfi guration</span></span>|<span data-ttu-id="bb6f8-525">Configuration .exe</span><span class="sxs-lookup"><span data-stu-id="bb6f8-525">Configuration .exe</span></span>|<span data-ttu-id="bb6f8-526">管理权限</span><span class="sxs-lookup"><span data-stu-id="bb6f8-526">Administrative privilege</span></span>|  

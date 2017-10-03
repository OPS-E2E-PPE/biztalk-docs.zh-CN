---
title: "解决 SQL Server 的权限问题的准则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60c24512-5f65-4363-b806-8dd52b22f179
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db02fd2a981d3f1dc34924e680caf5926f67871a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="guidelines-for-resolving-sql-server-permissions-problems"></a><span data-ttu-id="a1691-102">解决 SQL Server 权限问题的准则</span><span class="sxs-lookup"><span data-stu-id="a1691-102">Guidelines for Resolving SQL Server Permissions Problems</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="a1691-103"> 在运行时操作中大量使用了 Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 数据库，因此，正确设置 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 权限非常重要。</span><span class="sxs-lookup"><span data-stu-id="a1691-103"> makes extensive use of Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases for run-time operations and as such, it is important that the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] permissions are set correctly.</span></span> <span data-ttu-id="a1691-104">本主题提供了最大限度地减少 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 权限问题的一些通用准则以及操作步骤，您可依照这些步骤来解决影响 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 权限问题。</span><span class="sxs-lookup"><span data-stu-id="a1691-104">This topic provides some general guidelines for minimizing [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] permissions problems and steps that you can follow to troubleshoot [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] permissions problems that affect [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="general-guidelines"></a><span data-ttu-id="a1691-105">通用指导原则</span><span class="sxs-lookup"><span data-stu-id="a1691-105">General Guidelines</span></span>  
  
-   <span data-ttu-id="a1691-106">**使用 BizTalk Server 的多计算机安装的域用户和组**</span><span class="sxs-lookup"><span data-stu-id="a1691-106">**Use domain users and groups for a multicomputer installation of BizTalk Server**</span></span>  
  
     <span data-ttu-id="a1691-107">如果要配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使其在多计算机方案中运行（例如 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 安装在不同的计算机上），则必须使用域用户组和帐户。</span><span class="sxs-lookup"><span data-stu-id="a1691-107">You must use domain user groups and accounts when configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to run in a multicomputer scenario, for example, where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are installed on separate computers.</span></span> <span data-ttu-id="a1691-108">请不要尝试配置或运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中*传递*凭此可以避免使用域组和帐户的每台计算机创建配对的用户名和密码的身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="a1691-108">Do not attempt to configure or run [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a *pass-through* authentication scenario whereby matching pairs of usernames and passwords are created on each computer to avoid using domain groups and accounts.</span></span> <span data-ttu-id="a1691-109">虽然在某些情况下，此类直通方案可能运行正常；但在其他情况下，这将导致 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 失败并且不是支持的配置。</span><span class="sxs-lookup"><span data-stu-id="a1691-109">While such a pass-through scenario may appear to function correctly in some scenarios, this will cause [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to fail in other scenarios and is not a supported configuration.</span></span>  
  
     <span data-ttu-id="a1691-110">有关安装和配置详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在多计算机配置中，下载安装指南，网址[相关到 BizTalk Server 2013 的指南安装](http://go.microsoft.com/fwlink/p/?LinkID=269582)。</span><span class="sxs-lookup"><span data-stu-id="a1691-110">For more information about installing and configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a multicomputer configuration, download the Installation Guide at [Installation Guides Related to BizTalk Server 2013](http://go.microsoft.com/fwlink/p/?LinkID=269582).</span></span>  
  
-   <span data-ttu-id="a1691-111">**确保在相应的 SQL Server 角色中定义的相应的 Windows 用户和组**</span><span class="sxs-lookup"><span data-stu-id="a1691-111">**Ensure that the appropriate Windows users and groups are defined in the appropriate SQL Server roles**</span></span>  
  
     <span data-ttu-id="a1691-112">请验证正确[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]主题中的表中列出的角色成员身份[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a1691-112">Verify correct [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] role membership as listed in the table in the topic [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="a1691-113">**用户 SQL Server 事件探查器诊断权限问题**</span><span class="sxs-lookup"><span data-stu-id="a1691-113">**User SQL Server Profiler to diagnose permissions problems**</span></span>  
  
     <span data-ttu-id="a1691-114">设置[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]探查器跟踪来监视**审核登录失败事件**来收集有关权限失败的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="a1691-114">Set up a [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler trace to monitor the **Audit Login Failed Event** to gather detailed information about permissions failures.</span></span> <span data-ttu-id="a1691-115">有关如何使用信息[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]探查器，请参阅[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="a1691-115">For information about how to use [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Profiler, see the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] documentation.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="a1691-116">已知问题</span><span class="sxs-lookup"><span data-stu-id="a1691-116">Known Issues</span></span>  
  
#### <a name="the-sql-server-jobs-that-are-installed-with-biztalk-server-fail-to-execute"></a><span data-ttu-id="a1691-117">随 BizTalk Server 一起安装的 SQL Server 作业无法执行</span><span class="sxs-lookup"><span data-stu-id="a1691-117">The SQL Server jobs that are installed with BizTalk Server fail to execute</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="a1691-118">问题</span><span class="sxs-lookup"><span data-stu-id="a1691-118">Problem</span></span>  
 <span data-ttu-id="a1691-119">随 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 一起安装的 SQL Server 作业失败，并在 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 应用程序日志中生成类似于以下内容的错误：</span><span class="sxs-lookup"><span data-stu-id="a1691-119">The SQL Server jobs that are installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] fail and errors similar to the following are generated in the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Application log:</span></span>  
  
 <span data-ttu-id="a1691-120">事件类型: 警告</span><span class="sxs-lookup"><span data-stu-id="a1691-120">Event Type: Warning</span></span>  
  
 <span data-ttu-id="a1691-121">事件源： SQLSERVERAGENT</span><span class="sxs-lookup"><span data-stu-id="a1691-121">Event Source: SQLSERVERAGENT</span></span>  
  
 <span data-ttu-id="a1691-122">事件类别： 作业引擎</span><span class="sxs-lookup"><span data-stu-id="a1691-122">Event Category: Job Engine</span></span>  
  
 <span data-ttu-id="a1691-123">事件 ID: 208</span><span class="sxs-lookup"><span data-stu-id="a1691-123">Event ID: 208</span></span>  
  
 <span data-ttu-id="a1691-124">2008-6 月 29 日日期：</span><span class="sxs-lookup"><span data-stu-id="a1691-124">Date: 6/29/2008</span></span>  
  
 <span data-ttu-id="a1691-125">时间： 下午 4:45:01</span><span class="sxs-lookup"><span data-stu-id="a1691-125">Time: 4:45:01 PM</span></span>  
  
 <span data-ttu-id="a1691-126">用户：无</span><span class="sxs-lookup"><span data-stu-id="a1691-126">User: N/A</span></span>  
  
 <span data-ttu-id="a1691-127">计算机： *sql Server*</span><span class="sxs-lookup"><span data-stu-id="a1691-127">Computer: *SQLServer*</span></span>  
  
 <span data-ttu-id="a1691-128">说明:</span><span class="sxs-lookup"><span data-stu-id="a1691-128">Description:</span></span>  
  
 <span data-ttu-id="a1691-129">SQL Server 计划作业“备份 BizTalk Server”</span><span class="sxs-lookup"><span data-stu-id="a1691-129">SQL Server Scheduled Job 'Backup BizTalk Server'</span></span>  
  
 <span data-ttu-id="a1691-130">(0x4AC7C44A48541443927A56C5C6699ECF) 的状态： 失败-调用： 2008年-6-29 13:45:01-消息： 作业失败。</span><span class="sxs-lookup"><span data-stu-id="a1691-130">(0x4AC7C44A48541443927A56C5C6699ECF) - Status: Failed - Invoked on: 2008-6-29 13:45:01 - Message: The job failed.</span></span>  <span data-ttu-id="a1691-131">Schedule 305 (MarkAndBackupLogSched) 调用了该作业。</span><span class="sxs-lookup"><span data-stu-id="a1691-131">The Job was invoked by Schedule 305 (MarkAndBackupLogSched).</span></span> <span data-ttu-id="a1691-132">最后运行的是步骤 1 (BackupFull)。</span><span class="sxs-lookup"><span data-stu-id="a1691-132">The last step to run was step 1 (BackupFull).</span></span>  
  
 <span data-ttu-id="a1691-133">**-和-**</span><span class="sxs-lookup"><span data-stu-id="a1691-133">**- and -**</span></span>  
  
 <span data-ttu-id="a1691-134">事件类型： 信息</span><span class="sxs-lookup"><span data-stu-id="a1691-134">Event Type: Information</span></span>  
  
 <span data-ttu-id="a1691-135">事件源： MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a1691-135">Event Source: MSSQLSERVER</span></span>  
  
 <span data-ttu-id="a1691-136">事件类别: (4)</span><span class="sxs-lookup"><span data-stu-id="a1691-136">Event Category: (4)</span></span>  
  
 <span data-ttu-id="a1691-137">事件 ID: 17055</span><span class="sxs-lookup"><span data-stu-id="a1691-137">Event ID: 17055</span></span>  
  
 <span data-ttu-id="a1691-138">2008-6 月 29 日日期：</span><span class="sxs-lookup"><span data-stu-id="a1691-138">Date: 6/29/2008</span></span>  
  
 <span data-ttu-id="a1691-139">时间： 下午 4:45:01</span><span class="sxs-lookup"><span data-stu-id="a1691-139">Time: 4:45:01 PM</span></span>  
  
 <span data-ttu-id="a1691-140">用户：无</span><span class="sxs-lookup"><span data-stu-id="a1691-140">User: N/A</span></span>  
  
 <span data-ttu-id="a1691-141">计算机： *sql Server*</span><span class="sxs-lookup"><span data-stu-id="a1691-141">Computer: *SQLServer*</span></span>  
  
 <span data-ttu-id="a1691-142">说明:</span><span class="sxs-lookup"><span data-stu-id="a1691-142">Description:</span></span>  
  
 <span data-ttu-id="a1691-143">18456： 用户 NT AUTHORITY\SYSTEM 登录失败。</span><span class="sxs-lookup"><span data-stu-id="a1691-143">18456: Login failed for user 'NT AUTHORITY\SYSTEM'.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="a1691-144">原因</span><span class="sxs-lookup"><span data-stu-id="a1691-144">Cause</span></span>  
 <span data-ttu-id="a1691-145">如果从 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 中删除了 BUILTIN\Administrators 登录名，则会产生此错误。</span><span class="sxs-lookup"><span data-stu-id="a1691-145">This error can occur if the BUILTIN\Administrators login has been removed from [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="a1691-146">如果 BUILTIN\Administrators 登录名被删除，则 sqlmaint.exe 将无法登录到 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，这将阻止 SQL 作业运行。</span><span class="sxs-lookup"><span data-stu-id="a1691-146">If the BUILTIN\Administrators login is deleted, sqlmaint.exe will be unable to logon to [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] which will prevent SQL jobs from running.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="a1691-147">解决方法</span><span class="sxs-lookup"><span data-stu-id="a1691-147">Resolution</span></span>  
 <span data-ttu-id="a1691-148">若要解决此问题，请重新创建 BUILTIN\Administrators 登录名，并将其添加到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库和 Master 数据库的 db_owner 角色。</span><span class="sxs-lookup"><span data-stu-id="a1691-148">To resolve this issue, re-create the BUILTIN\Administrators Login and add it to the db_owner role for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and the Master database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1691-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1691-149">See Also</span></span>  
 <span data-ttu-id="a1691-150">[故障排除 SQL Server](../core/troubleshooting-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="a1691-150">[Troubleshooting SQL Server](../core/troubleshooting-sql-server.md) </span></span>  
 [<span data-ttu-id="a1691-151">BizTalk Server 权限的疑难解答</span><span class="sxs-lookup"><span data-stu-id="a1691-151">Troubleshooting BizTalk Server Permissions</span></span>](../core/troubleshooting-biztalk-server-permissions.md)
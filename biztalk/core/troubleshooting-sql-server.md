---
title: "故障排除 SQL Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f6707c5-7c6e-4375-bfa6-9b1a86ec5e81
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66d6d35ac668a324ed28f7c9519b32812e10cb3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-sql-server"></a><span data-ttu-id="99b35-102">故障排除 SQL Server</span><span class="sxs-lookup"><span data-stu-id="99b35-102">Troubleshooting SQL Server</span></span>
<span data-ttu-id="99b35-103">影响 Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的大多数 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 问题主要分为以下几类：</span><span class="sxs-lookup"><span data-stu-id="99b35-103">The majority of Microsoft [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] issues that affect Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] fall into one of the following categories:</span></span>  
  
-   <span data-ttu-id="99b35-104">与连接相关的问题</span><span class="sxs-lookup"><span data-stu-id="99b35-104">Connectivity-related problems</span></span>  
  
-   <span data-ttu-id="99b35-105">与权限相关的问题</span><span class="sxs-lookup"><span data-stu-id="99b35-105">Permissions-related problems</span></span>  
  
-   <span data-ttu-id="99b35-106">数据库大小问题</span><span class="sxs-lookup"><span data-stu-id="99b35-106">Database-sizing problems</span></span>  
  
 <span data-ttu-id="99b35-107">本主题分别介绍这些类别以及可采取的解决这些相关问题的步骤。</span><span class="sxs-lookup"><span data-stu-id="99b35-107">This topic discusses each of these categories and steps that you can take to resolve the associated problems.</span></span>  
  
## <a name="connectivity-related-problems"></a><span data-ttu-id="99b35-108">与连接相关的问题</span><span class="sxs-lookup"><span data-stu-id="99b35-108">Connectivity-Related Problems</span></span>  
 <span data-ttu-id="99b35-109">以下是与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机和包含 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 数据库的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机之间的连接问题相关的最普遍的问题。 </span><span class="sxs-lookup"><span data-stu-id="99b35-109">The following issues are most commonly associated with connectivity problems between the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer and the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer that houses the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
#### <a name="errors-related-to-failed-transactions-or-communication-with-the-underlying-transaction-manager-errors-are-written-to-the-biztalk-server-application-log"></a><span data-ttu-id="99b35-110">与失败事务相关的错误或“与底层事务管理器通信”错误被写入到 BizTalk Server 应用程序日志</span><span class="sxs-lookup"><span data-stu-id="99b35-110">Errors related to failed transactions or "Communication with the underlying transaction manager" errors are written to the BizTalk Server Application log</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="99b35-111">问题</span><span class="sxs-lookup"><span data-stu-id="99b35-111">Problem</span></span>  
 <span data-ttu-id="99b35-112">MSDTC 事务失败或无法与基础事务管理器通信，该值指示的错误将写入[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序日志。</span><span class="sxs-lookup"><span data-stu-id="99b35-112">Errors indicating an MSDTC transaction failure or a failure to communicate with the underlying transaction manager are written to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application log.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="99b35-113">原因</span><span class="sxs-lookup"><span data-stu-id="99b35-113">Cause</span></span>  
 <span data-ttu-id="99b35-114">之间的 MSDTC 连接[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]已失败。</span><span class="sxs-lookup"><span data-stu-id="99b35-114">MSDTC connectivity between [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]and[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] has failed.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="99b35-115">解决方法</span><span class="sxs-lookup"><span data-stu-id="99b35-115">Resolution</span></span>  
 <span data-ttu-id="99b35-116">有关疑难解答 MSDTC 之间的连接信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]保存的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[问题疑难解答与 MSDTC](../core/troubleshooting-problems-with-msdtc.md)。</span><span class="sxs-lookup"><span data-stu-id="99b35-116">For information about troubleshooting MSDTC connectivity between the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer and the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer that houses the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>  
  
#### <a name="error-a-connection-was-successfully-established-with-the-server-but-then-an-error-occurred-during-the-pre-login-handshake-occurs-when-connecting-to-remote-sql-server-databases-on-sql-server-2008"></a><span data-ttu-id="99b35-117">连接到 SQL Server 2008 上的远程 SQL Server 数据库时发生以下错误：“已与服务器成功建立连接，但是在预登录握手时发生错误”</span><span class="sxs-lookup"><span data-stu-id="99b35-117">Error "A connection was successfully established with the server, but then an error occurred during the pre-login handshake" occurs when connecting to remote SQL Server databases on SQL Server 2008</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="99b35-118">问题</span><span class="sxs-lookup"><span data-stu-id="99b35-118">Problem</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="99b35-119">失去与远程连接[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]保存的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成数据库和一条错误消息：</span><span class="sxs-lookup"><span data-stu-id="99b35-119"> loses connectivity with a remote [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer that houses the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and an error message is generated:</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="99b35-120">原因</span><span class="sxs-lookup"><span data-stu-id="99b35-120">Cause</span></span>  
 <span data-ttu-id="99b35-121">如果出现以下条件中的一个或多个，就可能出现此问题：</span><span class="sxs-lookup"><span data-stu-id="99b35-121">This problem may occur if one or more of the following conditions is true:</span></span>  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]<span data-ttu-id="99b35-122">未配置为接受远程连接。</span><span class="sxs-lookup"><span data-stu-id="99b35-122"> is not configured to accept remote connections.</span></span>  
  
-   <span data-ttu-id="99b35-123">所需协议[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]上或者未启用[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]正在运行的客户端计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="99b35-123">The necessary protocols for [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are not enabled on either the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer or the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] client computer that is running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="99b35-124">解决方法</span><span class="sxs-lookup"><span data-stu-id="99b35-124">Resolution</span></span>  
 <span data-ttu-id="99b35-125">请遵循以下步骤来解决此问题：</span><span class="sxs-lookup"><span data-stu-id="99b35-125">Follow these steps to resolve this problem:</span></span>  
  
-   <span data-ttu-id="99b35-126">**SQL Server 外围应用配置**工具不可用 SQL Server 2008 上。</span><span class="sxs-lookup"><span data-stu-id="99b35-126">The **SQL Server Surface Area Configuration** tool is not available on SQL Server 2008.</span></span> <span data-ttu-id="99b35-127">若要远程连接 SQL Server 2008 计算机上的 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，请按照 SQL Server 2008 联机帮助中的说明执行操作。</span><span class="sxs-lookup"><span data-stu-id="99b35-127">To enable remote connections for [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] on a SQL Server 2008 computer follow the instructions in the SQL Server 2008 online help.</span></span>  
  
-   <span data-ttu-id="99b35-128">使用**SQL Server 配置管理器**工具来启用**TCP/IP**和/或**Named Pipes**协议上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="99b35-128">Use the **SQL Server Configuration Manager** tool to enable the **TCP/IP** and/or the **Named Pipes** protocols on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
    1.  <span data-ttu-id="99b35-129">单击**启动**，指向**所有程序**，然后单击**SQL Server 配置管理器**。</span><span class="sxs-lookup"><span data-stu-id="99b35-129">Click **Start**, point to **All Programs**, and click **SQL Server Configuration Manager**.</span></span>  
  
    2.  <span data-ttu-id="99b35-130">单击以展开**SQL Server 网络配置**，然后单击**MSSQLSERVER 的协议**。</span><span class="sxs-lookup"><span data-stu-id="99b35-130">Click to expand **SQL Server Network Configuration** and then click **Protocols for MSSQLSERVER**.</span></span>  
  
    3.  <span data-ttu-id="99b35-131">右键单击**TCP/IP**协议，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="99b35-131">Right-click the **TCP/IP** protocol and then click **Enable**.</span></span>  
  
    4.  <span data-ttu-id="99b35-132">右键单击**Named Pipes**协议，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="99b35-132">Right-click the **Named Pipes** protocol and then click **Enable**.</span></span>  
  
    5.  <span data-ttu-id="99b35-133">关闭**SQL Server 配置管理器**工具。</span><span class="sxs-lookup"><span data-stu-id="99b35-133">Close the **SQL Server Configuration Manager** tool.</span></span>  
  
-   <span data-ttu-id="99b35-134">使用**SQL Server 配置管理器**工具来启用**TCP/IP**和/或**Named Pipes**协议上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]运行的客户端计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99b35-134">Use the **SQL Server Configuration Manager** tool to enable the **TCP/IP** and/or the **Named Pipes** protocols on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] client computer that is running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    1.  <span data-ttu-id="99b35-135">单击**启动**，指向**所有程序**，然后单击**SQL Server 配置管理器**。</span><span class="sxs-lookup"><span data-stu-id="99b35-135">Click **Start**, point to **All Programs**, and click **SQL Server Configuration Manager**.</span></span>  
  
    2.  <span data-ttu-id="99b35-136">单击以展开**SQL Server 网络配置**，然后单击**ClientProtocols**。</span><span class="sxs-lookup"><span data-stu-id="99b35-136">Click to expand **SQL Server Network Configuration** and then click **ClientProtocols**.</span></span>  
  
    3.  <span data-ttu-id="99b35-137">右键单击**TCP/IP**协议，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="99b35-137">Right-click the **TCP/IP** protocol and then click **Enable**.</span></span>  
  
    4.  <span data-ttu-id="99b35-138">右键单击**Named Pipes**协议，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="99b35-138">Right-click the **Named Pipes** protocol and then click **Enable**.</span></span>  
  
    5.  <span data-ttu-id="99b35-139">关闭**SQL Server 配置管理器**工具。</span><span class="sxs-lookup"><span data-stu-id="99b35-139">Close the **SQL Server Configuration Manager** tool.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99b35-140">确保至少一个协议上[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]正在运行的客户端计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]匹配上启用的协议[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="99b35-140">Ensure that at least one of the protocols on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] client computer that is running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] matches the protocols enabled on the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer.</span></span>  
  
#### <a name="a-biztalk-host-instance-fails-and-a-general-network-error-is-written-to-the-application-log-when-the-biztalk-server-based-server-processes-a-high-volume-of-documents"></a><span data-ttu-id="99b35-141">BizTalk 主机实例失败，并且基于 BizTalk Server 的服务器处理大量的文档时，"常规网络"错误会写入到应用程序日志</span><span class="sxs-lookup"><span data-stu-id="99b35-141">A BizTalk host instance fails and a "General Network" error is written to the Application log when the BizTalk Server-based server processes a high volume of documents</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="99b35-142">问题</span><span class="sxs-lookup"><span data-stu-id="99b35-142">Problem</span></span>  
 <span data-ttu-id="99b35-143">处理大量文档时，BizTalk 主机实例失败，并且一个“常规网络”错误被写入应用程序日志。</span><span class="sxs-lookup"><span data-stu-id="99b35-143">When processing a high volume of documents, a BizTalk host instance fails, and a "General Network" error is written to the Application log.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="99b35-144">原因</span><span class="sxs-lookup"><span data-stu-id="99b35-144">Cause</span></span>  
 <span data-ttu-id="99b35-145">出现此问题的原因是 Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 实现了一个安全功能，该功能可以减小与服务器的并发 TCP/IP 连接队列的大小。</span><span class="sxs-lookup"><span data-stu-id="99b35-145">This issue occurs because Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] implements a security feature that reduces the size of the queue for concurrent TCP/IP connections to the server.</span></span> <span data-ttu-id="99b35-146">此功能有助于防止拒绝服务攻击。</span><span class="sxs-lookup"><span data-stu-id="99b35-146">This feature helps prevent denial of service attacks.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="99b35-147">解决方法</span><span class="sxs-lookup"><span data-stu-id="99b35-147">Resolution</span></span>  
 <span data-ttu-id="99b35-148">有关解决此问题的详细信息，请参阅[避免 DBNETLIB 异常](../core/avoiding-dbnetlib-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="99b35-148">For more information about resolving this issue, see [Avoiding DBNETLIB Exceptions](../core/avoiding-dbnetlib-exceptions.md).</span></span>  
  
## <a name="permissions-related-problems"></a><span data-ttu-id="99b35-149">与权限相关的问题</span><span class="sxs-lookup"><span data-stu-id="99b35-149">Permissions-Related Problems</span></span>  
  
#### <a name="biztalk-server-run-time-or-design-time-operations-fail-and-a-cannot-open-database-requested-in-login-database-error-is-written-to-the-application-log-of-the-biztalk-server-or-sql-server-computer"></a><span data-ttu-id="99b35-150">运行时或设计时操作失败的 BizTalk Server 和一个"无法打开登录中所请求的数据库\<数据库 >"到 BizTalk Server 或 SQL Server 计算机的应用程序日志写入错误</span><span class="sxs-lookup"><span data-stu-id="99b35-150">BizTalk Server run-time or design-time operations fail and a "cannot open database requested in login \<database>" error is written to the Application log of the BizTalk Server or SQL Server computer</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="99b35-151">问题</span><span class="sxs-lookup"><span data-stu-id="99b35-151">Problem</span></span>  
 <span data-ttu-id="99b35-152">运行时或设计时操作将失败，出现类似于以下的错误写入到的应用程序日志[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]计算机：</span><span class="sxs-lookup"><span data-stu-id="99b35-152">A run-time or design-time operation fails and an error similar to the following is written to the application log of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computer:</span></span>  
  
 <span data-ttu-id="99b35-153">无法打开登录中所请求的数据库\<*数据库*>。</span><span class="sxs-lookup"><span data-stu-id="99b35-153">Cannot open database requested in login \<*database*>.</span></span> <span data-ttu-id="99b35-154">登录失败。</span><span class="sxs-lookup"><span data-stu-id="99b35-154">Login fails.</span></span>   
<span data-ttu-id="99b35-155">用户登录失败\<*用户名*>。</span><span class="sxs-lookup"><span data-stu-id="99b35-155">Login failed for user \<*username*>.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="99b35-156">原因</span><span class="sxs-lookup"><span data-stu-id="99b35-156">Cause</span></span>  
 <span data-ttu-id="99b35-157">如果指定的帐户不属于相应的 Windows 组，可能出现此错误或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]角色。</span><span class="sxs-lookup"><span data-stu-id="99b35-157">This error can occur if the specified account does not belong to the appropriate Windows group or [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] role.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="99b35-158">解决方法</span><span class="sxs-lookup"><span data-stu-id="99b35-158">Resolution</span></span>  
 <span data-ttu-id="99b35-159">确保指定的帐户是相应的 Windows 组的成员或[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]角色。</span><span class="sxs-lookup"><span data-stu-id="99b35-159">Ensure that the specified account is a member of the appropriate Windows group or [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] role.</span></span> <span data-ttu-id="99b35-160">有关相应的成员资格的详细信息，请参阅[Windows 组和 BizTalk Server 中的用户帐户](../core/windows-groups-and-user-accounts-in-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="99b35-160">For more information about the appropriate memberships, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
## <a name="database-sizing-problems"></a><span data-ttu-id="99b35-161">关于数据库大小的问题</span><span class="sxs-lookup"><span data-stu-id="99b35-161">Database-Sizing Problems</span></span>  
 <span data-ttu-id="99b35-162">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库增长时取消选中然后的性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境将会受到不利影响。</span><span class="sxs-lookup"><span data-stu-id="99b35-162">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases grow unchecked then the performance of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment will be adversely affected.</span></span> <span data-ttu-id="99b35-163">请遵循以下步骤来管理 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库的增长。</span><span class="sxs-lookup"><span data-stu-id="99b35-163">Follow the steps below to manage the growth of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
#### <a name="the-biztalk-server-messagebox-database-is-growing-unchecked-and-impacting-overall-performance"></a><span data-ttu-id="99b35-164">BizTalk Server MessageBox 数据库不断无限增长，会影响到整体性能。</span><span class="sxs-lookup"><span data-stu-id="99b35-164">The BizTalk Server MessageBox database is growing unchecked and impacting overall performance</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="99b35-165">问题</span><span class="sxs-lookup"><span data-stu-id="99b35-165">Problem</span></span>  
 <span data-ttu-id="99b35-166">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox 数据库的增长会对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境的性能产生不利影响。</span><span class="sxs-lookup"><span data-stu-id="99b35-166">Growth of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox database is adversely affecting performance of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="99b35-167">原因</span><span class="sxs-lookup"><span data-stu-id="99b35-167">Cause</span></span>  
 <span data-ttu-id="99b35-168">如果 SQL 代理作业的维护，会出现此问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库未运行。</span><span class="sxs-lookup"><span data-stu-id="99b35-168">This problem can occur if the SQL Agent jobs that maintain the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are not running.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="99b35-169">解决方法</span><span class="sxs-lookup"><span data-stu-id="99b35-169">Resolution</span></span>  
 <span data-ttu-id="99b35-170">确保维护的 SQL 代理作业[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库正在运行。</span><span class="sxs-lookup"><span data-stu-id="99b35-170">Ensure that the SQL Agent jobs that maintain the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases are running.</span></span> <span data-ttu-id="99b35-171">请参阅[数据库结构和作业](../core/database-structure-and-jobs.md)有关与安装的 SQL 代理作业的完整列表[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="99b35-171">See [Database Structure and Jobs](../core/database-structure-and-jobs.md) for a complete list of the SQL Agent jobs that are installed with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
#### <a name="the-biztalk-server-tracking-database-is-growing-unchecked-and-impacting-overall-performance"></a><span data-ttu-id="99b35-172">BizTalk Server 跟踪数据库不断无限增长，会影响到整体性能。</span><span class="sxs-lookup"><span data-stu-id="99b35-172">The BizTalk Server tracking database is growing unchecked and impacting overall performance</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="99b35-173">问题</span><span class="sxs-lookup"><span data-stu-id="99b35-173">Problem</span></span>  
 <span data-ttu-id="99b35-174">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]跟踪数据库的增长未选中状态和有不利影响的总体性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="99b35-174">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tracking database is growing unchecked and is adversely affecting the overall performance of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="99b35-175">原因</span><span class="sxs-lookup"><span data-stu-id="99b35-175">Cause</span></span>  
 <span data-ttu-id="99b35-176">如果不采取的步骤以清除和存档，会出现此问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="99b35-176">This problem can occur if steps are not taken to purge and archive the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tracking database.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="99b35-177">解决方法</span><span class="sxs-lookup"><span data-stu-id="99b35-177">Resolution</span></span>  
 <span data-ttu-id="99b35-178">应采取措施以清除和存档[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="99b35-178">Steps should be taken to purge and archive the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tracking database.</span></span> <span data-ttu-id="99b35-179">请参阅[存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="99b35-179">See [Archiving and Purging the BizTalk Tracking Database](../core/archiving-and-purging-the-biztalk-tracking-database.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99b35-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99b35-180">See Also</span></span>  
 [<span data-ttu-id="99b35-181">解决 SQL Server 的权限问题的准则</span><span class="sxs-lookup"><span data-stu-id="99b35-181">Guidelines for Resolving SQL Server Permissions Problems</span></span>](../core/guidelines-for-resolving-sql-server-permissions-problems.md)
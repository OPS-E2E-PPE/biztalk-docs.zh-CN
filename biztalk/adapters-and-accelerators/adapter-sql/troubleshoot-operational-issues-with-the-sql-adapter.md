---
title: "使用 BizTalk 中的 SQL 适配器进行的操作问题故障排除 |Microsoft 文档"
description: "常见的问题和解决方法为 SQL 适配器 BizTalk 适配器包 (BAP) 中"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c75f85f4-cd03-4c6a-aac9-a6d02d3c3449
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82bfb1782c6bccdafe4f69326cddff0f49974386
ms.sourcegitcommit: 6b6d905bbef7796c850178e99ac293578bb58317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2017
---
# <a name="troubleshoot-operational-issues-with-the-sql-adapter"></a><span data-ttu-id="fa3f8-103">使用 SQL 适配器进行故障排除操作问题：</span><span class="sxs-lookup"><span data-stu-id="fa3f8-103">Troubleshoot Operational Issues with the SQL adapter</span></span>
<span data-ttu-id="fa3f8-104">本部分讨论如何使用故障排除方法来解决操作使用时可能遇到的错误[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-104">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="fa3f8-105">启用跟踪</span><span class="sxs-lookup"><span data-stu-id="fa3f8-105">Enabling Tracing</span></span>  
 <span data-ttu-id="fa3f8-106">必须启用跟踪之间适配器， [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，并且 SQL Server 以收集问题的任何有关的详细信息在遇到时使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-106">You must enable tracing between the adapter, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], and SQL Server to gather more information about any issues you encounter while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="fa3f8-107">有关跟踪中的支持的详细信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[诊断跟踪和消息日志记录中的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-107">For more information about tracing support in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Diagnostic Tracing and Message Logging in the SQL adapter](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="fa3f8-108">已知问题</span><span class="sxs-lookup"><span data-stu-id="fa3f8-108">Known Issues</span></span>  
 <span data-ttu-id="fa3f8-109">以下是使用时可能遇到的最常见错误[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，以及其可能的原因和解决方法。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-109">The following are the most common errors you might encounter when using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <span data-ttu-id="fa3f8-110"><a name="BKMK_SQLLoadBinding"></a>在加载适配器绑定错误</span><span class="sxs-lookup"><span data-stu-id="fa3f8-110"><a name="BKMK_SQLLoadBinding"></a> Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="fa3f8-111">**问题**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-111">**Problem**</span></span>  
  
 <span data-ttu-id="fa3f8-112">当你尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，你将收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="fa3f8-112">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you get the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="fa3f8-113">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-113">**Cause**</span></span>  
  
 <span data-ttu-id="fa3f8-114">当你尝试启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，WCF 加载所有已安装适配器的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-114">When you try to start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="fa3f8-115">反过来，适配器绑定都依赖于企业应用程序的特定客户端软件。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-115">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="fa3f8-116">如果你这样做将适配器安装中包含的所有适配器的典型或完全安装，可能会遇到此问题[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-116">You might face this issue if you did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="fa3f8-117">但是，可能只有一个企业应用程序安装 LOB 客户端库。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-117">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="fa3f8-118">因此，GUI 无法加载其他适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-118">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="fa3f8-119">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-119">**Resolution**</span></span>  
  
 <span data-ttu-id="fa3f8-120">请确保执行适配器安装需要适配器的自定义安装。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-120">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
###  <span data-ttu-id="fa3f8-121"><a name="BKMK_SQLDisplay"></a>SQL 适配器不会显示在列表中在 BizTalk Server 管理控制台中的适配器</span><span class="sxs-lookup"><span data-stu-id="fa3f8-121"><a name="BKMK_SQLDisplay"></a> The SQL adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="fa3f8-122">**问题**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-122">**Problem**</span></span>  
  
 <span data-ttu-id="fa3f8-123">与不同的是较早版本附带的适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]未显示在列表中中适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-123">Unlike the earlier version of the adapters shipped with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="fa3f8-124">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-124">**Cause**</span></span>  
  
 <span data-ttu-id="fa3f8-125">最新[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-125">The latest [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="fa3f8-126">因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，并因此，不会显示基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-126">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="fa3f8-127">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-127">**Resolution**</span></span>  
  
 <span data-ttu-id="fa3f8-128">你可以显式添加[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-128">You can explicitly add the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <span data-ttu-id="fa3f8-129"><a name="BKMK_MissingAction"></a>在 SQL Server 数据库上执行操作时出错</span><span class="sxs-lookup"><span data-stu-id="fa3f8-129"><a name="BKMK_MissingAction"></a> Error while performing operations on a SQL Server database</span></span>  
 <span data-ttu-id="fa3f8-130">**问题**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-130">**Problem**</span></span>  
  
 <span data-ttu-id="fa3f8-131">适配器执行针对 SQL Server 数据库使用的任何操作时将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-131">The adapter gives the following error when performing any operation on a SQL Server database using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="fa3f8-132">**有关[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-132">**For [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]**</span></span>  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 <span data-ttu-id="fa3f8-133">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-133">**Cause**</span></span>  
  
 <span data-ttu-id="fa3f8-134">未指定消息的 WCF 操作。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-134">The WCF action for the message is not specified.</span></span> <span data-ttu-id="fa3f8-135">WCF 需要为每个操作，在 LOB 应用程序上执行的操作会告知适配器指定的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-135">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="fa3f8-136">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-136">**Resolution**</span></span>  
  
 <span data-ttu-id="fa3f8-137">指定的 SOAP 操作中发送端口或 BizTalk 业务流程中的消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-137">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="fa3f8-138">有关说明，请参阅[配置 SQL 适配器的 SOAP 操作](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-138">For instructions, see [Configure the SOAP action for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md).</span></span> <span data-ttu-id="fa3f8-139">请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)若要查看的每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-139">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) to see a list of actions for each operation.</span></span>  
  
###  <span data-ttu-id="fa3f8-140"><a name="BKMK_SQLInvalidOp"></a>与 ErrorCode InvalidOperationException 执行 FILESTREAM 操作时 = 5</span><span class="sxs-lookup"><span data-stu-id="fa3f8-140"><a name="BKMK_SQLInvalidOp"></a> InvalidOperationException with ErrorCode=5 while performing FILESTREAM operations</span></span>  
 <span data-ttu-id="fa3f8-141">**问题**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-141">**Problem**</span></span>  
  
 <span data-ttu-id="fa3f8-142">使用时遇到以下错误[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行 FILESTREAM 操作。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-142">You get the following error while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to perform FILESTREAM operations.</span></span>  
  
```  
System.InvalidOperationException: OpenSqlFileStream returned error.  
ErrorCode:5  
  
```  
  
 <span data-ttu-id="fa3f8-143">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-143">**Cause**</span></span>  
  
 <span data-ttu-id="fa3f8-144">你可能指定用于连接到 SQL Server 数据库的数据库凭据。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-144">You might have specified database credentials to connect to the SQL Server database.</span></span> <span data-ttu-id="fa3f8-145">若要执行 FILESTREAM 操作，必须始终使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-145">To perform FILESTREAM operations, you must always use Windows Authentication.</span></span> <span data-ttu-id="fa3f8-146">错误代码"5"表示访问被拒绝由于不正确的凭据。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-146">The error code “5” denotes that access is denied because of incorrect credentials.</span></span> <span data-ttu-id="fa3f8-147">有关不同的错误代码的详细信息，请参阅[系统错误代码 (0-499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-147">For more information about the different error codes, see [System Error Codes (0-499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx).</span></span>
  
 <span data-ttu-id="fa3f8-148">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-148">**Resolution**</span></span>  
  
 <span data-ttu-id="fa3f8-149">使用 Windows 身份验证连接到 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-149">Use Windows Authentication to connect to the SQL Server database.</span></span> <span data-ttu-id="fa3f8-150">在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你可以做到这一点将用户名称和密码字段保留为空白 WCF 自定义或 WCF SQL 端口配置对话框中。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-150">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can do so by leaving the user name and password fields blank in the WCF-Custom or WCF-SQL port configuration dialog box.</span></span>  
  
###  <span data-ttu-id="fa3f8-151"><a name="BKMK_SQLPolling"></a>轮询操作不返回任何消息即使 PollingStatement 和 PolledDataAvailableStatement 为指定的有效语句</span><span class="sxs-lookup"><span data-stu-id="fa3f8-151"><a name="BKMK_SQLPolling"></a> Polling operation does not return any messages even if valid statements are specified for PollingStatement and PolledDataAvailableStatement</span></span>  
 <span data-ttu-id="fa3f8-152">**问题**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-152">**Problem**</span></span>  
  
 <span data-ttu-id="fa3f8-153">即使为 PollingStatement 和 PolledDataAvailableStatement 绑定属性指定有效的值，则适配器不从 SQL Server 收到轮询消息。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-153">Even if valid values are specified for the PollingStatement and PolledDataAvailableStatement binding properties, the adapter does not receive a polling message from SQL Server.</span></span>  
  
 <span data-ttu-id="fa3f8-154">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-154">**Cause**</span></span>  
  
 <span data-ttu-id="fa3f8-155">验证任何其他事务是否已在轮询适配器的表上获取锁。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-155">Verify whether any other transaction has taken a lock on the table that the adapter is polling.</span></span>  
  
 <span data-ttu-id="fa3f8-156">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-156">**Resolution**</span></span>  
  
 <span data-ttu-id="fa3f8-157">如果你想要轮询正在更新作为另一个事务的一部分的表，可以考虑使用"使用 (nolock)"参数作为 PolledDataAvailableStatement 绑定属性指定的查询的一部分，以确保即使施加锁定返回数据被另一个事务。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-157">If you want to poll a table that is being updated as part of another transaction, you can consider using “with (nolock)” parameter as part of the query specified for PolledDataAvailableStatement binding property to ensure that data is returned even if a lock is imposed by the other transaction.</span></span> <span data-ttu-id="fa3f8-158">有关详细信息，请参阅[中数据库引擎的锁定 SQL](https://msdn.microsoft.com/library/ms190615.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-158">For more information, see [SQL Locking in the Database Engine](https://msdn.microsoft.com/library/ms190615.aspx).</span></span>
  
###  <span data-ttu-id="fa3f8-159"><a name="BKMK_SQLSingleOp"></a>该适配器无法插入、 更新或删除单个操作使用 BizTalk Server 中的数据的大型卷</span><span class="sxs-lookup"><span data-stu-id="fa3f8-159"><a name="BKMK_SQLSingleOp"></a> The adapter fails to insert, update, or delete large volumes of data in a single operation using BizTalk Server</span></span>  
 <span data-ttu-id="fa3f8-160">**问题**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-160">**Problem**</span></span>  
  
 <span data-ttu-id="fa3f8-161">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]无法插入、 更新或删除在单个操作中使用的数据大容量[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-161">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] fails to insert, update, or delete large volumes of data in a single operation using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fa3f8-162">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-162">**Cause**</span></span>  
  
 <span data-ttu-id="fa3f8-163">插入、 更新或删除的大量数据可能需要时间和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]或的事务中正在执行该操作，可能会超时。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-163">Inserting, updating, or deleting large volumes of data may take time and the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] or the transaction in which the operation is being performed, may time out.</span></span>  
  
 <span data-ttu-id="fa3f8-164">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-164">**Resolution**</span></span>  
  
-   <span data-ttu-id="fa3f8-165">**有关[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-165">**For [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]**</span></span>  
  
    1.  <span data-ttu-id="fa3f8-166">在 machine.config 中指定的 WCF 适配器的超时值。导航到 machine.config 文件在下\<系统驱动器 >: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG 并添加如下所示的摘要。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-166">Specify the timeout for the WCF adapter in the machine.config. Navigate to the machine.config file under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG and add the excerpt that resembles the following.</span></span>  
  
        ```  
        <configuration>  
         \<system.transactions>  
          <machineSettings maxTimeout="02:00:00" />  
         \</system.transactions>  
        </configuration>  
        ```  
  
         <span data-ttu-id="fa3f8-167">使用此设置时，WCF 适配器超时设置为 2 小时。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-167">With this setting, the WCF adapter timeout is set to 2 hours.</span></span>  
  
    2.  <span data-ttu-id="fa3f8-168">在 machine.config 中指定的超时设置的 MSDTC 事务。导航到 machine.config 文件在下\<系统驱动器 >: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG 并添加如下所示的摘要。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-168">Specify the timeout settings for MSDTC transactions in the machine.config. Navigate to the machine.config file under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG and add the excerpt that resembles the following.</span></span>  
  
        ```  
        \<system.transactions>   
                <defaultSettings distributedTransactionManagerName="<computer_name>" timeout="02:00:00"/>   
            \</system.transactions>  
  
        ```  
  
         <span data-ttu-id="fa3f8-169">使用此设置时，MSDTC 超时设置为 2 小时。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-169">With this setting, the MSDTC timeout is set to 2 hours.</span></span> <span data-ttu-id="fa3f8-170">MSDTC 超时的默认值为 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-170">The default value for MSDTC timeout is 10 minutes.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="fa3f8-171">你必须运行的适配器客户端和 SQL Server 的计算机上进行此更改。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-171">You must make this change on the computers running the adapter client and SQL Server.</span></span> <span data-ttu-id="fa3f8-172">摘录内容中，运行的适配器客户端和 SQL Server 计算机的名称替换 < 计算机名 >。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-172">In the excerpt, replace <computer_name> with the name of computer running the adapter client and SQL Server.</span></span>  
  
    3.  <span data-ttu-id="fa3f8-173">设置**SendTimeout**绑定属性[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]为相当大的值。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-173">Set the **SendTimeout** binding property for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to a fairly large value.</span></span> <span data-ttu-id="fa3f8-174">有关如何设置绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-174">For instructions on how to set the binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
###  <span data-ttu-id="fa3f8-175"><a name="BKMK_SQLFullSchemaValidate"></a>BizTalk Server 中的完整架构验证失败的响应消息包含数据集</span><span class="sxs-lookup"><span data-stu-id="fa3f8-175"><a name="BKMK_SQLFullSchemaValidate"></a> Full schema validation in BizTalk Server fails for response messages containing DataSet</span></span>  
 <span data-ttu-id="fa3f8-176">**问题**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-176">**Problem**</span></span>  
  
 <span data-ttu-id="fa3f8-177">在中的完整架构验证失败的操作，返回的响应消息包含的数据集，例如 ExecuteReader， [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-177">For operations that return a response message containing a DataSet, for example ExecuteReader, full schema validation fails in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="fa3f8-178">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-178">**Resolution**</span></span>  
  
 <span data-ttu-id="fa3f8-179">我们建议你不要包含数据集的响应消息的完整架构验证。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-179">We recommend you to not do a full schema validation for response messages containing a dataset.</span></span> <span data-ttu-id="fa3f8-180">相反，您无法执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fa3f8-180">Instead, you could do the following:</span></span>  
  
1.  <span data-ttu-id="fa3f8-181">一旦返回的响应消息的架构，请执行该操作。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-181">Execute the operation once that returns the response message with the schema.</span></span>  
  
2.  <span data-ttu-id="fa3f8-182">将从响应消息的架构复制到.xsd 文件并将此文件添加到你的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-182">Copy the schema from the response message to a .xsd file and add this file to your BizTalk project.</span></span>  
  
3.  <span data-ttu-id="fa3f8-183">业务流程中使用 xpath 查询从响应消息中提取数据。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-183">Use an xpath query in your orchestration to extract the data from the response message.</span></span>  
  
###  <span data-ttu-id="fa3f8-184"><a name="BKMK_SQLRootNode"></a>与 RootNode TypeName BizTalk 项目中的错误</span><span class="sxs-lookup"><span data-stu-id="fa3f8-184"><a name="BKMK_SQLRootNode"></a> Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="fa3f8-185">**问题**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-185">**Problem**</span></span>  
  
 <span data-ttu-id="fa3f8-186">在 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，如果从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效字符或保留的字**RootNode TypeName**属性，编译项目时将出现以下错误:</span><span class="sxs-lookup"><span data-stu-id="fa3f8-186">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="fa3f8-187">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-187">**Resolution**</span></span>  
  
1.  <span data-ttu-id="fa3f8-188">右键单击该错误并选择中引用的 rood 节点**属性**。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-188">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="fa3f8-189">有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，圆点 （.）。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-189">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <span data-ttu-id="fa3f8-190"><a name="BKMK_SQLMetadataStronglyTyped"></a>适配器失效，则生成的强类型与临时表的存储过程的元数据</span><span class="sxs-lookup"><span data-stu-id="fa3f8-190"><a name="BKMK_SQLMetadataStronglyTyped"></a> Adapter fails to generate metadata of strongly-typed stored procedure with temporary tables</span></span>  
 <span data-ttu-id="fa3f8-191">**问题**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-191">**Problem**</span></span>  
  
 <span data-ttu-id="fa3f8-192">适配器无法正常工作，生成的强类型的存储过程，包括其定义中的临时表的元数据。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-192">The adapter fails to generate metadata for strongly-typed stored procedures that include temporary tables in their definition.</span></span> <span data-ttu-id="fa3f8-193">适配器提供了以下异常。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-193">The adapter gives the following exception.</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.MetadataException:  
Retrieval of Operation Metadata has failed while building WSDL at 'TypedProcedure/<schema>/<stored_procedure_name>' --->  
System.Data.SqlClient.SqlException: Invalid object name '<temp_table_name>'.  
  
```  
  
 <span data-ttu-id="fa3f8-194">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-194">**Resolution**</span></span>  
  
 <span data-ttu-id="fa3f8-195">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持生成的元数据的强类型的存储过程包含其定义中的临时表。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-195">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support generating metadata for strongly-typed stored procedures that contain temporary tables in their definition.</span></span> <span data-ttu-id="fa3f8-196">相反，应生成相同的过程从下的元数据**过程**时使用的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-196">Instead, you should generate metadata for the same procedure from under the **Procedures** node while using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
###  <span data-ttu-id="fa3f8-197"><a name="BKMK_SQLVS2008"></a>使用 Visual Studio 中的适配器时出现的无效的绑定警告</span><span class="sxs-lookup"><span data-stu-id="fa3f8-197"><a name="BKMK_SQLVS2008"></a> Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="fa3f8-198">**问题**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-198">**Problem**</span></span>  
  
 <span data-ttu-id="fa3f8-199">当你使用该适配器在 Visual Studio 中创建应用程序并打开生成的适配器的配置文件 (app.config) 时，你将看到类似于以下警告：</span><span class="sxs-lookup"><span data-stu-id="fa3f8-199">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'sqlBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="fa3f8-200">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-200">**Cause**</span></span>  
  
 <span data-ttu-id="fa3f8-201">由于会出现此警告[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定， `sqlBinding`，不标准绑定随[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-201">This warning appears because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding, `sqlBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="fa3f8-202">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-202">**Resolution**</span></span>  
  
 <span data-ttu-id="fa3f8-203">可以安全地忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-203">You can safely ignore this warning.</span></span>  
  
###  <span data-ttu-id="fa3f8-204"><a name="BKMK_SQLNotification"></a>BizTalk Server 引发异常，如果你在同一应用程序使用多个通知架构或跨同一个主机上的多个应用程序使用通知架构</span><span class="sxs-lookup"><span data-stu-id="fa3f8-204"><a name="BKMK_SQLNotification"></a> BizTalk Server throws an exception if you use more than one Notification schema in the same application or use the Notification schema across multiple applications on the same host</span></span>  
 <span data-ttu-id="fa3f8-205">**问题**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-205">**Problem**</span></span>  
  
 <span data-ttu-id="fa3f8-206">BizTalk Server 引发 XLANG 异常或异常指出应用程序找不到文档规范，因为多个架构匹配的消息类型。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-206">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="fa3f8-207">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-207">**Cause**</span></span>  
  
 <span data-ttu-id="fa3f8-208">由于以下任一发生这种情况：</span><span class="sxs-lookup"><span data-stu-id="fa3f8-208">This happens because of either of the following:</span></span>  
  
-   <span data-ttu-id="fa3f8-209">在你生成多个通知架构在 BizTalk Server 项目中，将其部署到 BizTalk Server 应用程序，，然后运行应用程序从 SQL Server 数据库中接收通知。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-209">You have generated more than one Notification schema in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to receive notifications from the SQL Server database.</span></span> <span data-ttu-id="fa3f8-210">由于通知架构是公用的冲突之间没有部署 BizTalk Server 应用程序中的架构。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-210">Because the Notification schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
-   <span data-ttu-id="fa3f8-211">发生多个项目，你已为每个 BizTalk 服务器到单独的 BizTalk Server 应用程序在同一主机上的每个项目部署的项目生成通知架构，然后运行应用程序或应用程序接收来自通知SQL Server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-211">In case of multiple projects, you have generated a Notification schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to receive notifications from the SQL Server database.</span></span> <span data-ttu-id="fa3f8-212">因为架构和程序集都可访问 BizTalk Server 中的应用程序，各种 BizTalk Server 应用程序和程序集下部署的常见架构之间存在不冲突。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-212">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
 <span data-ttu-id="fa3f8-213">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-213">**Resolution**</span></span>  
  
 <span data-ttu-id="fa3f8-214">BizTalk Server 应用程序使用单个通知架构文件。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-214">Use a single Notification schema file for a BizTalk Server application.</span></span> <span data-ttu-id="fa3f8-215">如果你需要在同一主机上的多个 BizTalk Server 应用程序中使用通知架构，创建包含单个通知架构的应用程序，然后使用 BizTalk Server 中的所有其他应用程序中的通知架构。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-215">If you need to use the Notification schema in multiple BizTalk Server applications on the same host, create an application containing a single Notification schema, and then use the notification schema from all other applications in BizTalk Server.</span></span>  
  
###  <span data-ttu-id="fa3f8-216"><a name="BKMK_SQLRestoreConn"></a>适配器的客户端引发异常，正在执行的操作后连接恢复适配器客户端和 SQL Server 数据库之间</span><span class="sxs-lookup"><span data-stu-id="fa3f8-216"><a name="BKMK_SQLRestoreConn"></a> Adapter client throws an exception on performing an operation after the connectivity is restored between the adapter client and the SQL Server database</span></span>  
 <span data-ttu-id="fa3f8-217">**问题**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-217">**Problem**</span></span>  
  
 <span data-ttu-id="fa3f8-218">适配器的客户端引发以下异常上执行的 SQL Server 数据库上的操作：</span><span class="sxs-lookup"><span data-stu-id="fa3f8-218">Adapter client throws the following exception on executing an operation on the SQL Server database:</span></span>  
  
```  
{System.Data.Common.DbException} = {"A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.)"}  
```  
  
 <span data-ttu-id="fa3f8-219">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-219">**Cause**</span></span>  
  
 <span data-ttu-id="fa3f8-220">在执行期间的操作，该适配器使用连接来自 SQL ADO.NET 连接池来连接到 SQL Server 数据库，并执行该操作。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-220">During the execution of an operation, the adapter uses the connection from the SQL ADO.NET connection pool to connect to the SQL Server database, and perform the operation.</span></span> <span data-ttu-id="fa3f8-221">如果没有适配器客户端和 SQL Server 数据库之间的短暂的网络中断，或者如果 SQL Server 数据库暂时已关闭，SQL ADO.NET 连接池中的所有连接都将失效。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-221">If there is a brief network outage between the adapter client and the SQL Server database or if the SQL Server database is down temporarily, all the connections in the SQL ADO.NET connection pool become invalid.</span></span> <span data-ttu-id="fa3f8-222">连接恢复并尝试执行 SQL Server 数据库上的操作后，适配器使用的相同的无效连接从 SQL ADO.NET 连接池，并因此适配器客户端引发异常。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-222">After the connectivity is restored and you try to perform an operation on the SQL Server database, the adapter uses the same invalid connections from the SQL ADO.NET connection pool, and therefore the adapter client throws the exception.</span></span>  
  
 <span data-ttu-id="fa3f8-223">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-223">**Resolution**</span></span>  
  
 <span data-ttu-id="fa3f8-224">适配器客户端应在操作执行其中它们应捕获异常，并指定为"n + 1"的操作重试计数中实施重试逻辑，其中"n"是为 MaxConnectionPoolSize 绑定属性指定的值。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-224">The adapter client should implement retry logic in their operation execution where they should catch the exception and specify the operation retry count as “n+1”, where “n” is the value specified for the MaxConnectionPoolSize binding property.</span></span> <span data-ttu-id="fa3f8-225">这意味着，如果有"n"中的连接池已变为无效的连接数，从理论上讲适配器客户端应重试"n + 1"的最长时间，以获取有效的连接，并因此执行该操作。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-225">This implies that if there are “n” number of connections in the connection pool that have been rendered invalid, theoretically the adapter client should retry for a maximum of “n+1” times to get a valid connection, and hence perform the operation.</span></span>  
  
 <span data-ttu-id="fa3f8-226">例如，若要指定重试计数的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，打开**属性**对话框中的应用程序中发送端口，请单击**传输高级选项**的对话框中，和中的左窗格中**传输选项**区域中，指定中的值**重试计数**列表。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-226">For example, to specify the retry count in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], open the **Properties** dialog box of a send port in an application, click **Transport Advanced Options** in the left pane of the dialog box, and in the **Transport Options** area, specify a value in the **Retry count** list.</span></span>  
  
###  <span data-ttu-id="fa3f8-227"><a name="BKMK_MemUsage"></a>内存使用情况和线程计数的增加而在事务处理的入站操作中使用该适配器时</span><span class="sxs-lookup"><span data-stu-id="fa3f8-227"><a name="BKMK_MemUsage"></a> Memory usage and thread count increases when using the adapter in a transacted inbound operation</span></span>  
 <span data-ttu-id="fa3f8-228">**问题**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-228">**Problem**</span></span>  
  
 <span data-ttu-id="fa3f8-229">在事务处理的入站操作中，如轮询，**如果没有数据轮询表中可用**和适配器继续轮询，通过一段时间则会遇到内存使用量和线程计数的增加。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-229">In a transacted inbound operation, such as Polling, **if there is no data available in the table being polled** and the adapter continues to poll, over a period of time you experience an increase in the memory usage and the thread count.</span></span>  
  
 <span data-ttu-id="fa3f8-230">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-230">**Cause**</span></span>  
  
 <span data-ttu-id="fa3f8-231">**如果没有数据轮询表中可用**之后，每个接收超时周期[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]生成新的线程来继续轮询操作。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-231">**If there is no data available in the table being polled**, after every receive timeout cycle, [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] spawns a new thread to continue the polling operation.</span></span> <span data-ttu-id="fa3f8-232">因此，通过一段时间会增加线程计数和内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-232">Hence, the thread count and memory usage increases over a period of time.</span></span> <span data-ttu-id="fa3f8-233">但是，如果正在轮询一次的表具有一些数据，同一个线程继续执行所有后续的轮询。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-233">However, if the table being polled has some data, the same thread continues to perform all subsequent polls.</span></span>  
  
 <span data-ttu-id="fa3f8-234">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="fa3f8-234">**Resolution**</span></span>  
  
 <span data-ttu-id="fa3f8-235">我们建议设置**ReceiveTimeout**为最大可能值，这是 24.20:31:23.6470000 （24 天），以便生成新线程，仅每隔 24 天。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-235">We recommend setting the **ReceiveTimeout** to the maximum possible value, which is 24.20:31:23.6470000 (24 days) so that a new thread is spawned only every 24 days.</span></span> <span data-ttu-id="fa3f8-236">这将确保，内存使用情况和线程计数不会增长过多时间太短。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-236">This will ensure that the memory usage and thread count does not grow too much too soon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa3f8-237">如果已设置 SqlAdapterInboundTransactionBehavior，请确保 TransactionTimeout 也被配置为最大可能值，该值是 24.20:31:23.6470000 （24 天）。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-237">If SqlAdapterInboundTransactionBehavior has been set, make sure the TransactionTimeout is also configured to maximum possible value, which is 24.20:31:23.6470000 (24 days).</span></span> <span data-ttu-id="fa3f8-238">在使用此解决方法，我们可以添加 SqlAdapterInboundTransactionBehavior，仅当事务的隔离级别必须进行配置。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-238">When using this workaround, we can add the SqlAdapterInboundTransactionBehavior only if the transaction isolation level has to be configured.</span></span> <span data-ttu-id="fa3f8-239">否则，它是一种最佳做法来删除该行为。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-239">Else, it is a best practice to remove that behavior.</span></span>  
  
 <span data-ttu-id="fa3f8-240">有关详细信息**ReceiveTimeout**绑定属性，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-240">For more information about the **ReceiveTimeout** binding property, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="fa3f8-241">指定绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-241">For instructions on specifying binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa3f8-242">使用的适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，将超时设置为较大的值不会影响的适配器的功能。</span><span class="sxs-lookup"><span data-stu-id="fa3f8-242">When using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], setting the timeout to a large value does not impact the functionality of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa3f8-243">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa3f8-243">See Also</span></span>  
[<span data-ttu-id="fa3f8-244">解决 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="fa3f8-244">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)
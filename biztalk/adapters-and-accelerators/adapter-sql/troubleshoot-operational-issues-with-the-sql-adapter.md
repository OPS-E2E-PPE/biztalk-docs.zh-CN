---
title: 使用 SQL 适配器在 BizTalk 中进行的操作问题故障排除 |Microsoft Docs
description: 常见的问题和解决方法的 SQL 适配器在 BizTalk 适配器包 (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c75f85f4-cd03-4c6a-aac9-a6d02d3c3449
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d167777ccd9fd9ccb2ddc5a43410d798bde3e7b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367516"
---
# <a name="troubleshoot-operational-issues-with-the-sql-adapter"></a><span data-ttu-id="d4ed0-103">使用 SQL 适配器进行的操作问题故障排除</span><span class="sxs-lookup"><span data-stu-id="d4ed0-103">Troubleshoot Operational Issues with the SQL adapter</span></span>
<span data-ttu-id="d4ed0-104">本部分讨论如何使用故障排除技术来解决操作使用时可能遇到的错误[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-104">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="d4ed0-105">启用跟踪</span><span class="sxs-lookup"><span data-stu-id="d4ed0-105">Enabling Tracing</span></span>  
 <span data-ttu-id="d4ed0-106">必须启用该适配器之间的跟踪[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，并以收集问题的任何详细信息的 SQL Server 在使用时遇到[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-106">You must enable tracing between the adapter, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], and SQL Server to gather more information about any issues you encounter while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="d4ed0-107">有关跟踪中的支持的详细信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[诊断跟踪和消息日志记录中的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-107">For more information about tracing support in the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Diagnostic Tracing and Message Logging in the SQL adapter](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="d4ed0-108">已知问题</span><span class="sxs-lookup"><span data-stu-id="d4ed0-108">Known Issues</span></span>  
 <span data-ttu-id="d4ed0-109">以下是在使用时可能遇到的最常见错误[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，以及其可能的原因和解决方法。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-109">The following are the most common errors you might encounter when using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <a name="BKMK_SQLLoadBinding"></a> <span data-ttu-id="d4ed0-110">加载适配器绑定时出错</span><span class="sxs-lookup"><span data-stu-id="d4ed0-110">Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="d4ed0-111">**问题**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-111">**Problem**</span></span>  
  
 <span data-ttu-id="d4ed0-112">当您尝试启动[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]，收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="d4ed0-112">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you get the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="d4ed0-113">**原因**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-113">**Cause**</span></span>  
  
 <span data-ttu-id="d4ed0-114">当您尝试启动[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，WCF 将加载所有已安装的适配器的适配器绑定。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-114">When you try to start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="d4ed0-115">反过来，适配器绑定都依赖于企业应用程序特定的客户端软件。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-115">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="d4ed0-116">如果你这样做将适配器安装中包含的所有适配器的典型或完全安装，可能会遇到此问题[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-116">You might face this issue if you did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="d4ed0-117">但是，可能只有一个企业应用程序安装 LOB 客户端库。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-117">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="d4ed0-118">因此，在 GUI 无法加载其他适配器的绑定。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-118">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="d4ed0-119">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-119">**Resolution**</span></span>  
  
 <span data-ttu-id="d4ed0-120">请确保执行要安装仅需要的适配器的适配器的自定义安装。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-120">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
###  <a name="BKMK_SQLDisplay"></a> <span data-ttu-id="d4ed0-121">SQL 适配器不会显示在 BizTalk Server 管理控制台中的适配器列表中</span><span class="sxs-lookup"><span data-stu-id="d4ed0-121">The SQL adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="d4ed0-122">**问题**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-122">**Problem**</span></span>  
  
 <span data-ttu-id="d4ed0-123">与早期版本附带的适配器的不同[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，则[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]中的适配器列表中未显示[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-123">Unlike the earlier version of the adapters shipped with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="d4ed0-124">**原因**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-124">**Cause**</span></span>  
  
 <span data-ttu-id="d4ed0-125">最新[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]是 WCF 自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-125">The latest [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="d4ed0-126">因此，尽管[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中显示[!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，它不会显示 WCF 自定义绑定，因此，不会显示基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-126">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="d4ed0-127">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-127">**Resolution**</span></span>  
  
 <span data-ttu-id="d4ed0-128">您可以显式添加[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中所述的步骤[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-128">You can explicitly add the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <a name="BKMK_MissingAction"></a> <span data-ttu-id="d4ed0-129">在 SQL Server 数据库上执行操作时出错</span><span class="sxs-lookup"><span data-stu-id="d4ed0-129">Error while performing operations on a SQL Server database</span></span>  
 <span data-ttu-id="d4ed0-130">**问题**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-130">**Problem**</span></span>  
  
 <span data-ttu-id="d4ed0-131">执行 SQL Server 数据库使用的任何操作时，适配器将报告以下错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-131">The adapter gives the following error when performing any operation on a SQL Server database using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="d4ed0-132">**为 BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-132">**For BizTalk Server**</span></span>  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  <span data-ttu-id="d4ed0-133">**原因**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-133">**Cause**</span></span>  
  
  <span data-ttu-id="d4ed0-134">未指定消息的 WCF 操作。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-134">The WCF action for the message is not specified.</span></span> <span data-ttu-id="d4ed0-135">WCF 需要用于为每个操作，向适配器通知上的 LOB 应用程序执行的操作指定的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-135">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
  <span data-ttu-id="d4ed0-136">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-136">**Resolution**</span></span>  
  
  <span data-ttu-id="d4ed0-137">在发送端口或为 BizTalk 业务流程的消息上下文属性指定的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-137">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="d4ed0-138">有关说明，请参阅[配置 SQL 适配器的 SOAP 操作](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-138">For instructions, see [Configure the SOAP action for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md).</span></span> <span data-ttu-id="d4ed0-139">请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)若要查看每个操作的操作的列表。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-139">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md) to see a list of actions for each operation.</span></span>  
  
###  <a name="BKMK_SQLInvalidOp"></a> <span data-ttu-id="d4ed0-140">与错误代码的 InvalidOperationException 执行 FILESTREAM 操作时 = 5</span><span class="sxs-lookup"><span data-stu-id="d4ed0-140">InvalidOperationException with ErrorCode=5 while performing FILESTREAM operations</span></span>  
 <span data-ttu-id="d4ed0-141">**问题**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-141">**Problem**</span></span>  
  
 <span data-ttu-id="d4ed0-142">使用时遇到以下错误[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]用于执行 FILESTREAM 操作。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-142">You get the following error while using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to perform FILESTREAM operations.</span></span>  
  
```  
System.InvalidOperationException: OpenSqlFileStream returned error.  
ErrorCode:5  
  
```  
  
 <span data-ttu-id="d4ed0-143">**原因**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-143">**Cause**</span></span>  
  
 <span data-ttu-id="d4ed0-144">您可能会指定用于连接到 SQL Server 数据库的数据库凭据。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-144">You might have specified database credentials to connect to the SQL Server database.</span></span> <span data-ttu-id="d4ed0-145">若要执行 FILESTREAM 操作，必须始终使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-145">To perform FILESTREAM operations, you must always use Windows Authentication.</span></span> <span data-ttu-id="d4ed0-146">错误代码"5"表示的访问被拒绝，因为不正确的凭据。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-146">The error code “5” denotes that access is denied because of incorrect credentials.</span></span> <span data-ttu-id="d4ed0-147">有关不同的错误代码的详细信息，请参阅[系统错误代码 (0-最初包含 499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-147">For more information about the different error codes, see [System Error Codes (0-499)](https://msdn.microsoft.com/library/ms681382(VS.85).aspx).</span></span>
  
 <span data-ttu-id="d4ed0-148">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-148">**Resolution**</span></span>  
  
 <span data-ttu-id="d4ed0-149">使用 Windows 身份验证连接到 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-149">Use Windows Authentication to connect to the SQL Server database.</span></span> <span data-ttu-id="d4ed0-150">在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，就可以做到将用户名称和密码字段留空 WCF 自定义或 WCF SQL 端口配置对话框中。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-150">In [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can do so by leaving the user name and password fields blank in the WCF-Custom or WCF-SQL port configuration dialog box.</span></span>  
  
###  <a name="BKMK_SQLPolling"></a> <span data-ttu-id="d4ed0-151">轮询操作不返回任何消息即使 PollingStatement 和 PolledDataAvailableStatement 指定了有效语句</span><span class="sxs-lookup"><span data-stu-id="d4ed0-151">Polling operation does not return any messages even if valid statements are specified for PollingStatement and PolledDataAvailableStatement</span></span>  
 <span data-ttu-id="d4ed0-152">**问题**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-152">**Problem**</span></span>  
  
 <span data-ttu-id="d4ed0-153">即使为 PollingStatement 和 PolledDataAvailableStatement 绑定属性指定了有效的值，则该适配器不从 SQL Server 接收轮询消息。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-153">Even if valid values are specified for the PollingStatement and PolledDataAvailableStatement binding properties, the adapter does not receive a polling message from SQL Server.</span></span>  
  
 <span data-ttu-id="d4ed0-154">**原因**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-154">**Cause**</span></span>  
  
 <span data-ttu-id="d4ed0-155">验证任何其他事务是否已在适配器轮询的表上获取锁。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-155">Verify whether any other transaction has taken a lock on the table that the adapter is polling.</span></span>  
  
 <span data-ttu-id="d4ed0-156">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-156">**Resolution**</span></span>  
  
 <span data-ttu-id="d4ed0-157">如果你想要轮询正在更新作为另一个事务的一部分的表，可以考虑使用"with (nolock)"参数作为 PolledDataAvailableStatement 绑定属性指定的查询的一部分，以确保即使施加锁定返回数据由其他事务。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-157">If you want to poll a table that is being updated as part of another transaction, you can consider using “with (nolock)” parameter as part of the query specified for PolledDataAvailableStatement binding property to ensure that data is returned even if a lock is imposed by the other transaction.</span></span> <span data-ttu-id="d4ed0-158">有关详细信息，请参阅[数据库引擎中的锁定 SQL](https://msdn.microsoft.com/library/ms190615.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-158">For more information, see [SQL Locking in the Database Engine](https://msdn.microsoft.com/library/ms190615.aspx).</span></span>
  
###  <a name="BKMK_SQLSingleOp"></a> <span data-ttu-id="d4ed0-159">该适配器无法插入、 更新或删除在单个操作中使用 BizTalk Server 的数据量很大</span><span class="sxs-lookup"><span data-stu-id="d4ed0-159">The adapter fails to insert, update, or delete large volumes of data in a single operation using BizTalk Server</span></span>  
 <span data-ttu-id="d4ed0-160">**问题**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-160">**Problem**</span></span>  
  
 <span data-ttu-id="d4ed0-161">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]无法插入、 更新或删除在单个操作中使用的数据量很大[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-161">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] fails to insert, update, or delete large volumes of data in a single operation using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d4ed0-162">**原因**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-162">**Cause**</span></span>  
  
 <span data-ttu-id="d4ed0-163">插入、 更新或删除数据量很大可能需要时间和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]或在其中正在执行操作，该事务可能会超时。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-163">Inserting, updating, or deleting large volumes of data may take time and the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] or the transaction in which the operation is being performed, may time out.</span></span>  
  
 <span data-ttu-id="d4ed0-164">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-164">**Resolution**</span></span>  
  
- <span data-ttu-id="d4ed0-165">**为 BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-165">**For BizTalk Server**</span></span>  
  
  1. <span data-ttu-id="d4ed0-166">在 machine.config 中指定的 WCF 适配器的超时时间。导航到下的 machine.config 文件\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG 并添加如下所示的摘录。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-166">Specify the timeout for the WCF adapter in the machine.config. Navigate to the machine.config file under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG and add the excerpt that resembles the following.</span></span>  
  
     ```  
     <configuration>  
      <system.transactions>  
       <machineSettings maxTimeout="02:00:00" />  
      </system.transactions>  
     </configuration>  
     ```  
  
      <span data-ttu-id="d4ed0-167">使用此设置时，WCF 适配器超时设置为 2 小时。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-167">With this setting, the WCF adapter timeout is set to 2 hours.</span></span>  
  
  2. <span data-ttu-id="d4ed0-168">在 machine.config 中指定的超时设置的 MSDTC 事务。导航到下的 machine.config 文件\<系统驱动器\>: \WINDOWS\Microsoft.NET\Framework\\< 版本\>\CONFIG 并添加如下所示的摘录。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-168">Specify the timeout settings for MSDTC transactions in the machine.config. Navigate to the machine.config file under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG and add the excerpt that resembles the following.</span></span>  
  
     ```  
     <system.transactions>   
             <defaultSettings distributedTransactionManagerName="<computer_name>" timeout="02:00:00"/>   
         </system.transactions>  
  
     ```  
  
      <span data-ttu-id="d4ed0-169">使用此设置，MSDTC 超时设置为 2 小时。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-169">With this setting, the MSDTC timeout is set to 2 hours.</span></span> <span data-ttu-id="d4ed0-170">MSDTC 超时的默认值为 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-170">The default value for MSDTC timeout is 10 minutes.</span></span>  
  
     > [!IMPORTANT]
     >  <span data-ttu-id="d4ed0-171">运行适配器客户端和 SQL Server 的计算机上，必须进行此更改。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-171">You must make this change on the computers running the adapter client and SQL Server.</span></span> <span data-ttu-id="d4ed0-172">摘录中，运行适配器客户端和 SQL Server 计算机的名称替换 < 计算机名 >。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-172">In the excerpt, replace <computer_name> with the name of computer running the adapter client and SQL Server.</span></span>  
  
  3. <span data-ttu-id="d4ed0-173">设置**SendTimeout**绑定属性[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]为相当大的值。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-173">Set the **SendTimeout** binding property for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to a fairly large value.</span></span> <span data-ttu-id="d4ed0-174">有关如何设置绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-174">For instructions on how to set the binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
###  <a name="BKMK_SQLFullSchemaValidate"></a> <span data-ttu-id="d4ed0-175">包含数据集的响应消息的 BizTalk Server 中的完整架构验证失败</span><span class="sxs-lookup"><span data-stu-id="d4ed0-175">Full schema validation in BizTalk Server fails for response messages containing DataSet</span></span>  
 <span data-ttu-id="d4ed0-176">**问题**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-176">**Problem**</span></span>  
  
 <span data-ttu-id="d4ed0-177">返回包含数据集，例如 ExecuteReader 的响应消息的操作的完整架构验证失败中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-177">For operations that return a response message containing a DataSet, for example ExecuteReader, full schema validation fails in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="d4ed0-178">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-178">**Resolution**</span></span>  
  
 <span data-ttu-id="d4ed0-179">我们建议你为不包含数据集的响应消息的完整架构验证。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-179">We recommend you to not do a full schema validation for response messages containing a dataset.</span></span> <span data-ttu-id="d4ed0-180">相反，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4ed0-180">Instead, you could do the following:</span></span>  
  
1.  <span data-ttu-id="d4ed0-181">返回的响应消息的架构后，请执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-181">Execute the operation once that returns the response message with the schema.</span></span>  
  
2.  <span data-ttu-id="d4ed0-182">将架构从响应消息复制到一个.xsd 文件并将其添加到 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-182">Copy the schema from the response message to a .xsd file and add this file to your BizTalk project.</span></span>  
  
3.  <span data-ttu-id="d4ed0-183">在业务流程中使用 xpath 查询以从响应消息中提取的数据。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-183">Use an xpath query in your orchestration to extract the data from the response message.</span></span>  
  
###  <a name="BKMK_SQLRootNode"></a> <span data-ttu-id="d4ed0-184">使用 BizTalk 项目中的 RootNode TypeName 错误</span><span class="sxs-lookup"><span data-stu-id="d4ed0-184">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="d4ed0-185">**问题**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-185">**Problem**</span></span>  
  
 <span data-ttu-id="d4ed0-186">中的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，则从架构生成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]包含无效的字符或保留的字**RootNode TypeName**属性，编译项目时将发生以下错误:</span><span class="sxs-lookup"><span data-stu-id="d4ed0-186">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="d4ed0-187">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-187">**Resolution**</span></span>  
  
1.  <span data-ttu-id="d4ed0-188">右键单击该错误，然后选择中引用的 rood 这样节点**属性**。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-188">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="d4ed0-189">有关**RootNode TypeName**属性，删除任何非法字符或保留字，例如，点 （.）。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-189">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <a name="BKMK_SQLMetadataStronglyTyped"></a> <span data-ttu-id="d4ed0-190">适配器无法将生成的强类型化的存储过程与临时表的元数据</span><span class="sxs-lookup"><span data-stu-id="d4ed0-190">Adapter fails to generate metadata of strongly-typed stored procedure with temporary tables</span></span>  
 <span data-ttu-id="d4ed0-191">**问题**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-191">**Problem**</span></span>  
  
 <span data-ttu-id="d4ed0-192">该适配器无法生成的强类型化的存储过程，包括其定义中的临时表的元数据。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-192">The adapter fails to generate metadata for strongly-typed stored procedures that include temporary tables in their definition.</span></span> <span data-ttu-id="d4ed0-193">适配器提供了以下异常。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-193">The adapter gives the following exception.</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.MetadataException:  
Retrieval of Operation Metadata has failed while building WSDL at 'TypedProcedure/<schema>/<stored_procedure_name>' --->  
System.Data.SqlClient.SqlException: Invalid object name '<temp_table_name>'.  
  
```  
  
 <span data-ttu-id="d4ed0-194">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-194">**Resolution**</span></span>  
  
 <span data-ttu-id="d4ed0-195">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持生成元数据的强类型化的存储过程包含其定义中的临时表。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-195">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support generating metadata for strongly-typed stored procedures that contain temporary tables in their definition.</span></span> <span data-ttu-id="d4ed0-196">相反，应生成相同的过程从下的元数据**过程**时使用的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-196">Instead, you should generate metadata for the same procedure from under the **Procedures** node while using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
###  <a name="BKMK_SQLVS2008"></a> <span data-ttu-id="d4ed0-197">无效的绑定时出现的警告在 Visual Studio 中使用适配器</span><span class="sxs-lookup"><span data-stu-id="d4ed0-197">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="d4ed0-198">**问题**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-198">**Problem**</span></span>  
  
 <span data-ttu-id="d4ed0-199">当适配器用于在 Visual Studio 中创建应用程序并打开由适配器生成的配置文件 (app.config) 时，您会看到类似于下面的警告：</span><span class="sxs-lookup"><span data-stu-id="d4ed0-199">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'sqlBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="d4ed0-200">**原因**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-200">**Cause**</span></span>  
  
 <span data-ttu-id="d4ed0-201">会出现此警告[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]绑定， `sqlBinding`，不标准绑定随附于[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-201">This warning appears because the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding, `sqlBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="d4ed0-202">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-202">**Resolution**</span></span>  
  
 <span data-ttu-id="d4ed0-203">可以放心地忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-203">You can safely ignore this warning.</span></span>  
  
###  <a name="BKMK_SQLNotification"></a> <span data-ttu-id="d4ed0-204">BizTalk Server 将引发异常，如果在同一个应用程序中使用多个通知架构或在同一主机上的多个应用程序中使用通知架构</span><span class="sxs-lookup"><span data-stu-id="d4ed0-204">BizTalk Server throws an exception if you use more than one Notification schema in the same application or use the Notification schema across multiple applications on the same host</span></span>  
 <span data-ttu-id="d4ed0-205">**问题**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-205">**Problem**</span></span>  
  
 <span data-ttu-id="d4ed0-206">BizTalk Server 将引发异常，表明该应用程序找不到文档规范，因为多个架构匹配的消息类型或 XLANG 异常。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-206">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="d4ed0-207">**原因**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-207">**Cause**</span></span>  
  
 <span data-ttu-id="d4ed0-208">由于以下任一发生这种情况：</span><span class="sxs-lookup"><span data-stu-id="d4ed0-208">This happens because of either of the following:</span></span>  
  
- <span data-ttu-id="d4ed0-209">已生成多个通知架构在 BizTalk Server 项目中，部署到 BizTalk Server 应用程序，然后运行应用程序从 SQL Server 数据库中接收通知。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-209">You have generated more than one Notification schema in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to receive notifications from the SQL Server database.</span></span> <span data-ttu-id="d4ed0-210">由于通知架构都是公用的冲突之间没有 BizTalk Server 应用程序中部署的架构。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-210">Because the Notification schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
- <span data-ttu-id="d4ed0-211">发生多个项目时您已为每个 BizTalk Server 部署的项目，每个项目到同一主机上单独的 BizTalk Server 应用程序生成的通知架构，然后运行应用程序或应用程序以接收来自通知SQL Server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-211">In case of multiple projects, you have generated a Notification schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to receive notifications from the SQL Server database.</span></span> <span data-ttu-id="d4ed0-212">因为架构和程序集都是可访问 BizTalk Server 中的应用程序，则冲突之间常见的架构部署在各种 BizTalk Server 应用程序和程序集。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-212">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
  <span data-ttu-id="d4ed0-213">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-213">**Resolution**</span></span>  
  
  <span data-ttu-id="d4ed0-214">为 BizTalk Server 应用程序使用单个通知架构文件。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-214">Use a single Notification schema file for a BizTalk Server application.</span></span> <span data-ttu-id="d4ed0-215">如果需要在同一主机上的多个 BizTalk Server 应用程序中使用通知架构，创建包含单个通知架构的应用程序，然后使用 BizTalk Server 中的从所有其他应用程序的通知架构。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-215">If you need to use the Notification schema in multiple BizTalk Server applications on the same host, create an application containing a single Notification schema, and then use the notification schema from all other applications in BizTalk Server.</span></span>  
  
###  <a name="BKMK_SQLRestoreConn"></a> <span data-ttu-id="d4ed0-216">适配器客户端会引发异常的连接恢复之间适配器客户端和 SQL Server 数据库后执行的操作</span><span class="sxs-lookup"><span data-stu-id="d4ed0-216">Adapter client throws an exception on performing an operation after the connectivity is restored between the adapter client and the SQL Server database</span></span>  
 <span data-ttu-id="d4ed0-217">**问题**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-217">**Problem**</span></span>  
  
 <span data-ttu-id="d4ed0-218">适配器客户端会引发以下异常在执行 SQL Server 数据库上的操作：</span><span class="sxs-lookup"><span data-stu-id="d4ed0-218">Adapter client throws the following exception on executing an operation on the SQL Server database:</span></span>  
  
```  
{System.Data.Common.DbException} = {"A transport-level error has occurred when sending the request to the server. (provider: TCP Provider, error: 0 - An existing connection was forcibly closed by the remote host.)"}  
```  
  
 <span data-ttu-id="d4ed0-219">**原因**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-219">**Cause**</span></span>  
  
 <span data-ttu-id="d4ed0-220">执行过程中的操作，适配器使用该连接从 SQL ADO.NET 连接池中连接到 SQL Server 数据库，并执行该操作。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-220">During the execution of an operation, the adapter uses the connection from the SQL ADO.NET connection pool to connect to the SQL Server database, and perform the operation.</span></span> <span data-ttu-id="d4ed0-221">如果适配器客户端和 SQL Server 数据库之间的短暂的网络中断，或者如果 SQL Server 数据库暂时已关闭，SQL ADO.NET 连接池中的所有连接都将失效。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-221">If there is a brief network outage between the adapter client and the SQL Server database or if the SQL Server database is down temporarily, all the connections in the SQL ADO.NET connection pool become invalid.</span></span> <span data-ttu-id="d4ed0-222">还原连接并尝试对 SQL Server 数据库执行操作之后，则适配器将使用从 SQL ADO.NET 连接池中，相同的无效连接并因此适配器客户端引发异常。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-222">After the connectivity is restored and you try to perform an operation on the SQL Server database, the adapter uses the same invalid connections from the SQL ADO.NET connection pool, and therefore the adapter client throws the exception.</span></span>  
  
 <span data-ttu-id="d4ed0-223">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-223">**Resolution**</span></span>  
  
 <span data-ttu-id="d4ed0-224">适配器客户端应在其操作执行它们应该捕获异常和指定的操作重试计数为"n + 1"位置中实施重试逻辑，其中"n"是为 MaxConnectionPoolSize 绑定属性指定的值。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-224">The adapter client should implement retry logic in their operation execution where they should catch the exception and specify the operation retry count as “n+1”, where “n” is the value specified for the MaxConnectionPoolSize binding property.</span></span> <span data-ttu-id="d4ed0-225">这意味着，如果有"n"中的连接池具有已呈现为无效的连接数，从理论上讲适配器客户端应重试"n + 1"的最长时间，以获取有效的连接，并因此执行该操作。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-225">This implies that if there are “n” number of connections in the connection pool that have been rendered invalid, theoretically the adapter client should retry for a maximum of “n+1” times to get a valid connection, and hence perform the operation.</span></span>  
  
 <span data-ttu-id="d4ed0-226">例如，若要指定重试计数[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，打开**属性**对话框中的应用程序中的发送端口，单击**传输高级选项**在左窗格中的对话框中，并在**传输选项**区域中，指定的值**重试计数**列表。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-226">For example, to specify the retry count in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], open the **Properties** dialog box of a send port in an application, click **Transport Advanced Options** in the left pane of the dialog box, and in the **Transport Options** area, specify a value in the **Retry count** list.</span></span>  
  
###  <a name="BKMK_MemUsage"></a> <span data-ttu-id="d4ed0-227">内存使用情况和线程数将增加时在事务处理的入站操作中使用适配器</span><span class="sxs-lookup"><span data-stu-id="d4ed0-227">Memory usage and thread count increases when using the adapter in a transacted inbound operation</span></span>  
 <span data-ttu-id="d4ed0-228">**问题**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-228">**Problem**</span></span>  
  
 <span data-ttu-id="d4ed0-229">在事务处理的入站操作中，如轮询，**如果没有数据轮询表中可用**并且该适配器将继续轮询，一段时间内遇到内存使用情况和线程计数的增加。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-229">In a transacted inbound operation, such as Polling, **if there is no data available in the table being polled** and the adapter continues to poll, over a period of time you experience an increase in the memory usage and the thread count.</span></span>  
  
 <span data-ttu-id="d4ed0-230">**原因**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-230">**Cause**</span></span>  
  
 <span data-ttu-id="d4ed0-231">**如果没有数据轮询表中可用**后，每个接收超时周期[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]产生了一个新的线程无法继续轮询操作。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-231">**If there is no data available in the table being polled**, after every receive timeout cycle, [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] spawns a new thread to continue the polling operation.</span></span> <span data-ttu-id="d4ed0-232">因此，一段时间内会增加线程计数和内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-232">Hence, the thread count and memory usage increases over a period of time.</span></span> <span data-ttu-id="d4ed0-233">但是，如果正在轮询一次的表具有一些数据，同一个线程继续执行所有后续轮询。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-233">However, if the table being polled has some data, the same thread continues to perform all subsequent polls.</span></span>  
  
 <span data-ttu-id="d4ed0-234">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d4ed0-234">**Resolution**</span></span>  
  
 <span data-ttu-id="d4ed0-235">我们建议设置**ReceiveTimeout**的最大可能值，这是 24.20:31:23.6470000 （24 天），以便生成新线程，仅每隔 24 天。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-235">We recommend setting the **ReceiveTimeout** to the maximum possible value, which is 24.20:31:23.6470000 (24 days) so that a new thread is spawned only every 24 days.</span></span> <span data-ttu-id="d4ed0-236">这将确保，内存使用情况和线程计数不会不会变得太多时间太短。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-236">This will ensure that the memory usage and thread count does not grow too much too soon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4ed0-237">如果尚未设置 SqlAdapterInboundTransactionBehavior，请确保 TransactionTimeout 也被配置为最大可能值，即 24.20:31:23.6470000 （24 天）。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-237">If SqlAdapterInboundTransactionBehavior has been set, make sure the TransactionTimeout is also configured to maximum possible value, which is 24.20:31:23.6470000 (24 days).</span></span> <span data-ttu-id="d4ed0-238">在使用此解决方法，我们可以添加 SqlAdapterInboundTransactionBehavior，仅当事务隔离级别必须进行配置。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-238">When using this workaround, we can add the SqlAdapterInboundTransactionBehavior only if the transaction isolation level has to be configured.</span></span> <span data-ttu-id="d4ed0-239">否则，它是删除该行为的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-239">Else, it is a best practice to remove that behavior.</span></span>  
  
 <span data-ttu-id="d4ed0-240">有关详细信息**ReceiveTimeout**绑定属性，请参阅[了解有关 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-240">For more information about the **ReceiveTimeout** binding property, see [Read about the BizTalk Adapter for SQL Server adapter binding properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span> <span data-ttu-id="d4ed0-241">指定绑定属性的说明，请参阅[配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-241">For instructions on specifying binding properties, see [Configure the binding properties for the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4ed0-242">使用的适配器时[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，超时值设置为较大的值不会影响适配器的功能。</span><span class="sxs-lookup"><span data-stu-id="d4ed0-242">When using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], setting the timeout to a large value does not impact the functionality of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ed0-243">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4ed0-243">See Also</span></span>  
[<span data-ttu-id="d4ed0-244">SQL 适配器疑难解答</span><span class="sxs-lookup"><span data-stu-id="d4ed0-244">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)
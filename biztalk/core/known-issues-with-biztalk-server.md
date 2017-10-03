---
title: "已知问题与 BizTalk Server |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1aa5fb60-e8db-4cd2-88be-3c71b7b1d44d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b7998225af7ca598d4df5b4fd98f2826edce3a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-biztalk-server"></a><span data-ttu-id="80c04-102">BizTalk Server 的已知问题</span><span class="sxs-lookup"><span data-stu-id="80c04-102">Known Issues with BizTalk Server</span></span>
<span data-ttu-id="80c04-103">本主题列出 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的一些已知问题。</span><span class="sxs-lookup"><span data-stu-id="80c04-103">This topic lists some known issues with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="dtc-firewall-rules"></a><span data-ttu-id="80c04-104">DTC 防火墙规则</span><span class="sxs-lookup"><span data-stu-id="80c04-104">DTC Firewall Rules</span></span>  
 <span data-ttu-id="80c04-105">在单独的计算机上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 时，分布式事务协调器 (MS DTC) 处理计算机之间的事务。</span><span class="sxs-lookup"><span data-stu-id="80c04-105">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are installed on separate computers, Distributed Transaction Coordinator (MS DTC) handles the transactions between the computers.</span></span> <span data-ttu-id="80c04-106">因此，请在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 计算机上的防火墙规则中启用 DTC 端口。</span><span class="sxs-lookup"><span data-stu-id="80c04-106">As a result, enable the DTC ports within your firewall rules on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] computers.</span></span>  
  
 <span data-ttu-id="80c04-107">配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，如果未在防火墙中启用 DTC 端口，可能会发生以下错误：</span><span class="sxs-lookup"><span data-stu-id="80c04-107">When configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the following errors can occur when the DTC ports are not enabled in the firewall:</span></span>  
  
 <span data-ttu-id="80c04-108">**创建数据库; 期间出现 WMI 错误尝试回滚，并删除部分创建的数据库 SQLServerName\BizTalkMsgBoxDb**</span><span class="sxs-lookup"><span data-stu-id="80c04-108">**WMI Error occurred during database creation; attempt to rollback and delete the partially created database'SQLServerName\BizTalkMsgBoxDb'**</span></span>  
  
 <span data-ttu-id="80c04-109">**生成 WMI 错误描述： 类型为 System.EnterpriseServices.TransactionProxyException 已引发的异常。**</span><span class="sxs-lookup"><span data-stu-id="80c04-109">**WMI error description is generated: Exception of type 'System.EnterpriseServices.TransactionProxyException' was thrown.**</span></span>  
  
 <span data-ttu-id="80c04-110">以下链接提供了详细信息：</span><span class="sxs-lookup"><span data-stu-id="80c04-110">The following links provide more information:</span></span>  
  
 [<span data-ttu-id="80c04-111">管理服务器的端口</span><span class="sxs-lookup"><span data-stu-id="80c04-111">Ports for the Administration Server</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=275568)  
  
 [<span data-ttu-id="80c04-112">BizTalk Server 2013 和 2013 R2 的安装后步骤</span><span class="sxs-lookup"><span data-stu-id="80c04-112">Post-installation Steps for BizTalk Server 2013 and 2013 R2</span></span>](../install-and-config-guides/post-installation-steps-for-biztalk-server-2013-and-2013-r2.md)  
  
##  <span data-ttu-id="80c04-113"><a name="BKMK_BAM"></a>业务活动监视</span><span class="sxs-lookup"><span data-stu-id="80c04-113"><a name="BKMK_BAM"></a> Business Activity Monitoring</span></span>  
 <span data-ttu-id="80c04-114">本部分列出了业务活动监视 (BAM) 模块的已知问题。</span><span class="sxs-lookup"><span data-stu-id="80c04-114">This section lists the known issues with the Business Activity Monitoring (BAM) module.</span></span>  
  
### <a name="bam-definition-deployment-fails-due-to-a-sql-login-error"></a><span data-ttu-id="80c04-115">由于 SQL 登录错误而导致 BAM 定义部署失败</span><span class="sxs-lookup"><span data-stu-id="80c04-115">BAM definition deployment fails due to a SQL login error</span></span>  
 <span data-ttu-id="80c04-116">部署 BAM 定义时，该操作可能会由于登录错误（错误代码为 42000）而失败。</span><span class="sxs-lookup"><span data-stu-id="80c04-116">While deploying BAM definition, the operation might fail due to a login error with error code 42000.</span></span>  
  
```  
...  
Deploying Activity... Done.   
Deploying View... ERROR: The BAM deployment failed.   
Server: The current operation was cancelled because another operation in the transaction failed.   
OLE DB error: OLE DB or ODBC error: Login failed for user <username>.; 42000.   
…  
```  
  
 <span data-ttu-id="80c04-117">若要解决此问题，请确保 SQL Analysis Service 登录帐户在与 BAM 相关的所有数据库上都有权限。</span><span class="sxs-lookup"><span data-stu-id="80c04-117">To fix this issue, make sure the SQL Analysis Service logon account has permissions on all databases related to BAM.</span></span>  
  
### <a name="bam-configuration-might-result-in-warnings-related-to-the-bam-analysis-logon-account"></a><span data-ttu-id="80c04-118">BAM 配置可能会导致与 BAM Analysis 登录帐户相关的警告</span><span class="sxs-lookup"><span data-stu-id="80c04-118">BAM configuration might result in warnings related to the BAM Analysis logon account</span></span>  
 <span data-ttu-id="80c04-119">BAM 配置相关 BAM 要能够对其进行访问的所有数据库中添加 BAM 分析登录帐户的权限。</span><span class="sxs-lookup"><span data-stu-id="80c04-119">BAM configuration adds the permissions for BAM Analysis logon account in all the databases related to BAM to be able to access them.</span></span> <span data-ttu-id="80c04-120">但是，如果未满足以下任一先决条件，该配置可能无法访问这些数据库，并且会显示一条警告：</span><span class="sxs-lookup"><span data-stu-id="80c04-120">However, the configuration might fail to do so and give a warning if any of the following prerequisites is not met:</span></span>  
  
-   <span data-ttu-id="80c04-121">运行该 BAM 配置的用户应是安装了 Analysis Service 的计算机上的管理员。</span><span class="sxs-lookup"><span data-stu-id="80c04-121">The user under which the BAM configuration is run should be an administrator on the computer where Analysis Service is installed.</span></span>  
  
-   <span data-ttu-id="80c04-122">在该计算机上必须允许通过防火墙进行远程管理。</span><span class="sxs-lookup"><span data-stu-id="80c04-122">Remote administration through firewall must be allowed on that computer.</span></span>  
  
-   <span data-ttu-id="80c04-123">如果 BAM Analysis 登录帐户是安装了 BAM 相关数据库的 SQL Server 的管理员，那么同样可能会向你显示警告。</span><span class="sxs-lookup"><span data-stu-id="80c04-123">You might also get a warning if the BAM Analysis logon account is an administrator for the SQL Server where the BAM-related databases are installed.</span></span> <span data-ttu-id="80c04-124">你可以忽略该警告并继续操作。</span><span class="sxs-lookup"><span data-stu-id="80c04-124">You can ignore the warning and move ahead.</span></span>  
  
 <span data-ttu-id="80c04-125">**解决方法**– 您必须手动添加到 BAM 相关的所有数据库上的 BAM 分析登录帐户的权限。</span><span class="sxs-lookup"><span data-stu-id="80c04-125">**Workaround** – You must manually add the permission for the BAM Analysis logon account on all databases related to BAM.</span></span>  
  
### <a name="bam-portal-compatibility-with-internet-explorer-10"></a><span data-ttu-id="80c04-126">与 Internet Explorer 10 的 BAM 门户兼容性</span><span class="sxs-lookup"><span data-stu-id="80c04-126">BAM Portal Compatibility with Internet Explorer 10</span></span>  
 <span data-ttu-id="80c04-127">若要将 BAM 门户与 Internet Explorer 10 结合使用，必须始终在兼容模式下使用浏览器。</span><span class="sxs-lookup"><span data-stu-id="80c04-127">To use the BAM Portal with Internet Explorer 10, you must always use the browser in Compatibility mode.</span></span>  
  
### <a name="receiving-notification-e-mails-even-after-the-alert-host-service-is-stopped"></a><span data-ttu-id="80c04-128">即使在警报主机服务停止后仍接收通知电子邮件</span><span class="sxs-lookup"><span data-stu-id="80c04-128">Receiving notification e-mails even after the Alert Host service is stopped</span></span>  
 <span data-ttu-id="80c04-129">如果你使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]，如果你想要使用 BAM 警报，则必须在 SQL Server 中配置数据库邮件功能。</span><span class="sxs-lookup"><span data-stu-id="80c04-129">If you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], you must configure the Database Mail feature in SQL Server if you want to use BAM Alerts.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="80c04-130">使用警报的主机服务与数据库邮件功能结合使用来发送通知警报。</span><span class="sxs-lookup"><span data-stu-id="80c04-130"> uses an Alert Host service in conjunction with the Database Mail feature to send notification alerts.</span></span> <span data-ttu-id="80c04-131">警报主机服务在处理通知后，会将通知工作量继续传递给 SQL Server 中的数据库邮件组件。</span><span class="sxs-lookup"><span data-stu-id="80c04-131">The Alert Host service, after processing the notifications, passes on the notification workload to the Database Mail component in SQL Server.</span></span> <span data-ttu-id="80c04-132">因此，即使停止警报主机服务，也仍可能会收到一些针对警报主机服务已处理但数据库邮件组件未处理的事件通知。</span><span class="sxs-lookup"><span data-stu-id="80c04-132">So, even if you stop the Alert Host service, you might still get a few notifications for events that were processed by the Alert Host service but not by the Database Mail component.</span></span>  
  
### <a name="configuring-tracing-for-bam-alerts"></a><span data-ttu-id="80c04-133">为 BAM 警报配置跟踪</span><span class="sxs-lookup"><span data-stu-id="80c04-133">Configuring tracing for BAM Alerts</span></span>  
 <span data-ttu-id="80c04-134">如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与 [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] 结合使用，并且要为 BAM 警报启用诊断跟踪，则必须通过为 BAM 警报主机创建配置文件来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="80c04-134">If you are using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], and you want to enable diagnostic tracing for BAM Alerts, you must do so by creating a config file for the BAM Alerts host.</span></span> <span data-ttu-id="80c04-135">必须命名为文件**BAMAlerts.exe.config**并将其复制到与该 exe 文件相同的位置 (**BAMAlerts.exe**)，即在 files\microsoft BizTalk Server\Tracking\\。</span><span class="sxs-lookup"><span data-stu-id="80c04-135">You must name the file as **BAMAlerts.exe.config** and copy it to the same location as the EXE (**BAMAlerts.exe**), which is at \Program Files\Microsoft BizTalk Server\Tracking\\.</span></span>  
  
 <span data-ttu-id="80c04-136">示例配置文件如下所示。</span><span class="sxs-lookup"><span data-stu-id="80c04-136">A sample config file looks like the following.</span></span> <span data-ttu-id="80c04-137">此文件记录**信息**级别到事件查看器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="80c04-137">This file logs **Information** level details to the Event Viewer.</span></span>  
  
```  
<configuration>  
  <system.diagnostics>  
    <switches>  
      <add name="LogEventProvider" value="Info"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
##  <span data-ttu-id="80c04-138"><a name="BKMK_Upgrade"></a>BizTalk 服务器与 SQL Server 2012 一起使用时的问题</span><span class="sxs-lookup"><span data-stu-id="80c04-138"><a name="BKMK_Upgrade"></a> Issues While Using BizTalk Server with SQL Server 2012</span></span>  
 <span data-ttu-id="80c04-139">在使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]可以设置**远程登录超时值**SQL Server 中为 20 秒的值。</span><span class="sxs-lookup"><span data-stu-id="80c04-139">While using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] with [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] you can set the **Remote Login Timeout** value in SQL Server to 20 seconds.</span></span> <span data-ttu-id="80c04-140">否则，在任务繁忙时可能会出错。</span><span class="sxs-lookup"><span data-stu-id="80c04-140">If you don’t do so, you might encounter errors in stress conditions.</span></span> <span data-ttu-id="80c04-141">有关如何在中设置的远程登录超时值的说明[!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)]，请参阅[http://msdn.microsoft.com/library/ms175136.aspx](http://msdn.microsoft.com/library/ms175136.aspx)</span><span class="sxs-lookup"><span data-stu-id="80c04-141">For instructions on how to set the Remote Login Timeout value in [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)], see [http://msdn.microsoft.com/library/ms175136.aspx](http://msdn.microsoft.com/library/ms175136.aspx)</span></span>  
  
##  <span data-ttu-id="80c04-142"><a name="BKMK_Adapters"></a>适配器问题</span><span class="sxs-lookup"><span data-stu-id="80c04-142"><a name="BKMK_Adapters"></a> Issues with Adapters</span></span>  
 <span data-ttu-id="80c04-143">本部分列出了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 适配器的已知问题。</span><span class="sxs-lookup"><span data-stu-id="80c04-143">This section lists the known issues with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapters.</span></span>  
  
### <a name="dynamic-port-may-fail-while-using-the-windows-sharepoint-services-wss-adapter"></a><span data-ttu-id="80c04-144">在使用 Windows SharePoint Services (WSS) 适配器时，动态端口可能发生故障</span><span class="sxs-lookup"><span data-stu-id="80c04-144">Dynamic port may fail while using the Windows SharePoint Services (WSS) adapter</span></span>  
 <span data-ttu-id="80c04-145">使用 WSS 适配器的动态端口可能发生故障，并出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="80c04-145">A dynamic port using the WSS adapter may fail with the following error:</span></span>  
  
```  
Error details: The Windows SharePoint Services site was not found. The URL "http://server:443/site" points to a SharePoint object for which there is no Windows SharePoint Services site.  
```  
  
 <span data-ttu-id="80c04-146">**解决方法**:</span><span class="sxs-lookup"><span data-stu-id="80c04-146">**Workarounds**:</span></span>  
  
-   <span data-ttu-id="80c04-147">在端口配置中，站点 URL 同时包括端口号。</span><span class="sxs-lookup"><span data-stu-id="80c04-147">In the port configuration, for the site URL, include the port number as well.</span></span> <span data-ttu-id="80c04-148">例如， `http://server:80/site`。</span><span class="sxs-lookup"><span data-stu-id="80c04-148">For example, `http://server:80/site`.</span></span>  
  
-   <span data-ttu-id="80c04-149">启用**Windows Identity Foundation 3.5**功能。</span><span class="sxs-lookup"><span data-stu-id="80c04-149">Enable the **Windows Identity Foundation 3.5** feature.</span></span>  
  
-   <span data-ttu-id="80c04-150">确认运行 BizTalk 主机的帐户具有到 SharePoint 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="80c04-150">Confirm the account running the BizTalk host has access to SharePoint.</span></span>  
  
### <a name="adapters-available-with-biztalk-adapter-pack-cannot-be-administered-on-a-computer-that-only-has-biztalk-server-administration-component-installed"></a><span data-ttu-id="80c04-151">在只安装了 BizTalk Server 管理组件的计算机上，无法管理 BizTalk 适配器包中提供的适配器</span><span class="sxs-lookup"><span data-stu-id="80c04-151">Adapters available with BizTalk Adapter Pack cannot be administered on a computer that only has BizTalk Server Administration component installed</span></span>  
 <span data-ttu-id="80c04-152">如果在只安装了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台的计算机上安装 BizTalk 适配器包，则随 BizTalk 适配器包安装的适配器在你创建发送端口或接收位置时将不可用。</span><span class="sxs-lookup"><span data-stu-id="80c04-152">If you have BizTalk Adapter Pack installed on a computer that only has the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console installed, the adapters installed as part of the BizTalk Adapter Pack are not available when you create a send port or receive location.</span></span> <span data-ttu-id="80c04-153">原因是，这些适配器依赖于在同一计算机上安装的 BizTalk 运行时。</span><span class="sxs-lookup"><span data-stu-id="80c04-153">This is because these adapters have a dependency on the BizTalk Runtime to be installed on the same computer.</span></span>  
  
 <span data-ttu-id="80c04-154">解决方法 – 在已安装适配器包和 BizTalk Server 管理组件的计算机上安装 BizTalk Server 运行时。</span><span class="sxs-lookup"><span data-stu-id="80c04-154">Workaround – Install the BizTalk Server runtime on the computer that has the Adapter Pack and the BizTalk Server Administration component installed.</span></span> <span data-ttu-id="80c04-155">无需在该计算机上配置 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="80c04-155">You need not configure BizTalk Server on that computer.</span></span>  
  
## <a name="other-issues"></a><span data-ttu-id="80c04-156">其他问题</span><span class="sxs-lookup"><span data-stu-id="80c04-156">Other Issues</span></span>  
  
### <a name="setupbat-for-biztalk-server-samples-runs-with-a-32-bit-command-prompt"></a><span data-ttu-id="80c04-157">用于 BizTalk Server 示例的 Setup.bat 通过 32 位命令提示符来运行</span><span class="sxs-lookup"><span data-stu-id="80c04-157">Setup.bat for BizTalk Server Samples Runs with a 32-bit Command Prompt</span></span>  
 <span data-ttu-id="80c04-158">对于此版本随附的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 示例，必须只从 32 位命令提示符中运行附带的 setup.bat 文件。</span><span class="sxs-lookup"><span data-stu-id="80c04-158">For the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] samples shipped with this release, you must run the accompanying setup.bat files only from a 32-bit command prompt.</span></span> <span data-ttu-id="80c04-159">从 64 位命令提示符中运行批处理文件可能导致失败。</span><span class="sxs-lookup"><span data-stu-id="80c04-159">Running the batch files from a 64-bit command prompt might result in a failure.</span></span>  
  
### <a name="run-setup-as-administrator"></a><span data-ttu-id="80c04-160">以管理员身份运行安装程序</span><span class="sxs-lookup"><span data-stu-id="80c04-160">Run setup as Administrator</span></span>  
 <span data-ttu-id="80c04-161">在安装时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，使用**以管理员身份运行**选项。</span><span class="sxs-lookup"><span data-stu-id="80c04-161">When installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], use the **Run as Administrator** option.</span></span> <span data-ttu-id="80c04-162">否则，可能会出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="80c04-162">Otherwise, the following errors may occur:</span></span>  
  
 <span data-ttu-id="80c04-163">内部错误 2761年。</span><span class="sxs-lookup"><span data-stu-id="80c04-163">Internal Error 2761.</span></span> <span data-ttu-id="80c04-164">返回代码： 1</span><span class="sxs-lookup"><span data-stu-id="80c04-164">Return Code: 1</span></span>  
  
 <span data-ttu-id="80c04-165">MSI 安装返回 1603-安装时发生严重错误。</span><span class="sxs-lookup"><span data-stu-id="80c04-165">MSI installation returned 1603 - Fatal error during installation.</span></span>  
  
### <a name="using-certificates-with-1024-key-for-encoding-and-signing-results-in-failure-of-mime-smime-decoding"></a><span data-ttu-id="80c04-166">将证书用于 1024 密钥进行编码和签名会导致 MIME-SMIME 解码失败</span><span class="sxs-lookup"><span data-stu-id="80c04-166">Using certificates with 1024 key for encoding and signing results in failure of MIME-SMIME decoding</span></span>  
 <span data-ttu-id="80c04-167">在 Windows 8 中，如果使用包含 1024 密钥的证书对消息进行加密和签名操作，MIME-SMIME 解码在验证消息时会失败。</span><span class="sxs-lookup"><span data-stu-id="80c04-167">On Windows 8, when a message is encrypted and signed using certificates with 1024 key, MIME-SMIME decoding fails in authenticating the message.</span></span> <span data-ttu-id="80c04-168">为避免此问题，可使用包含 2048 密钥的证书。</span><span class="sxs-lookup"><span data-stu-id="80c04-168">To avoid this issue, you can use certificates with 2048 key.</span></span>  
  
### <a name="uddi-resolver-with-esb-toolkit-gives-a-serialization-error"></a><span data-ttu-id="80c04-169">UDDI 解析程序在与 ESB 工具包结合使用时发出序列化错误</span><span class="sxs-lookup"><span data-stu-id="80c04-169">UDDI resolver with ESB Toolkit gives a Serialization error</span></span>  
 <span data-ttu-id="80c04-170">如果将 UDDI 与 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]结合使用，在查找绑定详细信息时可能会遇到 XML 序列化错误。</span><span class="sxs-lookup"><span data-stu-id="80c04-170">While using UDDI with the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] you might encounter an XML serialization error when looking up the binding details.</span></span> <span data-ttu-id="80c04-171">如果未指定绑定密钥，则会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="80c04-171">This error occurs if the binding key is not specified.</span></span>  
  
### <a name="the-itinerary-designer-for-esb-toolkit"></a><span data-ttu-id="80c04-172">ESB 工具包的路线设计器</span><span class="sxs-lookup"><span data-stu-id="80c04-172">The itinerary designer for ESB Toolkit</span></span>  
 <span data-ttu-id="80c04-173">现在，[!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]的路线设计器属于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装介质的一部分。</span><span class="sxs-lookup"><span data-stu-id="80c04-173">The itinerary designer for the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] is now part of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation media.</span></span> <span data-ttu-id="80c04-174">在介质的根文件夹中可以找到路线设计器，其名称为 `Microsoft.Practices.Services.Itinerary.DslPackage.vsix`。</span><span class="sxs-lookup"><span data-stu-id="80c04-174">You can find the itinerary designer at the root folder of the media and has the name `Microsoft.Practices.Services.Itinerary.DslPackage.vsix`.</span></span> <span data-ttu-id="80c04-175">以前，此文件位于安装 [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)] 的位置，该位置通常为 \Program Files\Microsoft [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80c04-175">Earlier, this file was available at the location where you install the [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)], which typically is \Program Files\Microsoft [!INCLUDE[esbToolkit_short](../includes/esbtoolkit-short-md.md)].</span></span>  
  
### <a name="edi"></a><span data-ttu-id="80c04-176">EDI</span><span class="sxs-lookup"><span data-stu-id="80c04-176">EDI</span></span>  
 <span data-ttu-id="80c04-177">正在使用 EDI 批处理。</span><span class="sxs-lookup"><span data-stu-id="80c04-177">EDI Batching is being used.</span></span> <span data-ttu-id="80c04-178">在使用阿拉伯语日历或阿拉伯语本地设置时，业务流程挂起，并出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="80c04-178">When using an Arabic calendar or Arabic local settings, the orchestration suspends with the following error:</span></span>  
  
 <span data-ttu-id="80c04-179">**错误代码： 0xC0C01B52 （业务流程引擎错误） 错误描述： 冻结期间挂起由于持久性失败。**</span><span class="sxs-lookup"><span data-stu-id="80c04-179">**Error Code: 0xC0C01B52 (Orchestration Engine Error)Error Description: Suspend due to persistence failure during dehydration.**</span></span> <span data-ttu-id="80c04-180">阿拉伯语公历支持从日期*04/30/1900 00.00.00*到*05/13/2029年 23:59:59*。</span><span class="sxs-lookup"><span data-stu-id="80c04-180">Arabic Gregorian supports dates from *04/30/1900 00.00.00* to *05/13/2029 23:59:59*.</span></span>  
  
 <span data-ttu-id="80c04-181">要解决此行为的问题，请输入有效的阿拉伯语结束日期。</span><span class="sxs-lookup"><span data-stu-id="80c04-181">To resolve this behavior, enter a valid Arabic end date.</span></span>  
  
### <a name="enterprise-single-sign-on"></a><span data-ttu-id="80c04-182">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="80c04-182">Enterprise Single Sign-On</span></span>  
 <span data-ttu-id="80c04-183">安装 Enterprise Single Sign-On (ESSO) 或重新启动 ESSO 服务时，你可能会看到事件查看器中记录的以下错误。</span><span class="sxs-lookup"><span data-stu-id="80c04-183">When you install Enterprise Single Sign-On (ESSO) or when you restart the ESSO service you might see the following error logged in the Event Viewer.</span></span>  
  
 <span data-ttu-id="80c04-184">**无法加载 \program Files\Enterprise 单一登录 On\SSOPSServer.dll 错误代码： 0x8007007E，找不到指定的模块。**</span><span class="sxs-lookup"><span data-stu-id="80c04-184">**Failed to load \Program Files\Common Files\Enterprise Single Sign-On\SSOPSServer.dll Error code: 0x8007007E, The specified module could not be found.**</span></span> <span data-ttu-id="80c04-185">可以安全地忽略此错误。</span><span class="sxs-lookup"><span data-stu-id="80c04-185">You can safely ignore this error.</span></span>
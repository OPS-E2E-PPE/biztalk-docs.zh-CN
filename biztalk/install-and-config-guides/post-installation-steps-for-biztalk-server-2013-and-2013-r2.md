---
title: "BizTalk Server 2013 和 2013 R2 的安装后步骤 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3b47843-9da5-4144-8b84-135494b8ab43
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b86d8c4c1e1a22dad349c2cc8c2be5ca4b206b2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="post-installation-steps-for-biztalk-server-2013-and-2013-r2"></a><span data-ttu-id="65b2b-102">BizTalk Server 2013 和 2013 R2 的安装后步骤</span><span class="sxs-lookup"><span data-stu-id="65b2b-102">Post-installation Steps for BizTalk Server 2013 and 2013 R2</span></span>
  
##  <span data-ttu-id="65b2b-103"><a name="BKMK_NamedPipes"></a>启用 TCP/IP 和命名管道</span><span class="sxs-lookup"><span data-stu-id="65b2b-103"><a name="BKMK_NamedPipes"></a> Enable TCP/IP and Named Pipes</span></span>  
  
1.  <span data-ttu-id="65b2b-104">打开“SQL Server 配置管理器”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-104">Open **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="65b2b-105">展开“SQL Server 网络配置”，然后选择“MSSQLSERVER 的协议”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-105">Expand **SQL Server Network Configuration**, and select **Protocols for MSSQLSERVER**.</span></span>  
  
4.  <span data-ttu-id="65b2b-106">验证“TCP/IP”和“命名管道”是否都已启用。</span><span class="sxs-lookup"><span data-stu-id="65b2b-106">Verify that both **TCP/IP** and **Named Pipes** are enabled.</span></span> <span data-ttu-id="65b2b-107">如果已启用，继续进行下一步。</span><span class="sxs-lookup"><span data-stu-id="65b2b-107">If enabled, proceed to the next step.</span></span>  
  
     <span data-ttu-id="65b2b-108">如果未启用：</span><span class="sxs-lookup"><span data-stu-id="65b2b-108">If not enabled:</span></span>  
  
    -   <span data-ttu-id="65b2b-109">右键单击该协议，然后单击“启用”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-109">Right-click the protocol, and then click **Enable**.</span></span>  
  
    -   <span data-ttu-id="65b2b-110">如有必要，请重复此步骤以启用另一个协议。</span><span class="sxs-lookup"><span data-stu-id="65b2b-110">Repeat to enable the other protocol if necessary.</span></span>  
  
    -   <span data-ttu-id="65b2b-111">在左侧窗格中，单击“SQL Server 服务”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-111">In the left-hand pane, click **SQL Server Services**.</span></span>  
  
    -   <span data-ttu-id="65b2b-112">在右侧窗格中，右键单击“SQL Server (MSSQLSERVER)”，然后单击“停止”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-112">In the right-hand pane, right-click **SQL Server (MSSQLSERVER)**, and click **Stop**.</span></span>  
  
    -   <span data-ttu-id="65b2b-113">服务停止后，右键单击“SQL Server (MSSQLSERVER)”，然后单击“启动”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-113">When the service has stopped, right-click **SQL Server (MSSQLSERVER)**, and click **Start**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="65b2b-114">如果使用的是 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)]，可以停止“NS$BAMAlerts”服务。</span><span class="sxs-lookup"><span data-stu-id="65b2b-114">If you are using [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)], the **NS$BAMAlerts** service may be stopped.</span></span> <span data-ttu-id="65b2b-115">重新启动服务。</span><span class="sxs-lookup"><span data-stu-id="65b2b-115">Restart the service.</span></span>  
  
5.  <span data-ttu-id="65b2b-116">关闭“配置管理器”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-116">Close the **Configuration Manager**.</span></span>  
  
##  <span data-ttu-id="65b2b-117"><a name="BKMK_DTC"></a>启用本地主机服务器上的 DTC</span><span class="sxs-lookup"><span data-stu-id="65b2b-117"><a name="BKMK_DTC"></a> Enable DTC on the Local Host Server</span></span>  
  
1.  <span data-ttu-id="65b2b-118">打开“组件服务”：</span><span class="sxs-lookup"><span data-stu-id="65b2b-118">Open Component Services:</span></span>  
  
     <span data-ttu-id="65b2b-119">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**：选择 Windows 按钮，并键入“组件服务”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-119">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : Select the Windows button, and type **Component Services**.</span></span> <span data-ttu-id="65b2b-120">在“结果”窗口中，选择“组件服务”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-120">In the Results window, select **Component Services**.</span></span>  
  
     <span data-ttu-id="65b2b-121">**Windows 8.1**：选择 Windows 按钮，并键入“管理工具”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-121">**Windows 8.1**: Select the Windows button, and type **Administrative Tools**.</span></span> <span data-ttu-id="65b2b-122">在“搜索”窗口中，选择“设置”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-122">In the Search window, select **Settings**.</span></span> <span data-ttu-id="65b2b-123">在“结果”窗口中，单击“管理工具”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-123">In the Results window, click **Administrative Tools**.</span></span> <span data-ttu-id="65b2b-124">双击“组件服务”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-124">Double-click **Component Services**.</span></span>  
  
     <span data-ttu-id="65b2b-125">**Windows 7 SP1**：选择“启动”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-125">**Windows 7 SP1**: Select **Start**.</span></span> <span data-ttu-id="65b2b-126">在“搜索”文本框中，键入“组件服务”，然后单击以打开。</span><span class="sxs-lookup"><span data-stu-id="65b2b-126">In the **Search** text box, type **Component Services**, and click it to open.</span></span>  
  
2.  <span data-ttu-id="65b2b-127">在控制台树中，依次展开“组件服务”、“计算机”、“我的计算机”、“分布式事务处理协调器”，然后单击“本地 DTC”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-127">In the console tree, expand **Component Services**, expand **Computers**, expand **My Computer**, expand **Distributed Transaction Coordinator**, and then click **Local DTC**.</span></span>  
  
3.  <span data-ttu-id="65b2b-128">右键单击“本地 DTC”，选择“属性”打开“本地 DTC 属性”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-128">Right-click **Local DTC** and select **Properties** to open the **Local DTC Properties**.</span></span>  
  
4.  <span data-ttu-id="65b2b-129">选择“安全”选项卡。</span><span class="sxs-lookup"><span data-stu-id="65b2b-129">Select the **Security** tab.</span></span>  
  
5.  <span data-ttu-id="65b2b-130">确认已选中以下选项：</span><span class="sxs-lookup"><span data-stu-id="65b2b-130">Confirm the following options are checked:</span></span>  
  
    -   <span data-ttu-id="65b2b-131">**网络 DTC 访问**</span><span class="sxs-lookup"><span data-stu-id="65b2b-131">**Network DTC Access**</span></span>  
  
    -   <span data-ttu-id="65b2b-132">**允许入站**</span><span class="sxs-lookup"><span data-stu-id="65b2b-132">**Allow Inbound**</span></span>  
  
    -   <span data-ttu-id="65b2b-133">**允许出站**</span><span class="sxs-lookup"><span data-stu-id="65b2b-133">**Allow Outbound**</span></span>  
  
    -   <span data-ttu-id="65b2b-134">**不要求进行验证**</span><span class="sxs-lookup"><span data-stu-id="65b2b-134">**No Authentication Required**</span></span>  
  
     <span data-ttu-id="65b2b-135">有关可能需要的其他设置，请参阅 [MSDTC 疑难解答](../core/troubleshooting-problems-with-msdtc.md)。</span><span class="sxs-lookup"><span data-stu-id="65b2b-135">For additional settings that may be needed, see [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md).</span></span>  
  
6.  <span data-ttu-id="65b2b-136">选择“确定”关闭“本地 DTC 属性”对话框。</span><span class="sxs-lookup"><span data-stu-id="65b2b-136">Select **OK** to close the **Local DTC Properties** dialog box.</span></span> <span data-ttu-id="65b2b-137">如果系统提示，请重启 MSDTC 服务。</span><span class="sxs-lookup"><span data-stu-id="65b2b-137">Restart the MSDTC service if prompted.</span></span>  
  
7.  <span data-ttu-id="65b2b-138">关闭“组件服务”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-138">Close **Component Services**.</span></span>  
  
##  <span data-ttu-id="65b2b-139"><a name="BKMK_Firewall"></a>将 Windows 防火墙配置为启用 DTC</span><span class="sxs-lookup"><span data-stu-id="65b2b-139"><a name="BKMK_Firewall"></a> Configure Windows Firewall to Enable DTC</span></span>  
  
1.  <span data-ttu-id="65b2b-140">打开“Windows 防火墙”：</span><span class="sxs-lookup"><span data-stu-id="65b2b-140">Open **Windows Firewall**:</span></span>  
  
     <span data-ttu-id="65b2b-141">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**：单击 Windows 按钮，并键入“Windows 防火墙”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-141">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : Click the Windows button, and type **Windows Firewall**.</span></span> <span data-ttu-id="65b2b-142">在“结果”窗口中，单击“Windows 防火墙”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-142">In the Results window, click **Windows Firewall**.</span></span>  
  
     <span data-ttu-id="65b2b-143">**Windows 8.1**：单击 Windows 按钮，并键入“Windows 防火墙”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-143">**Windows 8.1**: Click the Windows button, and type **Windows Firewall**.</span></span> <span data-ttu-id="65b2b-144">在“搜索”窗口中，单击“设置”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-144">In the Search window, click **Settings**.</span></span> <span data-ttu-id="65b2b-145">在“结果”窗口中，单击“Windows 防火墙”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-145">In the Results window, click **Windows Firewall**.</span></span>  
  
     <span data-ttu-id="65b2b-146">**Windows 7 SP1**：单击“启动”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-146">**Windows 7 SP1**: Click **Start**.</span></span> <span data-ttu-id="65b2b-147">在“搜索”文本框中，键入“Windows 防火墙”，然后单击打开。</span><span class="sxs-lookup"><span data-stu-id="65b2b-147">In the **Search** text box, type **Windows Firewall**, and click it to open.</span></span>  
  
2.  <span data-ttu-id="65b2b-148">单击“高级设置”，然后单击“入站规则”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-148">Click **Advanced Settings** and click **Inbound Rules**.</span></span>  
  
3.  <span data-ttu-id="65b2b-149">在“入站规则”窗格中，（根据需要）右键单击“分布式事务处理协调器”\*，然后单击“启用规则”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-149">In the **Inbound Rules** pane, right-click **Distributed Transaction Coordinator** \* (as appropriate), and then click **Enable Rule**.</span></span>  
  
4.  <span data-ttu-id="65b2b-150">单击“出站规则”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-150">Click **Outbound Rules**.</span></span>  
  
5.  <span data-ttu-id="65b2b-151">在“出站规则”窗格中，（根据需要）右键单击“分布式事务处理协调器”\*，然后单击“启用规则”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-151">In the **Outbound Rules** pane, right-click **Distributed Transaction Coordinator** \* (as appropriate), and then click **Enable Rule**.</span></span>  
  
6.  <span data-ttu-id="65b2b-152">在“控制面板”中，将视图更改为按图标列出，然后双击“管理工具”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-152">On the **Control Panel**, change the view to list by icons, and then double-click **Administrative Tools**.</span></span>  
  
7.  <span data-ttu-id="65b2b-153">双击“服务”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-153">Double-click **Services**.</span></span>  
  
8.  <span data-ttu-id="65b2b-154">右键单击“COM+ 系统应用程序”，再单击“重启”，然后等待服务重启。</span><span class="sxs-lookup"><span data-stu-id="65b2b-154">Right-click **COM+ System Application**, click **Restart**, and wait for the service to restart.</span></span>  
  
9. <span data-ttu-id="65b2b-155">右键单击并重启“分布式事务处理协调器”服务。</span><span class="sxs-lookup"><span data-stu-id="65b2b-155">Right-click and restart the **Distributed Transaction Coordinator** service.</span></span>  
  
10. <span data-ttu-id="65b2b-156">右键单击并重启“SQL Server (MSSQLSERVER)”服务。</span><span class="sxs-lookup"><span data-stu-id="65b2b-156">Right-click and restart the **SQL Server (MSSQLSERVER)** service.</span></span>  
  
11. <span data-ttu-id="65b2b-157">关闭“服务(本地)”，然后关闭“管理工具”。</span><span class="sxs-lookup"><span data-stu-id="65b2b-157">Close **Services (Local)**, and then close **Administrative Tools**.</span></span>  
  
##  <span data-ttu-id="65b2b-158"><a name="BKMK_SQLAgent"></a>配置 SQL 代理作业</span><span class="sxs-lookup"><span data-stu-id="65b2b-158"><a name="BKMK_SQLAgent"></a> Configure SQL Agent Jobs</span></span>  
  
|<span data-ttu-id="65b2b-159">作业</span><span class="sxs-lookup"><span data-stu-id="65b2b-159">Job</span></span>|<span data-ttu-id="65b2b-160">说明</span><span class="sxs-lookup"><span data-stu-id="65b2b-160">Description</span></span>|<span data-ttu-id="65b2b-161">配置原因</span><span class="sxs-lookup"><span data-stu-id="65b2b-161">Why configure</span></span>|  
|---------|-----------------|-------------------|  
|<span data-ttu-id="65b2b-162">**备份 BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="65b2b-162">**Backup BizTalk Server**</span></span>|<span data-ttu-id="65b2b-163">此 SQL 代理作业用于备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库和日志文件。</span><span class="sxs-lookup"><span data-stu-id="65b2b-163">This SQL Agent job backs up the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases and the log files.</span></span> <span data-ttu-id="65b2b-164">在配置该作业时，需要确定频率和文件位置等参数。</span><span class="sxs-lookup"><span data-stu-id="65b2b-164">When configuring the job, you determine parameters like frequency and file location.</span></span><br /><br /> <span data-ttu-id="65b2b-165">以下链接介绍了 SQL 代理作业及其参数：</span><span class="sxs-lookup"><span data-stu-id="65b2b-165">The following links describe the SQL Agent job and its parameters:</span></span><br /><br /> <span data-ttu-id="65b2b-166">[备份和还原 BizTalk Server 数据库](http://msdn.microsoft.com/library/aa561125\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="65b2b-166">[Backing Up and Restoring BizTalk Server Databases](http://msdn.microsoft.com/library/aa561125\(v=bts.80\).aspx)</span></span><br /><br /> <span data-ttu-id="65b2b-167">[如何配置备份 BizTalk Server 作业](http://msdn.microsoft.com/library/aa546765\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="65b2b-167">[How to Configure the Backup BizTalk Server Job](http://msdn.microsoft.com/library/aa546765\(v=bts.80\).aspx)</span></span>|<span data-ttu-id="65b2b-168">此 SQL 代理作业还会截断事务日志，这有助于改进性能。</span><span class="sxs-lookup"><span data-stu-id="65b2b-168">This SQL Agent job also truncates the transaction logs, which helps improve performance.</span></span><br /><br /> <span data-ttu-id="65b2b-169">**备份 BizTalk Server** 作业不会移除或删除备份文件，包括较早的文件。</span><span class="sxs-lookup"><span data-stu-id="65b2b-169">The **Backup BizTalk Server** job does not remove or delete backup files, including older files.</span></span> <span data-ttu-id="65b2b-170">若要删除备份文件，请参阅[当备份文件在 Microsoft BizTalk Server 数据库服务器中累积一段时间后，“备份 BizTalk Server”作业失败](http://support.microsoft.com/kb/982546)。</span><span class="sxs-lookup"><span data-stu-id="65b2b-170">To delete backup files, refer to [The "Backup BizTalk Server" job fails when backup files accumulate over time in the Microsoft BizTalk Server database server](http://support.microsoft.com/kb/982546).</span></span>|  
|<span data-ttu-id="65b2b-171">**DTA 清除和存档**</span><span class="sxs-lookup"><span data-stu-id="65b2b-171">**DTA Purge and Archive**</span></span>|<span data-ttu-id="65b2b-172">此 SQL 代理作业可截断并存档 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 跟踪数据库 (BizTalkDTADb)。</span><span class="sxs-lookup"><span data-stu-id="65b2b-172">This SQL Agent job truncates and archives the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Tracking database (BizTalkDTADb).</span></span> <span data-ttu-id="65b2b-173">在配置该作业时，需要确定已完成实例的保留天数以及所有数据的保留天数等参数。</span><span class="sxs-lookup"><span data-stu-id="65b2b-173">When configuring the job, you determine parameters like how many days to keep completed instances and how many to days to keep all data.</span></span><br /><br /> <span data-ttu-id="65b2b-174">以下链接介绍了 SQL 代理作业及其参数：</span><span class="sxs-lookup"><span data-stu-id="65b2b-174">The following links describe the SQL Agent job and its parameters:</span></span><br /><br /> <span data-ttu-id="65b2b-175">[存档和清除 BizTalk 跟踪数据库](http://msdn.microsoft.com/library/aa560754\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="65b2b-175">[Archiving and Purging the BizTalk Tracking Database](http://msdn.microsoft.com/library/aa560754\(v=bts.80\).aspx)</span></span><br /><br /> <span data-ttu-id="65b2b-176">[如何配置 DTA 清除和存档作业](http://msdn.microsoft.com/library/aa558715\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="65b2b-176">[How to Configure the DTA Purge and Archive Job](http://msdn.microsoft.com/library/aa558715\(v=bts.80\).aspx)</span></span>|<span data-ttu-id="65b2b-177">此 SQL 代理作业通过维护跟踪主机和清除跟踪事件直接影响性能。</span><span class="sxs-lookup"><span data-stu-id="65b2b-177">This SQL Agent job directly impacts performance by maintaining the Tracking host and purging tracking events.</span></span><br /><br /> <span data-ttu-id="65b2b-178">性能主题包括：</span><span class="sxs-lookup"><span data-stu-id="65b2b-178">Performance topics include:</span></span><br /><br /> [<span data-ttu-id="65b2b-179">如何对 BizTalk Server 数据库进行维护和故障排除</span><span class="sxs-lookup"><span data-stu-id="65b2b-179">How to maintain and troubleshoot BizTalk Server databases</span></span>](http://support.microsoft.com/kb/952555)<br /><br /> <span data-ttu-id="65b2b-180">[跟踪数据库的大小调整准则](http://msdn.microsoft.com/library/aa559162\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="65b2b-180">[Tracking Database Sizing Guidelines](http://msdn.microsoft.com/library/aa559162\(v=bts.80\).aspx)</span></span>|  
  
 <span data-ttu-id="65b2b-181">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="65b2b-181">**Additional**</span></span>  
  
-   <span data-ttu-id="65b2b-182">安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，会自动创建若干个 SQL 代理作业，如以下链接所述：</span><span class="sxs-lookup"><span data-stu-id="65b2b-182">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is installed, several SQL Agent jobs are automatically created, as described in the following links:</span></span>  
  
     [<span data-ttu-id="65b2b-183">BizTalk Server 中的 SQL Server 代理作业的说明</span><span class="sxs-lookup"><span data-stu-id="65b2b-183">Description of the SQL Server Agent jobs in BizTalk Server</span></span>](http://support.microsoft.com/kb/919776)  
  
     <span data-ttu-id="65b2b-184">[数据库结构和作业](http://msdn.microsoft.com/library/aa561960\(v=bts.80\).aspx)</span><span class="sxs-lookup"><span data-stu-id="65b2b-184">[Database Structure and Jobs](http://msdn.microsoft.com/library/aa561960\(v=bts.80\).aspx)</span></span>  
  
##  <span data-ttu-id="65b2b-185"><a name="BKMK_InstallCU"></a>安装累积更新</span><span class="sxs-lookup"><span data-stu-id="65b2b-185"><a name="BKMK_InstallCU"></a> Install Cumulative Updates</span></span>  
 <span data-ttu-id="65b2b-186">安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 之后，安装 Windows Update 中列出的所有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 累积更新。</span><span class="sxs-lookup"><span data-stu-id="65b2b-186">After you install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], install any [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cumulative updates listed in Windows Update.</span></span> <span data-ttu-id="65b2b-187">[KB article 2555976](http://support.microsoft.com/kb/2555976) 列出了可用的 Service Pack 和累积更新。</span><span class="sxs-lookup"><span data-stu-id="65b2b-187">[KB article 2555976](http://support.microsoft.com/kb/2555976) lists available service packs and cumulative updates.</span></span>  
  
## <a name="next"></a><span data-ttu-id="65b2b-188">Next</span><span class="sxs-lookup"><span data-stu-id="65b2b-188">Next</span></span>  
[<span data-ttu-id="65b2b-189">配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="65b2b-189">Configure BizTalk Server</span></span>](../install-and-config-guides/configure-biztalk-server.md)
  
## <a name="see-also"></a><span data-ttu-id="65b2b-190">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65b2b-190">See Also</span></span>  
 [<span data-ttu-id="65b2b-191">附录 A：无提示安装</span><span class="sxs-lookup"><span data-stu-id="65b2b-191">Appendix A: Silent Installation</span></span>](../install-and-config-guides/appendix-a-silent-installation.md) 
 
[<span data-ttu-id="65b2b-192">附录 B：安装 Microsoft SharePoint 适配器</span><span class="sxs-lookup"><span data-stu-id="65b2b-192">Appendix B: Install the Microsoft SharePoint Adapter</span></span>](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)  

[<span data-ttu-id="65b2b-193">附录 C：可再发行的 CAB 文件</span><span class="sxs-lookup"><span data-stu-id="65b2b-193">Appendix C: Redistributable CAB Files</span></span>](../install-and-config-guides/appendix-c-redistributable-cab-files.md)  

[<span data-ttu-id="65b2b-194">附录 D：创建 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="65b2b-194">Appendix D: Create the SMTP Server</span></span>](../install-and-config-guides/appendix-d-create-the-smtp-server.md)

[<span data-ttu-id="65b2b-195">卸载 BizTalk Server 并取消配置以将其删除</span><span class="sxs-lookup"><span data-stu-id="65b2b-195">Uninstall and unconfigure BizTalk Server to remove it</span></span>](../install-and-config-guides/uninstall-and-unconfigure-biztalk-server-to-remove-it.md)

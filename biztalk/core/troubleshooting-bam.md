---
title: "故障排除 BAM |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e63299a8-5c74-4337-ba20-3213e0c6ea1f
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d47932ffd9f7843d0b3d95073ca54bce987b8f75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-bam"></a><span data-ttu-id="913bf-102">故障排除 BAM</span><span class="sxs-lookup"><span data-stu-id="913bf-102">Troubleshooting BAM</span></span>
<span data-ttu-id="913bf-103">本主题提供了帮助你解决使用业务活动监视 (BAM) 时可能遇到的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="913bf-103">This topic provides information to help you troubleshoot problems you might encounter when using Business Activity Monitoring (BAM).</span></span>  
  
## <a name="bam-deployment-failed"></a><span data-ttu-id="913bf-104">BAM 部署失败</span><span class="sxs-lookup"><span data-stu-id="913bf-104">BAM deployment failed</span></span>  
 <span data-ttu-id="913bf-105">如果在 SQL Server Analysis Services 不可用时尝试部署包含实时聚合 (RTA) 的 BAM 定义，则 Bm.exe 命令将显示以下消息：</span><span class="sxs-lookup"><span data-stu-id="913bf-105">If you attempt to deploy a BAM definition that includes a real-time aggregation (RTA) when SQL Server Analysis Services is not available, the Bm.exe command will display the following message:</span></span>  
  
 <span data-ttu-id="913bf-106">错误： BAM 部署失败。</span><span class="sxs-lookup"><span data-stu-id="913bf-106">ERROR: BAM deployment failed.</span></span> <span data-ttu-id="913bf-107">无法进行连接。</span><span class="sxs-lookup"><span data-stu-id="913bf-107">A connection cannot be made.</span></span> <span data-ttu-id="913bf-108">请确保服务器正在运行。</span><span class="sxs-lookup"><span data-stu-id="913bf-108">Ensure that the server is running.</span></span> <span data-ttu-id="913bf-109">无法建立连接，因为目标计算机主动拒绝 *\<IP 地址 >*。</span><span class="sxs-lookup"><span data-stu-id="913bf-109">No connection could be made because the target machine actively refused it *\<IP address>*.</span></span>  
  
 <span data-ttu-id="913bf-110">出现这种情况的原因是，SQL Server Analysis Services 必须已经安装和配置，并且必须正在运行才能部署包含 RTA 的 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="913bf-110">This occurs because SQL Server Analysis Services must have been installed and configured, and must be running in order to deploy a BAM definition that includes an RTA.</span></span>  
  
## <a name="cannot-refresh-the-live-data-workbook"></a><span data-ttu-id="913bf-111">无法刷新实时数据工作簿</span><span class="sxs-lookup"><span data-stu-id="913bf-111">Cannot refresh the live data workbook</span></span>  
 <span data-ttu-id="913bf-112">当你尝试在实时数据工作簿中刷新数据时，Microsoft Office Excel 可能会显示以下错误：</span><span class="sxs-lookup"><span data-stu-id="913bf-112">When you try to refresh the data in a live data workbook, Microsoft Office Excel might display the following error:</span></span>  
  
 `XML for Analysis parser: The CurrentCatalog XML/A property was not specified.`  
  
 <span data-ttu-id="913bf-113">出现这种情况是因为尚未将 BAM 加载项添加到 Excel。</span><span class="sxs-lookup"><span data-stu-id="913bf-113">This occurs because the BAM add-in has not been added to Excel.</span></span>  
  
#### <a name="to-add-the-bam-add-in-to-excel"></a><span data-ttu-id="913bf-114">向 Excel 添加 BAM 加载项</span><span class="sxs-lookup"><span data-stu-id="913bf-114">To add the BAM add-in to Excel</span></span>  
  
1.  <span data-ttu-id="913bf-115">单击**启动**，指向**所有程序**，指向**Microsoft Office**，然后单击**Microsoft Office Excel**。</span><span class="sxs-lookup"><span data-stu-id="913bf-115">Click **Start**, point to **All Programs**, point to **Microsoft Office**, and then click **Microsoft Office Excel**.</span></span>  
  
2.  <span data-ttu-id="913bf-116">单击**Microsoft Office 按钮**，然后单击**Excel 选项**。</span><span class="sxs-lookup"><span data-stu-id="913bf-116">Click the **Microsoft Office Button**, and then click **Excel Options**.</span></span>  
  
3.  <span data-ttu-id="913bf-117">在**Excel 选项**对话框中，单击**外接程序**。</span><span class="sxs-lookup"><span data-stu-id="913bf-117">In the **Excel Options** dialog box, click **Add-Ins**.</span></span>  
  
4.  <span data-ttu-id="913bf-118">在**外接程序**窗格中，单击**转**。</span><span class="sxs-lookup"><span data-stu-id="913bf-118">In the **Add-Ins** pane, click **Go**.</span></span>  
  
5.  <span data-ttu-id="913bf-119">在**外接程序**对话框中，选择**业务活动监视**复选框，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="913bf-119">In the **Add-Ins** dialog box, select the **Business Activity Monitoring** check box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="913bf-120">![添加 &#45; 单元对话框中](../core/media/addins.gif "外接程序")</span><span class="sxs-lookup"><span data-stu-id="913bf-120">![Add&#45;Ins dialog box](../core/media/addins.gif "AddIns")</span></span>  
  
## <a name="errorobject-library-invalid-or-contains-references-to-object-definitions-that-could-not-be-found-with-bam-excel-add-in-in-office"></a><span data-ttu-id="913bf-121">Office 中的 BAM Excel 加载项出现错误：“对象库无效或包含对无法找到的对象定义的引用”</span><span class="sxs-lookup"><span data-stu-id="913bf-121">Error:"Object library invalid or contains references to object definitions that could not be found" with BAM Excel Add-In in Office</span></span>  
 <span data-ttu-id="913bf-122">在升级 Microsoft Excel 后尝试使用 BAM Excel 加载项时，可能会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="913bf-122">You may receive this error, when you try use the BAM Excel Add-In after you upgrade Microsoft Excel.</span></span>  
  
 <span data-ttu-id="913bf-123">**解决方法：**由于 BAM 外接程序使用 ActiveX 控件，你必须从以下目录中删除任何缓存的.exd 文件：</span><span class="sxs-lookup"><span data-stu-id="913bf-123">**Resolution:** Since the BAM Add-In uses ActiveX controls, you have to delete any cached .exd files from the following directories:</span></span>  
  
-   <span data-ttu-id="913bf-124">C:\Documents and Settings\\< 用户名\>\Application Data\Microsoft\Forms</span><span class="sxs-lookup"><span data-stu-id="913bf-124">C:\Documents and Settings\\<username\>\Application Data\Microsoft\Forms</span></span>  
  
-   <span data-ttu-id="913bf-125">C:\Documents and Settings\\< 用户名\>\AppData\Local\Temp\VBE</span><span class="sxs-lookup"><span data-stu-id="913bf-125">C:\Documents and Settings\\<username\>\AppData\Local\Temp\VBE</span></span>  
  
## <a name="bam-portal-cannot-connect"></a><span data-ttu-id="913bf-126">BAM 门户无法连接</span><span class="sxs-lookup"><span data-stu-id="913bf-126">BAM portal cannot connect</span></span>  
 <span data-ttu-id="913bf-127">在 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] 中，你必须以管理员身份运行 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="913bf-127">In [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)], you must run the BAM portal as an administrator.</span></span>  
  
#### <a name="to-run-the-bam-portal-on-windows-server-2008-r2-or-windows-7"></a><span data-ttu-id="913bf-128">在 Windows Server 2008 R2 或 Windows 7 上运行 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="913bf-128">To run the BAM portal on Windows Server 2008 R2 or Windows 7</span></span>  
  
1.  <span data-ttu-id="913bf-129">单击**启动**，指向**所有程序**，右键单击**Internet Explorer**，然后单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="913bf-129">Click **Start**, point to **All Programs**, right-click **Internet Explorer**, and then click **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="913bf-130">在**用户帐户控制**对话框中，单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="913bf-130">In the **User Account Control** dialog box, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="913bf-131">在 Internet Explorer 地址栏中，键入`http://<server>/BAM`，其中*\<服务器 >*是运行 BAM 门户的计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="913bf-131">In the Internet Explorer address bar, type `http://<server>/BAM`, where *\<server>* is the name of the computer that is running the BAM portal.</span></span>  
  
## <a name="bam-portal-does-not-work-if-invalid-users-are-granted-permissions"></a><span data-ttu-id="913bf-132">如果向无效用户授予权限，BAM 门户则不起作用</span><span class="sxs-lookup"><span data-stu-id="913bf-132">BAM portal does not work if invalid users are granted permissions</span></span>  
 <span data-ttu-id="913bf-133">如果将具有 BAM 查看权限的 AD 用户从 AD 中删除，则 BAM 门户不会为任何用户正确加载（DBO 除外）。</span><span class="sxs-lookup"><span data-stu-id="913bf-133">If an AD user who has the BAM view permissions is removed from the AD, then the BAM portal does not load properly for any user (except DBO).</span></span>  
  
 <span data-ttu-id="913bf-134">要解决此问题，请将无效用户从相应的 bam_{viewname}view 安全角色中删除。 </span><span class="sxs-lookup"><span data-stu-id="913bf-134">To resolve this issue, remove the invalid user from the corresponding bam_{viewname}view security role.</span></span>  
  
## <a name="cannot-export-or-import-a-bam-definition-to-localhost"></a><span data-ttu-id="913bf-135">无法将 BAM 定义导出到 localhost 或从中导入</span><span class="sxs-lookup"><span data-stu-id="913bf-135">Cannot export or import a BAM definition to localhost</span></span>  
 <span data-ttu-id="913bf-136">将 BAM 定义导出为 XML 时，如果尝试导出到 localhost，将看到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="913bf-136">When you export a BAM definition as XML, you will see the following error message if you try to export to localhost:</span></span>  
  
 `The system cannot find the path specified.`  
  
 <span data-ttu-id="913bf-137">不支持将 BAM 定义导出到 localhost。</span><span class="sxs-lookup"><span data-stu-id="913bf-137">Exporting a BAM definition to localhost is not supported.</span></span> <span data-ttu-id="913bf-138">同样，不支持从 localhost 导入 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="913bf-138">Similarly, importing a BAM definition from localhost is not supported.</span></span>  
  
## <a name="alerts-do-not-work-after-upgrading-sql-server-editions"></a><span data-ttu-id="913bf-139">升级 SQL Server 版本后警报不再工作</span><span class="sxs-lookup"><span data-stu-id="913bf-139">Alerts do not work after upgrading SQL Server editions</span></span>  
 <span data-ttu-id="913bf-140">如果已从 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的一个版本升级到另一个版本（例如，从标准版到企业版），将不会重新启动 BAM 警报。</span><span class="sxs-lookup"><span data-stu-id="913bf-140">If you have upgraded from one edition of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] to another edition (for example, from Standard Edition to Enterprise Edition), BAM alerts will not restart.</span></span> <span data-ttu-id="913bf-141">若要解决此问题，请删除 BAM 警报并重新创建这些警报，或者升级 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 通知服务。</span><span class="sxs-lookup"><span data-stu-id="913bf-141">To fix this problem, either delete the BAM alerts and re-create them, or upgrade the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Notification Service.</span></span>  
  
#### <a name="to-upgrade-the-sql-server-notification-service"></a><span data-ttu-id="913bf-142">升级 SQL Server 通知服务</span><span class="sxs-lookup"><span data-stu-id="913bf-142">To upgrade the SQL Server Notification Service</span></span>  
  
1.  <span data-ttu-id="913bf-143">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2005**，然后单击**通知服务命令提示符**。</span><span class="sxs-lookup"><span data-stu-id="913bf-143">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2005**, and then click **Notification Service Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="913bf-144">在命令提示符下键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="913bf-144">Type the following command at the command prompt:</span></span>  
  
     `nscontrol.exe upgrade -name <instanceName>`  
  
## <a name="objectdisposedexception-exception"></a><span data-ttu-id="913bf-145">ObjectDisposedException Exception</span><span class="sxs-lookup"><span data-stu-id="913bf-145">ObjectDisposedException Exception</span></span>  
 <span data-ttu-id="913bf-146">如果你的应用程序使用 BAM WF 3.5 拦截器，你可能会收到以下错误消息： **System.ObjectDisposedException： 无法访问已释放的对象**。</span><span class="sxs-lookup"><span data-stu-id="913bf-146">If your application is using BAM WF 3.5 interceptor, you may receive the following error message: **System.ObjectDisposedException: Cannot access a disposed object**.</span></span> <span data-ttu-id="913bf-147">有关此错误消息的详细信息，请参阅[ObjectDisposedException 异常](http://go.microsoft.com/fwlink/?LinkID=195338)(http://go.microsoft.com/fwlink/?LinkID=195338)。</span><span class="sxs-lookup"><span data-stu-id="913bf-147">For more information about this error message, see [ObjectDisposedException Exception](http://go.microsoft.com/fwlink/?LinkID=195338) (http://go.microsoft.com/fwlink/?LinkID=195338).</span></span>   
<span data-ttu-id="913bf-148">若要解决此问题，安装修补程序在 960754 [http://go.microsoft.com/fwlink/?LinkID=195339](http://go.microsoft.com/fwlink/?LinkID=195339)。</span><span class="sxs-lookup"><span data-stu-id="913bf-148">To resolve this issue, install the hotfix 960754 available at [http://go.microsoft.com/fwlink/?LinkID=195339](http://go.microsoft.com/fwlink/?LinkID=195339).</span></span>  
  
## <a name="workbook-has-lost-its-vba-project-activex-controls-and-other-programmability-related-features"></a><span data-ttu-id="913bf-149">工作簿丢失了其 VBA 项目、ActiveX 控件及其他与可编程序相关的功能</span><span class="sxs-lookup"><span data-stu-id="913bf-149">Workbook has lost its VBA project, ActiveX controls and other programmability-related features</span></span>  
 <span data-ttu-id="913bf-150">当尝试在 Microsoft Excel 中使用 BAM.xla 时, 可能会收到以下错误：</span><span class="sxs-lookup"><span data-stu-id="913bf-150">When attempting to use BAM.xla in Microsoft Excel, you may get the following error:</span></span>  
  
 `This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.`  
  
 <span data-ttu-id="913bf-151">若要解决此问题，安装**应用程序的 Visual Basic**选项下**Office 共享功能**使用 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="913bf-151">To resolve this issue, install the **Visual Basic for Applications** option under **Office Shared Features** with Microsoft Office.</span></span>  
  
## <a name="pivot-table-fails-to-get-the-data"></a><span data-ttu-id="913bf-152">透视表无法获取数据</span><span class="sxs-lookup"><span data-stu-id="913bf-152">Pivot table fails to get the data</span></span>  
 <span data-ttu-id="913bf-153">你拥有对 BAM 数据库的访问权限和角色，也拥有对所部署的视图的权限。</span><span class="sxs-lookup"><span data-stu-id="913bf-153">You have permissions to access BAM databases, and also role and permissions on the views which are deployed.</span></span> <span data-ttu-id="913bf-154">“活动搜索”页正常工作，你可以查看数据。</span><span class="sxs-lookup"><span data-stu-id="913bf-154">The Activity Search page works as expected and you can see the data.</span></span> <span data-ttu-id="913bf-155">但是，在透视表中，会显示以下错误：</span><span class="sxs-lookup"><span data-stu-id="913bf-155">But, in the Pivot table, the following error is displayed:</span></span>  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* The following system error occurred:  No connection could be made because the target machine actively refused it.  
```  
  
 <span data-ttu-id="913bf-156">要解决此问题，请按照以下方式添加各个 DNS 设置：</span><span class="sxs-lookup"><span data-stu-id="913bf-156">To resolve this issue, add the respective DNS settings as follows:</span></span>  
  
1.  <span data-ttu-id="913bf-157">单击**启动**并转到**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="913bf-157">Click **Start** and go to **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="913bf-158">单击**网络和 Internet** ，然后单击**网络连接**。</span><span class="sxs-lookup"><span data-stu-id="913bf-158">Click **Network and Internet** and then click **Network Connections**.</span></span>  
  
3.  <span data-ttu-id="913bf-159">（如本地区域连接中） 的网络连接上右键单击并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="913bf-159">Right-click on the network connection (like Local Area Connection), and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="913bf-160">上**本地区域连接**页上，选择**Internet 协议版本 4 (TCP/IPv4)**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="913bf-160">On the **Local Area Connection** page, select **Internet Protocol Version 4 (TCP/IPv4)**, and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="913bf-161">单击 **“高级”**。</span><span class="sxs-lookup"><span data-stu-id="913bf-161">Click **Advanced**.</span></span> <span data-ttu-id="913bf-162">上**高级 TCP/IP 设置**页上，单击**DNS**选项卡。</span><span class="sxs-lookup"><span data-stu-id="913bf-162">On the **Advance TCP/IP Settings** page, click the **DNS** tab.</span></span>  
  
6.  <span data-ttu-id="913bf-163">选择**追加这些 DNS 后缀**，然后添加必需的 DNS 后缀。</span><span class="sxs-lookup"><span data-stu-id="913bf-163">Select **Append these DNS suffixes** and then add the required DNS suffixes.</span></span>  
  
7.  <span data-ttu-id="913bf-164">单击**确定**并关闭所有打开的窗口。</span><span class="sxs-lookup"><span data-stu-id="913bf-164">Click **OK** and close all the open windows.</span></span>  
  
## <a name="pivot-table-view-shows-all-values-as-0"></a><span data-ttu-id="913bf-165">透视表视图将所有值均显示为“0”</span><span class="sxs-lookup"><span data-stu-id="913bf-165">Pivot table view shows all values as “0”</span></span>  
 <span data-ttu-id="913bf-166">部署 BAM 门户后，“活动搜索”页将显示预期的结果。</span><span class="sxs-lookup"><span data-stu-id="913bf-166">When you deploy the BAM portal, the Activity Search page displays expected results.</span></span> <span data-ttu-id="913bf-167">但是，透视表视图将所有值均显示为“0”。</span><span class="sxs-lookup"><span data-stu-id="913bf-167">But, the Pivot table view displays all values as “0”.</span></span> <span data-ttu-id="913bf-168">将显示以下错误：</span><span class="sxs-lookup"><span data-stu-id="913bf-168">The following error is displayed:</span></span>  
  
```  
Failed to get data.  If available, errors returned from the provider are listed below.  
* Safety settings on this machine prohibit accessing a data source on another domain.  
```  
  
 <span data-ttu-id="913bf-169">要解决此问题，请按照以下方式将站点添加到区域：</span><span class="sxs-lookup"><span data-stu-id="913bf-169">To resolve this issue, add the site to the zone as follows:</span></span>  
  
1.  <span data-ttu-id="913bf-170">在 Internet Explorer 窗口中，单击**工具**，然后单击**Internet 选项**。</span><span class="sxs-lookup"><span data-stu-id="913bf-170">In the Internet Explorer window, click **Tools**, then click **Internet Options**.</span></span> <span data-ttu-id="913bf-171">单击**安全**选项卡上，然后选择**受信任的站点**区域。</span><span class="sxs-lookup"><span data-stu-id="913bf-171">Click the **Security** tab, and then select the **Trusted sites** zone.</span></span>  
  
2.  <span data-ttu-id="913bf-172">单击**自定义级别**设置区域的安全级别。</span><span class="sxs-lookup"><span data-stu-id="913bf-172">Click **Custom level** to set the security level for the zone.</span></span>  
  
3.  <span data-ttu-id="913bf-173">上**设置**页上，在**跨域访问数据源**选项，请单击**提示**。</span><span class="sxs-lookup"><span data-stu-id="913bf-173">On the **Settings** page, under the **Access data sources across domains** option, click **Prompt**.</span></span> <span data-ttu-id="913bf-174">系统会在组件要求此权限时提示你。</span><span class="sxs-lookup"><span data-stu-id="913bf-174">You will be prompted when a component requires this permission.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="913bf-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="913bf-175">See Also</span></span>  
 [<span data-ttu-id="913bf-176">使用业务活动监视</span><span class="sxs-lookup"><span data-stu-id="913bf-176">Using Business Activity Monitoring</span></span>](../core/using-business-activity-monitoring.md)
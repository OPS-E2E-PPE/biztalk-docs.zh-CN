---
title: "BAM 门户中的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e681e910-c664-479c-86f3-a6ae0ec97775
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0aa12d0f25a004f2e713f360e00c0f0c1192d304
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-in-the-bam-portal"></a><span data-ttu-id="643d9-102">BAM 门户中的已知的问题</span><span class="sxs-lookup"><span data-stu-id="643d9-102">Known Issues in the BAM Portal</span></span>
<span data-ttu-id="643d9-103">本主题中包含的信息可以帮助您确定和解决使用 BAM 门户过程中可能出现的问题。</span><span class="sxs-lookup"><span data-stu-id="643d9-103">This topic contains information to help you identify and resolve issues that can occur while you are using the BAM portal.</span></span>  
  
## <a name="errors-are-generated-when-the-bam-portal-and-internet-explorer-7-or-internet-explorer-8-are-on-the-same-computer-and-the-security-settings-are-set-to-low"></a><span data-ttu-id="643d9-104">BAM 门户和 Internet Explorer 7 或 Internet Explorer 8 位于同一台计算机和的安全设置设置为低时生成错误</span><span class="sxs-lookup"><span data-stu-id="643d9-104">Errors Are Generated When the BAM Portal and Internet Explorer 7 or Internet Explorer 8 Are on the Same Computer and the Security Settings Are Set to Low</span></span>  
 <span data-ttu-id="643d9-105">**问题**</span><span class="sxs-lookup"><span data-stu-id="643d9-105">**Problem**</span></span>  
  
 <span data-ttu-id="643d9-106">使用 Internet Explorer 7 或 Internet Explorer 7 或使用 Internet Explorer 8 时[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]， [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]可能会遇到的错误消息**中的服务器错误 / BAM 应用程序**到以下下情况：</span><span class="sxs-lookup"><span data-stu-id="643d9-106">When using Internet Explorer 7 or Internet Explorer 7 or Internet Explorer 8 with [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] you may encounter the error message **Server Error in '/BAM' Application** under the following circumstances:</span></span>  
  
-   <span data-ttu-id="643d9-107">单击指向不存在的活动实例的相关活动时。</span><span class="sxs-lookup"><span data-stu-id="643d9-107">While clicking a related activity that points to a non-existing activity instance.</span></span>  
  
-   <span data-ttu-id="643d9-108">在单击同时**保存警报**在以下方案中的按钮：</span><span class="sxs-lookup"><span data-stu-id="643d9-108">While clicking the **Save Alert** button in the following scenario:</span></span>  
  
    -   <span data-ttu-id="643d9-109">在创建查询**ActivitySearch**页，然后单击**设置警报**。</span><span class="sxs-lookup"><span data-stu-id="643d9-109">You create a query on the **ActivitySearch** page and then click **Set Alert**.</span></span>  
  
    -   <span data-ttu-id="643d9-110">你完成警报的字段，然后单击**保存警报**。</span><span class="sxs-lookup"><span data-stu-id="643d9-110">You complete the alert fields and then click **Save Alert**.</span></span>  
  
    -   <span data-ttu-id="643d9-111">单击“上一步”按钮。</span><span class="sxs-lookup"><span data-stu-id="643d9-111">You click the back button.</span></span>  
  
    -   <span data-ttu-id="643d9-112">你单击**保存警报**再次按钮。</span><span class="sxs-lookup"><span data-stu-id="643d9-112">You click the **Save Alert** button again.</span></span>  
  
 <span data-ttu-id="643d9-113">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="643d9-113">**Cause**</span></span>  
  
 <span data-ttu-id="643d9-114">当在将安全级别设置为低的情况下运行 [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]（或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]）和 Internet Explorer 7（或 Internet Explorer 8）时会产生错误，将以较低的权限执行 Web 请求。</span><span class="sxs-lookup"><span data-stu-id="643d9-114">When running [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] and Internet Explorer 7 or Internet Explorer 8 with the security level set to low, Web requests are executed with low privileges.</span></span> <span data-ttu-id="643d9-115">为了满足 Windows 的集成安全性，Internet Explorer 传递具有低权限的用户令牌。</span><span class="sxs-lookup"><span data-stu-id="643d9-115">To fulfill the Windows integrated security challenge, Internet Explorer passes a user token with low privileges.</span></span>  
  
 <span data-ttu-id="643d9-116">如果在安装 BAM 门户的计算机上使用 Internet Explorer，并在 Internet Explorer 中将安全级别设置为低，则门户将模拟具有低权限令牌的用户。</span><span class="sxs-lookup"><span data-stu-id="643d9-116">If you are using Internet Explorer on the same computer as the one on which the BAM portal is installed, and you set the security level in Internet Explorer to low, the portal impersonates the user with the low privileges token.</span></span> <span data-ttu-id="643d9-117">此令牌不具有向事件日志写入数据的权限。</span><span class="sxs-lookup"><span data-stu-id="643d9-117">This token does not have the permissions to write to the event log.</span></span> <span data-ttu-id="643d9-118">如果门户遇到错误，它将尝试将其记录到事件日志中并且此尝试将失败，因为用户令牌的权限被降低而不足以访问事件日志。</span><span class="sxs-lookup"><span data-stu-id="643d9-118">If the portal encounters an error, it attempts to log it to the event log and will fail since the reduced privileges of the user token are not sufficient to access the event log.</span></span>  
  
 <span data-ttu-id="643d9-119">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="643d9-119">**Resolution**</span></span>  
  
 <span data-ttu-id="643d9-120">如果需要从本地计算机上进行浏览，应将 http://localhost 添加到可信站点中。</span><span class="sxs-lookup"><span data-stu-id="643d9-120">If you need to browse from the local computer, you should add http://localhost to the list of trusted sites.</span></span>  
  
#### <a name="to-add-localhost-to-the-list-of-trusted-sites"></a><span data-ttu-id="643d9-121">将 localhost 添加到可信站点列表</span><span class="sxs-lookup"><span data-stu-id="643d9-121">To add localhost to the list of trusted sites</span></span>  
  
1.  <span data-ttu-id="643d9-122">在 Internet Explorer 中，单击**工具**，然后单击**Internet 选项**。</span><span class="sxs-lookup"><span data-stu-id="643d9-122">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="643d9-123">单击**安全**选项卡上，并依次**受信任的站点**中**选择要查看或更改安全设置的区域**窗口。</span><span class="sxs-lookup"><span data-stu-id="643d9-123">Click the **Security** tab, and then click **Trusted Sites** in the **Select a zone to view or change security settings** window.</span></span>  
  
3.  <span data-ttu-id="643d9-124">单击**站点**按钮。</span><span class="sxs-lookup"><span data-stu-id="643d9-124">Click the **Sites** button.</span></span>  
  
4.  <span data-ttu-id="643d9-125">在**向区域添加此网站**文本框中，键入**http://localhost**。</span><span class="sxs-lookup"><span data-stu-id="643d9-125">In the **Add this website to the zone** text box, type **http://localhost**.</span></span> <span data-ttu-id="643d9-126">如果**要求服务器验证 (https:) 此区域中的所有站点**复选框处于选中状态，请清除它，然后单击**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="643d9-126">If the **Require server verification (https:) for all sites in this zone** check box is selected, clear it and then click the **Add** button.</span></span> <span data-ttu-id="643d9-127">站点、 http://localhost, 将出现在**网站**列表。</span><span class="sxs-lookup"><span data-stu-id="643d9-127">The site, http://localhost, will appear in the **Websites** list.</span></span>  
  
5.  <span data-ttu-id="643d9-128">如有必要，还原**要求服务器验证 (https:) 此区域中的所有站点**到其原始状态的复选框。</span><span class="sxs-lookup"><span data-stu-id="643d9-128">If necessary, restore the **Require server verification (https:) for all sites in this zone** check box to its original state.</span></span>  
  
6.  <span data-ttu-id="643d9-129">单击**关闭**按钮，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="643d9-129">Click the **Close** button, and then click **OK**.</span></span>  
  
## <a name="bam-portal-aggregations-do-not-populate-existing-data-when-using-an-ip-address-as-a-url-in-internet-explorer-7"></a><span data-ttu-id="643d9-130">在 Internet Explorer 7 中将 IP 地址用作 URL 时，BAM 门户聚合不填充现有数据</span><span class="sxs-lookup"><span data-stu-id="643d9-130">Bam Portal Aggregations Do Not Populate Existing Data When Using an IP Address as a URL in Internet Explorer 7</span></span>  
 <span data-ttu-id="643d9-131">**问题**</span><span class="sxs-lookup"><span data-stu-id="643d9-131">**Problem**</span></span>  
  
 <span data-ttu-id="643d9-132">使用 IP 地址作为带 Internet Explorer 7 或 Internet Explorer 8 的 URL 时和[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]， [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]查看 BAM 门户，聚合显示以下消息:"没有详细信息。</span><span class="sxs-lookup"><span data-stu-id="643d9-132">When using an IP address as a URL with Internet Explorer 7 or Internet Explorer 8 and [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] to view the BAM portal, aggregations display the following message: "No detail.</span></span> <span data-ttu-id="643d9-133">The query could not be processed."</span><span class="sxs-lookup"><span data-stu-id="643d9-133">The query could not be processed."</span></span>  
  
 <span data-ttu-id="643d9-134">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="643d9-134">**Cause**</span></span>  
  
 <span data-ttu-id="643d9-135">在 Internet Explorer 7 或 Internet Explorer 8 中的默认安全设置阻止对站点使用 IPv4 和 IPv6 地址作为 Url 的访问。</span><span class="sxs-lookup"><span data-stu-id="643d9-135">The default security settings in Internet Explorer 7 or Internet Explorer 8 prevents access to sites using IPv4 and IPv6 addresses as URLs.</span></span>  
  
 <span data-ttu-id="643d9-136">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="643d9-136">**Resolution**</span></span>  
  
 <span data-ttu-id="643d9-137">将站点地址添加到受信任的站点列表中，即可跨域访问数据源。</span><span class="sxs-lookup"><span data-stu-id="643d9-137">Add the site address to the trusted sites list and enable access to data sources across domains.</span></span>  
  
#### <a name="to-add-the-ip-address-to-the-trusted-sites-list"></a><span data-ttu-id="643d9-138">将 IP 地址添加到受信任的站点列表中</span><span class="sxs-lookup"><span data-stu-id="643d9-138">To add the IP address to the trusted sites list</span></span>  
  
1.  <span data-ttu-id="643d9-139">在 Internet Explorer 中，单击**工具**，然后单击**Internet 选项**。</span><span class="sxs-lookup"><span data-stu-id="643d9-139">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="643d9-140">单击**安全**选项卡上，并依次**受信任的站点**安全区域。</span><span class="sxs-lookup"><span data-stu-id="643d9-140">Click the **Security** tab, and then click the **Trusted sites** security zone.</span></span>  
  
3.  <span data-ttu-id="643d9-141">单击**站点**按钮。</span><span class="sxs-lookup"><span data-stu-id="643d9-141">Click the **Sites** button.</span></span>  
  
4.  <span data-ttu-id="643d9-142">在**向区域添加此网站**，键入 BAM 门户的 IP 地址，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="643d9-142">In **Add this website to the zone**, type the IP address of the BAM portal, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="643d9-143">单击 **“关闭”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="643d9-143">Click **Close**, and then click **OK**.</span></span>  
  
#### <a name="to-enable-access-to-data-sources-across-domains"></a><span data-ttu-id="643d9-144">启用跨域数据源访问</span><span class="sxs-lookup"><span data-stu-id="643d9-144">To enable access to data sources across domains</span></span>  
  
1.  <span data-ttu-id="643d9-145">在 Internet Explorer 中，单击**工具**，然后单击**Internet 选项**。</span><span class="sxs-lookup"><span data-stu-id="643d9-145">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="643d9-146">单击**安全**选项卡上，并依次**受信任的站点**安全区域。</span><span class="sxs-lookup"><span data-stu-id="643d9-146">Click the **Security** tab, and then click the **Trusted Sites** security zone.</span></span>  
  
3.  <span data-ttu-id="643d9-147">单击**自定义级别**按钮为你向下滚动到**杂项**节点**设置**树。</span><span class="sxs-lookup"><span data-stu-id="643d9-147">Click the **Custom Level** button as you scroll down to the **Miscellaneous** node of the **Settings** tree.</span></span>  
  
4.  <span data-ttu-id="643d9-148">在**跨域访问数据源**节点，单击**启用单选**按钮，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="643d9-148">In the **Access data sources across domains** node, click the **Enable radio** button, and then click **OK**.</span></span>  
  
## <a name="bmexe-does-not-run-in-powershell"></a><span data-ttu-id="643d9-149">BM.exe 不在 PowerShell 中运行</span><span class="sxs-lookup"><span data-stu-id="643d9-149">BM.exe does not run in PowerShell</span></span>  
 <span data-ttu-id="643d9-150">**问题**</span><span class="sxs-lookup"><span data-stu-id="643d9-150">**Problem**</span></span>  
  
 <span data-ttu-id="643d9-151">在 PowerShell 中运行时，以下命名引发错误。</span><span class="sxs-lookup"><span data-stu-id="643d9-151">The following command throws an error when run in PowerShell.</span></span>  
  
```  
bm.exe get-config -FileName:config.xml  
```  
  
 <span data-ttu-id="643d9-152">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="643d9-152">**Cause**</span></span>  
  
 <span data-ttu-id="643d9-153">PowerShell 找不到的.exe 和配置文件的路径。</span><span class="sxs-lookup"><span data-stu-id="643d9-153">PowerShell could not locate the path of .exe and config files.</span></span>  
  
 <span data-ttu-id="643d9-154">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="643d9-154">**Resolution**</span></span>  
  
 <span data-ttu-id="643d9-155">在 PowerShell 中使用 bm.exe，如果指定.exe 和配置文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="643d9-155">If you use bm.exe in PowerShell, specify the full path of .exe and config files.</span></span> <span data-ttu-id="643d9-156">例如：`bm.exe get-config -FileName:config.xml`应指定为`“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`。</span><span class="sxs-lookup"><span data-stu-id="643d9-156">For example: `bm.exe get-config -FileName:config.xml` should be specified as `“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="643d9-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="643d9-157">See Also</span></span>  
 [<span data-ttu-id="643d9-158">规划 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="643d9-158">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)
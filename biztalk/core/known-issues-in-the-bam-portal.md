---
title: 使用 BAM 门户的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e681e910-c664-479c-86f3-a6ae0ec97775
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a6eb2c711b654f5541c2c8fb7c42540b9210eb8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380952"
---
# <a name="known-issues-in-the-bam-portal"></a><span data-ttu-id="bafda-102">BAM 门户中的已知的问题</span><span class="sxs-lookup"><span data-stu-id="bafda-102">Known Issues in the BAM Portal</span></span>
<span data-ttu-id="bafda-103">本主题包含有助于您确定和解决在使用 BAM 门户时可能出现的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="bafda-103">This topic contains information to help you identify and resolve issues that can occur while you are using the BAM portal.</span></span>  
  
## <a name="errors-occur-when-the-bam-portal-and-ie-are-on-the-same-computer-and-security-settings-are-low"></a><span data-ttu-id="bafda-104">BAM 门户和 IE 位于同一台计算机，和安全设置是低时出现错误</span><span class="sxs-lookup"><span data-stu-id="bafda-104">Errors occur when the BAM Portal and IE are on the same computer, and Security Settings are Low</span></span>  
 <span data-ttu-id="bafda-105">**问题**</span><span class="sxs-lookup"><span data-stu-id="bafda-105">**Problem**</span></span>  
  
 <span data-ttu-id="bafda-106">使用 Internet Explorer，可能会遇到的错误消息**中的服务器错误 / BAM 应用程序**在下列情况下：</span><span class="sxs-lookup"><span data-stu-id="bafda-106">When using Internet Explorer, you may encounter the error message **Server Error in '/BAM' Application** under the following circumstances:</span></span>  
  
- <span data-ttu-id="bafda-107">单击指向不存在的活动实例的相关的活动时。</span><span class="sxs-lookup"><span data-stu-id="bafda-107">While clicking a related activity that points to a non-existing activity instance.</span></span>  
  
- <span data-ttu-id="bafda-108">单击同时**保存警报**在以下方案中的按钮：</span><span class="sxs-lookup"><span data-stu-id="bafda-108">While clicking the **Save Alert** button in the following scenario:</span></span>  
  
  -   <span data-ttu-id="bafda-109">在创建查询**活动搜索**页，然后单击**设置警报**。</span><span class="sxs-lookup"><span data-stu-id="bafda-109">You create a query on the **ActivitySearch** page and then click **Set Alert**.</span></span>  
  
  -   <span data-ttu-id="bafda-110">填写各个警报字段然后依次**保存警报**。</span><span class="sxs-lookup"><span data-stu-id="bafda-110">You complete the alert fields and then click **Save Alert**.</span></span>  
  
  -   <span data-ttu-id="bafda-111">单击后退按钮。</span><span class="sxs-lookup"><span data-stu-id="bafda-111">You click the back button.</span></span>  
  
  -   <span data-ttu-id="bafda-112">单击**保存警报**按钮再次。</span><span class="sxs-lookup"><span data-stu-id="bafda-112">You click the **Save Alert** button again.</span></span>  
  
  <span data-ttu-id="bafda-113">**原因**</span><span class="sxs-lookup"><span data-stu-id="bafda-113">**Cause**</span></span>  
  
  <span data-ttu-id="bafda-114">如果使用的安全级别运行 Internet Explorer 设置为低，Web 请求执行具有较低的权限。</span><span class="sxs-lookup"><span data-stu-id="bafda-114">When running Internet Explorer with the security level set to low, Web requests are executed with low privileges.</span></span> <span data-ttu-id="bafda-115">为了满足 Windows 集成的安全性，Internet Explorer 传递具有较低的权限的用户令牌。</span><span class="sxs-lookup"><span data-stu-id="bafda-115">To fulfill the Windows integrated security challenge, Internet Explorer passes a user token with low privileges.</span></span>  
  
  <span data-ttu-id="bafda-116">如果与安装 BAM 门户的同一计算机上使用 Internet Explorer，您将安全级别设置在 Internet Explorer 中为低，则门户将模拟具有低权限令牌的用户。</span><span class="sxs-lookup"><span data-stu-id="bafda-116">If you are using Internet Explorer on the same computer as the one on which the BAM portal is installed, and you set the security level in Internet Explorer to low, the portal impersonates the user with the low privileges token.</span></span> <span data-ttu-id="bafda-117">此令牌没有写入事件日志的权限。</span><span class="sxs-lookup"><span data-stu-id="bafda-117">This token does not have the permissions to write to the event log.</span></span> <span data-ttu-id="bafda-118">如果在门户时遇到错误，它将尝试记录到事件日志并将失败，因为减少的权限的用户令牌没有足够权限来访问事件日志。</span><span class="sxs-lookup"><span data-stu-id="bafda-118">If the portal encounters an error, it attempts to log it to the event log and will fail since the reduced privileges of the user token are not sufficient to access the event log.</span></span>  
  
  <span data-ttu-id="bafda-119">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bafda-119">**Resolution**</span></span>  
  
  <span data-ttu-id="bafda-120">如果需要从本地计算机浏览，则应添加 http://localhost到受信任的站点的列表。</span><span class="sxs-lookup"><span data-stu-id="bafda-120">If you need to browse from the local computer, you should add http://localhost to the list of trusted sites.</span></span>  
  
#### <a name="add-localhost-to-the-list-of-trusted-sites"></a><span data-ttu-id="bafda-121">将 localhost 添加到受信任站点列表</span><span class="sxs-lookup"><span data-stu-id="bafda-121">Add localhost to the list of trusted sites</span></span>  
  
1.  <span data-ttu-id="bafda-122">在 Internet Explorer 中，单击**工具**，然后单击**Internet 选项**。</span><span class="sxs-lookup"><span data-stu-id="bafda-122">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="bafda-123">单击**安全**选项卡，然后依次**受信任的站点**中**选择要查看或更改安全设置的区域**窗口。</span><span class="sxs-lookup"><span data-stu-id="bafda-123">Click the **Security** tab, and then click **Trusted Sites** in the **Select a zone to view or change security settings** window.</span></span>  
  
3.  <span data-ttu-id="bafda-124">单击**站点**按钮。</span><span class="sxs-lookup"><span data-stu-id="bafda-124">Click the **Sites** button.</span></span>  
  
4.  <span data-ttu-id="bafda-125">在中**向区域添加此网站**文本框中，键入**http://localhost**。</span><span class="sxs-lookup"><span data-stu-id="bafda-125">In the **Add this website to the zone** text box, type **http://localhost**.</span></span> <span data-ttu-id="bafda-126">如果**要求服务器验证 (https:) 此区域中的所有站点**复选框处于选中状态，请清除它，然后单击**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="bafda-126">If the **Require server verification (https:) for all sites in this zone** check box is selected, clear it and then click the **Add** button.</span></span> <span data-ttu-id="bafda-127">在站点 http://localhost，将出现在**网站**列表。</span><span class="sxs-lookup"><span data-stu-id="bafda-127">The site, http://localhost, will appear in the **Websites** list.</span></span>  
  
5.  <span data-ttu-id="bafda-128">如有必要，还原**要求服务器验证 (https:) 此区域中的所有站点**到其原始状态的复选框。</span><span class="sxs-lookup"><span data-stu-id="bafda-128">If necessary, restore the **Require server verification (https:) for all sites in this zone** check box to its original state.</span></span>  
  
6.  <span data-ttu-id="bafda-129">单击**关闭**按钮，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="bafda-129">Click the **Close** button, and then click **OK**.</span></span>  
  
## <a name="bam-portal-aggregations-do-not-populate-existing-data-when-using-an-ip-address-as-a-url-in-internet-explorer"></a><span data-ttu-id="bafda-130">Bam 门户聚合不填充现有数据时使用 IP 地址作为 Internet Explorer 中的 URL</span><span class="sxs-lookup"><span data-stu-id="bafda-130">Bam Portal Aggregations Do Not Populate Existing Data When Using an IP Address as a URL in Internet Explorer</span></span>
 <span data-ttu-id="bafda-131">**问题**</span><span class="sxs-lookup"><span data-stu-id="bafda-131">**Problem**</span></span>  
  
 <span data-ttu-id="bafda-132">当使用 IP 地址作为 URL 来用于 Internet Explorer 查看 BAM 门户，聚合显示以下消息："没有详细信息。</span><span class="sxs-lookup"><span data-stu-id="bafda-132">When using an IP address as a URL with Internet Explorer to view the BAM portal, aggregations display the following message: "No detail.</span></span> <span data-ttu-id="bafda-133">查询无法处理。"</span><span class="sxs-lookup"><span data-stu-id="bafda-133">The query could not be processed."</span></span>  
  
 <span data-ttu-id="bafda-134">**原因**</span><span class="sxs-lookup"><span data-stu-id="bafda-134">**Cause**</span></span>  
  
 <span data-ttu-id="bafda-135">在 Internet Explorer 中的默认安全设置可能会导致使用 IPv4 和 IPv6 地址作为 Url 的站点无法访问。</span><span class="sxs-lookup"><span data-stu-id="bafda-135">The default security settings in Internet Explorer may prevent access to sites using IPv4 and IPv6 addresses as URLs.</span></span>  
  
 <span data-ttu-id="bafda-136">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bafda-136">**Resolution**</span></span>  
  
 <span data-ttu-id="bafda-137">将站点地址添加到受信任的站点列表并启用跨域访问数据源。</span><span class="sxs-lookup"><span data-stu-id="bafda-137">Add the site address to the trusted sites list and enable access to data sources across domains.</span></span>  
  
#### <a name="add-the-ip-address-to-the-trusted-sites-list"></a><span data-ttu-id="bafda-138">将 IP 地址添加到受信任的站点列表</span><span class="sxs-lookup"><span data-stu-id="bafda-138">Add the IP address to the trusted sites list</span></span>  
  
1.  <span data-ttu-id="bafda-139">在 Internet Explorer 中，单击**工具**，然后单击**Internet 选项**。</span><span class="sxs-lookup"><span data-stu-id="bafda-139">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="bafda-140">单击**安全**选项卡，然后依次**受信任的站点**安全区域。</span><span class="sxs-lookup"><span data-stu-id="bafda-140">Click the **Security** tab, and then click the **Trusted sites** security zone.</span></span>  
  
3.  <span data-ttu-id="bafda-141">单击**站点**按钮。</span><span class="sxs-lookup"><span data-stu-id="bafda-141">Click the **Sites** button.</span></span>  
  
4.  <span data-ttu-id="bafda-142">在中**向区域添加此网站**，键入 BAM 门户的 IP 地址，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="bafda-142">In **Add this website to the zone**, type the IP address of the BAM portal, and then click **Add**.</span></span>  
  
5.  <span data-ttu-id="bafda-143">单击 **“关闭”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="bafda-143">Click **Close**, and then click **OK**.</span></span>  
  
#### <a name="enable-access-to-data-sources-across-domains"></a><span data-ttu-id="bafda-144">启用跨域访问数据源</span><span class="sxs-lookup"><span data-stu-id="bafda-144">Enable access to data sources across domains</span></span>  
  
1.  <span data-ttu-id="bafda-145">在 Internet Explorer 中，单击**工具**，然后单击**Internet 选项**。</span><span class="sxs-lookup"><span data-stu-id="bafda-145">In Internet Explorer, click **Tools**, and then click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="bafda-146">单击**安全**选项卡，然后依次**受信任的站点**安全区域。</span><span class="sxs-lookup"><span data-stu-id="bafda-146">Click the **Security** tab, and then click the **Trusted Sites** security zone.</span></span>  
  
3.  <span data-ttu-id="bafda-147">单击**自定义级别**按钮，如您向下滚动到**杂项**节点的**设置**树。</span><span class="sxs-lookup"><span data-stu-id="bafda-147">Click the **Custom Level** button as you scroll down to the **Miscellaneous** node of the **Settings** tree.</span></span>  
  
4.  <span data-ttu-id="bafda-148">在中**跨域访问数据源**节点中，单击**启用单选**按钮，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="bafda-148">In the **Access data sources across domains** node, click the **Enable radio** button, and then click **OK**.</span></span>  
  
## <a name="bmexe-does-not-run-in-powershell"></a><span data-ttu-id="bafda-149">BM.exe 不在 PowerShell 中运行</span><span class="sxs-lookup"><span data-stu-id="bafda-149">BM.exe does not run in PowerShell</span></span>  
 <span data-ttu-id="bafda-150">**问题**</span><span class="sxs-lookup"><span data-stu-id="bafda-150">**Problem**</span></span>  
  
 <span data-ttu-id="bafda-151">以下命令将引发错误时在 PowerShell 中运行。</span><span class="sxs-lookup"><span data-stu-id="bafda-151">The following command throws an error when run in PowerShell.</span></span>  
  
```  
bm.exe get-config -FileName:config.xml  
```  
  
 <span data-ttu-id="bafda-152">**原因**</span><span class="sxs-lookup"><span data-stu-id="bafda-152">**Cause**</span></span>  
  
 <span data-ttu-id="bafda-153">PowerShell 找不到.exe 和配置文件的路径。</span><span class="sxs-lookup"><span data-stu-id="bafda-153">PowerShell could not locate the path of .exe and config files.</span></span>  
  
 <span data-ttu-id="bafda-154">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="bafda-154">**Resolution**</span></span>  
  
 <span data-ttu-id="bafda-155">在 PowerShell 中使用 bm.exe，如果指定.exe 和配置文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="bafda-155">If you use bm.exe in PowerShell, specify the full path of .exe and config files.</span></span> <span data-ttu-id="bafda-156">例如：`bm.exe get-config -FileName:config.xml`应指定为`“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`。</span><span class="sxs-lookup"><span data-stu-id="bafda-156">For example: `bm.exe get-config -FileName:config.xml` should be specified as `“%BizTalkPathTracking%”\bm.exe get-config -FileName:”%InstallDir%”\Tracking\config.xml`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bafda-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="bafda-157">See Also</span></span>  
 [<span data-ttu-id="bafda-158">规划 BAM 门户</span><span class="sxs-lookup"><span data-stu-id="bafda-158">Planning for the BAM Portal</span></span>](../core/planning-for-the-bam-portal.md)
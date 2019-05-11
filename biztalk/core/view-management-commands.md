---
title: 查看管理命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52f25ee3-9bb3-4682-a9ff-cac8c25f58c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbd91cf632b655fe3c2cb535f2ee4db3c889688d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243247"
---
# <a name="view-management-commands"></a><span data-ttu-id="5250e-102">视图管理命令</span><span class="sxs-lookup"><span data-stu-id="5250e-102">View Management Commands</span></span>
<span data-ttu-id="5250e-103">BAM 管理实用程序视图管理命令允许您可以使用已部署的视图。</span><span class="sxs-lookup"><span data-stu-id="5250e-103">The BAM Management utility view management commands allow you to work with deployed views.</span></span>  
  
-   <span data-ttu-id="5250e-104">获取视图：列出所有已部署的视图。</span><span class="sxs-lookup"><span data-stu-id="5250e-104">get-views: Lists all the deployed views.</span></span>  
  
-   <span data-ttu-id="5250e-105">删除视图：删除已部署的视图。</span><span class="sxs-lookup"><span data-stu-id="5250e-105">remove-view: Removes a deployed view.</span></span>  
  
-   <span data-ttu-id="5250e-106">get-rtawindow:获取视图的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5250e-106">get-rtawindow: Gets the duration on a view.</span></span>  
  
-   <span data-ttu-id="5250e-107">集 rtawindow:在视图上设置的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5250e-107">set-rtawindow: Sets the duration on a view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5250e-108">通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。</span><span class="sxs-lookup"><span data-stu-id="5250e-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="5250e-109">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="5250e-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="5250e-110">此开关可以与所有标准 BM 命令结合使用。</span><span class="sxs-lookup"><span data-stu-id="5250e-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5250e-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="5250e-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-views-command"></a><span data-ttu-id="5250e-112">get-views Command</span><span class="sxs-lookup"><span data-stu-id="5250e-112">get-views Command</span></span>  
 <span data-ttu-id="5250e-113">**Usage**</span><span class="sxs-lookup"><span data-stu-id="5250e-113">**Usage**</span></span>  
  
 <span data-ttu-id="5250e-114">**bm.exe get-views [ -Activity:\<activity name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="5250e-114">**bm.exe get-views [ -Activity:\<activity name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="5250e-115">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="5250e-115">**Parameters**</span></span>  
  
|<span data-ttu-id="5250e-116">参数</span><span class="sxs-lookup"><span data-stu-id="5250e-116">Parameter</span></span>|<span data-ttu-id="5250e-117">Description</span><span class="sxs-lookup"><span data-stu-id="5250e-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5250e-118">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="5250e-118">Activity:\<activity name\></span></span>|<span data-ttu-id="5250e-119">若要列出其视图的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-119">The name of the activity from which to list the views.</span></span>|  
|<span data-ttu-id="5250e-120">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="5250e-120">Server:\<server\></span></span>|<span data-ttu-id="5250e-121">可选：从中获取视图的列表的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-121">Optional: The name of the server from which to get the list of views.</span></span> <span data-ttu-id="5250e-122">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="5250e-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="5250e-123">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="5250e-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="5250e-124">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="5250e-124">Database:\<database\></span></span>|<span data-ttu-id="5250e-125">可选：从中获取视图的列表的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-125">Optional: The name of the database from which to get the list of views.</span></span> <span data-ttu-id="5250e-126">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="5250e-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="5250e-127">列出对其执行该命令的计算机上部署的视图。</span><span class="sxs-lookup"><span data-stu-id="5250e-127">Lists the views deployed on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="5250e-128">**示例**</span><span class="sxs-lookup"><span data-stu-id="5250e-128">**Examples**</span></span>  
  
```  
bm.exe get-views -Activity:PO1  
bm.exe get-views -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-view-command"></a><span data-ttu-id="5250e-129">remove-view 命令</span><span class="sxs-lookup"><span data-stu-id="5250e-129">remove-view Command</span></span>  
 <span data-ttu-id="5250e-130">**Usage**</span><span class="sxs-lookup"><span data-stu-id="5250e-130">**Usage**</span></span>  
  
 <span data-ttu-id="5250e-131">**bm.exe remove-view -Name:\<view name\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="5250e-131">**bm.exe remove-view -Name:\<view name\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="5250e-132">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="5250e-132">**Parameters**</span></span>  
  
|<span data-ttu-id="5250e-133">参数</span><span class="sxs-lookup"><span data-stu-id="5250e-133">Parameter</span></span>|<span data-ttu-id="5250e-134">Description</span><span class="sxs-lookup"><span data-stu-id="5250e-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5250e-135">名称：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="5250e-135">Name:\<view name\></span></span>|<span data-ttu-id="5250e-136">要删除的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-136">The name of the view to remove.</span></span>|  
|<span data-ttu-id="5250e-137">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="5250e-137">Server:\<server\></span></span>|<span data-ttu-id="5250e-138">可选：要从其中移除该视图的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-138">Optional: The name of the server from which to remove the view.</span></span> <span data-ttu-id="5250e-139">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="5250e-139">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="5250e-140">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="5250e-140">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="5250e-141">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="5250e-141">Database:\<database\></span></span>|<span data-ttu-id="5250e-142">可选：要从其中移除该视图的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-142">Optional: The name of the database from which to remove the view.</span></span> <span data-ttu-id="5250e-143">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="5250e-143">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="5250e-144">从 BAM 主导入数据库中删除指定的视图。</span><span class="sxs-lookup"><span data-stu-id="5250e-144">Removes the specified view from the BAM Primary Import database.</span></span> <span data-ttu-id="5250e-145">如果此视图具有相关警报，则会删除在同一时间。</span><span class="sxs-lookup"><span data-stu-id="5250e-145">If the view has dependent alerts, they are removed at the same time.</span></span>  
  
 <span data-ttu-id="5250e-146">**示例**</span><span class="sxs-lookup"><span data-stu-id="5250e-146">**Examples**</span></span>  
  
```  
bm.exe remove-view -Name:POView  
bm.exe remove-view -Name:MyView -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-rtawindow-command"></a><span data-ttu-id="5250e-147">get-rtawindow 命令</span><span class="sxs-lookup"><span data-stu-id="5250e-147">get-rtawindow Command</span></span>  
 <span data-ttu-id="5250e-148">**Usage**</span><span class="sxs-lookup"><span data-stu-id="5250e-148">**Usage**</span></span>  
  
 <span data-ttu-id="5250e-149">**bm.exe get-rtawindow -View:\<view name\> -Activity:\<activity name\> -Rta:\<RTA name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="5250e-149">**bm.exe get-rtawindow -View:\<view name\> -Activity:\<activity name\> -Rta:\<RTA name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="5250e-150">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="5250e-150">**Parameters**</span></span>  
  
|<span data-ttu-id="5250e-151">参数</span><span class="sxs-lookup"><span data-stu-id="5250e-151">Parameter</span></span>|<span data-ttu-id="5250e-152">Description</span><span class="sxs-lookup"><span data-stu-id="5250e-152">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5250e-153">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="5250e-153">View:\<view name\></span></span>|<span data-ttu-id="5250e-154">视图名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-154">The view name.</span></span>|  
|<span data-ttu-id="5250e-155">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="5250e-155">Activity:\<activity name\></span></span>|<span data-ttu-id="5250e-156">活动名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-156">The activity name.</span></span>|  
|<span data-ttu-id="5250e-157">Rta:\<RTA 名称\></span><span class="sxs-lookup"><span data-stu-id="5250e-157">Rta:\<RTA name\></span></span>|<span data-ttu-id="5250e-158">实时聚合的名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-158">The real-time aggregation name.</span></span>|  
|<span data-ttu-id="5250e-159">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="5250e-159">Server:\<server\></span></span>|<span data-ttu-id="5250e-160">可选：该活动所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-160">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="5250e-161">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="5250e-161">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="5250e-162">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="5250e-162">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="5250e-163">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="5250e-163">Database:\<database\></span></span>|<span data-ttu-id="5250e-164">可选：活动所处的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-164">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="5250e-165">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="5250e-165">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="5250e-166">显示指定实时聚合的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5250e-166">Displays the duration of the specified real-time aggregation.</span></span> <span data-ttu-id="5250e-167">该命令返回持续时间和持续时间单位所依据的单位的长度。</span><span class="sxs-lookup"><span data-stu-id="5250e-167">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
 <span data-ttu-id="5250e-168">**示例**</span><span class="sxs-lookup"><span data-stu-id="5250e-168">**Examples**</span></span>  
  
```  
bm.exe get-rtawindow -View:ManagerView -Activity:PO -Rta:Rta1  
bm.exe get-rtawindow -View:V1 -Activity:A2 -Rta:R3 -Server:S1 -Database:BamPI  
```  
  
## <a name="set-rtawindow-command"></a><span data-ttu-id="5250e-169">set-rtawindow 命令</span><span class="sxs-lookup"><span data-stu-id="5250e-169">set-rtawindow Command</span></span>  
 <span data-ttu-id="5250e-170">**Usage**</span><span class="sxs-lookup"><span data-stu-id="5250e-170">**Usage**</span></span>  
  
 <span data-ttu-id="5250e-171">**bm.exe 集 rtawindow 的视图：\<视图名称\>-活动：\<活动名称\>-名称：\<RTA 名称\>-TimeLength:\<整数\>-时间单位： Day&#124;小时&#124;分钟 [-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="5250e-171">**bm.exe set-rtawindow -View:\<view name\> -Activity:\<activity name\> -Name:\<RTA name\> -TimeLength:\<integer number\>-TimeUnit:Day&#124;Hour&#124;Minute[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="5250e-172">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="5250e-172">**Parameters**</span></span>  
  
|<span data-ttu-id="5250e-173">参数</span><span class="sxs-lookup"><span data-stu-id="5250e-173">Parameter</span></span>|<span data-ttu-id="5250e-174">Description</span><span class="sxs-lookup"><span data-stu-id="5250e-174">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5250e-175">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="5250e-175">View:\<view name\></span></span>|<span data-ttu-id="5250e-176">视图名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-176">The view name.</span></span>|  
|<span data-ttu-id="5250e-177">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="5250e-177">Activity:\<activity name\></span></span>|<span data-ttu-id="5250e-178">活动名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-178">The activity name.</span></span>|  
|<span data-ttu-id="5250e-179">名称：\<RTA 名称\></span><span class="sxs-lookup"><span data-stu-id="5250e-179">Name:\<RTA name\></span></span>|<span data-ttu-id="5250e-180">实时聚合的名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-180">The real-time aggregation name.</span></span>|  
|<span data-ttu-id="5250e-181">TimeLength:\<整数\></span><span class="sxs-lookup"><span data-stu-id="5250e-181">TimeLength:\<integer number\></span></span>|<span data-ttu-id="5250e-182">实时聚合的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5250e-182">The duration for the real-time aggregation.</span></span>|  
|<span data-ttu-id="5250e-183">TimeUnit:Month&#124;Day&#124;Hour&#124;Minute</span><span class="sxs-lookup"><span data-stu-id="5250e-183">TimeUnit:Month&#124;Day&#124;Hour&#124;Minute</span></span>|<span data-ttu-id="5250e-184">窗口持续时间度量单位。</span><span class="sxs-lookup"><span data-stu-id="5250e-184">The unit measure for the window duration.</span></span>|  
|<span data-ttu-id="5250e-185">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="5250e-185">Server:\<server\></span></span>|<span data-ttu-id="5250e-186">可选：该活动所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-186">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="5250e-187">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="5250e-187">The server must be in the same domain as the machine from which you are running bm.exe.</span></span> <span data-ttu-id="5250e-188">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="5250e-188">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="5250e-189">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="5250e-189">Database:\<database\></span></span>|<span data-ttu-id="5250e-190">可选：活动所处的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="5250e-190">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="5250e-191">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="5250e-191">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="5250e-192">设置指定实时聚合的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5250e-192">Sets the duration for the specified real-time aggregation.</span></span>  
  
 <span data-ttu-id="5250e-193">**示例**</span><span class="sxs-lookup"><span data-stu-id="5250e-193">**Examples**</span></span>  
  
```  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:5 -TimeUnit:Minute  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:1 -TimeUnit:Hour  
```  
  
## <a name="see-also"></a><span data-ttu-id="5250e-194">请参阅</span><span class="sxs-lookup"><span data-stu-id="5250e-194">See Also</span></span>  
 [<span data-ttu-id="5250e-195">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="5250e-195">BAM Management Utility</span></span>](../core/bam-management-utility.md)
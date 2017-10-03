---
title: "查看管理命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52f25ee3-9bb3-4682-a9ff-cac8c25f58c3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b0a641c6d461d02f8db3e0fb0112321e0657e44
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="view-management-commands"></a><span data-ttu-id="4185a-102">视图管理命令</span><span class="sxs-lookup"><span data-stu-id="4185a-102">View Management Commands</span></span>
<span data-ttu-id="4185a-103">您可借助 BAM 管理实用程序的视图管理命令来处理已部署的视图。</span><span class="sxs-lookup"><span data-stu-id="4185a-103">The BAM Management utility view management commands allow you to work with deployed views.</span></span>  
  
-   <span data-ttu-id="4185a-104">get 视图： 列出所有已部署的视图。</span><span class="sxs-lookup"><span data-stu-id="4185a-104">get-views: Lists all the deployed views.</span></span>  
  
-   <span data-ttu-id="4185a-105">删除视图： 删除已部署的视图。</span><span class="sxs-lookup"><span data-stu-id="4185a-105">remove-view: Removes a deployed view.</span></span>  
  
-   <span data-ttu-id="4185a-106">get rtawindow： 对视图中获取的持续时间。</span><span class="sxs-lookup"><span data-stu-id="4185a-106">get-rtawindow: Gets the duration on a view.</span></span>  
  
-   <span data-ttu-id="4185a-107">集 rtawindow： 在视图上设置的持续时间。</span><span class="sxs-lookup"><span data-stu-id="4185a-107">set-rtawindow: Sets the duration on a view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4185a-108">你可以通过包括启用任何 BM 实用工具命令的跟踪**-跟踪： 在 &#124; 关闭**参数交换机。</span><span class="sxs-lookup"><span data-stu-id="4185a-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="4185a-109">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="4185a-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="4185a-110">该开关可与所有标准 BM 命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="4185a-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4185a-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="4185a-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-views-command"></a><span data-ttu-id="4185a-112">get-views 命令</span><span class="sxs-lookup"><span data-stu-id="4185a-112">get-views Command</span></span>  
 <span data-ttu-id="4185a-113">**用法**</span><span class="sxs-lookup"><span data-stu-id="4185a-113">**Usage**</span></span>  
  
 <span data-ttu-id="4185a-114">**bm.exe get 视图 [-活动：\<活动名称 >] [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="4185a-114">**bm.exe get-views [ -Activity:\<activity name> ][ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="4185a-115">**参数**</span><span class="sxs-lookup"><span data-stu-id="4185a-115">**Parameters**</span></span>  
  
|<span data-ttu-id="4185a-116">参数</span><span class="sxs-lookup"><span data-stu-id="4185a-116">Parameter</span></span>|<span data-ttu-id="4185a-117">Description</span><span class="sxs-lookup"><span data-stu-id="4185a-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4185a-118">活动：\<活动名称 ></span><span class="sxs-lookup"><span data-stu-id="4185a-118">Activity:\<activity name></span></span>|<span data-ttu-id="4185a-119">列出其视图的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-119">The name of the activity from which to list the views.</span></span>|  
|<span data-ttu-id="4185a-120">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="4185a-120">Server:\<server></span></span>|<span data-ttu-id="4185a-121">可选： 用于获取视图的列表的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-121">Optional: The name of the server from which to get the list of views.</span></span> <span data-ttu-id="4185a-122">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="4185a-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="4185a-123">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="4185a-124">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="4185a-124">Database:\<database></span></span>|<span data-ttu-id="4185a-125">可选： 若要获取的视图列表的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-125">Optional: The name of the database from which to get the list of views.</span></span> <span data-ttu-id="4185a-126">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="4185a-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="4185a-127">列出在执行此命令的计算机上部署的视图。</span><span class="sxs-lookup"><span data-stu-id="4185a-127">Lists the views deployed on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="4185a-128">**示例**</span><span class="sxs-lookup"><span data-stu-id="4185a-128">**Examples**</span></span>  
  
```  
bm.exe get-views -Activity:PO1  
bm.exe get-views -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-view-command"></a><span data-ttu-id="4185a-129">remove-view 命令</span><span class="sxs-lookup"><span data-stu-id="4185a-129">remove-view Command</span></span>  
 <span data-ttu-id="4185a-130">**用法**</span><span class="sxs-lookup"><span data-stu-id="4185a-130">**Usage**</span></span>  
  
 <span data-ttu-id="4185a-131">**bm.exe 删除视图的名称：\<视图名称 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="4185a-131">**bm.exe remove-view -Name:\<view name> [ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="4185a-132">**参数**</span><span class="sxs-lookup"><span data-stu-id="4185a-132">**Parameters**</span></span>  
  
|<span data-ttu-id="4185a-133">参数</span><span class="sxs-lookup"><span data-stu-id="4185a-133">Parameter</span></span>|<span data-ttu-id="4185a-134">Description</span><span class="sxs-lookup"><span data-stu-id="4185a-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4185a-135">名称：\<视图名称 ></span><span class="sxs-lookup"><span data-stu-id="4185a-135">Name:\<view name></span></span>|<span data-ttu-id="4185a-136">要删除的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-136">The name of the view to remove.</span></span>|  
|<span data-ttu-id="4185a-137">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="4185a-137">Server:\<server></span></span>|<span data-ttu-id="4185a-138">可选： 要从中删除视图服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-138">Optional: The name of the server from which to remove the view.</span></span> <span data-ttu-id="4185a-139">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="4185a-139">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="4185a-140">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-140">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="4185a-141">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="4185a-141">Database:\<database></span></span>|<span data-ttu-id="4185a-142">可选： 要从中删除该视图的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-142">Optional: The name of the database from which to remove the view.</span></span> <span data-ttu-id="4185a-143">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="4185a-143">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="4185a-144">从 BAM 主导入数据库中删除所指定的视图。</span><span class="sxs-lookup"><span data-stu-id="4185a-144">Removes the specified view from the BAM Primary Import database.</span></span> <span data-ttu-id="4185a-145">如果该视图具有相关警报，则这些警报也将被一同删除。</span><span class="sxs-lookup"><span data-stu-id="4185a-145">If the view has dependent alerts, they are removed at the same time.</span></span>  
  
 <span data-ttu-id="4185a-146">**示例**</span><span class="sxs-lookup"><span data-stu-id="4185a-146">**Examples**</span></span>  
  
```  
bm.exe remove-view -Name:POView  
bm.exe remove-view -Name:MyView -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-rtawindow-command"></a><span data-ttu-id="4185a-147">get-rtawindow 命令</span><span class="sxs-lookup"><span data-stu-id="4185a-147">get-rtawindow Command</span></span>  
 <span data-ttu-id="4185a-148">**用法**</span><span class="sxs-lookup"><span data-stu-id="4185a-148">**Usage**</span></span>  
  
 <span data-ttu-id="4185a-149">**bm.exe get rtawindow 的视图：\<视图名称 >-活动：\<活动名称 >-Rta:\<RTA 名称 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="4185a-149">**bm.exe get-rtawindow -View:\<view name> -Activity:\<activity name> -Rta:\<RTA name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="4185a-150">**参数**</span><span class="sxs-lookup"><span data-stu-id="4185a-150">**Parameters**</span></span>  
  
|<span data-ttu-id="4185a-151">参数</span><span class="sxs-lookup"><span data-stu-id="4185a-151">Parameter</span></span>|<span data-ttu-id="4185a-152">Description</span><span class="sxs-lookup"><span data-stu-id="4185a-152">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4185a-153">视图：\<视图名称 ></span><span class="sxs-lookup"><span data-stu-id="4185a-153">View:\<view name></span></span>|<span data-ttu-id="4185a-154">视图名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-154">The view name.</span></span>|  
|<span data-ttu-id="4185a-155">活动：\<活动名称 ></span><span class="sxs-lookup"><span data-stu-id="4185a-155">Activity:\<activity name></span></span>|<span data-ttu-id="4185a-156">活动名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-156">The activity name.</span></span>|  
|<span data-ttu-id="4185a-157">Rta:\<RTA 名称 ></span><span class="sxs-lookup"><span data-stu-id="4185a-157">Rta:\<RTA name></span></span>|<span data-ttu-id="4185a-158">实时聚合的名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-158">The real-time aggregation name.</span></span>|  
|<span data-ttu-id="4185a-159">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="4185a-159">Server:\<server></span></span>|<span data-ttu-id="4185a-160">可选： 活动所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-160">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="4185a-161">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="4185a-161">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="4185a-162">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-162">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="4185a-163">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="4185a-163">Database:\<database></span></span>|<span data-ttu-id="4185a-164">可选： 在其上活动所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-164">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="4185a-165">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="4185a-165">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="4185a-166">显示指定实时聚合的持续时间。</span><span class="sxs-lookup"><span data-stu-id="4185a-166">Displays the duration of the specified real-time aggregation.</span></span> <span data-ttu-id="4185a-167">该命令返回持续时间的长度和度量单位。</span><span class="sxs-lookup"><span data-stu-id="4185a-167">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
 <span data-ttu-id="4185a-168">**示例**</span><span class="sxs-lookup"><span data-stu-id="4185a-168">**Examples**</span></span>  
  
```  
bm.exe get-rtawindow -View:ManagerView -Activity:PO -Rta:Rta1  
bm.exe get-rtawindow -View:V1 -Activity:A2 -Rta:R3 -Server:S1 -Database:BamPI  
```  
  
## <a name="set-rtawindow-command"></a><span data-ttu-id="4185a-169">set-rtawindow 命令</span><span class="sxs-lookup"><span data-stu-id="4185a-169">set-rtawindow Command</span></span>  
 <span data-ttu-id="4185a-170">**用法**</span><span class="sxs-lookup"><span data-stu-id="4185a-170">**Usage**</span></span>  
  
 <span data-ttu-id="4185a-171">**bm.exe 集 rtawindow 的视图：\<视图名称 >-活动：\<活动名称 >-名称：\<RTA 名称 >-TimeLength:\<整数 >-TimeUnit:Day &#124;小时 &#124;分钟 [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="4185a-171">**bm.exe set-rtawindow -View:\<view name> -Activity:\<activity name> -Name:\<RTA name> -TimeLength:\<integer number>-TimeUnit:Day&#124;Hour&#124;Minute[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="4185a-172">**参数**</span><span class="sxs-lookup"><span data-stu-id="4185a-172">**Parameters**</span></span>  
  
|<span data-ttu-id="4185a-173">参数</span><span class="sxs-lookup"><span data-stu-id="4185a-173">Parameter</span></span>|<span data-ttu-id="4185a-174">Description</span><span class="sxs-lookup"><span data-stu-id="4185a-174">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4185a-175">视图：\<视图名称 ></span><span class="sxs-lookup"><span data-stu-id="4185a-175">View:\<view name></span></span>|<span data-ttu-id="4185a-176">视图名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-176">The view name.</span></span>|  
|<span data-ttu-id="4185a-177">活动：\<活动名称 ></span><span class="sxs-lookup"><span data-stu-id="4185a-177">Activity:\<activity name></span></span>|<span data-ttu-id="4185a-178">活动名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-178">The activity name.</span></span>|  
|<span data-ttu-id="4185a-179">名称：\<RTA 名称 ></span><span class="sxs-lookup"><span data-stu-id="4185a-179">Name:\<RTA name></span></span>|<span data-ttu-id="4185a-180">实时聚合的名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-180">The real-time aggregation name.</span></span>|  
|<span data-ttu-id="4185a-181">TimeLength:\<整数 ></span><span class="sxs-lookup"><span data-stu-id="4185a-181">TimeLength:\<integer number></span></span>|<span data-ttu-id="4185a-182">实时聚合的持续时间。</span><span class="sxs-lookup"><span data-stu-id="4185a-182">The duration for the real-time aggregation.</span></span>|  
|<span data-ttu-id="4185a-183">TimeUnit:Month &#124; 天 &#124;小时 &#124;分钟</span><span class="sxs-lookup"><span data-stu-id="4185a-183">TimeUnit:Month&#124;Day&#124;Hour&#124;Minute</span></span>|<span data-ttu-id="4185a-184">时段的度量单位。</span><span class="sxs-lookup"><span data-stu-id="4185a-184">The unit measure for the window duration.</span></span>|  
|<span data-ttu-id="4185a-185">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="4185a-185">Server:\<server></span></span>|<span data-ttu-id="4185a-186">可选： 活动所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-186">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="4185a-187">服务器必须与从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="4185a-187">The server must be in the same domain as the machine from which you are running bm.exe.</span></span> <span data-ttu-id="4185a-188">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-188">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="4185a-189">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="4185a-189">Database:\<database></span></span>|<span data-ttu-id="4185a-190">可选： 在其上活动所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="4185a-190">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="4185a-191">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="4185a-191">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="4185a-192">设置指定实时聚合的持续时间。</span><span class="sxs-lookup"><span data-stu-id="4185a-192">Sets the duration for the specified real-time aggregation.</span></span>  
  
 <span data-ttu-id="4185a-193">**示例**</span><span class="sxs-lookup"><span data-stu-id="4185a-193">**Examples**</span></span>  
  
```  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:5 -TimeUnit:Minute  
bm.exe set-rtawindow -View:V -Activity:A -Name:R -TimeLength:1 -TimeUnit:Hour  
```  
  
## <a name="see-also"></a><span data-ttu-id="4185a-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4185a-194">See Also</span></span>  
 [<span data-ttu-id="4185a-195">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="4185a-195">BAM Management Utility</span></span>](../core/bam-management-utility.md)
---
title: 活动管理命令 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 34db54f3-4116-49de-880b-c9891a38d2e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18caccaf5207b5a63d0272c5d9e0277270c3e04c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967915"
---
# <a name="activity-management-commands"></a><span data-ttu-id="5e259-102">活动管理命令</span><span class="sxs-lookup"><span data-stu-id="5e259-102">Activity Management Commands</span></span>
<span data-ttu-id="5e259-103">你可借助 BAM 管理实用程序的活动管理命令来处理已部署的活动。</span><span class="sxs-lookup"><span data-stu-id="5e259-103">The BAM Management utility activity management commands allow you to work with deployed activities.</span></span>  
  
-   <span data-ttu-id="5e259-104">获取活动： 获取已部署的活动的列表。</span><span class="sxs-lookup"><span data-stu-id="5e259-104">get-activities: Gets a list of deployed activities.</span></span>  
  
-   <span data-ttu-id="5e259-105">删除活动： 中移除该活动。</span><span class="sxs-lookup"><span data-stu-id="5e259-105">remove-activity: Removes an activity.</span></span>  
  
-   <span data-ttu-id="5e259-106">get activitywindow： 获取活动的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5e259-106">get-activitywindow: Gets the duration for an activity.</span></span>  
  
-   <span data-ttu-id="5e259-107">集 activitywindow： 设置为活动的活动持续时间。</span><span class="sxs-lookup"><span data-stu-id="5e259-107">set-activitywindow: Sets the activity duration for an activity.</span></span>  
  
-   <span data-ttu-id="5e259-108">获取索引： 获取索引的列表。</span><span class="sxs-lookup"><span data-stu-id="5e259-108">get-index: Gets the list of indexes.</span></span>  
  
-   <span data-ttu-id="5e259-109">创建索引： 创建新的索引。</span><span class="sxs-lookup"><span data-stu-id="5e259-109">create-index: Creates a new index.</span></span>  
  
-   <span data-ttu-id="5e259-110">删除索引： 删除索引。</span><span class="sxs-lookup"><span data-stu-id="5e259-110">delete-index: Deletes an index.</span></span>  
  
-   <span data-ttu-id="5e259-111">get 存档： 获取已存档的活动的行为。</span><span class="sxs-lookup"><span data-stu-id="5e259-111">get-archive: Gets the behavior of archived activity.</span></span>  
  
-   <span data-ttu-id="5e259-112">集存档： 设置已存档的活动的行为。</span><span class="sxs-lookup"><span data-stu-id="5e259-112">set-archive: Sets the behavior of archived activity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e259-113">您可以通过包括启用 BAM 实用程序的任何命令上跟踪 **-跟踪： 在 &#124; 关闭**参数交换机。</span><span class="sxs-lookup"><span data-stu-id="5e259-113">You can enable tracing on any BAM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="5e259-114">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="5e259-114">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="5e259-115">该开关可与所有标准 BAM 命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="5e259-115">The switch can be used in conjunction with any normal BAM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e259-116">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="5e259-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-activities-command"></a><span data-ttu-id="5e259-117">get-activities 命令</span><span class="sxs-lookup"><span data-stu-id="5e259-117">get-activities Command</span></span>  
 <span data-ttu-id="5e259-118">**用法**</span><span class="sxs-lookup"><span data-stu-id="5e259-118">**Usage**</span></span>  
  
 <span data-ttu-id="5e259-119">**bm.exe get 活动 [的视图：\<视图名称\>] [-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="5e259-119">**bm.exe get-activities [ -View:\<view name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="5e259-120">**参数**</span><span class="sxs-lookup"><span data-stu-id="5e259-120">**Parameters**</span></span>  
  
|<span data-ttu-id="5e259-121">参数</span><span class="sxs-lookup"><span data-stu-id="5e259-121">Parameter</span></span>|<span data-ttu-id="5e259-122">Description</span><span class="sxs-lookup"><span data-stu-id="5e259-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e259-123">名称：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="5e259-123">Name:\<activity name\></span></span>|<span data-ttu-id="5e259-124">要删除的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-124">The name of the activity to remove.</span></span>|  
|<span data-ttu-id="5e259-125">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="5e259-125">Server:\<server\></span></span>|<span data-ttu-id="5e259-126">可选： 从其获取活动列表的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-126">Optional: The name of the server from which to get the list of activities.</span></span> <span data-ttu-id="5e259-127">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="5e259-127">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="5e259-128">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-128">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="5e259-129">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="5e259-129">Database:\<database\></span></span>|<span data-ttu-id="5e259-130">可选： 若要获取的活动列表的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-130">Optional: The name of the database from which to get the list of activities.</span></span> <span data-ttu-id="5e259-131">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="5e259-131">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="5e259-132">列出在执行此命令的计算机上部署的活动。</span><span class="sxs-lookup"><span data-stu-id="5e259-132">Lists the activities deployed on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="5e259-133">**示例**</span><span class="sxs-lookup"><span data-stu-id="5e259-133">**Examples**</span></span>  
  
```  
bm.exe get-activities -View:SalesManagerView  
bm.exe get-activities -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-activity-command"></a><span data-ttu-id="5e259-134">remove-activity 命令</span><span class="sxs-lookup"><span data-stu-id="5e259-134">remove-activity Command</span></span>  
 <span data-ttu-id="5e259-135">**用法**</span><span class="sxs-lookup"><span data-stu-id="5e259-135">**Usage**</span></span>  
  
 <span data-ttu-id="5e259-136">**bm.exe 删除活动的名称：\<活动名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="5e259-136">**bm.exe remove-activity -Name:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="5e259-137">**参数**</span><span class="sxs-lookup"><span data-stu-id="5e259-137">**Parameters**</span></span>  
  
|<span data-ttu-id="5e259-138">参数</span><span class="sxs-lookup"><span data-stu-id="5e259-138">Parameter</span></span>|<span data-ttu-id="5e259-139">Description</span><span class="sxs-lookup"><span data-stu-id="5e259-139">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e259-140">名称：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="5e259-140">Name:\<activity name\></span></span>|<span data-ttu-id="5e259-141">要删除的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-141">The name of the activity to remove.</span></span>|  
|<span data-ttu-id="5e259-142">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="5e259-142">Server:\<server\></span></span>|<span data-ttu-id="5e259-143">可选： 要从中移除活动服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-143">Optional: The name of the server from which to remove the activity.</span></span> <span data-ttu-id="5e259-144">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="5e259-144">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="5e259-145">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-145">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="5e259-146">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="5e259-146">Database:\<database\></span></span>|<span data-ttu-id="5e259-147">可选： 要从中移除活动数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-147">Optional: The name of the database from which to remove the activity.</span></span> <span data-ttu-id="5e259-148">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="5e259-148">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="5e259-149">从 BAM 主导入数据库中删除指定的活动。</span><span class="sxs-lookup"><span data-stu-id="5e259-149">Removes the specified activity from the BAM Primary Import database.</span></span> <span data-ttu-id="5e259-150">如果该活动具有相关视图，则此命令将失败并报告错误。</span><span class="sxs-lookup"><span data-stu-id="5e259-150">If the activity has dependent views, the command will fail and report an error.</span></span> <span data-ttu-id="5e259-151">使用 remove-view 命令删除所有相关视图后，即可再次执行 remove-activity 命令。</span><span class="sxs-lookup"><span data-stu-id="5e259-151">Use the remove-view command to remove all the dependent views and execute the remove-activity command again.</span></span>  
  
 <span data-ttu-id="5e259-152">**示例**</span><span class="sxs-lookup"><span data-stu-id="5e259-152">**Examples**</span></span>  
  
```  
bm.exe remove-activity -Name:PurchaseOrder  
bm.exe remove-activity -Name:PO -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-activitywindow-command"></a><span data-ttu-id="5e259-153">get-activitywindow 命令</span><span class="sxs-lookup"><span data-stu-id="5e259-153">get-activitywindow Command</span></span>  
 <span data-ttu-id="5e259-154">**用法**</span><span class="sxs-lookup"><span data-stu-id="5e259-154">**Usage**</span></span>  
  
 <span data-ttu-id="5e259-155">**bm.exe get activitywindow 的活动：\<活动名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="5e259-155">**bm.exe get-activitywindow -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="5e259-156">**参数**</span><span class="sxs-lookup"><span data-stu-id="5e259-156">**Parameters**</span></span>  
  
|<span data-ttu-id="5e259-157">参数</span><span class="sxs-lookup"><span data-stu-id="5e259-157">Parameter</span></span>|<span data-ttu-id="5e259-158">Description</span><span class="sxs-lookup"><span data-stu-id="5e259-158">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e259-159">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="5e259-159">Activity:\<activity name\></span></span>|<span data-ttu-id="5e259-160">.Activity 的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-160">The name of the .activity.</span></span>|  
|<span data-ttu-id="5e259-161">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="5e259-161">Server:\<server\></span></span>|<span data-ttu-id="5e259-162">可选： 活动所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-162">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="5e259-163">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="5e259-163">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="5e259-164">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-164">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="5e259-165">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="5e259-165">Database:\<database\></span></span>|<span data-ttu-id="5e259-166">可选： 在其上活动所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-166">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="5e259-167">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="5e259-167">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="5e259-168">显示指定活动的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5e259-168">Displays the duration for the specified activity.</span></span> <span data-ttu-id="5e259-169">该命令返回持续时间的长度和度量单位。</span><span class="sxs-lookup"><span data-stu-id="5e259-169">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
 <span data-ttu-id="5e259-170">**示例**</span><span class="sxs-lookup"><span data-stu-id="5e259-170">**Examples**</span></span>  
  
```  
bm.exe get-activitywindow -Activity:PurchaseOrder  
bm.exe get-activitywindow -Activity:PO -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="set-activitywindow-command"></a><span data-ttu-id="5e259-171">set-activitywindow 命令</span><span class="sxs-lookup"><span data-stu-id="5e259-171">set-activitywindow Command</span></span>  
 <span data-ttu-id="5e259-172">**用法**</span><span class="sxs-lookup"><span data-stu-id="5e259-172">**Usage**</span></span>  
  
 <span data-ttu-id="5e259-173">**bm.exe 集 activitywindow 的活动：\<活动名称\>-TimeLength:\<整数\>-时间单位： 月 &#124; 天 &#124;小时 &#124;分钟 [-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="5e259-173">**bm.exe set-activitywindow -Activity:\<activity name\> -TimeLength:\<integer number\> -TimeUnit:Month&#124;Day&#124;Hour&#124;Minute[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="5e259-174">**参数**</span><span class="sxs-lookup"><span data-stu-id="5e259-174">**Parameters**</span></span>  
  
|<span data-ttu-id="5e259-175">参数</span><span class="sxs-lookup"><span data-stu-id="5e259-175">Parameter</span></span>|<span data-ttu-id="5e259-176">Description</span><span class="sxs-lookup"><span data-stu-id="5e259-176">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e259-177">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="5e259-177">Activity:\<activity name\></span></span>|<span data-ttu-id="5e259-178">活动的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-178">The name of the activity.</span></span>|  
|<span data-ttu-id="5e259-179">TimeLength:\<整数\></span><span class="sxs-lookup"><span data-stu-id="5e259-179">TimeLength:\<integer number\></span></span>|<span data-ttu-id="5e259-180">活动的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5e259-180">The duration for the activity.</span></span>|  
|<span data-ttu-id="5e259-181">TimeUnit:Month &#124; 天 &#124;小时 &#124;分钟</span><span class="sxs-lookup"><span data-stu-id="5e259-181">TimeUnit:Month&#124;Day&#124;Hour&#124;Minute</span></span>|<span data-ttu-id="5e259-182">持续时间的度量单位。</span><span class="sxs-lookup"><span data-stu-id="5e259-182">The unit measure for the duration.</span></span>|  
|<span data-ttu-id="5e259-183">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="5e259-183">Server:\<server\></span></span>|<span data-ttu-id="5e259-184">可选： 活动所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-184">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="5e259-185">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="5e259-185">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="5e259-186">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-186">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="5e259-187">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="5e259-187">Database:\<database\></span></span>|<span data-ttu-id="5e259-188">可选： 在其上活动所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-188">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="5e259-189">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="5e259-189">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="5e259-190">设置指定活动的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5e259-190">Sets the duration for the specified activity.</span></span>  
  
 <span data-ttu-id="5e259-191">**示例**</span><span class="sxs-lookup"><span data-stu-id="5e259-191">**Examples**</span></span>  
  
```  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:6 -TimeUnit:Day  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:1 -TimeUnit:Month  
```  
  
## <a name="get-index-command"></a><span data-ttu-id="5e259-192">get-index 命令</span><span class="sxs-lookup"><span data-stu-id="5e259-192">get-index Command</span></span>  
 <span data-ttu-id="5e259-193">**用法**</span><span class="sxs-lookup"><span data-stu-id="5e259-193">**Usage**</span></span>  
  
 <span data-ttu-id="5e259-194">**bm.exe get 索引的活动：\<活动名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="5e259-194">**bm.exe get-index -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="5e259-195">**参数**</span><span class="sxs-lookup"><span data-stu-id="5e259-195">**Parameters**</span></span>  
  
|<span data-ttu-id="5e259-196">参数</span><span class="sxs-lookup"><span data-stu-id="5e259-196">Parameter</span></span>|<span data-ttu-id="5e259-197">Description</span><span class="sxs-lookup"><span data-stu-id="5e259-197">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e259-198">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="5e259-198">Activity:\<activity name\></span></span>|<span data-ttu-id="5e259-199">活动的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-199">The name of the activity.</span></span>|  
|<span data-ttu-id="5e259-200">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="5e259-200">Server:\<server\></span></span>|<span data-ttu-id="5e259-201">可选： 活动所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-201">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="5e259-202">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="5e259-202">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="5e259-203">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-203">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="5e259-204">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="5e259-204">Database:\<database\></span></span>|<span data-ttu-id="5e259-205">可选： 在其上活动所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-205">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="5e259-206">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="5e259-206">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="5e259-207">列出已为指定活动创建的所有索引。</span><span class="sxs-lookup"><span data-stu-id="5e259-207">Lists all the indexes that have been created for the specified activity.</span></span>  
  
 <span data-ttu-id="5e259-208">**示例**</span><span class="sxs-lookup"><span data-stu-id="5e259-208">**Examples**</span></span>  
  
```  
bm.exe get-index -Activity:PurchaseOrder  
bm.exe get-index -Activity:PurchaseOrder -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="create-index-command"></a><span data-ttu-id="5e259-209">create-index 命令</span><span class="sxs-lookup"><span data-stu-id="5e259-209">create-index Command</span></span>  
 <span data-ttu-id="5e259-210">**用法**</span><span class="sxs-lookup"><span data-stu-id="5e259-210">**Usage**</span></span>  
  
 <span data-ttu-id="5e259-211">**bm.exe 创建索引 IndexName:\<索引名称\>的活动：\<活动名称\>的检查点：\<checkpoint1\>[，\<checkpoint2\>...][-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="5e259-211">**bm.exe create-index -IndexName:\<index name\> -Activity:\<activity name\> -Checkpoint:\<checkpoint1\>[,\<checkpoint2\>...][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="5e259-212">**参数**</span><span class="sxs-lookup"><span data-stu-id="5e259-212">**Parameters**</span></span>  
  
|<span data-ttu-id="5e259-213">参数</span><span class="sxs-lookup"><span data-stu-id="5e259-213">Parameter</span></span>|<span data-ttu-id="5e259-214">Description</span><span class="sxs-lookup"><span data-stu-id="5e259-214">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e259-215">IndexName:\<索引名称\></span><span class="sxs-lookup"><span data-stu-id="5e259-215">IndexName:\<index name\></span></span>|<span data-ttu-id="5e259-216">新索引的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-216">The name of the new index.</span></span>|  
|<span data-ttu-id="5e259-217">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="5e259-217">Activity:\<activity name\></span></span>|<span data-ttu-id="5e259-218">创建索引的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-218">The name of the activity for which the index is created.</span></span>|  
|<span data-ttu-id="5e259-219">检查点：\<checkpoint1\>[，\<checkpoint2\>...]</span><span class="sxs-lookup"><span data-stu-id="5e259-219">Checkpoint:\<checkpoint1\>[,\<checkpoint2\>...]</span></span>|<span data-ttu-id="5e259-220">以逗号分隔的索引检查点列表。</span><span class="sxs-lookup"><span data-stu-id="5e259-220">A comma-delimited list of checkpoints for the index.</span></span>|  
|<span data-ttu-id="5e259-221">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="5e259-221">Server:\<server\></span></span>|<span data-ttu-id="5e259-222">可选： 活动所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-222">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="5e259-223">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="5e259-223">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="5e259-224">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-224">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="5e259-225">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="5e259-225">Database:\<database\></span></span>|<span data-ttu-id="5e259-226">可选： 在其上活动所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-226">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="5e259-227">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="5e259-227">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="5e259-228">使用指定检查点为指定的活动创建索引。</span><span class="sxs-lookup"><span data-stu-id="5e259-228">Creates an index for the specified activity using the specified checkpoints.</span></span>  
  
 <span data-ttu-id="5e259-229">**示例**</span><span class="sxs-lookup"><span data-stu-id="5e259-229">**Examples**</span></span>  
  
```  
bm.exe create-index -IndexName:Idx1 -Activity:PO -Checkpoint:State,City  
bm.exe create-index -IndexName:Idx2 -Activity:PO -Checkpoint:Amount -Server:S1  
```  
  
## <a name="delete-index-command"></a><span data-ttu-id="5e259-230">delete-index 命令</span><span class="sxs-lookup"><span data-stu-id="5e259-230">delete-index Command</span></span>  
 <span data-ttu-id="5e259-231">**用法**</span><span class="sxs-lookup"><span data-stu-id="5e259-231">**Usage**</span></span>  
  
 <span data-ttu-id="5e259-232">**bm.exe 删除索引 IndexName:\<索引名称\>的活动：\<活动名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="5e259-232">**bm.exe delete-index -IndexName:\<index name\> -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="5e259-233">**参数**</span><span class="sxs-lookup"><span data-stu-id="5e259-233">**Parameters**</span></span>  
  
|<span data-ttu-id="5e259-234">参数</span><span class="sxs-lookup"><span data-stu-id="5e259-234">Parameter</span></span>|<span data-ttu-id="5e259-235">Description</span><span class="sxs-lookup"><span data-stu-id="5e259-235">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e259-236">IndexName:\<索引名称\></span><span class="sxs-lookup"><span data-stu-id="5e259-236">IndexName:\<index name\></span></span>|<span data-ttu-id="5e259-237">要删除的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-237">The name of the index to delete.</span></span>|  
|<span data-ttu-id="5e259-238">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="5e259-238">Activity:\<activity name\></span></span>|<span data-ttu-id="5e259-239">删除索引的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-239">The name of the activity for which the index is deleted.</span></span>|  
|<span data-ttu-id="5e259-240">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="5e259-240">Server:\<server\></span></span>|<span data-ttu-id="5e259-241">可选： 活动所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-241">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="5e259-242">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="5e259-242">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="5e259-243">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-243">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="5e259-244">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="5e259-244">Database:\<database\></span></span>|<span data-ttu-id="5e259-245">可选： 在其上活动所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-245">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="5e259-246">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="5e259-246">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="5e259-247">从指定活动中删除具有给定名称的指定索引。</span><span class="sxs-lookup"><span data-stu-id="5e259-247">Deletes the specified index with the given name from the specified activity.</span></span>  
  
 <span data-ttu-id="5e259-248">**示例**</span><span class="sxs-lookup"><span data-stu-id="5e259-248">**Examples**</span></span>  
  
```  
bm.exe delete-index -IndexName:Idx1 -Activity:PO  
bm.exe delete-index -IndexName:Idx2 -Activity:PO -Server:S1 -Database:BamPI1  
```  
  
## <a name="set-archive-command"></a><span data-ttu-id="5e259-249">set-archive 命令</span><span class="sxs-lookup"><span data-stu-id="5e259-249">set-archive Command</span></span>  
 <span data-ttu-id="5e259-250">**用法**</span><span class="sxs-lookup"><span data-stu-id="5e259-250">**Usage**</span></span>  
  
 <span data-ttu-id="5e259-251">**bm.exe get 存档的活动：\<活动\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="5e259-251">**bm.exe get-archive -Activity:\<activity\> [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="5e259-252">**参数**</span><span class="sxs-lookup"><span data-stu-id="5e259-252">**Parameters**</span></span>  
  
|<span data-ttu-id="5e259-253">参数</span><span class="sxs-lookup"><span data-stu-id="5e259-253">Parameter</span></span>|<span data-ttu-id="5e259-254">Description</span><span class="sxs-lookup"><span data-stu-id="5e259-254">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e259-255">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="5e259-255">Activity:\<activity name\></span></span>|<span data-ttu-id="5e259-256">要显示其行为的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-256">The name of the activity for which the behavior is to be displayed.</span></span>|  
|<span data-ttu-id="5e259-257">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="5e259-257">Server:\<server\></span></span>|<span data-ttu-id="5e259-258">可选： 活动所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-258">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="5e259-259">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="5e259-259">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="5e259-260">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-260">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="5e259-261">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="5e259-261">Database:\<database\></span></span>|<span data-ttu-id="5e259-262">可选： 在其上活动所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-262">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="5e259-263">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="5e259-263">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="5e259-264">获取指定活动的存档程序包的行为，无论存档程序包是存档还是清除活动数据。</span><span class="sxs-lookup"><span data-stu-id="5e259-264">Gets the behavior of the archiving package for the specified activity, whether the archiving package will archive orpurge activity data.</span></span>  
  
 <span data-ttu-id="5e259-265">**示例**</span><span class="sxs-lookup"><span data-stu-id="5e259-265">**Examples**</span></span>  
  
```  
bm.exe get-archive -Activity:PurchaseOrder  
```  
  
## <a name="set-archive-command"></a><span data-ttu-id="5e259-266">set-archive 命令</span><span class="sxs-lookup"><span data-stu-id="5e259-266">set-archive Command</span></span>  
 <span data-ttu-id="5e259-267">**用法**</span><span class="sxs-lookup"><span data-stu-id="5e259-267">**Usage**</span></span>  
  
 <span data-ttu-id="5e259-268">**bm.exe 集的存档的活动：\<活动\>-ShouldArchive: True [-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="5e259-268">**bm.exe set-archive -Activity:\<activity\> -ShouldArchive:True [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="5e259-269">**参数**</span><span class="sxs-lookup"><span data-stu-id="5e259-269">**Parameters**</span></span>  
  
|<span data-ttu-id="5e259-270">参数</span><span class="sxs-lookup"><span data-stu-id="5e259-270">Parameter</span></span>|<span data-ttu-id="5e259-271">Description</span><span class="sxs-lookup"><span data-stu-id="5e259-271">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e259-272">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="5e259-272">Activity:\<activity name\></span></span>|<span data-ttu-id="5e259-273">要显示其行为的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-273">The name of the activity for which the behavior is to be displayed.</span></span>|  
|<span data-ttu-id="5e259-274">ShouldArchive: True</span><span class="sxs-lookup"><span data-stu-id="5e259-274">ShouldArchive: True</span></span>|<span data-ttu-id="5e259-275">如果设置为 True，则将活动移至存档数据库。</span><span class="sxs-lookup"><span data-stu-id="5e259-275">If set to True, the activity is moved to Archive DB.</span></span> <span data-ttu-id="5e259-276">如果设置为 False，则清除活动。</span><span class="sxs-lookup"><span data-stu-id="5e259-276">If set to False, the activity is purged.</span></span>|  
|<span data-ttu-id="5e259-277">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="5e259-277">Server:\<server\></span></span>|<span data-ttu-id="5e259-278">可选： 活动所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-278">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="5e259-279">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="5e259-279">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="5e259-280">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-280">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="5e259-281">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="5e259-281">Database:\<database\></span></span>|<span data-ttu-id="5e259-282">可选： 在其上活动所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="5e259-282">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="5e259-283">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="5e259-283">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="5e259-284">设置指定活动的存档程序包的行为，以便将活动数据移至存档数据库。</span><span class="sxs-lookup"><span data-stu-id="5e259-284">Sets the behavior of the archiving package for the activity specified so that activity data is moved into the Archive DB.</span></span> <span data-ttu-id="5e259-285">默认情况下，会为部署的新活动设置此行为。</span><span class="sxs-lookup"><span data-stu-id="5e259-285">By default, this behavior is set for new activities that are deployed.</span></span>  
  
 <span data-ttu-id="5e259-286">**示例**</span><span class="sxs-lookup"><span data-stu-id="5e259-286">**Examples**</span></span>  
  
 <span data-ttu-id="5e259-287">若要清除 BAM 活动数据，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5e259-287">To purge the BAM activity data, execute the following:</span></span>  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:False  
```  
  
 <span data-ttu-id="5e259-288">若要将 BAM 活动数据移至 BAMArchive 数据库，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5e259-288">To move the BAM activity data to the BAMArchive database, execute the following:</span></span>  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:True  
```  
  
## <a name="see-also"></a><span data-ttu-id="5e259-289">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e259-289">See Also</span></span>  
 [<span data-ttu-id="5e259-290">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="5e259-290">BAM Management Utility</span></span>](../core/bam-management-utility.md)
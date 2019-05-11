---
title: 活动管理命令 |Microsoft Docs
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
ms.openlocfilehash: 6dc32b005d0a6492fbdce87a1149c23c5a13442e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361677"
---
# <a name="activity-management-commands"></a><span data-ttu-id="f62df-102">活动管理命令</span><span class="sxs-lookup"><span data-stu-id="f62df-102">Activity Management Commands</span></span>
<span data-ttu-id="f62df-103">BAM 管理实用程序活动管理命令允许您可以使用已部署的活动。</span><span class="sxs-lookup"><span data-stu-id="f62df-103">The BAM Management utility activity management commands allow you to work with deployed activities.</span></span>  
  
-   <span data-ttu-id="f62df-104">获取活动：获取已部署的活动的列表。</span><span class="sxs-lookup"><span data-stu-id="f62df-104">get-activities: Gets a list of deployed activities.</span></span>  
  
-   <span data-ttu-id="f62df-105">删除活动：删除活动。</span><span class="sxs-lookup"><span data-stu-id="f62df-105">remove-activity: Removes an activity.</span></span>  
  
-   <span data-ttu-id="f62df-106">get-activitywindow:获取活动的持续时间。</span><span class="sxs-lookup"><span data-stu-id="f62df-106">get-activitywindow: Gets the duration for an activity.</span></span>  
  
-   <span data-ttu-id="f62df-107">set-activitywindow:设置活动的活动的持续时间。</span><span class="sxs-lookup"><span data-stu-id="f62df-107">set-activitywindow: Sets the activity duration for an activity.</span></span>  
  
-   <span data-ttu-id="f62df-108">获取索引：获取索引的列表。</span><span class="sxs-lookup"><span data-stu-id="f62df-108">get-index: Gets the list of indexes.</span></span>  
  
-   <span data-ttu-id="f62df-109">创建索引：创建新的索引。</span><span class="sxs-lookup"><span data-stu-id="f62df-109">create-index: Creates a new index.</span></span>  
  
-   <span data-ttu-id="f62df-110">删除索引：删除索引。</span><span class="sxs-lookup"><span data-stu-id="f62df-110">delete-index: Deletes an index.</span></span>  
  
-   <span data-ttu-id="f62df-111">get-存档：获取已存档活动的行为。</span><span class="sxs-lookup"><span data-stu-id="f62df-111">get-archive: Gets the behavior of archived activity.</span></span>  
  
-   <span data-ttu-id="f62df-112">设置存档：设置已存档活动的行为。</span><span class="sxs-lookup"><span data-stu-id="f62df-112">set-archive: Sets the behavior of archived activity.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f62df-113">通过将可以启用任何 BAM 实用程序命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。</span><span class="sxs-lookup"><span data-stu-id="f62df-113">You can enable tracing on any BAM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="f62df-114">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="f62df-114">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="f62df-115">此开关可以与所有标准 BAM 命令结合使用。</span><span class="sxs-lookup"><span data-stu-id="f62df-115">The switch can be used in conjunction with any normal BAM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f62df-116">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="f62df-116">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-activities-command"></a><span data-ttu-id="f62df-117">get-activities 命令</span><span class="sxs-lookup"><span data-stu-id="f62df-117">get-activities Command</span></span>  
 <span data-ttu-id="f62df-118">**Usage**</span><span class="sxs-lookup"><span data-stu-id="f62df-118">**Usage**</span></span>  
  
 <span data-ttu-id="f62df-119">**bm.exe get-activities [ -View:\<view name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="f62df-119">**bm.exe get-activities [ -View:\<view name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="f62df-120">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="f62df-120">**Parameters**</span></span>  
  
|<span data-ttu-id="f62df-121">参数</span><span class="sxs-lookup"><span data-stu-id="f62df-121">Parameter</span></span>|<span data-ttu-id="f62df-122">Description</span><span class="sxs-lookup"><span data-stu-id="f62df-122">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f62df-123">名称：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="f62df-123">Name:\<activity name\></span></span>|<span data-ttu-id="f62df-124">要删除的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-124">The name of the activity to remove.</span></span>|  
|<span data-ttu-id="f62df-125">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="f62df-125">Server:\<server\></span></span>|<span data-ttu-id="f62df-126">可选：从中获取活动的列表服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-126">Optional: The name of the server from which to get the list of activities.</span></span> <span data-ttu-id="f62df-127">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="f62df-127">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f62df-128">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="f62df-128">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f62df-129">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="f62df-129">Database:\<database\></span></span>|<span data-ttu-id="f62df-130">可选：从中获取活动的列表的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-130">Optional: The name of the database from which to get the list of activities.</span></span> <span data-ttu-id="f62df-131">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="f62df-131">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f62df-132">列出了在其执行此命令的计算机上部署的活动。</span><span class="sxs-lookup"><span data-stu-id="f62df-132">Lists the activities deployed on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="f62df-133">**示例**</span><span class="sxs-lookup"><span data-stu-id="f62df-133">**Examples**</span></span>  
  
```  
bm.exe get-activities -View:SalesManagerView  
bm.exe get-activities -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-activity-command"></a><span data-ttu-id="f62df-134">remove-activity 命令</span><span class="sxs-lookup"><span data-stu-id="f62df-134">remove-activity Command</span></span>  
 <span data-ttu-id="f62df-135">**Usage**</span><span class="sxs-lookup"><span data-stu-id="f62df-135">**Usage**</span></span>  
  
 <span data-ttu-id="f62df-136">**bm.exe remove-activity -Name:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="f62df-136">**bm.exe remove-activity -Name:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="f62df-137">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="f62df-137">**Parameters**</span></span>  
  
|<span data-ttu-id="f62df-138">参数</span><span class="sxs-lookup"><span data-stu-id="f62df-138">Parameter</span></span>|<span data-ttu-id="f62df-139">Description</span><span class="sxs-lookup"><span data-stu-id="f62df-139">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f62df-140">名称：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="f62df-140">Name:\<activity name\></span></span>|<span data-ttu-id="f62df-141">要删除的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-141">The name of the activity to remove.</span></span>|  
|<span data-ttu-id="f62df-142">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="f62df-142">Server:\<server\></span></span>|<span data-ttu-id="f62df-143">可选：要从中移除活动的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-143">Optional: The name of the server from which to remove the activity.</span></span> <span data-ttu-id="f62df-144">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="f62df-144">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f62df-145">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="f62df-145">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f62df-146">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="f62df-146">Database:\<database\></span></span>|<span data-ttu-id="f62df-147">可选：要从中移除活动的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-147">Optional: The name of the database from which to remove the activity.</span></span> <span data-ttu-id="f62df-148">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="f62df-148">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f62df-149">从 BAM 主导入数据库中删除指定的活动。</span><span class="sxs-lookup"><span data-stu-id="f62df-149">Removes the specified activity from the BAM Primary Import database.</span></span> <span data-ttu-id="f62df-150">如果该活动具有相关的视图，该命令将失败并报告错误。</span><span class="sxs-lookup"><span data-stu-id="f62df-150">If the activity has dependent views, the command will fail and report an error.</span></span> <span data-ttu-id="f62df-151">使用 remove-view 命令删除所有相关的视图，然后再次执行 remove-activity 命令。</span><span class="sxs-lookup"><span data-stu-id="f62df-151">Use the remove-view command to remove all the dependent views and execute the remove-activity command again.</span></span>  
  
 <span data-ttu-id="f62df-152">**示例**</span><span class="sxs-lookup"><span data-stu-id="f62df-152">**Examples**</span></span>  
  
```  
bm.exe remove-activity -Name:PurchaseOrder  
bm.exe remove-activity -Name:PO -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="get-activitywindow-command"></a><span data-ttu-id="f62df-153">get-activitywindow 命令</span><span class="sxs-lookup"><span data-stu-id="f62df-153">get-activitywindow Command</span></span>  
 <span data-ttu-id="f62df-154">**Usage**</span><span class="sxs-lookup"><span data-stu-id="f62df-154">**Usage**</span></span>  
  
 <span data-ttu-id="f62df-155">**bm.exe get-activitywindow -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="f62df-155">**bm.exe get-activitywindow -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="f62df-156">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="f62df-156">**Parameters**</span></span>  
  
|<span data-ttu-id="f62df-157">参数</span><span class="sxs-lookup"><span data-stu-id="f62df-157">Parameter</span></span>|<span data-ttu-id="f62df-158">Description</span><span class="sxs-lookup"><span data-stu-id="f62df-158">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f62df-159">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="f62df-159">Activity:\<activity name\></span></span>|<span data-ttu-id="f62df-160">.Activity 的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-160">The name of the .activity.</span></span>|  
|<span data-ttu-id="f62df-161">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="f62df-161">Server:\<server\></span></span>|<span data-ttu-id="f62df-162">可选：该活动所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-162">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="f62df-163">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="f62df-163">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f62df-164">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="f62df-164">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f62df-165">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="f62df-165">Database:\<database\></span></span>|<span data-ttu-id="f62df-166">可选：活动所处的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-166">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="f62df-167">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="f62df-167">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f62df-168">显示指定活动的持续时间。</span><span class="sxs-lookup"><span data-stu-id="f62df-168">Displays the duration for the specified activity.</span></span> <span data-ttu-id="f62df-169">该命令返回持续时间和持续时间单位所依据的单位的长度。</span><span class="sxs-lookup"><span data-stu-id="f62df-169">The command returns the length of the duration and the units by which the duration is measured.</span></span>  
  
 <span data-ttu-id="f62df-170">**示例**</span><span class="sxs-lookup"><span data-stu-id="f62df-170">**Examples**</span></span>  
  
```  
bm.exe get-activitywindow -Activity:PurchaseOrder  
bm.exe get-activitywindow -Activity:PO -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="set-activitywindow-command"></a><span data-ttu-id="f62df-171">set-activitywindow 命令</span><span class="sxs-lookup"><span data-stu-id="f62df-171">set-activitywindow Command</span></span>  
 <span data-ttu-id="f62df-172">**Usage**</span><span class="sxs-lookup"><span data-stu-id="f62df-172">**Usage**</span></span>  
  
 <span data-ttu-id="f62df-173">**bm.exe set-activitywindow -Activity:\<activity name\> -TimeLength:\<integer number\> -TimeUnit:Month&#124;Day&#124;Hour&#124;Minute[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="f62df-173">**bm.exe set-activitywindow -Activity:\<activity name\> -TimeLength:\<integer number\> -TimeUnit:Month&#124;Day&#124;Hour&#124;Minute[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="f62df-174">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="f62df-174">**Parameters**</span></span>  
  
|<span data-ttu-id="f62df-175">参数</span><span class="sxs-lookup"><span data-stu-id="f62df-175">Parameter</span></span>|<span data-ttu-id="f62df-176">Description</span><span class="sxs-lookup"><span data-stu-id="f62df-176">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f62df-177">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="f62df-177">Activity:\<activity name\></span></span>|<span data-ttu-id="f62df-178">活动的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-178">The name of the activity.</span></span>|  
|<span data-ttu-id="f62df-179">TimeLength:\<整数\></span><span class="sxs-lookup"><span data-stu-id="f62df-179">TimeLength:\<integer number\></span></span>|<span data-ttu-id="f62df-180">活动的持续时间。</span><span class="sxs-lookup"><span data-stu-id="f62df-180">The duration for the activity.</span></span>|  
|<span data-ttu-id="f62df-181">TimeUnit:Month&#124;Day&#124;Hour&#124;Minute</span><span class="sxs-lookup"><span data-stu-id="f62df-181">TimeUnit:Month&#124;Day&#124;Hour&#124;Minute</span></span>|<span data-ttu-id="f62df-182">持续时间度量单位。</span><span class="sxs-lookup"><span data-stu-id="f62df-182">The unit measure for the duration.</span></span>|  
|<span data-ttu-id="f62df-183">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="f62df-183">Server:\<server\></span></span>|<span data-ttu-id="f62df-184">可选：该活动所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-184">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="f62df-185">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="f62df-185">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f62df-186">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="f62df-186">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f62df-187">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="f62df-187">Database:\<database\></span></span>|<span data-ttu-id="f62df-188">可选：活动所处的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-188">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="f62df-189">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="f62df-189">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f62df-190">设置指定活动的持续时间。</span><span class="sxs-lookup"><span data-stu-id="f62df-190">Sets the duration for the specified activity.</span></span>  
  
 <span data-ttu-id="f62df-191">**示例**</span><span class="sxs-lookup"><span data-stu-id="f62df-191">**Examples**</span></span>  
  
```  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:6 -TimeUnit:Day  
bm.exe set-activitywindow -Activity:PurchaseOrder -TimeLength:1 -TimeUnit:Month  
```  
  
## <a name="get-index-command"></a><span data-ttu-id="f62df-192">get-index 命令</span><span class="sxs-lookup"><span data-stu-id="f62df-192">get-index Command</span></span>  
 <span data-ttu-id="f62df-193">**Usage**</span><span class="sxs-lookup"><span data-stu-id="f62df-193">**Usage**</span></span>  
  
 <span data-ttu-id="f62df-194">**bm.exe get-index -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="f62df-194">**bm.exe get-index -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="f62df-195">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="f62df-195">**Parameters**</span></span>  
  
|<span data-ttu-id="f62df-196">参数</span><span class="sxs-lookup"><span data-stu-id="f62df-196">Parameter</span></span>|<span data-ttu-id="f62df-197">Description</span><span class="sxs-lookup"><span data-stu-id="f62df-197">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f62df-198">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="f62df-198">Activity:\<activity name\></span></span>|<span data-ttu-id="f62df-199">活动的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-199">The name of the activity.</span></span>|  
|<span data-ttu-id="f62df-200">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="f62df-200">Server:\<server\></span></span>|<span data-ttu-id="f62df-201">可选：该活动所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-201">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="f62df-202">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="f62df-202">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f62df-203">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="f62df-203">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f62df-204">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="f62df-204">Database:\<database\></span></span>|<span data-ttu-id="f62df-205">可选：活动所处的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-205">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="f62df-206">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="f62df-206">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f62df-207">列出已为指定的活动创建的所有索引。</span><span class="sxs-lookup"><span data-stu-id="f62df-207">Lists all the indexes that have been created for the specified activity.</span></span>  
  
 <span data-ttu-id="f62df-208">**示例**</span><span class="sxs-lookup"><span data-stu-id="f62df-208">**Examples**</span></span>  
  
```  
bm.exe get-index -Activity:PurchaseOrder  
bm.exe get-index -Activity:PurchaseOrder -Server:Ship -Database:ShipDatabase  
```  
  
## <a name="create-index-command"></a><span data-ttu-id="f62df-209">create index 命令</span><span class="sxs-lookup"><span data-stu-id="f62df-209">create-index Command</span></span>  
 <span data-ttu-id="f62df-210">**Usage**</span><span class="sxs-lookup"><span data-stu-id="f62df-210">**Usage**</span></span>  
  
 <span data-ttu-id="f62df-211">**bm.exe create-index -IndexName:\<index name\> -Activity:\<activity name\> -Checkpoint:\<checkpoint1\>[,\<checkpoint2\>...][ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="f62df-211">**bm.exe create-index -IndexName:\<index name\> -Activity:\<activity name\> -Checkpoint:\<checkpoint1\>[,\<checkpoint2\>...][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="f62df-212">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="f62df-212">**Parameters**</span></span>  
  
|<span data-ttu-id="f62df-213">参数</span><span class="sxs-lookup"><span data-stu-id="f62df-213">Parameter</span></span>|<span data-ttu-id="f62df-214">Description</span><span class="sxs-lookup"><span data-stu-id="f62df-214">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f62df-215">IndexName:\<索引名称\></span><span class="sxs-lookup"><span data-stu-id="f62df-215">IndexName:\<index name\></span></span>|<span data-ttu-id="f62df-216">新的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-216">The name of the new index.</span></span>|  
|<span data-ttu-id="f62df-217">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="f62df-217">Activity:\<activity name\></span></span>|<span data-ttu-id="f62df-218">为其创建索引的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-218">The name of the activity for which the index is created.</span></span>|  
|<span data-ttu-id="f62df-219">Checkpoint:\<checkpoint1\>[,\<checkpoint2\>...]</span><span class="sxs-lookup"><span data-stu-id="f62df-219">Checkpoint:\<checkpoint1\>[,\<checkpoint2\>...]</span></span>|<span data-ttu-id="f62df-220">以逗号分隔的索引检查点的列表。</span><span class="sxs-lookup"><span data-stu-id="f62df-220">A comma-delimited list of checkpoints for the index.</span></span>|  
|<span data-ttu-id="f62df-221">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="f62df-221">Server:\<server\></span></span>|<span data-ttu-id="f62df-222">可选：该活动所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-222">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="f62df-223">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="f62df-223">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f62df-224">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="f62df-224">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f62df-225">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="f62df-225">Database:\<database\></span></span>|<span data-ttu-id="f62df-226">可选：活动所处的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-226">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="f62df-227">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="f62df-227">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f62df-228">创建使用指定的检查点的指定活动的索引。</span><span class="sxs-lookup"><span data-stu-id="f62df-228">Creates an index for the specified activity using the specified checkpoints.</span></span>  
  
 <span data-ttu-id="f62df-229">**示例**</span><span class="sxs-lookup"><span data-stu-id="f62df-229">**Examples**</span></span>  
  
```  
bm.exe create-index -IndexName:Idx1 -Activity:PO -Checkpoint:State,City  
bm.exe create-index -IndexName:Idx2 -Activity:PO -Checkpoint:Amount -Server:S1  
```  
  
## <a name="delete-index-command"></a><span data-ttu-id="f62df-230">delete-index 命令</span><span class="sxs-lookup"><span data-stu-id="f62df-230">delete-index Command</span></span>  
 <span data-ttu-id="f62df-231">**Usage**</span><span class="sxs-lookup"><span data-stu-id="f62df-231">**Usage**</span></span>  
  
 <span data-ttu-id="f62df-232">**bm.exe delete-index -IndexName:\<index name\> -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="f62df-232">**bm.exe delete-index -IndexName:\<index name\> -Activity:\<activity name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="f62df-233">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="f62df-233">**Parameters**</span></span>  
  
|<span data-ttu-id="f62df-234">参数</span><span class="sxs-lookup"><span data-stu-id="f62df-234">Parameter</span></span>|<span data-ttu-id="f62df-235">Description</span><span class="sxs-lookup"><span data-stu-id="f62df-235">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f62df-236">IndexName:\<索引名称\></span><span class="sxs-lookup"><span data-stu-id="f62df-236">IndexName:\<index name\></span></span>|<span data-ttu-id="f62df-237">要删除的索引的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-237">The name of the index to delete.</span></span>|  
|<span data-ttu-id="f62df-238">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="f62df-238">Activity:\<activity name\></span></span>|<span data-ttu-id="f62df-239">会删除该索引的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-239">The name of the activity for which the index is deleted.</span></span>|  
|<span data-ttu-id="f62df-240">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="f62df-240">Server:\<server\></span></span>|<span data-ttu-id="f62df-241">可选：该活动所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-241">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="f62df-242">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="f62df-242">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f62df-243">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="f62df-243">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f62df-244">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="f62df-244">Database:\<database\></span></span>|<span data-ttu-id="f62df-245">可选：活动所处的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-245">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="f62df-246">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="f62df-246">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f62df-247">从指定的活动中删除具有给定名称的指定的索引。</span><span class="sxs-lookup"><span data-stu-id="f62df-247">Deletes the specified index with the given name from the specified activity.</span></span>  
  
 <span data-ttu-id="f62df-248">**示例**</span><span class="sxs-lookup"><span data-stu-id="f62df-248">**Examples**</span></span>  
  
```  
bm.exe delete-index -IndexName:Idx1 -Activity:PO  
bm.exe delete-index -IndexName:Idx2 -Activity:PO -Server:S1 -Database:BamPI1  
```  
  
## <a name="set-archive-command"></a><span data-ttu-id="f62df-249">set-archive 命令</span><span class="sxs-lookup"><span data-stu-id="f62df-249">set-archive Command</span></span>  
 <span data-ttu-id="f62df-250">**Usage**</span><span class="sxs-lookup"><span data-stu-id="f62df-250">**Usage**</span></span>  
  
 <span data-ttu-id="f62df-251">**bm.exe get-archive -Activity:\<activity\> [-Server:\<server\>] [-Database:\<database\>]**</span><span class="sxs-lookup"><span data-stu-id="f62df-251">**bm.exe get-archive -Activity:\<activity\> [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="f62df-252">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="f62df-252">**Parameters**</span></span>  
  
|<span data-ttu-id="f62df-253">参数</span><span class="sxs-lookup"><span data-stu-id="f62df-253">Parameter</span></span>|<span data-ttu-id="f62df-254">Description</span><span class="sxs-lookup"><span data-stu-id="f62df-254">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f62df-255">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="f62df-255">Activity:\<activity name\></span></span>|<span data-ttu-id="f62df-256">为其行为是要显示的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-256">The name of the activity for which the behavior is to be displayed.</span></span>|  
|<span data-ttu-id="f62df-257">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="f62df-257">Server:\<server\></span></span>|<span data-ttu-id="f62df-258">可选：该活动所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-258">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="f62df-259">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="f62df-259">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f62df-260">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="f62df-260">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f62df-261">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="f62df-261">Database:\<database\></span></span>|<span data-ttu-id="f62df-262">可选：活动所处的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-262">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="f62df-263">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="f62df-263">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f62df-264">获取指定活动的存档程序包行为，是否存档程序包是存档还是清除活动数据。</span><span class="sxs-lookup"><span data-stu-id="f62df-264">Gets the behavior of the archiving package for the specified activity, whether the archiving package will archive orpurge activity data.</span></span>  
  
 <span data-ttu-id="f62df-265">**示例**</span><span class="sxs-lookup"><span data-stu-id="f62df-265">**Examples**</span></span>  
  
```  
bm.exe get-archive -Activity:PurchaseOrder  
```  
  
## <a name="set-archive-command"></a><span data-ttu-id="f62df-266">set-archive 命令</span><span class="sxs-lookup"><span data-stu-id="f62df-266">set-archive Command</span></span>  
 <span data-ttu-id="f62df-267">**Usage**</span><span class="sxs-lookup"><span data-stu-id="f62df-267">**Usage**</span></span>  
  
 <span data-ttu-id="f62df-268">**bm.exe set-archive -Activity:\<activity\> -ShouldArchive:True [-Server:\<server\>] [-Database:\<database\>]**</span><span class="sxs-lookup"><span data-stu-id="f62df-268">**bm.exe set-archive -Activity:\<activity\> -ShouldArchive:True [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="f62df-269">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="f62df-269">**Parameters**</span></span>  
  
|<span data-ttu-id="f62df-270">参数</span><span class="sxs-lookup"><span data-stu-id="f62df-270">Parameter</span></span>|<span data-ttu-id="f62df-271">Description</span><span class="sxs-lookup"><span data-stu-id="f62df-271">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f62df-272">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="f62df-272">Activity:\<activity name\></span></span>|<span data-ttu-id="f62df-273">为其行为是要显示的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-273">The name of the activity for which the behavior is to be displayed.</span></span>|  
|<span data-ttu-id="f62df-274">ShouldArchive:True</span><span class="sxs-lookup"><span data-stu-id="f62df-274">ShouldArchive: True</span></span>|<span data-ttu-id="f62df-275">如果设置为 True，则将活动移至存档数据库。</span><span class="sxs-lookup"><span data-stu-id="f62df-275">If set to True, the activity is moved to Archive DB.</span></span> <span data-ttu-id="f62df-276">如果设置为 False，该活动将清除。</span><span class="sxs-lookup"><span data-stu-id="f62df-276">If set to False, the activity is purged.</span></span>|  
|<span data-ttu-id="f62df-277">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="f62df-277">Server:\<server\></span></span>|<span data-ttu-id="f62df-278">可选：该活动所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-278">Optional: The name of the server on which the activity resides.</span></span> <span data-ttu-id="f62df-279">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="f62df-279">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="f62df-280">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="f62df-280">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="f62df-281">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="f62df-281">Database:\<database\></span></span>|<span data-ttu-id="f62df-282">可选：活动所处的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="f62df-282">Optional: The name of the database on which the activity resides.</span></span> <span data-ttu-id="f62df-283">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="f62df-283">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="f62df-284">设置指定，以便活动数据移至存档数据库的活动的存档程序包行为。</span><span class="sxs-lookup"><span data-stu-id="f62df-284">Sets the behavior of the archiving package for the activity specified so that activity data is moved into the Archive DB.</span></span> <span data-ttu-id="f62df-285">默认情况下部署的新活动设置此行为。</span><span class="sxs-lookup"><span data-stu-id="f62df-285">By default, this behavior is set for new activities that are deployed.</span></span>  
  
 <span data-ttu-id="f62df-286">**示例**</span><span class="sxs-lookup"><span data-stu-id="f62df-286">**Examples**</span></span>  
  
 <span data-ttu-id="f62df-287">若要清除 BAM 活动数据，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f62df-287">To purge the BAM activity data, execute the following:</span></span>  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:False  
```  
  
 <span data-ttu-id="f62df-288">将 BAM 活动数据移至 BAMArchive 数据库，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f62df-288">To move the BAM activity data to the BAMArchive database, execute the following:</span></span>  
  
```  
bm.exe set-archive -Activity:PurchaseOrder -ShouldArchive:True  
```  
  
## <a name="see-also"></a><span data-ttu-id="f62df-289">请参阅</span><span class="sxs-lookup"><span data-stu-id="f62df-289">See Also</span></span>  
 [<span data-ttu-id="f62df-290">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="f62df-290">BAM Management Utility</span></span>](../core/bam-management-utility.md)
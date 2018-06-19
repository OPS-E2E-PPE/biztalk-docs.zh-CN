---
title: 警报管理命令 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a96d8de7-a918-4737-aa35-4e1abf6bb08f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f419e7a0019287383080c319961b8a3831d27bb4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967683"
---
# <a name="alert-management-commands"></a><span data-ttu-id="ae2e6-102">警报管理命令</span><span class="sxs-lookup"><span data-stu-id="ae2e6-102">Alert Management Commands</span></span>
<span data-ttu-id="ae2e6-103">您可借助 BAM 管理实用程序的警报管理命令来处理已部署的警报。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-103">The BAM management utility alert management commands allow you to work with deployed alerts.</span></span>  
  
-   <span data-ttu-id="ae2e6-104">get 警报： 获取已部署的警报的列表。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-104">get-alerts: Get a list of deployed alerts.</span></span>  
  
-   <span data-ttu-id="ae2e6-105">删除警报： 删除警报。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-105">remove-alerts: Removes an alert.</span></span>  
  
-   <span data-ttu-id="ae2e6-106">启用警报： 启用对视图的警报。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-106">enable-alerts: Enables alerts on a view.</span></span>  
  
-   <span data-ttu-id="ae2e6-107">禁用警报： 禁用对视图的警报。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-107">disable-alerts: Disables alerts on a view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae2e6-108">你可以通过包括启用任何 BM 实用工具命令的跟踪 **-跟踪： 在 &#124; 关闭**参数交换机。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="ae2e6-109">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="ae2e6-110">该开关可与所有标准 BM 命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae2e6-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-alerts-command"></a><span data-ttu-id="ae2e6-112">get-alerts 命令</span><span class="sxs-lookup"><span data-stu-id="ae2e6-112">get-alerts Command</span></span>  
 <span data-ttu-id="ae2e6-113">**用法**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-113">**Usage**</span></span>  
  
 <span data-ttu-id="ae2e6-114">**bm.exe get 警报 [的视图：\<视图名称\>] [-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-114">**bm.exe get-alerts [ -View:\<view name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="ae2e6-115">**参数**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-115">**Parameters**</span></span>  
  
|<span data-ttu-id="ae2e6-116">参数</span><span class="sxs-lookup"><span data-stu-id="ae2e6-116">Parameter</span></span>|<span data-ttu-id="ae2e6-117">Description</span><span class="sxs-lookup"><span data-stu-id="ae2e6-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae2e6-118">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="ae2e6-118">View:\<view name\></span></span>|<span data-ttu-id="ae2e6-119">从中获取警报列表的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-119">The name of the view from which to get the list of alerts.</span></span>|  
|<span data-ttu-id="ae2e6-120">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="ae2e6-120">Server:\<server\></span></span>|<span data-ttu-id="ae2e6-121">可选： 视图所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-121">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="ae2e6-122">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="ae2e6-123">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="ae2e6-124">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="ae2e6-124">Database:\<database\></span></span>|<span data-ttu-id="ae2e6-125">可选： 在其上视图所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-125">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="ae2e6-126">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="ae2e6-127">列出在执行此命令的计算机上定义的警报。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-127">Lists the alerts defined on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="ae2e6-128">**示例**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-128">**Examples**</span></span>  
  
```  
bm.exe get-alerts -View:ManagerView  
bm.exe get-alerts -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-alerts-command"></a><span data-ttu-id="ae2e6-129">remove-alerts 命令</span><span class="sxs-lookup"><span data-stu-id="ae2e6-129">remove-alerts Command</span></span>  
 <span data-ttu-id="ae2e6-130">**用法**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-130">**Usage**</span></span>  
  
 <span data-ttu-id="ae2e6-131">**bm.exe 删除警报的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-131">**bm.exe remove-alerts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="ae2e6-132">**参数**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-132">**Parameters**</span></span>  
  
|<span data-ttu-id="ae2e6-133">参数</span><span class="sxs-lookup"><span data-stu-id="ae2e6-133">Parameter</span></span>|<span data-ttu-id="ae2e6-134">Description</span><span class="sxs-lookup"><span data-stu-id="ae2e6-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae2e6-135">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="ae2e6-135">View:\<view name\></span></span>|<span data-ttu-id="ae2e6-136">从中删除警报的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-136">The name of the view from which to remove alerts.</span></span>|  
|<span data-ttu-id="ae2e6-137">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="ae2e6-137">Server:\<server\></span></span>|<span data-ttu-id="ae2e6-138">可选： 视图所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-138">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="ae2e6-139">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-139">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="ae2e6-140">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-140">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="ae2e6-141">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="ae2e6-141">Database:\<database\></span></span>|<span data-ttu-id="ae2e6-142">可选： 在其上视图所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-142">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="ae2e6-143">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-143">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="ae2e6-144">删除指定视图中的所有警报。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-144">Removes all alerts on the specified view.</span></span>  
  
 <span data-ttu-id="ae2e6-145">**示例**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-145">**Examples**</span></span>  
  
```  
bm.exe remove-alerts -View:SalesManagerView  
bm.exe remove-alerts -View:Shipments -Server:Ship1  
```  
  
## <a name="enable-alerts-command"></a><span data-ttu-id="ae2e6-146">enable-alerts 命令</span><span class="sxs-lookup"><span data-stu-id="ae2e6-146">enable-alerts Command</span></span>  
 <span data-ttu-id="ae2e6-147">**用法**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-147">**Usage**</span></span>  
  
 <span data-ttu-id="ae2e6-148">**bm.exe 启用警报的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-148">**bm.exe enable-alerts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="ae2e6-149">**参数**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-149">**Parameters**</span></span>  
  
|<span data-ttu-id="ae2e6-150">参数</span><span class="sxs-lookup"><span data-stu-id="ae2e6-150">Parameter</span></span>|<span data-ttu-id="ae2e6-151">Description</span><span class="sxs-lookup"><span data-stu-id="ae2e6-151">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae2e6-152">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="ae2e6-152">View:\<view name\></span></span>|<span data-ttu-id="ae2e6-153">启用警报的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-153">The name of the view on which to enable alerts.</span></span>|  
|<span data-ttu-id="ae2e6-154">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="ae2e6-154">Server:\<server\></span></span>|<span data-ttu-id="ae2e6-155">可选： 视图所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-155">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="ae2e6-156">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-156">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="ae2e6-157">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-157">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="ae2e6-158">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="ae2e6-158">Database:\<database\></span></span>|<span data-ttu-id="ae2e6-159">可选： 在其上视图所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-159">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="ae2e6-160">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-160">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="ae2e6-161">对指定视图启用警报。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-161">Enables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="ae2e6-162">**示例**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-162">**Examples**</span></span>  
  
```  
bm.exe enable-alerts -View:SalesManagerView  
bm.exe enable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="disable-alerts-command"></a><span data-ttu-id="ae2e6-163">disable-alerts 命令</span><span class="sxs-lookup"><span data-stu-id="ae2e6-163">disable-alerts Command</span></span>  
 <span data-ttu-id="ae2e6-164">**用法**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-164">**Usage**</span></span>  
  
 <span data-ttu-id="ae2e6-165">**bm.exe 禁用警报的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-165">**bm.exe disable-alerts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="ae2e6-166">**参数**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-166">**Parameters**</span></span>  
  
|<span data-ttu-id="ae2e6-167">参数</span><span class="sxs-lookup"><span data-stu-id="ae2e6-167">Parameter</span></span>|<span data-ttu-id="ae2e6-168">Description</span><span class="sxs-lookup"><span data-stu-id="ae2e6-168">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae2e6-169">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="ae2e6-169">View:\<view name\></span></span>|<span data-ttu-id="ae2e6-170">禁用警报的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-170">The name of the view on which to disable alerts.</span></span>|  
|<span data-ttu-id="ae2e6-171">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="ae2e6-171">Server:\<server\></span></span>|<span data-ttu-id="ae2e6-172">可选： 视图所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-172">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="ae2e6-173">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-173">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="ae2e6-174">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-174">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="ae2e6-175">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="ae2e6-175">Database:\<database\></span></span>|<span data-ttu-id="ae2e6-176">可选： 在其上视图所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-176">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="ae2e6-177">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-177">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="ae2e6-178">对指定视图禁用警报。</span><span class="sxs-lookup"><span data-stu-id="ae2e6-178">Disables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="ae2e6-179">**示例**</span><span class="sxs-lookup"><span data-stu-id="ae2e6-179">**Examples**</span></span>  
  
```  
bm.exe disable-alerts -View:SalesManagerView  
bm.exe disable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae2e6-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae2e6-180">See Also</span></span>  
 [<span data-ttu-id="ae2e6-181">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="ae2e6-181">BAM Management Utility</span></span>](../core/bam-management-utility.md)
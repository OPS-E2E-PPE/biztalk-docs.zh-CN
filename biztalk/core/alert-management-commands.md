---
title: "警报管理命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a96d8de7-a918-4737-aa35-4e1abf6bb08f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b73129d884fea81bdb64609de5e95570275a344
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="alert-management-commands"></a><span data-ttu-id="8bda3-102">警报管理命令</span><span class="sxs-lookup"><span data-stu-id="8bda3-102">Alert Management Commands</span></span>
<span data-ttu-id="8bda3-103">您可借助 BAM 管理实用程序的警报管理命令来处理已部署的警报。</span><span class="sxs-lookup"><span data-stu-id="8bda3-103">The BAM management utility alert management commands allow you to work with deployed alerts.</span></span>  
  
-   <span data-ttu-id="8bda3-104">get 警报： 获取已部署的警报的列表。</span><span class="sxs-lookup"><span data-stu-id="8bda3-104">get-alerts: Get a list of deployed alerts.</span></span>  
  
-   <span data-ttu-id="8bda3-105">删除警报： 删除警报。</span><span class="sxs-lookup"><span data-stu-id="8bda3-105">remove-alerts: Removes an alert.</span></span>  
  
-   <span data-ttu-id="8bda3-106">启用警报： 启用对视图的警报。</span><span class="sxs-lookup"><span data-stu-id="8bda3-106">enable-alerts: Enables alerts on a view.</span></span>  
  
-   <span data-ttu-id="8bda3-107">禁用警报： 禁用对视图的警报。</span><span class="sxs-lookup"><span data-stu-id="8bda3-107">disable-alerts: Disables alerts on a view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bda3-108">你可以通过包括启用任何 BM 实用工具命令的跟踪**-跟踪： 在 &#124; 关闭**参数交换机。</span><span class="sxs-lookup"><span data-stu-id="8bda3-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="8bda3-109">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="8bda3-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="8bda3-110">该开关可与所有标准 BM 命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="8bda3-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8bda3-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="8bda3-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-alerts-command"></a><span data-ttu-id="8bda3-112">get-alerts 命令</span><span class="sxs-lookup"><span data-stu-id="8bda3-112">get-alerts Command</span></span>  
 <span data-ttu-id="8bda3-113">**用法**</span><span class="sxs-lookup"><span data-stu-id="8bda3-113">**Usage**</span></span>  
  
 <span data-ttu-id="8bda3-114">**bm.exe get 警报 [的视图：\<视图名称 >] [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="8bda3-114">**bm.exe get-alerts [ -View:\<view name> ][ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="8bda3-115">**参数**</span><span class="sxs-lookup"><span data-stu-id="8bda3-115">**Parameters**</span></span>  
  
|<span data-ttu-id="8bda3-116">参数</span><span class="sxs-lookup"><span data-stu-id="8bda3-116">Parameter</span></span>|<span data-ttu-id="8bda3-117">Description</span><span class="sxs-lookup"><span data-stu-id="8bda3-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bda3-118">视图：\<视图名称 ></span><span class="sxs-lookup"><span data-stu-id="8bda3-118">View:\<view name></span></span>|<span data-ttu-id="8bda3-119">从中获取警报列表的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-119">The name of the view from which to get the list of alerts.</span></span>|  
|<span data-ttu-id="8bda3-120">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="8bda3-120">Server:\<server></span></span>|<span data-ttu-id="8bda3-121">可选： 视图所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-121">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="8bda3-122">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="8bda3-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="8bda3-123">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="8bda3-124">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="8bda3-124">Database:\<database></span></span>|<span data-ttu-id="8bda3-125">可选： 在其上视图所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-125">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="8bda3-126">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="8bda3-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="8bda3-127">列出在执行此命令的计算机上定义的警报。</span><span class="sxs-lookup"><span data-stu-id="8bda3-127">Lists the alerts defined on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="8bda3-128">**示例**</span><span class="sxs-lookup"><span data-stu-id="8bda3-128">**Examples**</span></span>  
  
```  
bm.exe get-alerts -View:ManagerView  
bm.exe get-alerts -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-alerts-command"></a><span data-ttu-id="8bda3-129">remove-alerts 命令</span><span class="sxs-lookup"><span data-stu-id="8bda3-129">remove-alerts Command</span></span>  
 <span data-ttu-id="8bda3-130">**用法**</span><span class="sxs-lookup"><span data-stu-id="8bda3-130">**Usage**</span></span>  
  
 <span data-ttu-id="8bda3-131">**bm.exe 删除警报的视图：\<视图名称 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="8bda3-131">**bm.exe remove-alerts -View:\<view name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="8bda3-132">**参数**</span><span class="sxs-lookup"><span data-stu-id="8bda3-132">**Parameters**</span></span>  
  
|<span data-ttu-id="8bda3-133">参数</span><span class="sxs-lookup"><span data-stu-id="8bda3-133">Parameter</span></span>|<span data-ttu-id="8bda3-134">Description</span><span class="sxs-lookup"><span data-stu-id="8bda3-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bda3-135">视图：\<视图名称 ></span><span class="sxs-lookup"><span data-stu-id="8bda3-135">View:\<view name></span></span>|<span data-ttu-id="8bda3-136">从中删除警报的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-136">The name of the view from which to remove alerts.</span></span>|  
|<span data-ttu-id="8bda3-137">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="8bda3-137">Server:\<server></span></span>|<span data-ttu-id="8bda3-138">可选： 视图所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-138">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="8bda3-139">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="8bda3-139">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="8bda3-140">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-140">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="8bda3-141">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="8bda3-141">Database:\<database></span></span>|<span data-ttu-id="8bda3-142">可选： 在其上视图所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-142">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="8bda3-143">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="8bda3-143">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="8bda3-144">删除指定视图中的所有警报。</span><span class="sxs-lookup"><span data-stu-id="8bda3-144">Removes all alerts on the specified view.</span></span>  
  
 <span data-ttu-id="8bda3-145">**示例**</span><span class="sxs-lookup"><span data-stu-id="8bda3-145">**Examples**</span></span>  
  
```  
bm.exe remove-alerts -View:SalesManagerView  
bm.exe remove-alerts -View:Shipments -Server:Ship1  
```  
  
## <a name="enable-alerts-command"></a><span data-ttu-id="8bda3-146">enable-alerts 命令</span><span class="sxs-lookup"><span data-stu-id="8bda3-146">enable-alerts Command</span></span>  
 <span data-ttu-id="8bda3-147">**用法**</span><span class="sxs-lookup"><span data-stu-id="8bda3-147">**Usage**</span></span>  
  
 <span data-ttu-id="8bda3-148">**bm.exe 启用警报的视图：\<视图名称 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="8bda3-148">**bm.exe enable-alerts -View:\<view name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="8bda3-149">**参数**</span><span class="sxs-lookup"><span data-stu-id="8bda3-149">**Parameters**</span></span>  
  
|<span data-ttu-id="8bda3-150">参数</span><span class="sxs-lookup"><span data-stu-id="8bda3-150">Parameter</span></span>|<span data-ttu-id="8bda3-151">Description</span><span class="sxs-lookup"><span data-stu-id="8bda3-151">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bda3-152">视图：\<视图名称 ></span><span class="sxs-lookup"><span data-stu-id="8bda3-152">View:\<view name></span></span>|<span data-ttu-id="8bda3-153">启用警报的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-153">The name of the view on which to enable alerts.</span></span>|  
|<span data-ttu-id="8bda3-154">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="8bda3-154">Server:\<server></span></span>|<span data-ttu-id="8bda3-155">可选： 视图所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-155">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="8bda3-156">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="8bda3-156">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="8bda3-157">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-157">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="8bda3-158">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="8bda3-158">Database:\<database></span></span>|<span data-ttu-id="8bda3-159">可选： 在其上视图所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-159">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="8bda3-160">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="8bda3-160">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="8bda3-161">对指定视图启用警报。</span><span class="sxs-lookup"><span data-stu-id="8bda3-161">Enables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="8bda3-162">**示例**</span><span class="sxs-lookup"><span data-stu-id="8bda3-162">**Examples**</span></span>  
  
```  
bm.exe enable-alerts -View:SalesManagerView  
bm.exe enable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="disable-alerts-command"></a><span data-ttu-id="8bda3-163">disable-alerts 命令</span><span class="sxs-lookup"><span data-stu-id="8bda3-163">disable-alerts Command</span></span>  
 <span data-ttu-id="8bda3-164">**用法**</span><span class="sxs-lookup"><span data-stu-id="8bda3-164">**Usage**</span></span>  
  
 <span data-ttu-id="8bda3-165">**bm.exe 禁用警报的视图：\<视图名称 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="8bda3-165">**bm.exe disable-alerts -View:\<view name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="8bda3-166">**参数**</span><span class="sxs-lookup"><span data-stu-id="8bda3-166">**Parameters**</span></span>  
  
|<span data-ttu-id="8bda3-167">参数</span><span class="sxs-lookup"><span data-stu-id="8bda3-167">Parameter</span></span>|<span data-ttu-id="8bda3-168">Description</span><span class="sxs-lookup"><span data-stu-id="8bda3-168">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bda3-169">视图：\<视图名称 ></span><span class="sxs-lookup"><span data-stu-id="8bda3-169">View:\<view name></span></span>|<span data-ttu-id="8bda3-170">禁用警报的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-170">The name of the view on which to disable alerts.</span></span>|  
|<span data-ttu-id="8bda3-171">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="8bda3-171">Server:\<server></span></span>|<span data-ttu-id="8bda3-172">可选： 视图所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-172">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="8bda3-173">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="8bda3-173">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="8bda3-174">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-174">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="8bda3-175">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="8bda3-175">Database:\<database></span></span>|<span data-ttu-id="8bda3-176">可选： 在其上视图所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="8bda3-176">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="8bda3-177">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="8bda3-177">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="8bda3-178">对指定视图禁用警报。</span><span class="sxs-lookup"><span data-stu-id="8bda3-178">Disables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="8bda3-179">**示例**</span><span class="sxs-lookup"><span data-stu-id="8bda3-179">**Examples**</span></span>  
  
```  
bm.exe disable-alerts -View:SalesManagerView  
bm.exe disable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="see-also"></a><span data-ttu-id="8bda3-180">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bda3-180">See Also</span></span>  
 [<span data-ttu-id="8bda3-181">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="8bda3-181">BAM Management Utility</span></span>](../core/bam-management-utility.md)
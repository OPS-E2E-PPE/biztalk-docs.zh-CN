---
title: 警报管理命令 |Microsoft Docs
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
ms.openlocfilehash: 651bc1d0df943df022cf597bb7292cb3143ad327
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359295"
---
# <a name="alert-management-commands"></a><span data-ttu-id="33144-102">警报管理命令</span><span class="sxs-lookup"><span data-stu-id="33144-102">Alert Management Commands</span></span>
<span data-ttu-id="33144-103">BAM 管理实用程序警报管理命令允许您可以使用已部署的警报。</span><span class="sxs-lookup"><span data-stu-id="33144-103">The BAM management utility alert management commands allow you to work with deployed alerts.</span></span>  
  
-   <span data-ttu-id="33144-104">get-alerts:获取已部署的警报的列表。</span><span class="sxs-lookup"><span data-stu-id="33144-104">get-alerts: Get a list of deployed alerts.</span></span>  
  
-   <span data-ttu-id="33144-105">删除警报：删除警报。</span><span class="sxs-lookup"><span data-stu-id="33144-105">remove-alerts: Removes an alert.</span></span>  
  
-   <span data-ttu-id="33144-106">启用警报：对视图启用警报。</span><span class="sxs-lookup"><span data-stu-id="33144-106">enable-alerts: Enables alerts on a view.</span></span>  
  
-   <span data-ttu-id="33144-107">禁用的警报：对视图禁用警报。</span><span class="sxs-lookup"><span data-stu-id="33144-107">disable-alerts: Disables alerts on a view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33144-108">通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。</span><span class="sxs-lookup"><span data-stu-id="33144-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="33144-109">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="33144-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="33144-110">此开关可以与所有标准 BM 命令结合使用。</span><span class="sxs-lookup"><span data-stu-id="33144-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33144-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="33144-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-alerts-command"></a><span data-ttu-id="33144-112">get-alerts Command</span><span class="sxs-lookup"><span data-stu-id="33144-112">get-alerts Command</span></span>  
 <span data-ttu-id="33144-113">**Usage**</span><span class="sxs-lookup"><span data-stu-id="33144-113">**Usage**</span></span>  
  
 <span data-ttu-id="33144-114">**bm.exe get-alerts [ -View:\<view name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="33144-114">**bm.exe get-alerts [ -View:\<view name\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="33144-115">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="33144-115">**Parameters**</span></span>  
  
|<span data-ttu-id="33144-116">参数</span><span class="sxs-lookup"><span data-stu-id="33144-116">Parameter</span></span>|<span data-ttu-id="33144-117">Description</span><span class="sxs-lookup"><span data-stu-id="33144-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33144-118">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="33144-118">View:\<view name\></span></span>|<span data-ttu-id="33144-119">要从其中获取警报的列表视图的名称。</span><span class="sxs-lookup"><span data-stu-id="33144-119">The name of the view from which to get the list of alerts.</span></span>|  
|<span data-ttu-id="33144-120">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="33144-120">Server:\<server\></span></span>|<span data-ttu-id="33144-121">可选：该视图所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="33144-121">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="33144-122">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="33144-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="33144-123">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="33144-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="33144-124">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="33144-124">Database:\<database\></span></span>|<span data-ttu-id="33144-125">可选：视图所驻留的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="33144-125">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="33144-126">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="33144-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="33144-127">列出对其执行该命令的计算机上定义的警报。</span><span class="sxs-lookup"><span data-stu-id="33144-127">Lists the alerts defined on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="33144-128">**示例**</span><span class="sxs-lookup"><span data-stu-id="33144-128">**Examples**</span></span>  
  
```  
bm.exe get-alerts -View:ManagerView  
bm.exe get-alerts -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="remove-alerts-command"></a><span data-ttu-id="33144-129">remove-alerts 命令</span><span class="sxs-lookup"><span data-stu-id="33144-129">remove-alerts Command</span></span>  
 <span data-ttu-id="33144-130">**Usage**</span><span class="sxs-lookup"><span data-stu-id="33144-130">**Usage**</span></span>  
  
 <span data-ttu-id="33144-131">**bm.exe 删除警报的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="33144-131">**bm.exe remove-alerts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="33144-132">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="33144-132">**Parameters**</span></span>  
  
|<span data-ttu-id="33144-133">参数</span><span class="sxs-lookup"><span data-stu-id="33144-133">Parameter</span></span>|<span data-ttu-id="33144-134">Description</span><span class="sxs-lookup"><span data-stu-id="33144-134">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33144-135">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="33144-135">View:\<view name\></span></span>|<span data-ttu-id="33144-136">要从其中移除警报视图的名称。</span><span class="sxs-lookup"><span data-stu-id="33144-136">The name of the view from which to remove alerts.</span></span>|  
|<span data-ttu-id="33144-137">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="33144-137">Server:\<server\></span></span>|<span data-ttu-id="33144-138">可选：该视图所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="33144-138">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="33144-139">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="33144-139">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="33144-140">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="33144-140">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="33144-141">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="33144-141">Database:\<database\></span></span>|<span data-ttu-id="33144-142">可选：视图所驻留的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="33144-142">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="33144-143">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="33144-143">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="33144-144">删除指定的视图上的所有警报。</span><span class="sxs-lookup"><span data-stu-id="33144-144">Removes all alerts on the specified view.</span></span>  
  
 <span data-ttu-id="33144-145">**示例**</span><span class="sxs-lookup"><span data-stu-id="33144-145">**Examples**</span></span>  
  
```  
bm.exe remove-alerts -View:SalesManagerView  
bm.exe remove-alerts -View:Shipments -Server:Ship1  
```  
  
## <a name="enable-alerts-command"></a><span data-ttu-id="33144-146">enable-alerts 命令</span><span class="sxs-lookup"><span data-stu-id="33144-146">enable-alerts Command</span></span>  
 <span data-ttu-id="33144-147">**Usage**</span><span class="sxs-lookup"><span data-stu-id="33144-147">**Usage**</span></span>  
  
 <span data-ttu-id="33144-148">**bm.exe 启用警报的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="33144-148">**bm.exe enable-alerts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="33144-149">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="33144-149">**Parameters**</span></span>  
  
|<span data-ttu-id="33144-150">参数</span><span class="sxs-lookup"><span data-stu-id="33144-150">Parameter</span></span>|<span data-ttu-id="33144-151">Description</span><span class="sxs-lookup"><span data-stu-id="33144-151">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33144-152">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="33144-152">View:\<view name\></span></span>|<span data-ttu-id="33144-153">要启用的警报视图的名称。</span><span class="sxs-lookup"><span data-stu-id="33144-153">The name of the view on which to enable alerts.</span></span>|  
|<span data-ttu-id="33144-154">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="33144-154">Server:\<server\></span></span>|<span data-ttu-id="33144-155">可选：该视图所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="33144-155">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="33144-156">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="33144-156">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="33144-157">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="33144-157">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="33144-158">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="33144-158">Database:\<database\></span></span>|<span data-ttu-id="33144-159">可选：视图所驻留的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="33144-159">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="33144-160">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="33144-160">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="33144-161">对指定视图启用警报。</span><span class="sxs-lookup"><span data-stu-id="33144-161">Enables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="33144-162">**示例**</span><span class="sxs-lookup"><span data-stu-id="33144-162">**Examples**</span></span>  
  
```  
bm.exe enable-alerts -View:SalesManagerView  
bm.exe enable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="disable-alerts-command"></a><span data-ttu-id="33144-163">disable-alerts 命令</span><span class="sxs-lookup"><span data-stu-id="33144-163">disable-alerts Command</span></span>  
 <span data-ttu-id="33144-164">**Usage**</span><span class="sxs-lookup"><span data-stu-id="33144-164">**Usage**</span></span>  
  
 <span data-ttu-id="33144-165">**bm.exe 禁用警报的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="33144-165">**bm.exe disable-alerts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="33144-166">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="33144-166">**Parameters**</span></span>  
  
|<span data-ttu-id="33144-167">参数</span><span class="sxs-lookup"><span data-stu-id="33144-167">Parameter</span></span>|<span data-ttu-id="33144-168">Description</span><span class="sxs-lookup"><span data-stu-id="33144-168">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33144-169">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="33144-169">View:\<view name\></span></span>|<span data-ttu-id="33144-170">要禁用警报的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="33144-170">The name of the view on which to disable alerts.</span></span>|  
|<span data-ttu-id="33144-171">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="33144-171">Server:\<server\></span></span>|<span data-ttu-id="33144-172">可选：该视图所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="33144-172">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="33144-173">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="33144-173">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="33144-174">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="33144-174">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="33144-175">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="33144-175">Database:\<database\></span></span>|<span data-ttu-id="33144-176">可选：视图所驻留的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="33144-176">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="33144-177">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="33144-177">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="33144-178">对指定视图禁用警报。</span><span class="sxs-lookup"><span data-stu-id="33144-178">Disables alerts on the specified view.</span></span>  
  
 <span data-ttu-id="33144-179">**示例**</span><span class="sxs-lookup"><span data-stu-id="33144-179">**Examples**</span></span>  
  
```  
bm.exe disable-alerts -View:SalesManagerView  
bm.exe disable-alerts -View:SalesManagerView -Server:s1 -Database:db2  
```  
  
## <a name="see-also"></a><span data-ttu-id="33144-180">请参阅</span><span class="sxs-lookup"><span data-stu-id="33144-180">See Also</span></span>  
 [<span data-ttu-id="33144-181">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="33144-181">BAM Management Utility</span></span>](../core/bam-management-utility.md)
---
title: "用户管理命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: feb12226-a4da-4fc5-93a1-aced239f60a9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79f908933015fa07e2ecf77a2e61d31227f73e62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="user-management-commands"></a><span data-ttu-id="9cdbe-102">用户管理命令</span><span class="sxs-lookup"><span data-stu-id="9cdbe-102">User Management Commands</span></span>
<span data-ttu-id="9cdbe-103">BAM 管理实用程序的警报用户管理命令允许您获取、添加和删除用户。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-103">The BAM Management utility alert user management commands allow you to get, add, and remove users.</span></span>  
  
-   <span data-ttu-id="9cdbe-104">get 帐户： 获取所有用户和组可以访问指定的视图的列表。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-104">get-accounts: Gets a list of all users and groups that can access a specified view.</span></span>  
  
-   <span data-ttu-id="9cdbe-105">添加帐户： 授予访问权限指定的用户或组指定的视图。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-105">add-account: Grants access rights for the specified user or group to the specified view.</span></span>  
  
-   <span data-ttu-id="9cdbe-106">删除帐户： 删除从指定的视图的访问权限的用户或组。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-106">remove-account: Removes access rights for a user or group from a specified view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9cdbe-107">你可以通过包括启用任何 BM 实用工具命令的跟踪**-跟踪： 在 &#124; 关闭**参数交换机。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-107">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="9cdbe-108">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-108">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="9cdbe-109">该开关可与所有标准 BM 命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-109">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9cdbe-110">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-110">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-accounts-command"></a><span data-ttu-id="9cdbe-111">get-accounts 命令</span><span class="sxs-lookup"><span data-stu-id="9cdbe-111">get-accounts Command</span></span>  
 <span data-ttu-id="9cdbe-112">**用法**</span><span class="sxs-lookup"><span data-stu-id="9cdbe-112">**Usage**</span></span>  
  
 <span data-ttu-id="9cdbe-113">**bm.exe get 帐户的视图：\<视图名称 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="9cdbe-113">**bm.exe get-accounts -View:\<view name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="9cdbe-114">**参数**</span><span class="sxs-lookup"><span data-stu-id="9cdbe-114">**Parameters**</span></span>  
  
|<span data-ttu-id="9cdbe-115">参数</span><span class="sxs-lookup"><span data-stu-id="9cdbe-115">Parameter</span></span>|<span data-ttu-id="9cdbe-116">Description</span><span class="sxs-lookup"><span data-stu-id="9cdbe-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9cdbe-117">视图：\<视图名称 ></span><span class="sxs-lookup"><span data-stu-id="9cdbe-117">View:\<view name></span></span>|<span data-ttu-id="9cdbe-118">列出其帐户的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-118">The name of the view for which to list accounts.</span></span>|  
|<span data-ttu-id="9cdbe-119">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="9cdbe-119">Server:\<server></span></span>|<span data-ttu-id="9cdbe-120">可选： 用于检索帐户的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-120">Optional: The name of the server from which to retrieve the accounts.</span></span> <span data-ttu-id="9cdbe-121">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-121">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="9cdbe-122">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-122">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="9cdbe-123">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="9cdbe-123">Database:\<database></span></span>|<span data-ttu-id="9cdbe-124">可选： 要从中检索帐户数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-124">Optional: The name of the database from which to retrieve the accounts.</span></span> <span data-ttu-id="9cdbe-125">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-125">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="9cdbe-126">列出可访问指定视图的所有用户和组。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-126">Lists all users and groups that can access the specified view.</span></span>  
  
 <span data-ttu-id="9cdbe-127">**示例**</span><span class="sxs-lookup"><span data-stu-id="9cdbe-127">**Examples**</span></span>  
  
 `bm.exe get-accounts -View:PurchaseOrder`  
  
 `bm.exe get-accounts -View:ShipmentOrder -Server:Ship -Database:ShipDatabase`  
  
## <a name="add-account-command"></a><span data-ttu-id="9cdbe-128">add-account 命令</span><span class="sxs-lookup"><span data-stu-id="9cdbe-128">add-account Command</span></span>  
 <span data-ttu-id="9cdbe-129">**用法**</span><span class="sxs-lookup"><span data-stu-id="9cdbe-129">**Usage**</span></span>  
  
 <span data-ttu-id="9cdbe-130">**bm.exe 添加帐户 AccountName:\<帐户名称 >-视图：\<视图名称 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="9cdbe-130">**bm.exe add-account -AccountName:\<account name> -View:\<view name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="9cdbe-131">**参数**</span><span class="sxs-lookup"><span data-stu-id="9cdbe-131">**Parameters**</span></span>  
  
|<span data-ttu-id="9cdbe-132">参数</span><span class="sxs-lookup"><span data-stu-id="9cdbe-132">Parameter</span></span>|<span data-ttu-id="9cdbe-133">Description</span><span class="sxs-lookup"><span data-stu-id="9cdbe-133">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9cdbe-134">AccountName: < 帐户名称</span><span class="sxs-lookup"><span data-stu-id="9cdbe-134">AccountName:<account name</span></span>|<span data-ttu-id="9cdbe-135">向其授予权限的帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-135">The name of the account to which rights are granted.</span></span>|  
|<span data-ttu-id="9cdbe-136">视图：\<视图名称 ></span><span class="sxs-lookup"><span data-stu-id="9cdbe-136">View:\<view name></span></span>|<span data-ttu-id="9cdbe-137">向其授予权限的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-137">The name of the view to which rights are granted.</span></span>|  
|<span data-ttu-id="9cdbe-138">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="9cdbe-138">Server:\<server></span></span>|<span data-ttu-id="9cdbe-139">可选： 视图所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-139">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="9cdbe-140">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-140">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="9cdbe-141">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-141">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="9cdbe-142">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="9cdbe-142">Database:\<database></span></span>|<span data-ttu-id="9cdbe-143">可选： 在其上视图所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-143">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="9cdbe-144">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-144">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="9cdbe-145">授予指定的用户或组对指定视图的访问权限。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-145">Grants the specified user or group access rights to the specified view.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9cdbe-146">如果你使用的实时聚合 (Rta)，与添加用户**添加帐户**命令都不会自动授予 SQL Server 登录权限。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-146">If you are using Real Time Aggregations (RTAs), users added with **add-account** command are not automatically granted logon rights to SQL Server.</span></span> <span data-ttu-id="9cdbe-147">如果你使用的 Rta，考虑建立包含所有需要查看的 Rta 视图的用户的 Windows 用户组。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-147">If you are using RTAs, consider establishing a Windows user group that contains all of the users that need to see views of the RTAs.</span></span> <span data-ttu-id="9cdbe-148">授予该组对 BAM 主导入数据库的宿主 SQL Server 的显式登录权限。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-148">Grant that group explicit SQL Server logon rights on the SQL server hosting the BAM Primary Import databases.</span></span>  
  
 <span data-ttu-id="9cdbe-149">**示例**</span><span class="sxs-lookup"><span data-stu-id="9cdbe-149">**Examples**</span></span>  
  
```  
bm.exe add-account -AccountName:john -View:PurchaseOrder  
bm.exe add-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="remove-account-command"></a><span data-ttu-id="9cdbe-150">remove-account 命令</span><span class="sxs-lookup"><span data-stu-id="9cdbe-150">remove-account Command</span></span>  
 <span data-ttu-id="9cdbe-151">**用法**</span><span class="sxs-lookup"><span data-stu-id="9cdbe-151">**Usage**</span></span>  
  
 <span data-ttu-id="9cdbe-152">**bm.exe 删除帐户 AccountName:\<帐户名称 >-视图：\<视图名称 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="9cdbe-152">**bm.exe remove-account -AccountName:\<account name> -View:\<view name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="9cdbe-153">**参数**</span><span class="sxs-lookup"><span data-stu-id="9cdbe-153">**Parameters**</span></span>  
  
|<span data-ttu-id="9cdbe-154">参数</span><span class="sxs-lookup"><span data-stu-id="9cdbe-154">Parameter</span></span>|<span data-ttu-id="9cdbe-155">Description</span><span class="sxs-lookup"><span data-stu-id="9cdbe-155">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9cdbe-156">AccountName:\<帐户名称 ></span><span class="sxs-lookup"><span data-stu-id="9cdbe-156">AccountName:\<account name></span></span>|<span data-ttu-id="9cdbe-157">删除其视图权限的帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-157">The name of the account from which to remove rights to the view.</span></span>|  
|<span data-ttu-id="9cdbe-158">视图：\<视图名称 ></span><span class="sxs-lookup"><span data-stu-id="9cdbe-158">View:\<view name></span></span>|<span data-ttu-id="9cdbe-159">删除权限的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-159">The name of the view to which rights are removed.</span></span>|  
|<span data-ttu-id="9cdbe-160">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="9cdbe-160">Server:\<server></span></span>|<span data-ttu-id="9cdbe-161">可选： 视图所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-161">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="9cdbe-162">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-162">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="9cdbe-163">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-163">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="9cdbe-164">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="9cdbe-164">Database:\<database></span></span>|<span data-ttu-id="9cdbe-165">可选： 在其上视图所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-165">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="9cdbe-166">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-166">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="9cdbe-167">从指定的视图中删除用户或用户组的访问权限。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-167">Removes access rights for a user or group from a specified view.</span></span> <span data-ttu-id="9cdbe-168">从视图中删除帐户将从为指定视图定义的警报中删除该帐户及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-168">Removing an account from a view removes that account and all of its members from alerts defined for the specified view.</span></span> <span data-ttu-id="9cdbe-169">如果该帐户是警报的唯一所有者，则当前用户 (admin) 将成为警报的新所有者。</span><span class="sxs-lookup"><span data-stu-id="9cdbe-169">If that account is the sole owner of an alert, the current user (admin) becomes the new owner of the alert.</span></span>  
  
 <span data-ttu-id="9cdbe-170">**示例**</span><span class="sxs-lookup"><span data-stu-id="9cdbe-170">**Examples**</span></span>  
  
```  
bm.exe remove-account -AccountName:john -View:PurchaseOrder  
bm.exe remove-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="see-also"></a><span data-ttu-id="9cdbe-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9cdbe-171">See Also</span></span>  
 [<span data-ttu-id="9cdbe-172">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="9cdbe-172">BAM Management Utility</span></span>](../core/bam-management-utility.md)
---
title: 用户管理命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feb12226-a4da-4fc5-93a1-aced239f60a9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b79ff5a6bc94faab130de5d7d793612f2130d732
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399962"
---
# <a name="user-management-commands"></a><span data-ttu-id="48ce8-102">用户管理命令</span><span class="sxs-lookup"><span data-stu-id="48ce8-102">User Management Commands</span></span>
<span data-ttu-id="48ce8-103">BAM 管理实用程序警报用户管理命令可以获取、 添加和删除用户。</span><span class="sxs-lookup"><span data-stu-id="48ce8-103">The BAM Management utility alert user management commands allow you to get, add, and remove users.</span></span>  
  
-   <span data-ttu-id="48ce8-104">get-accounts:获取所有用户和组可以访问指定的视图的列表。</span><span class="sxs-lookup"><span data-stu-id="48ce8-104">get-accounts: Gets a list of all users and groups that can access a specified view.</span></span>  
  
-   <span data-ttu-id="48ce8-105">添加帐户：授予访问权限指定的用户或组对指定视图的权限。</span><span class="sxs-lookup"><span data-stu-id="48ce8-105">add-account: Grants access rights for the specified user or group to the specified view.</span></span>  
  
-   <span data-ttu-id="48ce8-106">删除帐户：删除访问权限的用户或组从指定的视图。</span><span class="sxs-lookup"><span data-stu-id="48ce8-106">remove-account: Removes access rights for a user or group from a specified view.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48ce8-107">通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。</span><span class="sxs-lookup"><span data-stu-id="48ce8-107">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="48ce8-108">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="48ce8-108">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="48ce8-109">此开关可以与所有标准 BM 命令结合使用。</span><span class="sxs-lookup"><span data-stu-id="48ce8-109">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48ce8-110">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="48ce8-110">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-accounts-command"></a><span data-ttu-id="48ce8-111">get-accounts 命令</span><span class="sxs-lookup"><span data-stu-id="48ce8-111">get-accounts Command</span></span>  
 <span data-ttu-id="48ce8-112">**Usage**</span><span class="sxs-lookup"><span data-stu-id="48ce8-112">**Usage**</span></span>  
  
 <span data-ttu-id="48ce8-113">**bm.exe 获取帐户的视图：\<视图名称\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="48ce8-113">**bm.exe get-accounts -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="48ce8-114">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="48ce8-114">**Parameters**</span></span>  
  
|<span data-ttu-id="48ce8-115">参数</span><span class="sxs-lookup"><span data-stu-id="48ce8-115">Parameter</span></span>|<span data-ttu-id="48ce8-116">Description</span><span class="sxs-lookup"><span data-stu-id="48ce8-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="48ce8-117">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="48ce8-117">View:\<view name\></span></span>|<span data-ttu-id="48ce8-118">列出帐户到为其视图的名称。</span><span class="sxs-lookup"><span data-stu-id="48ce8-118">The name of the view for which to list accounts.</span></span>|  
|<span data-ttu-id="48ce8-119">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="48ce8-119">Server:\<server\></span></span>|<span data-ttu-id="48ce8-120">可选：要从中检索帐户的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="48ce8-120">Optional: The name of the server from which to retrieve the accounts.</span></span> <span data-ttu-id="48ce8-121">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="48ce8-121">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="48ce8-122">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="48ce8-122">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="48ce8-123">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="48ce8-123">Database:\<database\></span></span>|<span data-ttu-id="48ce8-124">可选：要从中检索帐户的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="48ce8-124">Optional: The name of the database from which to retrieve the accounts.</span></span> <span data-ttu-id="48ce8-125">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="48ce8-125">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="48ce8-126">列出所有用户和组可以访问指定的视图。</span><span class="sxs-lookup"><span data-stu-id="48ce8-126">Lists all users and groups that can access the specified view.</span></span>  
  
 <span data-ttu-id="48ce8-127">**示例**</span><span class="sxs-lookup"><span data-stu-id="48ce8-127">**Examples**</span></span>  
  
 `bm.exe get-accounts -View:PurchaseOrder`  
  
 `bm.exe get-accounts -View:ShipmentOrder -Server:Ship -Database:ShipDatabase`  
  
## <a name="add-account-command"></a><span data-ttu-id="48ce8-128">添加帐户命令</span><span class="sxs-lookup"><span data-stu-id="48ce8-128">add-account Command</span></span>  
 <span data-ttu-id="48ce8-129">**Usage**</span><span class="sxs-lookup"><span data-stu-id="48ce8-129">**Usage**</span></span>  
  
 <span data-ttu-id="48ce8-130">**bm.exe add-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="48ce8-130">**bm.exe add-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="48ce8-131">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="48ce8-131">**Parameters**</span></span>  
  
|<span data-ttu-id="48ce8-132">参数</span><span class="sxs-lookup"><span data-stu-id="48ce8-132">Parameter</span></span>|<span data-ttu-id="48ce8-133">Description</span><span class="sxs-lookup"><span data-stu-id="48ce8-133">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="48ce8-134">AccountName: < 帐户名称</span><span class="sxs-lookup"><span data-stu-id="48ce8-134">AccountName:<account name</span></span>|<span data-ttu-id="48ce8-135">要向其授予权限的帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="48ce8-135">The name of the account to which rights are granted.</span></span>|  
|<span data-ttu-id="48ce8-136">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="48ce8-136">View:\<view name\></span></span>|<span data-ttu-id="48ce8-137">要向其授予权限的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="48ce8-137">The name of the view to which rights are granted.</span></span>|  
|<span data-ttu-id="48ce8-138">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="48ce8-138">Server:\<server\></span></span>|<span data-ttu-id="48ce8-139">可选：该视图所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="48ce8-139">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="48ce8-140">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="48ce8-140">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="48ce8-141">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="48ce8-141">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="48ce8-142">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="48ce8-142">Database:\<database\></span></span>|<span data-ttu-id="48ce8-143">可选：视图所驻留的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="48ce8-143">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="48ce8-144">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="48ce8-144">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="48ce8-145">授予指定的用户或组对指定视图的访问权限。</span><span class="sxs-lookup"><span data-stu-id="48ce8-145">Grants the specified user or group access rights to the specified view.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="48ce8-146">如果使用的实时聚合 (Rta)，使用添加用户**添加帐户**命令不会自动授予 SQL Server 登录权限。</span><span class="sxs-lookup"><span data-stu-id="48ce8-146">If you are using Real Time Aggregations (RTAs), users added with **add-account** command are not automatically granted logon rights to SQL Server.</span></span> <span data-ttu-id="48ce8-147">如果使用 Rta，请考虑建立一个包含的所有用户需要查看的 Rta 视图的 Windows 用户组。</span><span class="sxs-lookup"><span data-stu-id="48ce8-147">If you are using RTAs, consider establishing a Windows user group that contains all of the users that need to see views of the RTAs.</span></span> <span data-ttu-id="48ce8-148">授予该组对 BAM 主导入数据库的宿主 SQL 服务器上的显式 SQL Server 登录权限。</span><span class="sxs-lookup"><span data-stu-id="48ce8-148">Grant that group explicit SQL Server logon rights on the SQL server hosting the BAM Primary Import databases.</span></span>  
  
 <span data-ttu-id="48ce8-149">**示例**</span><span class="sxs-lookup"><span data-stu-id="48ce8-149">**Examples**</span></span>  
  
```  
bm.exe add-account -AccountName:john -View:PurchaseOrder  
bm.exe add-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="remove-account-command"></a><span data-ttu-id="48ce8-150">remove-account 命令</span><span class="sxs-lookup"><span data-stu-id="48ce8-150">remove-account Command</span></span>  
 <span data-ttu-id="48ce8-151">**Usage**</span><span class="sxs-lookup"><span data-stu-id="48ce8-151">**Usage**</span></span>  
  
 <span data-ttu-id="48ce8-152">**bm.exe remove-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="48ce8-152">**bm.exe remove-account -AccountName:\<account name\> -View:\<view name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="48ce8-153">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="48ce8-153">**Parameters**</span></span>  
  
|<span data-ttu-id="48ce8-154">参数</span><span class="sxs-lookup"><span data-stu-id="48ce8-154">Parameter</span></span>|<span data-ttu-id="48ce8-155">Description</span><span class="sxs-lookup"><span data-stu-id="48ce8-155">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="48ce8-156">AccountName:\<帐户名称\></span><span class="sxs-lookup"><span data-stu-id="48ce8-156">AccountName:\<account name\></span></span>|<span data-ttu-id="48ce8-157">要从其中移除对视图的权限的帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="48ce8-157">The name of the account from which to remove rights to the view.</span></span>|  
|<span data-ttu-id="48ce8-158">视图：\<视图名称\></span><span class="sxs-lookup"><span data-stu-id="48ce8-158">View:\<view name\></span></span>|<span data-ttu-id="48ce8-159">删除权限的视图的名称。</span><span class="sxs-lookup"><span data-stu-id="48ce8-159">The name of the view to which rights are removed.</span></span>|  
|<span data-ttu-id="48ce8-160">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="48ce8-160">Server:\<server\></span></span>|<span data-ttu-id="48ce8-161">可选：该视图所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="48ce8-161">Optional: The name of the server on which the view resides.</span></span> <span data-ttu-id="48ce8-162">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="48ce8-162">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="48ce8-163">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="48ce8-163">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="48ce8-164">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="48ce8-164">Database:\<database\></span></span>|<span data-ttu-id="48ce8-165">可选：视图所驻留的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="48ce8-165">Optional: The name of the database on which the view resides.</span></span> <span data-ttu-id="48ce8-166">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="48ce8-166">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="48ce8-167">删除访问权限的用户或组从指定的视图。</span><span class="sxs-lookup"><span data-stu-id="48ce8-167">Removes access rights for a user or group from a specified view.</span></span> <span data-ttu-id="48ce8-168">从视图中删除帐户从为指定的视图定义的警报中删除该帐户及其所有成员。</span><span class="sxs-lookup"><span data-stu-id="48ce8-168">Removing an account from a view removes that account and all of its members from alerts defined for the specified view.</span></span> <span data-ttu-id="48ce8-169">如果该帐户是警报的唯一所有者，当前用户 (admin) 将成为新所有者的警报。</span><span class="sxs-lookup"><span data-stu-id="48ce8-169">If that account is the sole owner of an alert, the current user (admin) becomes the new owner of the alert.</span></span>  
  
 <span data-ttu-id="48ce8-170">**示例**</span><span class="sxs-lookup"><span data-stu-id="48ce8-170">**Examples**</span></span>  
  
```  
bm.exe remove-account -AccountName:john -View:PurchaseOrder  
bm.exe remove-account -AccountName:Agents -View:PO -Server:Srv1 -Database:Db2  
```  
  
## <a name="see-also"></a><span data-ttu-id="48ce8-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="48ce8-171">See Also</span></span>  
 [<span data-ttu-id="48ce8-172">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="48ce8-172">BAM Management Utility</span></span>](../core/bam-management-utility.md)
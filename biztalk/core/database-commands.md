---
title: 数据库命令 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c54131-0793-45a9-822a-554cd4fc05a2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2232602ec5a91768f4b9dbde5f6c63a79de0c332
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971363"
---
# <a name="database-commands"></a><span data-ttu-id="6290d-102">数据库命令</span><span class="sxs-lookup"><span data-stu-id="6290d-102">Database Commands</span></span>
<span data-ttu-id="6290d-103">BAM 管理实用程序数据库命令允许你使用 BAM 数据库：</span><span class="sxs-lookup"><span data-stu-id="6290d-103">The BAM Management utility database commands allow you to work with the BAM databases:</span></span>  
  
-   <span data-ttu-id="6290d-104">安装程序数据库： 将创建所 BAM 特定数据库。</span><span class="sxs-lookup"><span data-stu-id="6290d-104">setup-databases: Creates the BAM-specific databases.</span></span>  
  
-   <span data-ttu-id="6290d-105">迁移 sql： 迁移 BAM 数据库：</span><span class="sxs-lookup"><span data-stu-id="6290d-105">migrate-sql: Migrates your BAM databases from:</span></span>  
  
    -   <span data-ttu-id="6290d-106">与 Microsoft SQL Server 2008 的 Microsoft SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="6290d-106">Microsoft SQL Server 2000 to Microsoft SQL Server 2008</span></span>  
  
    -   <span data-ttu-id="6290d-107">与 Microsoft SQL Server 2008 的 Microsoft SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="6290d-107">Microsoft SQL Server 2005 to Microsoft SQL Server 2008</span></span>  
  
-   <span data-ttu-id="6290d-108">启用引用： 启用对分布式 BAM 主导入数据库的引用。</span><span class="sxs-lookup"><span data-stu-id="6290d-108">enable-reference: Enables a reference to a distributed BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="6290d-109">获取引用： 获取对分布式 BAM 主导入数据库的引用的列表。</span><span class="sxs-lookup"><span data-stu-id="6290d-109">get-references: Gets a list of references to distributed BAM Primary Import databases.</span></span>  
  
-   <span data-ttu-id="6290d-110">禁用参考： 禁用对 BAM 主导入数据库的引用。</span><span class="sxs-lookup"><span data-stu-id="6290d-110">disable-reference: Disables a reference to a BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6290d-111">你可以通过包括启用任何 BM 实用工具命令的跟踪 **-跟踪： 在 &#124; 关闭**参数交换机。</span><span class="sxs-lookup"><span data-stu-id="6290d-111">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="6290d-112">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="6290d-112">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="6290d-113">该开关可与所有标准 BM 命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="6290d-113">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6290d-114">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="6290d-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="setup-databases-command"></a><span data-ttu-id="6290d-115">安装程序数据库命令</span><span class="sxs-lookup"><span data-stu-id="6290d-115">setup-databases Command</span></span>  
 <span data-ttu-id="6290d-116">**用法**</span><span class="sxs-lookup"><span data-stu-id="6290d-116">**Usage**</span></span>  
  
 <span data-ttu-id="6290d-117">**bm.exe 安装程序数据库 ConfigFile:\<配置文件\>[-NSUser:\<通知服务用户名\>] [-NSUserPassword:\<通知服务用户密码\> ]**</span><span class="sxs-lookup"><span data-stu-id="6290d-117">**bm.exe setup-databases-ConfigFile:\<configuration file\>[ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ]**</span></span>  
  
 <span data-ttu-id="6290d-118">**参数**</span><span class="sxs-lookup"><span data-stu-id="6290d-118">**Parameters**</span></span>  
  
|<span data-ttu-id="6290d-119">参数</span><span class="sxs-lookup"><span data-stu-id="6290d-119">Parameter</span></span>|<span data-ttu-id="6290d-120">Description</span><span class="sxs-lookup"><span data-stu-id="6290d-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6290d-121">ConfigFile:\<配置文件\></span><span class="sxs-lookup"><span data-stu-id="6290d-121">ConfigFile:\<configuration file\></span></span>|<span data-ttu-id="6290d-122">BAM 配置文件从其创建数据库。</span><span class="sxs-lookup"><span data-stu-id="6290d-122">The BAM configuration file from which to create the database.</span></span>|  
|<span data-ttu-id="6290d-123">NSUser:\<通知服务用户名\></span><span class="sxs-lookup"><span data-stu-id="6290d-123">NSUser:\<notifications service user name\></span></span>|<span data-ttu-id="6290d-124">可选： 通知服务用户有权创建数据库用户 ID。</span><span class="sxs-lookup"><span data-stu-id="6290d-124">Optional: The user ID of a notifications services user with permissions to create databases.</span></span>|  
|<span data-ttu-id="6290d-125">NSUserPassword</span><span class="sxs-lookup"><span data-stu-id="6290d-125">NSUserPassword</span></span>|<span data-ttu-id="6290d-126">可选： 指定的通知服务用户的密码。</span><span class="sxs-lookup"><span data-stu-id="6290d-126">Optional: The password for the specified notifications services user.</span></span>|  
  
 <span data-ttu-id="6290d-127">创建如果不存在配置文件 （BAM 主导入、 BAM 星型架构、 BAM 存档、 BAM 分析和警报） 中描述的数据库。</span><span class="sxs-lookup"><span data-stu-id="6290d-127">Creates the databases described in the configuration file (BAM Primary Import, BAM Star Schema, BAM Archive, BAM Analysis, and alerts) if they do not already exist.</span></span> <span data-ttu-id="6290d-128">数据库创建后，命令将创建关联的 BAM 元数据的表和存储的过程。</span><span class="sxs-lookup"><span data-stu-id="6290d-128">Once the databases are created, the command creates the associated BAM metadata tables and stored procedures.</span></span>  
  
 <span data-ttu-id="6290d-129">如果你要设置 BAM 警报，则需要的 NSUser 和 NSUserPassword 参数。</span><span class="sxs-lookup"><span data-stu-id="6290d-129">The NSUser and NSUserPassword parameters are required if you are setting up BAM alerts.</span></span> <span data-ttu-id="6290d-130">如果未在命令行上指定 NSUserPassword，bm.exe 将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="6290d-130">If the NSUserPassword is not specified on the command line, bm.exe prompts you for the password.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6290d-131">后该命令完成时，你可能注意到在跟踪日志中 AlertModule 中的发生异常：</span><span class="sxs-lookup"><span data-stu-id="6290d-131">After the completion of the command, you may note an exception from the AlertModule in the trace log:</span></span>  
>   
>  <span data-ttu-id="6290d-132">“指定的帐户是数据库所有者。</span><span class="sxs-lookup"><span data-stu-id="6290d-132">"The specified account is the Database Owner.</span></span> <span data-ttu-id="6290d-133">数据库所有者始终拥有对视图的访问权限，并且不能添加到视图中或从视图中删除。”</span><span class="sxs-lookup"><span data-stu-id="6290d-133">The Database owner always has access to the view and cannot be added to or removed from the view."</span></span>  
>   
>  <span data-ttu-id="6290d-134">此外，你可能会看到来自 NotificationServices #19001 的事件中的警告。</span><span class="sxs-lookup"><span data-stu-id="6290d-134">In addition, you may see a warning in the event from NotificationServices #19001.</span></span>  
>   
>  <span data-ttu-id="6290d-135">如果执行命令期间没有报告任何错误，你可以放心地忽略这些注意事项。</span><span class="sxs-lookup"><span data-stu-id="6290d-135">If no errors were reported during the execution of the command, you can safely disregard these notices.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6290d-136">如果使用 BAM 配置文件不包含警报部分中，执行安装程序数据库命令，并且你已配置 BAM 警报，bm.exe 将覆盖配置，以便警报将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="6290d-136">If you execute a setup-database command, using a BAM configuration file that does not contain an alerts section, and you have already configured BAM Alerts, bm.exe will overwrite the configuration such that alerts will no longer function.</span></span>  
  
 <span data-ttu-id="6290d-137">若要设置的 BAM 数据库必须承载 BAMPrimaryImport、 BAMStarSchema 和 BAMArchive 数据库的 Microsoft SQL 服务器上具有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="6290d-137">To set up the BAM databases you must have administrator permissions on the Microsoft SQL server hosting the BAMPrimaryImport, BAMStarSchema, and BAMArchive databases.</span></span> <span data-ttu-id="6290d-138">若要设置 SQL Notification Services 数据库，你必须具有管理员权限和是本地管理员组的成员，以及是任何其他附加管理组已配置，如 BTS 管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="6290d-138">To set up SQL Notification Services databases, you must have administrator permissions and be a member of the local administrators group, as well as be a member of any other additional administrative groups that have been configured, such as the BTS Admins group.</span></span>  
  
 <span data-ttu-id="6290d-139">**示例**</span><span class="sxs-lookup"><span data-stu-id="6290d-139">**Examples**</span></span>  
  
```  
bm.exe setup-databases -ConfigFile:BamConfiguration.xml  
bm.exe setup-databases -ConfigFile:cfg.xml -NSUser:domain\user1  
```  
  
## <a name="migrate-sql-command"></a><span data-ttu-id="6290d-140">迁移 sql 命令</span><span class="sxs-lookup"><span data-stu-id="6290d-140">migrate-sql Command</span></span>  
 <span data-ttu-id="6290d-141">**用法**</span><span class="sxs-lookup"><span data-stu-id="6290d-141">**Usage**</span></span>  
  
 <span data-ttu-id="6290d-142">**bm.exe 迁移 sql-从： sql2000-到： sql2008 [-NSUser:\<通知服务用户名\>] [-NSUserPassword:\<通知服务用户密码\>] [-Server:\<服务器\> ][-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="6290d-142">**bm.exe migrate-sql -From:sql2000 -To:sql2008 [ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="6290d-143">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="6290d-143">\- Or -</span></span>  
  
 <span data-ttu-id="6290d-144">**bm.exe 迁移 sql-从： sql2005-到： sql2008 [-NSUser:\<通知服务用户名\>] [-NSUserPassword:\<通知服务用户密码\>] [-Server:\<服务器\> ][-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="6290d-144">**bm.exe migrate-sql -From:sql2005 -To:sql2008 [ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="6290d-145">**参数**</span><span class="sxs-lookup"><span data-stu-id="6290d-145">**Parameters**</span></span>  
  
|<span data-ttu-id="6290d-146">参数</span><span class="sxs-lookup"><span data-stu-id="6290d-146">Parameter</span></span>|<span data-ttu-id="6290d-147">Description</span><span class="sxs-lookup"><span data-stu-id="6290d-147">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6290d-148">从： sql2000</span><span class="sxs-lookup"><span data-stu-id="6290d-148">From: sql2000</span></span>|<span data-ttu-id="6290d-149">指定要从 Microsoft SQL Server 2000 数据库进行转换。</span><span class="sxs-lookup"><span data-stu-id="6290d-149">Specifies that you are converting from a Microsoft SQL Server 2000 database.</span></span>|  
|<span data-ttu-id="6290d-150">到： sql2008</span><span class="sxs-lookup"><span data-stu-id="6290d-150">To:sql2008</span></span>|<span data-ttu-id="6290d-151">指定要将转换为 Microsoft SQL Server 2008 数据库。</span><span class="sxs-lookup"><span data-stu-id="6290d-151">Specifies that you are converting to a Microsoft SQL Server 2008 database.</span></span>|  
|<span data-ttu-id="6290d-152">从： sql2005</span><span class="sxs-lookup"><span data-stu-id="6290d-152">From: sql2005</span></span>|<span data-ttu-id="6290d-153">指定你要从 Microsoft SQL Server 2005 数据库转换。</span><span class="sxs-lookup"><span data-stu-id="6290d-153">Specifies that you are converting from a Microsoft SQL Server 2005 database.</span></span>|  
|<span data-ttu-id="6290d-154">到： sql2008</span><span class="sxs-lookup"><span data-stu-id="6290d-154">To:sql2008</span></span>|<span data-ttu-id="6290d-155">指定要将转换为 Microsoft SQL Server 2008 数据库。</span><span class="sxs-lookup"><span data-stu-id="6290d-155">Specifies that you are converting to a Microsoft SQL Server 2008 database.</span></span>|  
|<span data-ttu-id="6290d-156">NSUser:\<通知服务用户名\></span><span class="sxs-lookup"><span data-stu-id="6290d-156">NSUser:\<notifications service user name\></span></span>|<span data-ttu-id="6290d-157">可选： 通知服务用户有权创建数据库用户 ID。</span><span class="sxs-lookup"><span data-stu-id="6290d-157">Optional: The user ID of a Notifications Services user with permissions to create databases.</span></span>|  
|<span data-ttu-id="6290d-158">NSUserPassword</span><span class="sxs-lookup"><span data-stu-id="6290d-158">NSUserPassword</span></span>|<span data-ttu-id="6290d-159">可选： 指定的通知服务用户的密码。</span><span class="sxs-lookup"><span data-stu-id="6290d-159">Optional: The password for the specified Notifications Services user.</span></span>|  
|<span data-ttu-id="6290d-160">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="6290d-160">Server:\<server\></span></span>|<span data-ttu-id="6290d-161">可选： 转换后的数据库将驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-161">Optional: The name of the server on which the converted database will reside.</span></span> <span data-ttu-id="6290d-162">服务器必须是与承载 Microsoft SQL Server 2008 数据库的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="6290d-162">The server must be in the same domain as the computer hosting the Microsoft SQL Server 2008 database.</span></span> <span data-ttu-id="6290d-163">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-163">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="6290d-164">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="6290d-164">Database:\<database\></span></span>|<span data-ttu-id="6290d-165">可选： 将其命名为的已转换的数据库。</span><span class="sxs-lookup"><span data-stu-id="6290d-165">Optional: Then name of the converted database.</span></span> <span data-ttu-id="6290d-166">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="6290d-166">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="6290d-167">可以从 Microsoft SQL Server 2000 或 Microsoft SQL Server 2005 的 BAM 基础结构迁移到 Microsoft SQL Server 2008。</span><span class="sxs-lookup"><span data-stu-id="6290d-167">Migrates the BAM infrastructure from Microsoft SQL Server 2000 or Microsoft SQL Server 2005 to Microsoft SQL Server 2008.</span></span> <span data-ttu-id="6290d-168">你将数据库服务器和升级 Analysis server 从 Microsoft SQL Server 2000 或 Microsoft SQL Server 2005 到 Microsoft SQL Server 2008 后，请使用此命令。</span><span class="sxs-lookup"><span data-stu-id="6290d-168">Use this command after you upgrade your database server and Analysis server from Microsoft SQL Server 2000 or Microsoft SQL Server 2005 to Microsoft SQL Server 2008.</span></span>  
  
 <span data-ttu-id="6290d-169">如果配置 BAM 警报，则需要的 NSUser 和 NSUserPassword 参数。</span><span class="sxs-lookup"><span data-stu-id="6290d-169">The NSUser and NSUserPassword parameters are required if BAM alerts are configured.</span></span> <span data-ttu-id="6290d-170">如果未在命令行上指定 NSUserPassword，bm.exe 将提示你输入密码。</span><span class="sxs-lookup"><span data-stu-id="6290d-170">If the NSUserPassword is not specified on the command line, bm.exe prompts you for the password.</span></span>  
  
 <span data-ttu-id="6290d-171">若要迁移的 SQL Server Notification Services 数据库，你必须具有管理员权限和是本地管理员组的成员，以及是其他任何其他管理组的已配置，如 BTS 成员管理员组。</span><span class="sxs-lookup"><span data-stu-id="6290d-171">To migrate the SQL Server Notification Services databases, you must have administrator permissions and be a member of the local administrators group, as well as be a member of any other additional administrative groups that have been configured, such as the BTS Admins group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6290d-172">如果你收到错误消息"错误： 无法在计算机上启动服务 NS$ BAMAlerts\<计算机名称\>。</span><span class="sxs-lookup"><span data-stu-id="6290d-172">If you receive the error message "ERROR: Cannot start service NS$BAMAlerts on computer '\<computer name\>'.</span></span> <span data-ttu-id="6290d-173">该服务未及时响应启动请求或控制请求。”，请手动重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="6290d-173">The service did not respond to the start or control request in a timely fashion.", try restarting the service manually.</span></span> <span data-ttu-id="6290d-174">如果在迁移期间，SQL Server 是极其繁忙，服务可能无法重新启动。</span><span class="sxs-lookup"><span data-stu-id="6290d-174">If the SQL Server is extremely busy during a migration, the service may not restart.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6290d-175">Notification Services 的安装位置在计算机上运行迁移 sql 命令，你必须属于该计算机上的本地管理员组。</span><span class="sxs-lookup"><span data-stu-id="6290d-175">To run the migrate-sql command on the computer where Notification Services is installed, you must belong to the Local Administrators group on that computer.</span></span>  
  
 <span data-ttu-id="6290d-176">**示例**</span><span class="sxs-lookup"><span data-stu-id="6290d-176">**Examples**</span></span>  
  
```  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
```  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
## <a name="enable-reference-command"></a><span data-ttu-id="6290d-177">启用引用命令</span><span class="sxs-lookup"><span data-stu-id="6290d-177">enable-reference Command</span></span>  
 <span data-ttu-id="6290d-178">**用法**</span><span class="sxs-lookup"><span data-stu-id="6290d-178">**Usage**</span></span>  
  
 <span data-ttu-id="6290d-179">**bm.exe 启用引用 TargetServer:\<目标服务器\>-TargetDatabase:\<目标数据库\>[-Server:\<服务器\>] [-数据库：\<数据库\> ]**</span><span class="sxs-lookup"><span data-stu-id="6290d-179">**bm.exe enable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="6290d-180">**参数**</span><span class="sxs-lookup"><span data-stu-id="6290d-180">**Parameters**</span></span>  
  
|<span data-ttu-id="6290d-181">参数</span><span class="sxs-lookup"><span data-stu-id="6290d-181">Parameter</span></span>|<span data-ttu-id="6290d-182">Description</span><span class="sxs-lookup"><span data-stu-id="6290d-182">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6290d-183">TargetServer:\<目标服务器\></span><span class="sxs-lookup"><span data-stu-id="6290d-183">TargetServer:\<target server\></span></span>|<span data-ttu-id="6290d-184">引用已启用到服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-184">The name of the server to which the reference is enabled.</span></span> <span data-ttu-id="6290d-185">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="6290d-185">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="6290d-186">TargetDatabase:\<目标数据库\></span><span class="sxs-lookup"><span data-stu-id="6290d-186">TargetDatabase:\<target database\></span></span>|<span data-ttu-id="6290d-187">引用已启用到数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-187">The name of the database to which the reference is enabled.</span></span>|  
|<span data-ttu-id="6290d-188">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="6290d-188">Server:\<server\></span></span>|<span data-ttu-id="6290d-189">可选： 将具有启用的引用的目标服务器和数据库服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-189">Optional: The name of the server which will have a reference enabled to the target server and database.</span></span> <span data-ttu-id="6290d-190">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-190">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="6290d-191">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="6290d-191">Database:\<database\></span></span>|<span data-ttu-id="6290d-192">可选： 将具有对目标服务器和数据库启用的引用的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-192">Optional: The name of the database which will have a reference enabled to the target server and database.</span></span> <span data-ttu-id="6290d-193">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="6290d-193">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="6290d-194">启用对其他分布式 BAM 主导入数据库的引用。</span><span class="sxs-lookup"><span data-stu-id="6290d-194">Enables a reference to another distributed BAM Primary Import database.</span></span> <span data-ttu-id="6290d-195">这样可从当前数据库订阅目标 BAM 主导入数据库上的视图和活动元数据。</span><span class="sxs-lookup"><span data-stu-id="6290d-195">This allows subscriptions from the current database to the view and activity metadata on the target BAM Primary Import database.</span></span> <span data-ttu-id="6290d-196">此功能可用于启用对分布式活动的导航。</span><span class="sxs-lookup"><span data-stu-id="6290d-196">You use this to enable navigation of the distributed activities.</span></span>  
  
 <span data-ttu-id="6290d-197">可以指定目标服务器为一个 SQL Server 实例，例如“mymachine2\myinstance”。</span><span class="sxs-lookup"><span data-stu-id="6290d-197">You can specify the target server as an instance of SQL Server, for example, 'mymachine2\myinstance'.</span></span>  
  
 <span data-ttu-id="6290d-198">**示例**</span><span class="sxs-lookup"><span data-stu-id="6290d-198">**Examples**</span></span>  
  
```  
bm.exe enable-reference -TargetServer:MySrv -TargetDatabase:BamPrimaryImport  
bm.exe enable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="get-references-command"></a><span data-ttu-id="6290d-199">get-references 命令</span><span class="sxs-lookup"><span data-stu-id="6290d-199">get-references Command</span></span>  
 <span data-ttu-id="6290d-200">**用法**</span><span class="sxs-lookup"><span data-stu-id="6290d-200">**Usage**</span></span>  
  
 <span data-ttu-id="6290d-201">**bm.exe get 引用 [-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="6290d-201">**bm.exe get-references [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="6290d-202">**参数**</span><span class="sxs-lookup"><span data-stu-id="6290d-202">**Parameters**</span></span>  
  
|<span data-ttu-id="6290d-203">参数</span><span class="sxs-lookup"><span data-stu-id="6290d-203">Parameter</span></span>|<span data-ttu-id="6290d-204">Description</span><span class="sxs-lookup"><span data-stu-id="6290d-204">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6290d-205">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="6290d-205">Server:\<server\></span></span>|<span data-ttu-id="6290d-206">可选： 若要获取的引用列表的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-206">Optional: The name of the server on which to get a list of references.</span></span> <span data-ttu-id="6290d-207">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="6290d-207">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="6290d-208">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-208">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="6290d-209">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="6290d-209">Database:\<database\></span></span>|<span data-ttu-id="6290d-210">可选： 用于获取的引用列表上的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-210">Optional: The name of the database on which to get a list of references.</span></span> <span data-ttu-id="6290d-211">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="6290d-211">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="6290d-212">列出执行此命令的计算机上所启用的引用。</span><span class="sxs-lookup"><span data-stu-id="6290d-212">Lists the references enabled on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="6290d-213">**示例**</span><span class="sxs-lookup"><span data-stu-id="6290d-213">**Examples**</span></span>  
  
```  
bm.exe get-references  
bm.exe get-references -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="disable-reference-command"></a><span data-ttu-id="6290d-214">disable-reference 命令</span><span class="sxs-lookup"><span data-stu-id="6290d-214">disable-reference Command</span></span>  
 <span data-ttu-id="6290d-215">**用法**</span><span class="sxs-lookup"><span data-stu-id="6290d-215">**Usage**</span></span>  
  
 <span data-ttu-id="6290d-216">**bm.exe 禁用引用 TargetServer:\<目标服务器\>-TargetDatabase:\<目标数据库\>[-Server:\<服务器\>] [-数据库：\<数据库\> ]**</span><span class="sxs-lookup"><span data-stu-id="6290d-216">**bm.exe disable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="6290d-217">**参数**</span><span class="sxs-lookup"><span data-stu-id="6290d-217">**Parameters**</span></span>  
  
|<span data-ttu-id="6290d-218">参数</span><span class="sxs-lookup"><span data-stu-id="6290d-218">Parameter</span></span>|<span data-ttu-id="6290d-219">Description</span><span class="sxs-lookup"><span data-stu-id="6290d-219">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6290d-220">TargetServer:\<目标服务器\></span><span class="sxs-lookup"><span data-stu-id="6290d-220">TargetServer:\<target server\></span></span>|<span data-ttu-id="6290d-221">要禁用引用的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-221">The name of the server on which to disable the references.</span></span> <span data-ttu-id="6290d-222">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="6290d-222">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="6290d-223">TargetDatabase:\<目标数据库\></span><span class="sxs-lookup"><span data-stu-id="6290d-223">TargetDatabase:\<target database\></span></span>|<span data-ttu-id="6290d-224">要禁用引用的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-224">The name of the database on which to disable the references.</span></span>|  
|<span data-ttu-id="6290d-225">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="6290d-225">Server:\<server\></span></span>|<span data-ttu-id="6290d-226">可选： 哪些引用到目标服务器和数据库位于要禁用服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-226">Optional: The name of the server on which references to the target server and database are to be disabled.</span></span> <span data-ttu-id="6290d-227">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="6290d-227">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="6290d-228">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="6290d-228">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="6290d-229">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="6290d-229">Database:\<database\></span></span>|<span data-ttu-id="6290d-230">可选： 将哪些引用到目标服务器上的数据库和数据库的名称要禁用。</span><span class="sxs-lookup"><span data-stu-id="6290d-230">Optional: The name of the database on which references to the target server and database are to be disabled.</span></span> <span data-ttu-id="6290d-231">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="6290d-231">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="6290d-232">禁用对目标服务器上其他分布式 BAM 主导入数据库的引用。</span><span class="sxs-lookup"><span data-stu-id="6290d-232">Disables a reference to another distributed BAM Primary Import database on the target server.</span></span>  
  
 <span data-ttu-id="6290d-233">可以指定目标服务器为一个 SQL Server 实例，例如“mymachine2\myinstance”。</span><span class="sxs-lookup"><span data-stu-id="6290d-233">You can specify the target server as an instance of SQL Server, for example, 'mymachine2\myinstance'.</span></span>  
  
 <span data-ttu-id="6290d-234">**示例**</span><span class="sxs-lookup"><span data-stu-id="6290d-234">**Examples**</span></span>  
  
```  
bm.exe disable-reference -TargetServer:MySrv -TargetDatabase:BamPI  
bm.exe disable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="see-also"></a><span data-ttu-id="6290d-235">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6290d-235">See Also</span></span>  
 [<span data-ttu-id="6290d-236">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="6290d-236">BAM Management Utility</span></span>](../core/bam-management-utility.md)
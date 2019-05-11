---
title: 数据库命令 |Microsoft Docs
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
ms.openlocfilehash: e5bb9d25db876fb7d48900b1ee47f187544a4b87
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389775"
---
# <a name="database-commands"></a><span data-ttu-id="c0f61-102">数据库命令</span><span class="sxs-lookup"><span data-stu-id="c0f61-102">Database Commands</span></span>
<span data-ttu-id="c0f61-103">BAM 管理实用程序的数据库命令使您能够使用 BAM 数据库：</span><span class="sxs-lookup"><span data-stu-id="c0f61-103">The BAM Management utility database commands allow you to work with the BAM databases:</span></span>  
  
-   <span data-ttu-id="c0f61-104">安装程序数据库：创建特定于 BAM 的数据库。</span><span class="sxs-lookup"><span data-stu-id="c0f61-104">setup-databases: Creates the BAM-specific databases.</span></span>  
  
-   <span data-ttu-id="c0f61-105">migrate-sql:可以迁移从 BAM 数据库：</span><span class="sxs-lookup"><span data-stu-id="c0f61-105">migrate-sql: Migrates your BAM databases from:</span></span>  
  
    -   <span data-ttu-id="c0f61-106">与 Microsoft SQL Server 2008 的 Microsoft SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="c0f61-106">Microsoft SQL Server 2000 to Microsoft SQL Server 2008</span></span>  
  
    -   <span data-ttu-id="c0f61-107">与 Microsoft SQL Server 2008 的 Microsoft SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="c0f61-107">Microsoft SQL Server 2005 to Microsoft SQL Server 2008</span></span>  
  
-   <span data-ttu-id="c0f61-108">启用的引用：启用对分布式 BAM 主导入数据库的引用。</span><span class="sxs-lookup"><span data-stu-id="c0f61-108">enable-reference: Enables a reference to a distributed BAM Primary Import database.</span></span>  
  
-   <span data-ttu-id="c0f61-109">获取引用：获取对分布式 BAM 主导入数据库的引用的列表。</span><span class="sxs-lookup"><span data-stu-id="c0f61-109">get-references: Gets a list of references to distributed BAM Primary Import databases.</span></span>  
  
-   <span data-ttu-id="c0f61-110">禁用参考：禁用对 BAM 主导入数据库的引用。</span><span class="sxs-lookup"><span data-stu-id="c0f61-110">disable-reference: Disables a reference to a BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0f61-111">通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。</span><span class="sxs-lookup"><span data-stu-id="c0f61-111">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="c0f61-112">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="c0f61-112">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="c0f61-113">此开关可以与所有标准 BM 命令结合使用。</span><span class="sxs-lookup"><span data-stu-id="c0f61-113">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0f61-114">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="c0f61-114">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="setup-databases-command"></a><span data-ttu-id="c0f61-115">设置数据库命令</span><span class="sxs-lookup"><span data-stu-id="c0f61-115">setup-databases Command</span></span>  
 <span data-ttu-id="c0f61-116">**Usage**</span><span class="sxs-lookup"><span data-stu-id="c0f61-116">**Usage**</span></span>  
  
 <span data-ttu-id="c0f61-117">**bm.exe 设置-数据库-ConfigFile:\<配置文件\>[-NSUser:\<通知服务用户名\>] [-NSUserPassword:\<通知服务用户密码\>]**</span><span class="sxs-lookup"><span data-stu-id="c0f61-117">**bm.exe setup-databases-ConfigFile:\<configuration file\>[ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ]**</span></span>  
  
 <span data-ttu-id="c0f61-118">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="c0f61-118">**Parameters**</span></span>  
  
|<span data-ttu-id="c0f61-119">参数</span><span class="sxs-lookup"><span data-stu-id="c0f61-119">Parameter</span></span>|<span data-ttu-id="c0f61-120">Description</span><span class="sxs-lookup"><span data-stu-id="c0f61-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0f61-121">ConfigFile:\<配置文件\></span><span class="sxs-lookup"><span data-stu-id="c0f61-121">ConfigFile:\<configuration file\></span></span>|<span data-ttu-id="c0f61-122">从其创建数据库的 BAM 配置文件。</span><span class="sxs-lookup"><span data-stu-id="c0f61-122">The BAM configuration file from which to create the database.</span></span>|  
|<span data-ttu-id="c0f61-123">NSUser:\<通知服务用户名\></span><span class="sxs-lookup"><span data-stu-id="c0f61-123">NSUser:\<notifications service user name\></span></span>|<span data-ttu-id="c0f61-124">可选：通知服务用户有权创建数据库用户 ID。</span><span class="sxs-lookup"><span data-stu-id="c0f61-124">Optional: The user ID of a notifications services user with permissions to create databases.</span></span>|  
|<span data-ttu-id="c0f61-125">NSUserPassword</span><span class="sxs-lookup"><span data-stu-id="c0f61-125">NSUserPassword</span></span>|<span data-ttu-id="c0f61-126">可选：指定的通知服务用户的密码。</span><span class="sxs-lookup"><span data-stu-id="c0f61-126">Optional: The password for the specified notifications services user.</span></span>|  
  
 <span data-ttu-id="c0f61-127">创建配置文件 （BAM 主导入、 BAM 星型架构、 BAM 存档、 BAM 分析和警报） 中所述如果它们尚不存在的数据库。</span><span class="sxs-lookup"><span data-stu-id="c0f61-127">Creates the databases described in the configuration file (BAM Primary Import, BAM Star Schema, BAM Archive, BAM Analysis, and alerts) if they do not already exist.</span></span> <span data-ttu-id="c0f61-128">一旦创建了数据库，该命令将创建关联的 BAM 元数据表和存储的过程。</span><span class="sxs-lookup"><span data-stu-id="c0f61-128">Once the databases are created, the command creates the associated BAM metadata tables and stored procedures.</span></span>  
  
 <span data-ttu-id="c0f61-129">如果您设置了 BAM 警报，则需要 NSUser 和 NSUserPassword 参数。</span><span class="sxs-lookup"><span data-stu-id="c0f61-129">The NSUser and NSUserPassword parameters are required if you are setting up BAM alerts.</span></span> <span data-ttu-id="c0f61-130">如果 NSUserPassword 未指定命令行上，则 bm.exe 会提示您输入密码。</span><span class="sxs-lookup"><span data-stu-id="c0f61-130">If the NSUserPassword is not specified on the command line, bm.exe prompts you for the password.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0f61-131">之后该命令完成时，你可能注意到从跟踪日志中 AlertModule 异常：</span><span class="sxs-lookup"><span data-stu-id="c0f61-131">After the completion of the command, you may note an exception from the AlertModule in the trace log:</span></span>  
>   
>  <span data-ttu-id="c0f61-132">"指定的帐户是数据库所有者。</span><span class="sxs-lookup"><span data-stu-id="c0f61-132">"The specified account is the Database Owner.</span></span> <span data-ttu-id="c0f61-133">数据库所有者始终有权访问视图并不能添加到或从视图中删除。"</span><span class="sxs-lookup"><span data-stu-id="c0f61-133">The Database owner always has access to the view and cannot be added to or removed from the view."</span></span>  
>   
>  <span data-ttu-id="c0f61-134">此外，可能会看到从 NotificationServices #19001 事件中的警告。</span><span class="sxs-lookup"><span data-stu-id="c0f61-134">In addition, you may see a warning in the event from NotificationServices #19001.</span></span>  
>   
>  <span data-ttu-id="c0f61-135">如果该命令执行期间未不报告任何错误，可以安全地忽略这些声明。</span><span class="sxs-lookup"><span data-stu-id="c0f61-135">If no errors were reported during the execution of the command, you can safely disregard these notices.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c0f61-136">如果使用的 BAM 配置文件不包含警报部分，执行安装程序数据库命令，并且已配置了 BAM 警报，bm.exe 将覆盖配置，以便警报将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="c0f61-136">If you execute a setup-database command, using a BAM configuration file that does not contain an alerts section, and you have already configured BAM Alerts, bm.exe will overwrite the configuration such that alerts will no longer function.</span></span>  
  
 <span data-ttu-id="c0f61-137">若要设置 BAM 数据库必须在承载 BAMPrimaryImport、 BAMStarSchema 和 BAMArchive 数据库的 Microsoft SQL server 上具有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="c0f61-137">To set up the BAM databases you must have administrator permissions on the Microsoft SQL server hosting the BAMPrimaryImport, BAMStarSchema, and BAMArchive databases.</span></span> <span data-ttu-id="c0f61-138">若要设置 SQL Notification Services 数据库，您必须具有管理员权限并且是本地管理员组的成员，以及是任何其他的其他管理组的已配置，如 BTS Admins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="c0f61-138">To set up SQL Notification Services databases, you must have administrator permissions and be a member of the local administrators group, as well as be a member of any other additional administrative groups that have been configured, such as the BTS Admins group.</span></span>  
  
 <span data-ttu-id="c0f61-139">**示例**</span><span class="sxs-lookup"><span data-stu-id="c0f61-139">**Examples**</span></span>  
  
```  
bm.exe setup-databases -ConfigFile:BamConfiguration.xml  
bm.exe setup-databases -ConfigFile:cfg.xml -NSUser:domain\user1  
```  
  
## <a name="migrate-sql-command"></a><span data-ttu-id="c0f61-140">迁移 sql 命令</span><span class="sxs-lookup"><span data-stu-id="c0f61-140">migrate-sql Command</span></span>  
 <span data-ttu-id="c0f61-141">**Usage**</span><span class="sxs-lookup"><span data-stu-id="c0f61-141">**Usage**</span></span>  
  
 <span data-ttu-id="c0f61-142">**bm.exe-从： sql2000-到： sql2008 [-NSUser:\<通知服务用户名\>] [-NSUserPassword:\<通知服务用户密码\>] [-Server:\<server\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="c0f61-142">**bm.exe migrate-sql -From:sql2000 -To:sql2008 [ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c0f61-143">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="c0f61-143">\- Or -</span></span>  
  
 <span data-ttu-id="c0f61-144">**bm.exe-从： sql2005-到： sql2008 [-NSUser:\<通知服务用户名\>] [-NSUserPassword:\<通知服务用户密码\>] [-Server:\<server\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="c0f61-144">**bm.exe migrate-sql -From:sql2005 -To:sql2008 [ -NSUser:\<notifications service user name\> ][ -NSUserPassword:\<notifications service user password\> ][ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c0f61-145">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="c0f61-145">**Parameters**</span></span>  
  
|<span data-ttu-id="c0f61-146">参数</span><span class="sxs-lookup"><span data-stu-id="c0f61-146">Parameter</span></span>|<span data-ttu-id="c0f61-147">Description</span><span class="sxs-lookup"><span data-stu-id="c0f61-147">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0f61-148">从： sql2000</span><span class="sxs-lookup"><span data-stu-id="c0f61-148">From: sql2000</span></span>|<span data-ttu-id="c0f61-149">指定要将从 Microsoft SQL Server 2000 数据库转换。</span><span class="sxs-lookup"><span data-stu-id="c0f61-149">Specifies that you are converting from a Microsoft SQL Server 2000 database.</span></span>|  
|<span data-ttu-id="c0f61-150">到： sql2008</span><span class="sxs-lookup"><span data-stu-id="c0f61-150">To:sql2008</span></span>|<span data-ttu-id="c0f61-151">指定要将转换为 Microsoft SQL Server 2008 数据库。</span><span class="sxs-lookup"><span data-stu-id="c0f61-151">Specifies that you are converting to a Microsoft SQL Server 2008 database.</span></span>|  
|<span data-ttu-id="c0f61-152">从： sql2005</span><span class="sxs-lookup"><span data-stu-id="c0f61-152">From: sql2005</span></span>|<span data-ttu-id="c0f61-153">指定要将从 Microsoft SQL Server 2005 数据库转换。</span><span class="sxs-lookup"><span data-stu-id="c0f61-153">Specifies that you are converting from a Microsoft SQL Server 2005 database.</span></span>|  
|<span data-ttu-id="c0f61-154">到： sql2008</span><span class="sxs-lookup"><span data-stu-id="c0f61-154">To:sql2008</span></span>|<span data-ttu-id="c0f61-155">指定要将转换为 Microsoft SQL Server 2008 数据库。</span><span class="sxs-lookup"><span data-stu-id="c0f61-155">Specifies that you are converting to a Microsoft SQL Server 2008 database.</span></span>|  
|<span data-ttu-id="c0f61-156">NSUser:\<通知服务用户名\></span><span class="sxs-lookup"><span data-stu-id="c0f61-156">NSUser:\<notifications service user name\></span></span>|<span data-ttu-id="c0f61-157">可选：通知服务用户有权创建数据库用户 ID。</span><span class="sxs-lookup"><span data-stu-id="c0f61-157">Optional: The user ID of a Notifications Services user with permissions to create databases.</span></span>|  
|<span data-ttu-id="c0f61-158">NSUserPassword</span><span class="sxs-lookup"><span data-stu-id="c0f61-158">NSUserPassword</span></span>|<span data-ttu-id="c0f61-159">可选：指定通知服务用户的密码。</span><span class="sxs-lookup"><span data-stu-id="c0f61-159">Optional: The password for the specified Notifications Services user.</span></span>|  
|<span data-ttu-id="c0f61-160">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="c0f61-160">Server:\<server\></span></span>|<span data-ttu-id="c0f61-161">可选：转换后的数据库将驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="c0f61-161">Optional: The name of the server on which the converted database will reside.</span></span> <span data-ttu-id="c0f61-162">服务器必须与承载 Microsoft SQL Server 2008 数据库的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="c0f61-162">The server must be in the same domain as the computer hosting the Microsoft SQL Server 2008 database.</span></span> <span data-ttu-id="c0f61-163">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="c0f61-163">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c0f61-164">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="c0f61-164">Database:\<database\></span></span>|<span data-ttu-id="c0f61-165">可选：然后转换后的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="c0f61-165">Optional: Then name of the converted database.</span></span> <span data-ttu-id="c0f61-166">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="c0f61-166">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c0f61-167">将从 Microsoft SQL Server 2000 或 Microsoft SQL Server 2005 的 BAM 基础结构迁移到 Microsoft SQL Server 2008。</span><span class="sxs-lookup"><span data-stu-id="c0f61-167">Migrates the BAM infrastructure from Microsoft SQL Server 2000 or Microsoft SQL Server 2005 to Microsoft SQL Server 2008.</span></span> <span data-ttu-id="c0f61-168">在升级后将数据库服务器和分析服务器从 Microsoft SQL Server 2000 或 Microsoft SQL Server 2005 为 Microsoft SQL Server 2008，请使用此命令。</span><span class="sxs-lookup"><span data-stu-id="c0f61-168">Use this command after you upgrade your database server and Analysis server from Microsoft SQL Server 2000 or Microsoft SQL Server 2005 to Microsoft SQL Server 2008.</span></span>  
  
 <span data-ttu-id="c0f61-169">如果配置 BAM 警报，则需要 NSUser 和 NSUserPassword 参数。</span><span class="sxs-lookup"><span data-stu-id="c0f61-169">The NSUser and NSUserPassword parameters are required if BAM alerts are configured.</span></span> <span data-ttu-id="c0f61-170">如果 NSUserPassword 未指定命令行上，则 bm.exe 会提示您输入密码。</span><span class="sxs-lookup"><span data-stu-id="c0f61-170">If the NSUserPassword is not specified on the command line, bm.exe prompts you for the password.</span></span>  
  
 <span data-ttu-id="c0f61-171">若要迁移的 SQL Server Notification Services 数据库，您必须具有管理员权限是本地管理员组的成员，以及是任何其他的其他管理组的已配置，如 BTS 的成员管理员组。</span><span class="sxs-lookup"><span data-stu-id="c0f61-171">To migrate the SQL Server Notification Services databases, you must have administrator permissions and be a member of the local administrators group, as well as be a member of any other additional administrative groups that have been configured, such as the BTS Admins group.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0f61-172">如果收到错误消息"错误：无法在计算机上启动服务 NS$ BAMAlerts\<计算机名\>。</span><span class="sxs-lookup"><span data-stu-id="c0f61-172">If you receive the error message "ERROR: Cannot start service NS$BAMAlerts on computer '\<computer name\>'.</span></span> <span data-ttu-id="c0f61-173">该服务未响应及时的方式。 在启动或控制请求"，请尝试手动重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="c0f61-173">The service did not respond to the start or control request in a timely fashion.", try restarting the service manually.</span></span> <span data-ttu-id="c0f61-174">如果在迁移期间，SQL Server 是极其繁忙，则可能无法重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="c0f61-174">If the SQL Server is extremely busy during a migration, the service may not restart.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0f61-175">若要安装 Notification Services 的计算机上运行迁移 sql 命令，你必须属于该计算机上的本地管理员组。</span><span class="sxs-lookup"><span data-stu-id="c0f61-175">To run the migrate-sql command on the computer where Notification Services is installed, you must belong to the Local Administrators group on that computer.</span></span>  
  
 <span data-ttu-id="c0f61-176">**示例**</span><span class="sxs-lookup"><span data-stu-id="c0f61-176">**Examples**</span></span>  
  
```  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2000 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
```  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -NSUser:domain\user1  
bm.exe migrate-sql -From:sql2005 -To:sql2008 -Server:MyServer -Database:db1  
```  
  
## <a name="enable-reference-command"></a><span data-ttu-id="c0f61-177">启用 reference 命令</span><span class="sxs-lookup"><span data-stu-id="c0f61-177">enable-reference Command</span></span>  
 <span data-ttu-id="c0f61-178">**Usage**</span><span class="sxs-lookup"><span data-stu-id="c0f61-178">**Usage**</span></span>  
  
 <span data-ttu-id="c0f61-179">**bm.exe enable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="c0f61-179">**bm.exe enable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c0f61-180">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="c0f61-180">**Parameters**</span></span>  
  
|<span data-ttu-id="c0f61-181">参数</span><span class="sxs-lookup"><span data-stu-id="c0f61-181">Parameter</span></span>|<span data-ttu-id="c0f61-182">Description</span><span class="sxs-lookup"><span data-stu-id="c0f61-182">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0f61-183">TargetServer:\<目标服务器\></span><span class="sxs-lookup"><span data-stu-id="c0f61-183">TargetServer:\<target server\></span></span>|<span data-ttu-id="c0f61-184">为其启用引用的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="c0f61-184">The name of the server to which the reference is enabled.</span></span> <span data-ttu-id="c0f61-185">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="c0f61-185">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="c0f61-186">TargetDatabase:\<目标数据库\></span><span class="sxs-lookup"><span data-stu-id="c0f61-186">TargetDatabase:\<target database\></span></span>|<span data-ttu-id="c0f61-187">为其启用引用的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="c0f61-187">The name of the database to which the reference is enabled.</span></span>|  
|<span data-ttu-id="c0f61-188">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="c0f61-188">Server:\<server\></span></span>|<span data-ttu-id="c0f61-189">可选：这会启用对目标服务器和数据库的引用的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="c0f61-189">Optional: The name of the server which will have a reference enabled to the target server and database.</span></span> <span data-ttu-id="c0f61-190">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="c0f61-190">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c0f61-191">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="c0f61-191">Database:\<database\></span></span>|<span data-ttu-id="c0f61-192">可选：这会启用对目标服务器和数据库的引用的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="c0f61-192">Optional: The name of the database which will have a reference enabled to the target server and database.</span></span> <span data-ttu-id="c0f61-193">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="c0f61-193">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c0f61-194">启用对另一个分布式 BAM 主导入数据库的引用。</span><span class="sxs-lookup"><span data-stu-id="c0f61-194">Enables a reference to another distributed BAM Primary Import database.</span></span> <span data-ttu-id="c0f61-195">这允许对视图和活动元数据从当前数据库订阅目标 BAM 主导入数据库上。</span><span class="sxs-lookup"><span data-stu-id="c0f61-195">This allows subscriptions from the current database to the view and activity metadata on the target BAM Primary Import database.</span></span> <span data-ttu-id="c0f61-196">此位置用于启用分布式活动导航。</span><span class="sxs-lookup"><span data-stu-id="c0f61-196">You use this to enable navigation of the distributed activities.</span></span>  
  
 <span data-ttu-id="c0f61-197">您可以指定目标服务器为 SQL Server，例如，mymachine2\myinstance 的实例。</span><span class="sxs-lookup"><span data-stu-id="c0f61-197">You can specify the target server as an instance of SQL Server, for example, 'mymachine2\myinstance'.</span></span>  
  
 <span data-ttu-id="c0f61-198">**示例**</span><span class="sxs-lookup"><span data-stu-id="c0f61-198">**Examples**</span></span>  
  
```  
bm.exe enable-reference -TargetServer:MySrv -TargetDatabase:BamPrimaryImport  
bm.exe enable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="get-references-command"></a><span data-ttu-id="c0f61-199">get-references 命令</span><span class="sxs-lookup"><span data-stu-id="c0f61-199">get-references Command</span></span>  
 <span data-ttu-id="c0f61-200">**Usage**</span><span class="sxs-lookup"><span data-stu-id="c0f61-200">**Usage**</span></span>  
  
 <span data-ttu-id="c0f61-201">**bm.exe get-references [ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="c0f61-201">**bm.exe get-references [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c0f61-202">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="c0f61-202">**Parameters**</span></span>  
  
|<span data-ttu-id="c0f61-203">参数</span><span class="sxs-lookup"><span data-stu-id="c0f61-203">Parameter</span></span>|<span data-ttu-id="c0f61-204">Description</span><span class="sxs-lookup"><span data-stu-id="c0f61-204">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0f61-205">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="c0f61-205">Server:\<server\></span></span>|<span data-ttu-id="c0f61-206">可选：若要获取的引用列表的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="c0f61-206">Optional: The name of the server on which to get a list of references.</span></span> <span data-ttu-id="c0f61-207">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="c0f61-207">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c0f61-208">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="c0f61-208">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c0f61-209">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="c0f61-209">Database:\<database\></span></span>|<span data-ttu-id="c0f61-210">可选：要获取的引用列表的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="c0f61-210">Optional: The name of the database on which to get a list of references.</span></span> <span data-ttu-id="c0f61-211">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="c0f61-211">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c0f61-212">列出对其执行该命令在计算机上启用的引用。</span><span class="sxs-lookup"><span data-stu-id="c0f61-212">Lists the references enabled on the computer on which the command is executed.</span></span>  
  
 <span data-ttu-id="c0f61-213">**示例**</span><span class="sxs-lookup"><span data-stu-id="c0f61-213">**Examples**</span></span>  
  
```  
bm.exe get-references  
bm.exe get-references -Server:MyServer -Database:MyPrimaryImport  
```  
  
## <a name="disable-reference-command"></a><span data-ttu-id="c0f61-214">disable-reference 命令</span><span class="sxs-lookup"><span data-stu-id="c0f61-214">disable-reference Command</span></span>  
 <span data-ttu-id="c0f61-215">**Usage**</span><span class="sxs-lookup"><span data-stu-id="c0f61-215">**Usage**</span></span>  
  
 <span data-ttu-id="c0f61-216">**bm.exe disable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="c0f61-216">**bm.exe disable-reference -TargetServer:\<target server\> -TargetDatabase:\<target database\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="c0f61-217">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="c0f61-217">**Parameters**</span></span>  
  
|<span data-ttu-id="c0f61-218">参数</span><span class="sxs-lookup"><span data-stu-id="c0f61-218">Parameter</span></span>|<span data-ttu-id="c0f61-219">Description</span><span class="sxs-lookup"><span data-stu-id="c0f61-219">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0f61-220">TargetServer:\<目标服务器\></span><span class="sxs-lookup"><span data-stu-id="c0f61-220">TargetServer:\<target server\></span></span>|<span data-ttu-id="c0f61-221">若要禁用引用的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="c0f61-221">The name of the server on which to disable the references.</span></span> <span data-ttu-id="c0f61-222">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="c0f61-222">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="c0f61-223">TargetDatabase:\<目标数据库\></span><span class="sxs-lookup"><span data-stu-id="c0f61-223">TargetDatabase:\<target database\></span></span>|<span data-ttu-id="c0f61-224">要禁用引用的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="c0f61-224">The name of the database on which to disable the references.</span></span>|  
|<span data-ttu-id="c0f61-225">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="c0f61-225">Server:\<server\></span></span>|<span data-ttu-id="c0f61-226">可选：哪些引用到目标服务器和数据库要禁用的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="c0f61-226">Optional: The name of the server on which references to the target server and database are to be disabled.</span></span> <span data-ttu-id="c0f61-227">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="c0f61-227">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="c0f61-228">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="c0f61-228">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="c0f61-229">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="c0f61-229">Database:\<database\></span></span>|<span data-ttu-id="c0f61-230">可选：要禁用的哪些引用到目标服务器上的数据库和数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="c0f61-230">Optional: The name of the database on which references to the target server and database are to be disabled.</span></span> <span data-ttu-id="c0f61-231">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="c0f61-231">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="c0f61-232">禁用对目标服务器上的其他分布式 BAM 主导入数据库的引用。</span><span class="sxs-lookup"><span data-stu-id="c0f61-232">Disables a reference to another distributed BAM Primary Import database on the target server.</span></span>  
  
 <span data-ttu-id="c0f61-233">您可以指定目标服务器为 SQL Server，例如，mymachine2\myinstance 的实例。</span><span class="sxs-lookup"><span data-stu-id="c0f61-233">You can specify the target server as an instance of SQL Server, for example, 'mymachine2\myinstance'.</span></span>  
  
 <span data-ttu-id="c0f61-234">**示例**</span><span class="sxs-lookup"><span data-stu-id="c0f61-234">**Examples**</span></span>  
  
```  
bm.exe disable-reference -TargetServer:MySrv -TargetDatabase:BamPI  
bm.exe disable-reference -TargetServer:s2 -TargetDatabase:db1 -Server:s1  
```  
  
## <a name="see-also"></a><span data-ttu-id="c0f61-235">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0f61-235">See Also</span></span>  
 [<span data-ttu-id="c0f61-236">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="c0f61-236">BAM Management Utility</span></span>](../core/bam-management-utility.md)
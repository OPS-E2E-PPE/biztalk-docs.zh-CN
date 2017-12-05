---
title: "基础结构管理命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2f1a88c-19fc-4384-b6bb-f95962a32921
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c82dc5cb65156af86e66abfeffef206f18add5cb
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="infrastructure-management-commands"></a><span data-ttu-id="0a7f3-102">基础结构管理命令</span><span class="sxs-lookup"><span data-stu-id="0a7f3-102">Infrastructure Management Commands</span></span>
<span data-ttu-id="0a7f3-103">通过 BAM 管理 (BM) 实用程序命令，可以获取和更新 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-103">The BAM Management (BM) utility configuration commands allow you get and update the BAM configuration.</span></span>  
  
-   <span data-ttu-id="0a7f3-104">get-config： 获取 BAM 配置文件。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-104">get-config: Gets the BAM configuration file.</span></span>  
  
-   <span data-ttu-id="0a7f3-105">更新-config： 更新 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-105">update-config: Updates the BAM configuration.</span></span>  
  
-   <span data-ttu-id="0a7f3-106">获取变更： 列出对 BAM 基础结构的更改。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-106">get-changes: Lists changes to the BAM infrastructure.</span></span>  
  
-   <span data-ttu-id="0a7f3-107">get defxml： 获取包含 BAM 主导入数据库中的所有项目的文件。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-107">get-defxml: Gets a file containing all the artifacts in the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a7f3-108">你可以通过包括启用任何 BM 实用工具命令的跟踪**-跟踪： 在 &#124; 关闭**参数交换机。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="0a7f3-109">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="0a7f3-110">该开关可与所有标准 BM 命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a7f3-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-config-command"></a><span data-ttu-id="0a7f3-112">get-config 命令</span><span class="sxs-lookup"><span data-stu-id="0a7f3-112">get-config Command</span></span>  
 <span data-ttu-id="0a7f3-113">**用法**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-113">**Usage**</span></span>  
  
 <span data-ttu-id="0a7f3-114">**bm.exe get-config FileName:\<输出文件\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-114">**bm.exe get-config -FileName:\<output file\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="0a7f3-115">**参数**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-115">**Parameters**</span></span>  
  
|<span data-ttu-id="0a7f3-116">参数</span><span class="sxs-lookup"><span data-stu-id="0a7f3-116">Parameter</span></span>|<span data-ttu-id="0a7f3-117">Description</span><span class="sxs-lookup"><span data-stu-id="0a7f3-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a7f3-118">文件名：\<输出文件\></span><span class="sxs-lookup"><span data-stu-id="0a7f3-118">FileName:\<output file\></span></span>|<span data-ttu-id="0a7f3-119">保存配置的文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-119">The path and name to which to save the configuration file.</span></span>|  
|<span data-ttu-id="0a7f3-120">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="0a7f3-120">Server:\<server\></span></span>|<span data-ttu-id="0a7f3-121">可选： 从其获取配置服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-121">Optional: The name of the server from which to get the configuration.</span></span> <span data-ttu-id="0a7f3-122">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="0a7f3-123">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="0a7f3-124">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="0a7f3-124">Database:\<database\></span></span>|<span data-ttu-id="0a7f3-125">可选： 若要获取的配置的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-125">Optional: The name of the database from which to get the configuration.</span></span> <span data-ttu-id="0a7f3-126">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="0a7f3-127">检索 BAM 配置 XML，并将其保存到指定的文件中。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-127">Retrieves the BAM configuration XML and saves it in the specified file.</span></span> <span data-ttu-id="0a7f3-128">**Get-config**命令将不会覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-128">The **get-config** command will not overwrite the existing file.</span></span>  
  
 <span data-ttu-id="0a7f3-129">**示例**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-129">**Examples**</span></span>  
  
```  
bm.exe get-config -FileName:MyConfig.xml  
bm.exe get-config -FileName:BAMConfiguration.xml -Server:OrdersServer  
```  
  
## <a name="update-config-command"></a><span data-ttu-id="0a7f3-130">update-config 命令</span><span class="sxs-lookup"><span data-stu-id="0a7f3-130">update-config Command</span></span>  
 <span data-ttu-id="0a7f3-131">**用法**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-131">**Usage**</span></span>  
  
 <span data-ttu-id="0a7f3-132">**bm.exe 更新-config FileName:\<配置文件\>**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-132">**bm.exe update-config -FileName:\<config file\>**</span></span>  
  
 <span data-ttu-id="0a7f3-133">**参数**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-133">**Parameters**</span></span>  
  
|<span data-ttu-id="0a7f3-134">参数</span><span class="sxs-lookup"><span data-stu-id="0a7f3-134">Parameter</span></span>|<span data-ttu-id="0a7f3-135">Description</span><span class="sxs-lookup"><span data-stu-id="0a7f3-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a7f3-136">文件名：\<配置文件\></span><span class="sxs-lookup"><span data-stu-id="0a7f3-136">FileName:\<config file\></span></span>|<span data-ttu-id="0a7f3-137">更新 BAM 基础结构所用配置文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-137">The path and name of the configuration file from which to update the BAM infrastructure.</span></span>|  
  
 <span data-ttu-id="0a7f3-138">更新本地计算机上包含 BAM 配置 XML 文件中的配置。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-138">Updates the configuration on the local computer from a file containing BAM configuration XML.</span></span> <span data-ttu-id="0a7f3-139">可以添加当前配置中尚不存在的服务器名和数据库名。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-139">You can add server and database names that do not already exist in the current configuration.</span></span> <span data-ttu-id="0a7f3-140">如果已在服务器或数据库中部署了动态基础结构，则更改服务器名或数据库名将失败，并且 bm.exe 会报告错误。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-140">Changing server or database names that already have dynamic infrastructure deployed in will fail and bm.exe will report an error.</span></span>  
  
 <span data-ttu-id="0a7f3-141">如果修改了送达的警报的文件存放位置，</span><span class="sxs-lookup"><span data-stu-id="0a7f3-141">If you modify the file drop location for alerts delivered by file.</span></span> <span data-ttu-id="0a7f3-142">则必须重新启动 SQL Notification Services。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-142">You must restart the SQL Notifications Services.</span></span> <span data-ttu-id="0a7f3-143">如果没有重新启动 NS 服务，则警报将继续传送到原始的文件存放位置。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-143">If the NS service is not restarted, alerts will continue being delivered to the original file drop location.</span></span>  
  
 <span data-ttu-id="0a7f3-144">修改 BAM 配置文件的以下行，可以更改文件存放位置。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-144">The file drop location is changed by modifying the following line of the BAM configuration file.</span></span>  
  
 <span data-ttu-id="0a7f3-145">\<属性名称 ="FileDropUNC"\>\\\\< 计算机名\>\alerts\</Property\></span><span class="sxs-lookup"><span data-stu-id="0a7f3-145">\<Property Name="FileDropUNC"\>\\\\<computer name\>\alerts\</Property\></span></span>  
  
 <span data-ttu-id="0a7f3-146">适当的步骤来更新的引用，请参阅[备份和还原 BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-146">For appropriate steps to update the references, see [Backing Up and Restoring BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0a7f3-147">如果执行 update-database 命令时使用不包含警报部分的 BAM 配置文件，但是已经配置了 BAM 警报，则 bm.exe 将覆盖该配置，因而这些警报就不再起作用。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-147">If you execute an update-database command, using a BAM configuration file that does not contain an alerts section, and you have already configured BAM Alerts, bm.exe will overwrite the configuration such that alerts will no longer function.</span></span>  
  
 <span data-ttu-id="0a7f3-148">**示例**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-148">**Examples**</span></span>  
  
```  
bm.exe update-config -FileName:MyConfig.xml  
```  
  
## <a name="get-changes-command"></a><span data-ttu-id="0a7f3-149">get-changes 命令</span><span class="sxs-lookup"><span data-stu-id="0a7f3-149">get-changes Command</span></span>  
 <span data-ttu-id="0a7f3-150">**用法**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-150">**Usage**</span></span>  
  
 <span data-ttu-id="0a7f3-151">**bm.exe 获取变更 [-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-151">**bm.exe get-changes [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="0a7f3-152">**参数**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-152">**Parameters**</span></span>  
  
|<span data-ttu-id="0a7f3-153">参数</span><span class="sxs-lookup"><span data-stu-id="0a7f3-153">Parameter</span></span>|<span data-ttu-id="0a7f3-154">Description</span><span class="sxs-lookup"><span data-stu-id="0a7f3-154">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a7f3-155">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="0a7f3-155">Server:\<server\></span></span>|<span data-ttu-id="0a7f3-156">可选： BAM 主导入数据库所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-156">Optional: The name of the server on which the BAM Primary Import database resides.</span></span> <span data-ttu-id="0a7f3-157">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-157">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="0a7f3-158">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-158">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="0a7f3-159">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="0a7f3-159">Database:\<database\></span></span>|<span data-ttu-id="0a7f3-160">可选： 如果未指定的名称，bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-160">Optional: If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="0a7f3-161">获取应用于 BAM 主导入数据库的一系列更改。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-161">Gets a list of changes applied to the BAM Primary Import database.</span></span> <span data-ttu-id="0a7f3-162">使用此命令可以审核对 BAM 基础结构所做的更改。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-162">You can use this command to audit changes to the BAM Infrastructure.</span></span> <span data-ttu-id="0a7f3-163">该命令将返回以下信息：</span><span class="sxs-lookup"><span data-stu-id="0a7f3-163">The command returns the following information:</span></span>  
  
 <span data-ttu-id="0a7f3-164">更改的命令类型以及应用更改所依据的文件。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-164">The command type of the change and the file from which the change was applied.</span></span>  
  
 <span data-ttu-id="0a7f3-165">谁应用了更改。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-165">Who applied the change.</span></span>  
  
 <span data-ttu-id="0a7f3-166">更改了哪些活动。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-166">Which activities were changed.</span></span>  
  
 <span data-ttu-id="0a7f3-167">更改了哪些视图。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-167">Which views were changed.</span></span>  
  
 <span data-ttu-id="0a7f3-168">**示例**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-168">**Examples**</span></span>  
  
```  
bm.exe get-changes  
```  
  
 <span data-ttu-id="0a7f3-169">命令输出</span><span class="sxs-lookup"><span data-stu-id="0a7f3-169">Output of command</span></span>  
  
 <span data-ttu-id="0a7f3-170">\#1： 部署 c:\bam\ordermanagement.xml</span><span class="sxs-lookup"><span data-stu-id="0a7f3-170">\#1: Deploy c:\bam\ordermanagement.xml</span></span>  
  
 <span data-ttu-id="0a7f3-171">By domain\user at 12/30/2005 8:17:08 PM (v3.5.1536.0).</span><span class="sxs-lookup"><span data-stu-id="0a7f3-171">By domain\user at 12/30/2005 8:17:08 PM (v3.5.1536.0).</span></span>  
  
 <span data-ttu-id="0a7f3-172">活动： OrderMgmt</span><span class="sxs-lookup"><span data-stu-id="0a7f3-172">Activities: OrderMgmt</span></span>  
  
 <span data-ttu-id="0a7f3-173">视图： SalesManager</span><span class="sxs-lookup"><span data-stu-id="0a7f3-173">Views: SalesManager</span></span>  
  
## <a name="get-defxml-command"></a><span data-ttu-id="0a7f3-174">get-defxml 命令</span><span class="sxs-lookup"><span data-stu-id="0a7f3-174">get-defxml Command</span></span>  
 <span data-ttu-id="0a7f3-175">**用法**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-175">**Usage**</span></span>  
  
 <span data-ttu-id="0a7f3-176">**bm.exe get defxml FileName:\<输出文件\>[-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-176">**bm.exe get-defxml -FileName:\<output file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="0a7f3-177">**参数**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-177">**Parameters**</span></span>  
  
|<span data-ttu-id="0a7f3-178">参数</span><span class="sxs-lookup"><span data-stu-id="0a7f3-178">Parameter</span></span>|<span data-ttu-id="0a7f3-179">Description</span><span class="sxs-lookup"><span data-stu-id="0a7f3-179">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a7f3-180">文件名：\<输出文件\></span><span class="sxs-lookup"><span data-stu-id="0a7f3-180">FileName:\<output file\></span></span>|<span data-ttu-id="0a7f3-181">保存定义的文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-181">The path and name of the file to which to save the definitions.</span></span>|  
|<span data-ttu-id="0a7f3-182">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="0a7f3-182">Server:\<server\></span></span>|<span data-ttu-id="0a7f3-183">可选： 从其获取定义服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-183">Optional: The name of the server from which to get the definitions.</span></span> <span data-ttu-id="0a7f3-184">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-184">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="0a7f3-185">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-185">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="0a7f3-186">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="0a7f3-186">Database:\<database\></span></span>|<span data-ttu-id="0a7f3-187">可选： 从其获取定义数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-187">Optional: The name of the database from which to get the definitions.</span></span> <span data-ttu-id="0a7f3-188">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-188">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="0a7f3-189">从 BAM 主导入数据库检索所有项目，并将这些项目保存到一个 XML 格式的文件中。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-189">Retrieves all artifacts on from the BAM Primary Import database and saves them in a file as XML.</span></span> <span data-ttu-id="0a7f3-190">此命令不会覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="0a7f3-190">The command will not overwrite existing files.</span></span>  
  
 <span data-ttu-id="0a7f3-191">**示例**</span><span class="sxs-lookup"><span data-stu-id="0a7f3-191">**Examples**</span></span>  
  
```  
bm.exe get-defxml -FileName:BAMDefinition.xml  
bm.exe get-defxml -FileName:MyDef.xml -Server:MyServer -Database:MyPI  
```  
  
## <a name="see-also"></a><span data-ttu-id="0a7f3-192">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a7f3-192">See Also</span></span>  
 [<span data-ttu-id="0a7f3-193">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="0a7f3-193">BAM Management Utility</span></span>](../core/bam-management-utility.md)
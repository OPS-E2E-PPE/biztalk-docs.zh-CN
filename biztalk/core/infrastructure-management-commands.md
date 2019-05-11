---
title: 基础结构管理命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f1a88c-19fc-4384-b6bb-f95962a32921
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a75743ae6f6b65bcab0afa42dd5536e8bfbf1c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382195"
---
# <a name="infrastructure-management-commands"></a><span data-ttu-id="aba29-102">基础结构管理命令</span><span class="sxs-lookup"><span data-stu-id="aba29-102">Infrastructure Management Commands</span></span>
<span data-ttu-id="aba29-103">BAM 管理 (BM) 实用程序命令，可以获取和更新 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="aba29-103">The BAM Management (BM) utility configuration commands allow you get and update the BAM configuration.</span></span>  
  
-   <span data-ttu-id="aba29-104">获取配置：获取 BAM 配置文件。</span><span class="sxs-lookup"><span data-stu-id="aba29-104">get-config: Gets the BAM configuration file.</span></span>  
  
-   <span data-ttu-id="aba29-105">更新配置：更新 BAM 配置。</span><span class="sxs-lookup"><span data-stu-id="aba29-105">update-config: Updates the BAM configuration.</span></span>  
  
-   <span data-ttu-id="aba29-106">get-更改：列出对 BAM 基础结构的更改。</span><span class="sxs-lookup"><span data-stu-id="aba29-106">get-changes: Lists changes to the BAM infrastructure.</span></span>  
  
-   <span data-ttu-id="aba29-107">get-defxml:获取包含 BAM 主导入数据库中的所有项目的文件。</span><span class="sxs-lookup"><span data-stu-id="aba29-107">get-defxml: Gets a file containing all the artifacts in the BAM Primary Import database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aba29-108">通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。</span><span class="sxs-lookup"><span data-stu-id="aba29-108">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="aba29-109">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="aba29-109">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="aba29-110">此开关可以与所有标准 BM 命令结合使用。</span><span class="sxs-lookup"><span data-stu-id="aba29-110">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aba29-111">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="aba29-111">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="get-config-command"></a><span data-ttu-id="aba29-112">get-config 命令</span><span class="sxs-lookup"><span data-stu-id="aba29-112">get-config Command</span></span>  
 <span data-ttu-id="aba29-113">**Usage**</span><span class="sxs-lookup"><span data-stu-id="aba29-113">**Usage**</span></span>  
  
 <span data-ttu-id="aba29-114">**bm.exe get-config -FileName:\<output file\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="aba29-114">**bm.exe get-config -FileName:\<output file\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="aba29-115">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="aba29-115">**Parameters**</span></span>  
  
|<span data-ttu-id="aba29-116">参数</span><span class="sxs-lookup"><span data-stu-id="aba29-116">Parameter</span></span>|<span data-ttu-id="aba29-117">Description</span><span class="sxs-lookup"><span data-stu-id="aba29-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aba29-118">文件名：\<输出文件\></span><span class="sxs-lookup"><span data-stu-id="aba29-118">FileName:\<output file\></span></span>|<span data-ttu-id="aba29-119">路径和要保存配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="aba29-119">The path and name to which to save the configuration file.</span></span>|  
|<span data-ttu-id="aba29-120">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="aba29-120">Server:\<server\></span></span>|<span data-ttu-id="aba29-121">可选：从中获取配置服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="aba29-121">Optional: The name of the server from which to get the configuration.</span></span> <span data-ttu-id="aba29-122">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="aba29-122">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="aba29-123">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="aba29-123">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="aba29-124">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="aba29-124">Database:\<database\></span></span>|<span data-ttu-id="aba29-125">可选：从中获取配置数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="aba29-125">Optional: The name of the database from which to get the configuration.</span></span> <span data-ttu-id="aba29-126">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="aba29-126">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="aba29-127">检索 BAM 配置 XML 并将其保存在指定的文件。</span><span class="sxs-lookup"><span data-stu-id="aba29-127">Retrieves the BAM configuration XML and saves it in the specified file.</span></span> <span data-ttu-id="aba29-128">**获取配置**命令不会覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="aba29-128">The **get-config** command will not overwrite the existing file.</span></span>  
  
 <span data-ttu-id="aba29-129">**示例**</span><span class="sxs-lookup"><span data-stu-id="aba29-129">**Examples**</span></span>  
  
```  
bm.exe get-config -FileName:MyConfig.xml  
bm.exe get-config -FileName:BAMConfiguration.xml -Server:OrdersServer  
```  
  
## <a name="update-config-command"></a><span data-ttu-id="aba29-130">update-config 命令</span><span class="sxs-lookup"><span data-stu-id="aba29-130">update-config Command</span></span>  
 <span data-ttu-id="aba29-131">**Usage**</span><span class="sxs-lookup"><span data-stu-id="aba29-131">**Usage**</span></span>  
  
 <span data-ttu-id="aba29-132">**bm.exe 更新-config-FileName:\<配置文件\>**</span><span class="sxs-lookup"><span data-stu-id="aba29-132">**bm.exe update-config -FileName:\<config file\>**</span></span>  
  
 <span data-ttu-id="aba29-133">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="aba29-133">**Parameters**</span></span>  
  
|<span data-ttu-id="aba29-134">参数</span><span class="sxs-lookup"><span data-stu-id="aba29-134">Parameter</span></span>|<span data-ttu-id="aba29-135">Description</span><span class="sxs-lookup"><span data-stu-id="aba29-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aba29-136">文件名：\<配置文件\></span><span class="sxs-lookup"><span data-stu-id="aba29-136">FileName:\<config file\></span></span>|<span data-ttu-id="aba29-137">路径和从其更新 BAM 基础结构的配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="aba29-137">The path and name of the configuration file from which to update the BAM infrastructure.</span></span>|  
  
 <span data-ttu-id="aba29-138">更新包含 BAM 配置 XML 的文件从本地计算机上的配置。</span><span class="sxs-lookup"><span data-stu-id="aba29-138">Updates the configuration on the local computer from a file containing BAM configuration XML.</span></span> <span data-ttu-id="aba29-139">可以在当前配置中添加服务器和数据库名称尚不存在。</span><span class="sxs-lookup"><span data-stu-id="aba29-139">You can add server and database names that do not already exist in the current configuration.</span></span> <span data-ttu-id="aba29-140">更改服务器或已动态基础结构中部署的数据库名称将会失败，并且 bm.exe 会报告错误。</span><span class="sxs-lookup"><span data-stu-id="aba29-140">Changing server or database names that already have dynamic infrastructure deployed in will fail and bm.exe will report an error.</span></span>  
  
 <span data-ttu-id="aba29-141">如果修改了送达的警报的文件的文件存放位置。</span><span class="sxs-lookup"><span data-stu-id="aba29-141">If you modify the file drop location for alerts delivered by file.</span></span> <span data-ttu-id="aba29-142">必须重新启动 SQL Notification Services。</span><span class="sxs-lookup"><span data-stu-id="aba29-142">You must restart the SQL Notifications Services.</span></span> <span data-ttu-id="aba29-143">如果不重新启动 NS 服务，警报将继续传送到原始文件存放位置。</span><span class="sxs-lookup"><span data-stu-id="aba29-143">If the NS service is not restarted, alerts will continue being delivered to the original file drop location.</span></span>  
  
 <span data-ttu-id="aba29-144">通过修改 BAM 配置文件的以下行可以更改文件存放位置。</span><span class="sxs-lookup"><span data-stu-id="aba29-144">The file drop location is changed by modifying the following line of the BAM configuration file.</span></span>  
  
 <span data-ttu-id="aba29-145">\<属性名称 ="FileDropUNC"\>\\\\< 计算机名\>\alerts\</Property\></span><span class="sxs-lookup"><span data-stu-id="aba29-145">\<Property Name="FileDropUNC"\>\\\\<computer name\>\alerts\</Property\></span></span>  
  
 <span data-ttu-id="aba29-146">若要更新的引用的适当步骤，请参阅[备份和还原 BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="aba29-146">For appropriate steps to update the references, see [Backing Up and Restoring BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aba29-147">如果执行更新数据库命令，使用 BAM 配置文件不包含警报部分，并且已配置了 BAM 警报，bm.exe 将覆盖配置，以便警报将不再起作用。</span><span class="sxs-lookup"><span data-stu-id="aba29-147">If you execute an update-database command, using a BAM configuration file that does not contain an alerts section, and you have already configured BAM Alerts, bm.exe will overwrite the configuration such that alerts will no longer function.</span></span>  
  
 <span data-ttu-id="aba29-148">**示例**</span><span class="sxs-lookup"><span data-stu-id="aba29-148">**Examples**</span></span>  
  
```  
bm.exe update-config -FileName:MyConfig.xml  
```  
  
## <a name="get-changes-command"></a><span data-ttu-id="aba29-149">get-changes 命令</span><span class="sxs-lookup"><span data-stu-id="aba29-149">get-changes Command</span></span>  
 <span data-ttu-id="aba29-150">**Usage**</span><span class="sxs-lookup"><span data-stu-id="aba29-150">**Usage**</span></span>  
  
 <span data-ttu-id="aba29-151">**bm.exe get-changes [ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="aba29-151">**bm.exe get-changes [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="aba29-152">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="aba29-152">**Parameters**</span></span>  
  
|<span data-ttu-id="aba29-153">参数</span><span class="sxs-lookup"><span data-stu-id="aba29-153">Parameter</span></span>|<span data-ttu-id="aba29-154">Description</span><span class="sxs-lookup"><span data-stu-id="aba29-154">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aba29-155">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="aba29-155">Server:\<server\></span></span>|<span data-ttu-id="aba29-156">可选：BAM 主导入数据库所在的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="aba29-156">Optional: The name of the server on which the BAM Primary Import database resides.</span></span> <span data-ttu-id="aba29-157">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="aba29-157">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="aba29-158">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="aba29-158">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="aba29-159">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="aba29-159">Database:\<database\></span></span>|<span data-ttu-id="aba29-160">可选：如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="aba29-160">Optional: If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="aba29-161">获取更改应用到 BAM 主导入数据库的列表。</span><span class="sxs-lookup"><span data-stu-id="aba29-161">Gets a list of changes applied to the BAM Primary Import database.</span></span> <span data-ttu-id="aba29-162">此命令可用于审核对 BAM 基础结构的更改。</span><span class="sxs-lookup"><span data-stu-id="aba29-162">You can use this command to audit changes to the BAM Infrastructure.</span></span> <span data-ttu-id="aba29-163">该命令返回以下信息：</span><span class="sxs-lookup"><span data-stu-id="aba29-163">The command returns the following information:</span></span>  
  
 <span data-ttu-id="aba29-164">更改和从其应用更改的文件的命令类型。</span><span class="sxs-lookup"><span data-stu-id="aba29-164">The command type of the change and the file from which the change was applied.</span></span>  
  
 <span data-ttu-id="aba29-165">谁应用了更改。</span><span class="sxs-lookup"><span data-stu-id="aba29-165">Who applied the change.</span></span>  
  
 <span data-ttu-id="aba29-166">更改了哪些活动。</span><span class="sxs-lookup"><span data-stu-id="aba29-166">Which activities were changed.</span></span>  
  
 <span data-ttu-id="aba29-167">更改了哪些视图。</span><span class="sxs-lookup"><span data-stu-id="aba29-167">Which views were changed.</span></span>  
  
 <span data-ttu-id="aba29-168">**示例**</span><span class="sxs-lookup"><span data-stu-id="aba29-168">**Examples**</span></span>  
  
```  
bm.exe get-changes  
```  
  
 <span data-ttu-id="aba29-169">命令的输出</span><span class="sxs-lookup"><span data-stu-id="aba29-169">Output of command</span></span>  
  
 <span data-ttu-id="aba29-170">\#1:部署 c:\bam\ordermanagement.xml</span><span class="sxs-lookup"><span data-stu-id="aba29-170">\#1: Deploy c:\bam\ordermanagement.xml</span></span>  
  
 <span data-ttu-id="aba29-171">通过在 2005 年 12 月 30 日的域 \ 用户 8:17:08 PM (v3.5.1536.0)。</span><span class="sxs-lookup"><span data-stu-id="aba29-171">By domain\user at 12/30/2005 8:17:08 PM (v3.5.1536.0).</span></span>  
  
 <span data-ttu-id="aba29-172">活动：OrderMgmt</span><span class="sxs-lookup"><span data-stu-id="aba29-172">Activities: OrderMgmt</span></span>  
  
 <span data-ttu-id="aba29-173">Views:SalesManager</span><span class="sxs-lookup"><span data-stu-id="aba29-173">Views: SalesManager</span></span>  
  
## <a name="get-defxml-command"></a><span data-ttu-id="aba29-174">get-defxml 命令</span><span class="sxs-lookup"><span data-stu-id="aba29-174">get-defxml Command</span></span>  
 <span data-ttu-id="aba29-175">**Usage**</span><span class="sxs-lookup"><span data-stu-id="aba29-175">**Usage**</span></span>  
  
 <span data-ttu-id="aba29-176">**bm.exe get-defxml -FileName:\<output file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="aba29-176">**bm.exe get-defxml -FileName:\<output file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="aba29-177">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="aba29-177">**Parameters**</span></span>  
  
|<span data-ttu-id="aba29-178">参数</span><span class="sxs-lookup"><span data-stu-id="aba29-178">Parameter</span></span>|<span data-ttu-id="aba29-179">Description</span><span class="sxs-lookup"><span data-stu-id="aba29-179">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aba29-180">文件名：\<输出文件\></span><span class="sxs-lookup"><span data-stu-id="aba29-180">FileName:\<output file\></span></span>|<span data-ttu-id="aba29-181">路径和要将定义保存到文件的名称。</span><span class="sxs-lookup"><span data-stu-id="aba29-181">The path and name of the file to which to save the definitions.</span></span>|  
|<span data-ttu-id="aba29-182">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="aba29-182">Server:\<server\></span></span>|<span data-ttu-id="aba29-183">可选：从中获取定义服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="aba29-183">Optional: The name of the server from which to get the definitions.</span></span> <span data-ttu-id="aba29-184">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="aba29-184">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="aba29-185">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="aba29-185">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="aba29-186">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="aba29-186">Database:\<database\></span></span>|<span data-ttu-id="aba29-187">可选：从中获取定义的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="aba29-187">Optional: The name of the database from which to get the definitions.</span></span> <span data-ttu-id="aba29-188">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="aba29-188">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="aba29-189">从 BAM 主导入数据库上检索所有项目，并将其保存为 XML 文件中。</span><span class="sxs-lookup"><span data-stu-id="aba29-189">Retrieves all artifacts on from the BAM Primary Import database and saves them in a file as XML.</span></span> <span data-ttu-id="aba29-190">该命令不会覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="aba29-190">The command will not overwrite existing files.</span></span>  
  
 <span data-ttu-id="aba29-191">**示例**</span><span class="sxs-lookup"><span data-stu-id="aba29-191">**Examples**</span></span>  
  
```  
bm.exe get-defxml -FileName:BAMDefinition.xml  
bm.exe get-defxml -FileName:MyDef.xml -Server:MyServer -Database:MyPI  
```  
  
## <a name="see-also"></a><span data-ttu-id="aba29-192">请参阅</span><span class="sxs-lookup"><span data-stu-id="aba29-192">See Also</span></span>  
 [<span data-ttu-id="aba29-193">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="aba29-193">BAM Management Utility</span></span>](../core/bam-management-utility.md)
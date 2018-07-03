---
title: 侦听器管理命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2be6460-1f81-4bc3-a831-34ff24d65d34
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aefeefc7010c4cefca323782dac5a1349479a07d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023163"
---
# <a name="interceptor-management-commands"></a><span data-ttu-id="46875-102">侦听器管理命令</span><span class="sxs-lookup"><span data-stu-id="46875-102">Interceptor Management Commands</span></span>
<span data-ttu-id="46875-103">为了支持新的 BAM 侦听器功能，在 BAM 管理实用程序中添加了四个新命令。</span><span class="sxs-lookup"><span data-stu-id="46875-103">To support the new BAM interceptor functionality, four new commands have been added to the BAM Management utility.</span></span>  
  
 <span data-ttu-id="46875-104">这些命令支持侦听器的部署、检索和删除。</span><span class="sxs-lookup"><span data-stu-id="46875-104">These commands support the deployment, retrieval, and removal of interceptors.</span></span> <span data-ttu-id="46875-105">还提供了一个命令用于列出已配置的侦听器。</span><span class="sxs-lookup"><span data-stu-id="46875-105">A command is also provided to list the configured interceptors.</span></span>  
  
-   <span data-ttu-id="46875-106">部署侦听器： 部署侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="46875-106">deploy-interceptor: Deploys an interceptor configuration.</span></span>  
  
-   <span data-ttu-id="46875-107">get interceptorlist： 获取一系列活动在其部署拦截。</span><span class="sxs-lookup"><span data-stu-id="46875-107">get-interceptorlist: Gets a list of activities on which interception is deployed.</span></span>  
  
-   <span data-ttu-id="46875-108">获取侦听器： 获取侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="46875-108">get-interceptor: Gets the interceptor configuration.</span></span>  
  
-   <span data-ttu-id="46875-109">删除侦听器： 侦听器配置中删除。</span><span class="sxs-lookup"><span data-stu-id="46875-109">remove-interceptor: Removes an interceptor configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46875-110">通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。</span><span class="sxs-lookup"><span data-stu-id="46875-110">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="46875-111">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="46875-111">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="46875-112">该开关可与所有标准 BM 命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="46875-112">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46875-113">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="46875-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="deploy-interceptor-command"></a><span data-ttu-id="46875-114">deploy-interceptor 命令</span><span class="sxs-lookup"><span data-stu-id="46875-114">deploy-interceptor Command</span></span>  
 <span data-ttu-id="46875-115">**Usage**</span><span class="sxs-lookup"><span data-stu-id="46875-115">**Usage**</span></span>  
  
 <span data-ttu-id="46875-116">**bm.exe 部署侦听器-FileName:\<配置 XML 文件名\>[-Force: True] [-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="46875-116">**bm.exe deploy-interceptor -FileName:\<Configuration XML Filename\> [-Force:True ] [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="46875-117">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="46875-117">**Parameters**</span></span>  
  
|<span data-ttu-id="46875-118">参数</span><span class="sxs-lookup"><span data-stu-id="46875-118">Parameter</span></span>|<span data-ttu-id="46875-119">Description</span><span class="sxs-lookup"><span data-stu-id="46875-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46875-120">文件名：\<配置 XML 文件名\></span><span class="sxs-lookup"><span data-stu-id="46875-120">FileName:\<Configuration XML Filename\></span></span>|<span data-ttu-id="46875-121">包含侦听器配置的 XML 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="46875-121">The name of the XML file containing the interceptor configuration.</span></span>|  
|<span data-ttu-id="46875-122">Force:True</span><span class="sxs-lookup"><span data-stu-id="46875-122">Force:True</span></span>|<span data-ttu-id="46875-123">可选： 在检测到事件源名称冲突时强制部署侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="46875-123">Optional: Forces deployment of the interceptor configuration when event source name collisions are detected.</span></span>|  
|<span data-ttu-id="46875-124">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="46875-124">Server:\<server\></span></span>|<span data-ttu-id="46875-125">可选： 若要部署侦听器的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="46875-125">Optional: The name of the server on which to deploy the interceptor.</span></span> <span data-ttu-id="46875-126">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="46875-126">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="46875-127">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="46875-127">Database:\<database\></span></span>|<span data-ttu-id="46875-128">可选： 要对其配置侦听器的 BAM 主导入数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="46875-128">Optional: The name of the BAM Primary Import database on which to configure the interceptor.</span></span>|  
  
 <span data-ttu-id="46875-129">此命令将侦听器配置部署到指定的服务器和数据库。</span><span class="sxs-lookup"><span data-stu-id="46875-129">This command deploys the interceptor configuration to the specified server and database.</span></span> <span data-ttu-id="46875-130">在部署期间，BAM 管理实用程序执行以下验证：</span><span class="sxs-lookup"><span data-stu-id="46875-130">During deployment, the BAM Management utility performs the following validations:</span></span>  
  
- <span data-ttu-id="46875-131">XSD 验证： 根据公用侦听器配置架构进行验证的侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="46875-131">XSD validation: The interceptor configuration is validated against the common interceptor configuration schema.</span></span>  
  
- <span data-ttu-id="46875-132">验证活动存在（部署在主导入数据库中）且检查点有效（存在并具有匹配的数据类型）。</span><span class="sxs-lookup"><span data-stu-id="46875-132">Validation that the activity exists (is deployed in the Primary Import database) and that checkpoints are valid (exist and have a matching data type).</span></span>  
  
  <span data-ttu-id="46875-133">如果在事件源名称中检测到冲突，则发出描述冲突的警告。</span><span class="sxs-lookup"><span data-stu-id="46875-133">If a collision is detected in the event source name, a warning is thrown describing the collision.</span></span> <span data-ttu-id="46875-134">对于冲突时，部署将失败，除非 **– Force: True**参数标志。</span><span class="sxs-lookup"><span data-stu-id="46875-134">In the case of a collision, the deployment will fail unless the **–Force:True** parameter flag is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46875-135">**– Force: True**参数可潜在删除引用同名事件源的侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="46875-135">The **–Force:True** parameter potentially removes interceptor configurations that reference event sources with the same name.</span></span> <span data-ttu-id="46875-136">应使用**get 侦听器**命令，以使用之前创建的现有侦听器配置备份 **– Force: True**参数。</span><span class="sxs-lookup"><span data-stu-id="46875-136">You should use the **get-interceptor** command to create a backup of existing interceptor configurations before using the **–Force:True** parameter.</span></span>  
  
 <span data-ttu-id="46875-137">**示例**</span><span class="sxs-lookup"><span data-stu-id="46875-137">**Examples**</span></span>  
  
```  
bm.exe deploy-interceptor  -FileName:myInceptor.xml  
bm.exe deploy-interceptor  -FileName:myInceptor.xml -Force:True  
```  
  
## <a name="get-interceptorlist-command"></a><span data-ttu-id="46875-138">get-interceptorlist 命令</span><span class="sxs-lookup"><span data-stu-id="46875-138">get-interceptorlist Command</span></span>  
 <span data-ttu-id="46875-139">**Usage**</span><span class="sxs-lookup"><span data-stu-id="46875-139">**Usage**</span></span>  
  
 <span data-ttu-id="46875-140">**bm.exe get interceptorlist [-Server:\<服务器\>] [-数据库：\<数据库\>]**</span><span class="sxs-lookup"><span data-stu-id="46875-140">**bm.exe get-interceptorlist [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="46875-141">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="46875-141">**Parameters**</span></span>  
  
|<span data-ttu-id="46875-142">参数</span><span class="sxs-lookup"><span data-stu-id="46875-142">Parameter</span></span>|<span data-ttu-id="46875-143">Description</span><span class="sxs-lookup"><span data-stu-id="46875-143">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46875-144">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="46875-144">Server:\<server\></span></span>|<span data-ttu-id="46875-145">可选： 要返回的已部署侦听器列表服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="46875-145">Optional: The name of the server from which to return a list of deployed interceptors.</span></span> <span data-ttu-id="46875-146">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="46875-146">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="46875-147">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="46875-147">Database:\<database\></span></span>|<span data-ttu-id="46875-148">可选： 要从中检索已部署的侦听器的 BAM 主导入数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="46875-148">Optional: The name of the BAM Primary Import database from which to retrieve the deployed interceptors.</span></span>|  
  
 <span data-ttu-id="46875-149">此命令返回活动的列表及为之启用侦听的关联事件源。</span><span class="sxs-lookup"><span data-stu-id="46875-149">This command returns a list of the activities, and their associated event sources, for which interception is enabled.</span></span>  
  
 <span data-ttu-id="46875-150">**示例**</span><span class="sxs-lookup"><span data-stu-id="46875-150">**Example**</span></span>  
  
```  
bm.exe get-interceptorlist   
```  
  
## <a name="get-interceptor-command"></a><span data-ttu-id="46875-151">get-interceptor 命令</span><span class="sxs-lookup"><span data-stu-id="46875-151">get-interceptor Command</span></span>  
 <span data-ttu-id="46875-152">**Usage**</span><span class="sxs-lookup"><span data-stu-id="46875-152">**Usage**</span></span>  
  
 <span data-ttu-id="46875-153">**bm.exe get 侦听器 [-Server:\<服务器\>] [-数据库：\<数据库\>]-FileName:\<配置 XML 文件名\>[-活动：\<活动名称\>][-EventSource:\<事件源名称\>]**</span><span class="sxs-lookup"><span data-stu-id="46875-153">**bm.exe get-interceptor [-Server:\<server\>] [-Database:\<database\>] -FileName: \<Configuration XML Filename\> [ -Activity: \<Activity Name\>] [-EventSource: \<Event Source Name\>]**</span></span>  
  
 <span data-ttu-id="46875-154">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="46875-154">**Parameters**</span></span>  
  
|<span data-ttu-id="46875-155">参数</span><span class="sxs-lookup"><span data-stu-id="46875-155">Parameter</span></span>|<span data-ttu-id="46875-156">Description</span><span class="sxs-lookup"><span data-stu-id="46875-156">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46875-157">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="46875-157">Server:\<server\></span></span>|<span data-ttu-id="46875-158">可选： 要从中检索已部署的侦听器的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="46875-158">Optional: The name of the server from which to retrieve the deployed interceptor.</span></span> <span data-ttu-id="46875-159">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="46875-159">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="46875-160">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="46875-160">Database:\<database\></span></span>|<span data-ttu-id="46875-161">可选： 要从中检索已部署的侦听器的 BAM 主导入数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="46875-161">Optional: The name of the BAM Primary Import database from which to retrieve deployed interceptor.</span></span>|  
|<span data-ttu-id="46875-162">文件名：\<配置 XML 文件名\></span><span class="sxs-lookup"><span data-stu-id="46875-162">FileName:\<Configuration XML Filename\></span></span>|<span data-ttu-id="46875-163">向其写入侦听器配置的 XML 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="46875-163">The name of the XML file to which to write the interceptor configuration.</span></span>|  
|<span data-ttu-id="46875-164">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="46875-164">Activity:\<Activity Name\></span></span>|<span data-ttu-id="46875-165">可选： 指定要为其返回已配置的侦听器的活动。</span><span class="sxs-lookup"><span data-stu-id="46875-165">Optional: Specifies the activity for which to return the configured interceptor.</span></span> <span data-ttu-id="46875-166">可以结合使用**EventSource**参数以便进一步指定要返回的配置。</span><span class="sxs-lookup"><span data-stu-id="46875-166">Can be used in conjunction with the **EventSource** parameter to further specify the configuration to return.</span></span>|  
|<span data-ttu-id="46875-167">EventSource:\<事件源名称\></span><span class="sxs-lookup"><span data-stu-id="46875-167">EventSource:\<Event Source Name\></span></span>|<span data-ttu-id="46875-168">可选： 指定要为其返回已配置的侦听器的事件源。</span><span class="sxs-lookup"><span data-stu-id="46875-168">Optional: Specifies the event source for which to return the configured interceptor.</span></span> <span data-ttu-id="46875-169">可以结合使用**活动**参数以便进一步指定要返回的配置。</span><span class="sxs-lookup"><span data-stu-id="46875-169">Can be used in conjunction with the **Activity** parameter to further specify the configuration to return.</span></span>|  
  
 <span data-ttu-id="46875-170">如果没有提供活动名称或事件源名称，该命令将为所有事件源和活动返回包含侦听器配置的有效配置文件。</span><span class="sxs-lookup"><span data-stu-id="46875-170">If no activity name or event source name is provided, the command returns a valid configuration file containing the interceptor configurations for all event sources and activities.</span></span>  
  
 <span data-ttu-id="46875-171">如果只提供活动名称，该命令将为该活动的所有事件源返回有效的侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="46875-171">If only an activity name is provided, the command returns a valid interceptor configuration file for all event sources for that activity.</span></span>  
  
 <span data-ttu-id="46875-172">如果只提供事件源名称，该命令将为所有活动中的该事件源返回有效的侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="46875-172">If only an event source name is provided, the command returns a valid interceptor configuration file for that event source across all activities.</span></span>  
  
 <span data-ttu-id="46875-173">如果同时提供了活动名称和事件源名称，则该命令将为该活动的该事件源返回有效的侦听器配置文件。</span><span class="sxs-lookup"><span data-stu-id="46875-173">If both an activity name and an event source name are provided, then the command returns a valid interceptor configuration file for that event source for that activity.</span></span>  
  
 <span data-ttu-id="46875-174">**示例**</span><span class="sxs-lookup"><span data-stu-id="46875-174">**Examples**</span></span>  
  
```  
bm.exe get-interceptor   
bm.exe get-interceptor  -Activity:ShippingPO  
```  
  
## <a name="remove-interceptor-command"></a><span data-ttu-id="46875-175">remove-interceptor 命令</span><span class="sxs-lookup"><span data-stu-id="46875-175">remove-interceptor Command</span></span>  
 <span data-ttu-id="46875-176">**Usage**</span><span class="sxs-lookup"><span data-stu-id="46875-176">**Usage**</span></span>  
  
 <span data-ttu-id="46875-177">**bm.exe 删除侦听器 [-Server:\<服务器\>] [-数据库：\<数据库\>] [-活动：\<活动名称\>] [-EventSource:\<事件源名称\>]**</span><span class="sxs-lookup"><span data-stu-id="46875-177">**bm.exe remove-interceptor [-Server:\<server\>] [-Database:\<database\>] [ -Activity: \<Activity Name\>][-EventSource: \<Event Source Name\>]**</span></span>  
  
 <span data-ttu-id="46875-178">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="46875-178">**Parameters**</span></span>  
  
|<span data-ttu-id="46875-179">参数</span><span class="sxs-lookup"><span data-stu-id="46875-179">Parameter</span></span>|<span data-ttu-id="46875-180">Description</span><span class="sxs-lookup"><span data-stu-id="46875-180">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="46875-181">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="46875-181">Server:\<server\></span></span>|<span data-ttu-id="46875-182">可选： 在其配置侦听器的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="46875-182">Optional: The name of the server on which the interceptor is configured.</span></span> <span data-ttu-id="46875-183">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="46875-183">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="46875-184">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="46875-184">Database:\<database\></span></span>|<span data-ttu-id="46875-185">可选： 在其配置侦听器的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="46875-185">Optional: The name of the database on which the interceptor is configured.</span></span>|  
|<span data-ttu-id="46875-186">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="46875-186">Activity: \<Activity Name\></span></span>|<span data-ttu-id="46875-187">可选： 指定要为其删除指定的侦听器的活动。</span><span class="sxs-lookup"><span data-stu-id="46875-187">Optional: Specifies the activity for which to remove the specified interceptor.</span></span> <span data-ttu-id="46875-188">可以结合使用**EventSource**参数以便进一步指定要返回的配置。</span><span class="sxs-lookup"><span data-stu-id="46875-188">Can be used in conjunction with the **EventSource** parameter to further specify the configuration to return.</span></span>|  
|<span data-ttu-id="46875-189">EventSource:\<事件源名称\></span><span class="sxs-lookup"><span data-stu-id="46875-189">EventSource: \<Event Source Name\></span></span>|<span data-ttu-id="46875-190">可选： 指定要为其删除指定的侦听器的事件源。</span><span class="sxs-lookup"><span data-stu-id="46875-190">Optional: Specifies the event source for which to remove the specified interceptor.</span></span> <span data-ttu-id="46875-191">可以结合使用**活动**参数以便进一步指定要返回的配置。</span><span class="sxs-lookup"><span data-stu-id="46875-191">Can be used in conjunction with the **Activity** parameter to further specify the configuration to return.</span></span>|  
  
 <span data-ttu-id="46875-192">如果只提供活动名称，该命令将为该活动的所有事件源删除侦听器。</span><span class="sxs-lookup"><span data-stu-id="46875-192">If only an activity name is provided, the command removes the interceptor for all event sources for that activity.</span></span>  
  
 <span data-ttu-id="46875-193">如果只提供事件源名称，该命令只删除所有活动的该事件源部分。</span><span class="sxs-lookup"><span data-stu-id="46875-193">If only an event source name is provided, the command removes only that event source portion for all activities.</span></span>  
  
 <span data-ttu-id="46875-194">**示例**</span><span class="sxs-lookup"><span data-stu-id="46875-194">**Example**</span></span>  
  
```  
bm.exe remove-interceptor   
```  
  
## <a name="see-also"></a><span data-ttu-id="46875-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="46875-195">See Also</span></span>  
 [<span data-ttu-id="46875-196">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="46875-196">BAM Management Utility</span></span>](../core/bam-management-utility.md)
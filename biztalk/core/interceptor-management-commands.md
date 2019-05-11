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
ms.openlocfilehash: dbce63f7c5616396dd208460323f6aac98adff99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331723"
---
# <a name="interceptor-management-commands"></a><span data-ttu-id="4f73b-102">侦听器管理命令</span><span class="sxs-lookup"><span data-stu-id="4f73b-102">Interceptor Management Commands</span></span>
<span data-ttu-id="4f73b-103">若要支持的新的 BAM 侦听器功能，具有已四个新命令添加到 BAM 管理实用程序。</span><span class="sxs-lookup"><span data-stu-id="4f73b-103">To support the new BAM interceptor functionality, four new commands have been added to the BAM Management utility.</span></span>  
  
 <span data-ttu-id="4f73b-104">这些命令支持部署、 检索和删除的侦听器。</span><span class="sxs-lookup"><span data-stu-id="4f73b-104">These commands support the deployment, retrieval, and removal of interceptors.</span></span> <span data-ttu-id="4f73b-105">此外提供一个命令来列出已配置的侦听器。</span><span class="sxs-lookup"><span data-stu-id="4f73b-105">A command is also provided to list the configured interceptors.</span></span>  
  
-   <span data-ttu-id="4f73b-106">部署侦听器：部署侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="4f73b-106">deploy-interceptor: Deploys an interceptor configuration.</span></span>  
  
-   <span data-ttu-id="4f73b-107">get-interceptorlist:获取在其部署拦截的活动的列表。</span><span class="sxs-lookup"><span data-stu-id="4f73b-107">get-interceptorlist: Gets a list of activities on which interception is deployed.</span></span>  
  
-   <span data-ttu-id="4f73b-108">get-interceptor:获取侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="4f73b-108">get-interceptor: Gets the interceptor configuration.</span></span>  
  
-   <span data-ttu-id="4f73b-109">删除侦听器：删除侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="4f73b-109">remove-interceptor: Removes an interceptor configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f73b-110">通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。</span><span class="sxs-lookup"><span data-stu-id="4f73b-110">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="4f73b-111">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="4f73b-111">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="4f73b-112">此开关可以与所有标准 BM 命令结合使用。</span><span class="sxs-lookup"><span data-stu-id="4f73b-112">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f73b-113">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="4f73b-113">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="deploy-interceptor-command"></a><span data-ttu-id="4f73b-114">deploy-interceptor 命令</span><span class="sxs-lookup"><span data-stu-id="4f73b-114">deploy-interceptor Command</span></span>  
 <span data-ttu-id="4f73b-115">**Usage**</span><span class="sxs-lookup"><span data-stu-id="4f73b-115">**Usage**</span></span>  
  
 <span data-ttu-id="4f73b-116">**bm.exe deploy-interceptor -FileName:\<Configuration XML Filename\> [-Force:True ] [-Server:\<server\>] [-Database:\<database\>]**</span><span class="sxs-lookup"><span data-stu-id="4f73b-116">**bm.exe deploy-interceptor -FileName:\<Configuration XML Filename\> [-Force:True ] [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="4f73b-117">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="4f73b-117">**Parameters**</span></span>  
  
|<span data-ttu-id="4f73b-118">参数</span><span class="sxs-lookup"><span data-stu-id="4f73b-118">Parameter</span></span>|<span data-ttu-id="4f73b-119">Description</span><span class="sxs-lookup"><span data-stu-id="4f73b-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f73b-120">文件名：\<配置 XML 文件名\></span><span class="sxs-lookup"><span data-stu-id="4f73b-120">FileName:\<Configuration XML Filename\></span></span>|<span data-ttu-id="4f73b-121">包含侦听器配置的 XML 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="4f73b-121">The name of the XML file containing the interceptor configuration.</span></span>|  
|<span data-ttu-id="4f73b-122">Force:True</span><span class="sxs-lookup"><span data-stu-id="4f73b-122">Force:True</span></span>|<span data-ttu-id="4f73b-123">可选：强制部署侦听器配置时检测到事件源名称冲突。</span><span class="sxs-lookup"><span data-stu-id="4f73b-123">Optional: Forces deployment of the interceptor configuration when event source name collisions are detected.</span></span>|  
|<span data-ttu-id="4f73b-124">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="4f73b-124">Server:\<server\></span></span>|<span data-ttu-id="4f73b-125">可选：若要部署侦听器的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4f73b-125">Optional: The name of the server on which to deploy the interceptor.</span></span> <span data-ttu-id="4f73b-126">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="4f73b-126">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="4f73b-127">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="4f73b-127">Database:\<database\></span></span>|<span data-ttu-id="4f73b-128">可选：要对其配置侦听器的 BAM 主导入数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="4f73b-128">Optional: The name of the BAM Primary Import database on which to configure the interceptor.</span></span>|  
  
 <span data-ttu-id="4f73b-129">此命令将侦听器配置部署到指定的服务器和数据库。</span><span class="sxs-lookup"><span data-stu-id="4f73b-129">This command deploys the interceptor configuration to the specified server and database.</span></span> <span data-ttu-id="4f73b-130">在部署期间，BAM 管理实用程序执行以下验证：</span><span class="sxs-lookup"><span data-stu-id="4f73b-130">During deployment, the BAM Management utility performs the following validations:</span></span>  
  
- <span data-ttu-id="4f73b-131">XSD 验证：根据公用侦听器配置架构进行验证的侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="4f73b-131">XSD validation: The interceptor configuration is validated against the common interceptor configuration schema.</span></span>  
  
- <span data-ttu-id="4f73b-132">验证活动存在 （部署在主导入数据库中） 和检查点是有效 （存在并具有匹配的数据类型）。</span><span class="sxs-lookup"><span data-stu-id="4f73b-132">Validation that the activity exists (is deployed in the Primary Import database) and that checkpoints are valid (exist and have a matching data type).</span></span>  
  
  <span data-ttu-id="4f73b-133">如果事件源名称中检测到冲突，则会引发一条警告，描述冲突。</span><span class="sxs-lookup"><span data-stu-id="4f73b-133">If a collision is detected in the event source name, a warning is thrown describing the collision.</span></span> <span data-ttu-id="4f73b-134">对于冲突时，部署将失败，除非 **– Force: True**参数标志。</span><span class="sxs-lookup"><span data-stu-id="4f73b-134">In the case of a collision, the deployment will fail unless the **–Force:True** parameter flag is used.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f73b-135">**– Force: True**参数可潜在删除引用同名事件源的侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="4f73b-135">The **–Force:True** parameter potentially removes interceptor configurations that reference event sources with the same name.</span></span> <span data-ttu-id="4f73b-136">应使用**get 侦听器**命令，以使用之前创建的现有侦听器配置备份 **– Force: True**参数。</span><span class="sxs-lookup"><span data-stu-id="4f73b-136">You should use the **get-interceptor** command to create a backup of existing interceptor configurations before using the **–Force:True** parameter.</span></span>  
  
 <span data-ttu-id="4f73b-137">**示例**</span><span class="sxs-lookup"><span data-stu-id="4f73b-137">**Examples**</span></span>  
  
```  
bm.exe deploy-interceptor  -FileName:myInceptor.xml  
bm.exe deploy-interceptor  -FileName:myInceptor.xml -Force:True  
```  
  
## <a name="get-interceptorlist-command"></a><span data-ttu-id="4f73b-138">get-interceptorlist 命令</span><span class="sxs-lookup"><span data-stu-id="4f73b-138">get-interceptorlist Command</span></span>  
 <span data-ttu-id="4f73b-139">**Usage**</span><span class="sxs-lookup"><span data-stu-id="4f73b-139">**Usage**</span></span>  
  
 <span data-ttu-id="4f73b-140">**bm.exe get-interceptorlist [-Server:\<server\>] [-Database:\<database\>]**</span><span class="sxs-lookup"><span data-stu-id="4f73b-140">**bm.exe get-interceptorlist [-Server:\<server\>] [-Database:\<database\>]**</span></span>  
  
 <span data-ttu-id="4f73b-141">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="4f73b-141">**Parameters**</span></span>  
  
|<span data-ttu-id="4f73b-142">参数</span><span class="sxs-lookup"><span data-stu-id="4f73b-142">Parameter</span></span>|<span data-ttu-id="4f73b-143">Description</span><span class="sxs-lookup"><span data-stu-id="4f73b-143">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f73b-144">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="4f73b-144">Server:\<server\></span></span>|<span data-ttu-id="4f73b-145">可选：从中返回一组已部署侦听器的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4f73b-145">Optional: The name of the server from which to return a list of deployed interceptors.</span></span> <span data-ttu-id="4f73b-146">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="4f73b-146">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="4f73b-147">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="4f73b-147">Database:\<database\></span></span>|<span data-ttu-id="4f73b-148">可选：要从中检索已部署的侦听器的 BAM 主导入数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="4f73b-148">Optional: The name of the BAM Primary Import database from which to retrieve the deployed interceptors.</span></span>|  
  
 <span data-ttu-id="4f73b-149">此命令将返回一系列活动，并为其启用侦听与其关联的事件源。</span><span class="sxs-lookup"><span data-stu-id="4f73b-149">This command returns a list of the activities, and their associated event sources, for which interception is enabled.</span></span>  
  
 <span data-ttu-id="4f73b-150">**示例**</span><span class="sxs-lookup"><span data-stu-id="4f73b-150">**Example**</span></span>  
  
```  
bm.exe get-interceptorlist   
```  
  
## <a name="get-interceptor-command"></a><span data-ttu-id="4f73b-151">get-interceptor 命令</span><span class="sxs-lookup"><span data-stu-id="4f73b-151">get-interceptor Command</span></span>  
 <span data-ttu-id="4f73b-152">**Usage**</span><span class="sxs-lookup"><span data-stu-id="4f73b-152">**Usage**</span></span>  
  
 <span data-ttu-id="4f73b-153">**bm.exe get-interceptor [-Server:\<server\>] [-Database:\<database\>] -FileName:\<配置 XML 文件名\>[-活动：\<活动名称\>] [-EventSource:\<事件源名称\>]**</span><span class="sxs-lookup"><span data-stu-id="4f73b-153">**bm.exe get-interceptor [-Server:\<server\>] [-Database:\<database\>] -FileName: \<Configuration XML Filename\> [ -Activity: \<Activity Name\>] [-EventSource: \<Event Source Name\>]**</span></span>  
  
 <span data-ttu-id="4f73b-154">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="4f73b-154">**Parameters**</span></span>  
  
|<span data-ttu-id="4f73b-155">参数</span><span class="sxs-lookup"><span data-stu-id="4f73b-155">Parameter</span></span>|<span data-ttu-id="4f73b-156">Description</span><span class="sxs-lookup"><span data-stu-id="4f73b-156">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f73b-157">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="4f73b-157">Server:\<server\></span></span>|<span data-ttu-id="4f73b-158">可选：要从中检索已部署的侦听器的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4f73b-158">Optional: The name of the server from which to retrieve the deployed interceptor.</span></span> <span data-ttu-id="4f73b-159">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="4f73b-159">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="4f73b-160">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="4f73b-160">Database:\<database\></span></span>|<span data-ttu-id="4f73b-161">可选：要从中检索已部署的侦听器的 BAM 主导入数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="4f73b-161">Optional: The name of the BAM Primary Import database from which to retrieve deployed interceptor.</span></span>|  
|<span data-ttu-id="4f73b-162">文件名：\<配置 XML 文件名\></span><span class="sxs-lookup"><span data-stu-id="4f73b-162">FileName:\<Configuration XML Filename\></span></span>|<span data-ttu-id="4f73b-163">要向其写入侦听器配置 XML 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="4f73b-163">The name of the XML file to which to write the interceptor configuration.</span></span>|  
|<span data-ttu-id="4f73b-164">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="4f73b-164">Activity:\<Activity Name\></span></span>|<span data-ttu-id="4f73b-165">可选：指定要为其返回已配置的侦听器的活动。</span><span class="sxs-lookup"><span data-stu-id="4f73b-165">Optional: Specifies the activity for which to return the configured interceptor.</span></span> <span data-ttu-id="4f73b-166">可以结合使用**EventSource**参数以便进一步指定要返回的配置。</span><span class="sxs-lookup"><span data-stu-id="4f73b-166">Can be used in conjunction with the **EventSource** parameter to further specify the configuration to return.</span></span>|  
|<span data-ttu-id="4f73b-167">EventSource:\<事件源名称\></span><span class="sxs-lookup"><span data-stu-id="4f73b-167">EventSource:\<Event Source Name\></span></span>|<span data-ttu-id="4f73b-168">可选：指定要为其返回已配置的侦听器的事件源。</span><span class="sxs-lookup"><span data-stu-id="4f73b-168">Optional: Specifies the event source for which to return the configured interceptor.</span></span> <span data-ttu-id="4f73b-169">可以结合使用**活动**参数以便进一步指定要返回的配置。</span><span class="sxs-lookup"><span data-stu-id="4f73b-169">Can be used in conjunction with the **Activity** parameter to further specify the configuration to return.</span></span>|  
  
 <span data-ttu-id="4f73b-170">如果未提供任何活动名称或事件源名称，该命令将返回包含所有事件源和活动的侦听器配置的有效的配置文件。</span><span class="sxs-lookup"><span data-stu-id="4f73b-170">If no activity name or event source name is provided, the command returns a valid configuration file containing the interceptor configurations for all event sources and activities.</span></span>  
  
 <span data-ttu-id="4f73b-171">如果只提供活动名称，该命令将返回有效的侦听器配置文件的该活动的所有事件源。</span><span class="sxs-lookup"><span data-stu-id="4f73b-171">If only an activity name is provided, the command returns a valid interceptor configuration file for all event sources for that activity.</span></span>  
  
 <span data-ttu-id="4f73b-172">如果只提供事件源名称，该命令返回有效的侦听器配置文件，该事件源的所有活动中。</span><span class="sxs-lookup"><span data-stu-id="4f73b-172">If only an event source name is provided, the command returns a valid interceptor configuration file for that event source across all activities.</span></span>  
  
 <span data-ttu-id="4f73b-173">如果提供的活动名称和事件源名称，然后该命令返回有效的侦听器配置文件的该活动的该事件源。</span><span class="sxs-lookup"><span data-stu-id="4f73b-173">If both an activity name and an event source name are provided, then the command returns a valid interceptor configuration file for that event source for that activity.</span></span>  
  
 <span data-ttu-id="4f73b-174">**示例**</span><span class="sxs-lookup"><span data-stu-id="4f73b-174">**Examples**</span></span>  
  
```  
bm.exe get-interceptor   
bm.exe get-interceptor  -Activity:ShippingPO  
```  
  
## <a name="remove-interceptor-command"></a><span data-ttu-id="4f73b-175">remove-interceptor 命令</span><span class="sxs-lookup"><span data-stu-id="4f73b-175">remove-interceptor Command</span></span>  
 <span data-ttu-id="4f73b-176">**Usage**</span><span class="sxs-lookup"><span data-stu-id="4f73b-176">**Usage**</span></span>  
  
 <span data-ttu-id="4f73b-177">**bm.exe remove-interceptor [-Server:\<server\>] [-Database:\<database\>] [ -Activity:\<活动名称\>] [-EventSource:\<事件源名称\>]**</span><span class="sxs-lookup"><span data-stu-id="4f73b-177">**bm.exe remove-interceptor [-Server:\<server\>] [-Database:\<database\>] [ -Activity: \<Activity Name\>][-EventSource: \<Event Source Name\>]**</span></span>  
  
 <span data-ttu-id="4f73b-178">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="4f73b-178">**Parameters**</span></span>  
  
|<span data-ttu-id="4f73b-179">参数</span><span class="sxs-lookup"><span data-stu-id="4f73b-179">Parameter</span></span>|<span data-ttu-id="4f73b-180">Description</span><span class="sxs-lookup"><span data-stu-id="4f73b-180">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f73b-181">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="4f73b-181">Server:\<server\></span></span>|<span data-ttu-id="4f73b-182">可选：在其配置侦听器的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4f73b-182">Optional: The name of the server on which the interceptor is configured.</span></span> <span data-ttu-id="4f73b-183">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="4f73b-183">The server must be in the same domain as the computer from which you are running bm.exe.</span></span>|  
|<span data-ttu-id="4f73b-184">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="4f73b-184">Database:\<database\></span></span>|<span data-ttu-id="4f73b-185">可选：在其配置侦听器的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="4f73b-185">Optional: The name of the database on which the interceptor is configured.</span></span>|  
|<span data-ttu-id="4f73b-186">活动：\<活动名称\></span><span class="sxs-lookup"><span data-stu-id="4f73b-186">Activity: \<Activity Name\></span></span>|<span data-ttu-id="4f73b-187">可选：指定要为其删除指定的侦听器的活动。</span><span class="sxs-lookup"><span data-stu-id="4f73b-187">Optional: Specifies the activity for which to remove the specified interceptor.</span></span> <span data-ttu-id="4f73b-188">可以结合使用**EventSource**参数以便进一步指定要返回的配置。</span><span class="sxs-lookup"><span data-stu-id="4f73b-188">Can be used in conjunction with the **EventSource** parameter to further specify the configuration to return.</span></span>|  
|<span data-ttu-id="4f73b-189">EventSource:\<事件源名称\></span><span class="sxs-lookup"><span data-stu-id="4f73b-189">EventSource: \<Event Source Name\></span></span>|<span data-ttu-id="4f73b-190">可选：指定要为其删除指定的侦听器的事件源。</span><span class="sxs-lookup"><span data-stu-id="4f73b-190">Optional: Specifies the event source for which to remove the specified interceptor.</span></span> <span data-ttu-id="4f73b-191">可以结合使用**活动**参数以便进一步指定要返回的配置。</span><span class="sxs-lookup"><span data-stu-id="4f73b-191">Can be used in conjunction with the **Activity** parameter to further specify the configuration to return.</span></span>|  
  
 <span data-ttu-id="4f73b-192">如果只提供活动名称，该命令将删除为该活动的所有事件源的侦听器。</span><span class="sxs-lookup"><span data-stu-id="4f73b-192">If only an activity name is provided, the command removes the interceptor for all event sources for that activity.</span></span>  
  
 <span data-ttu-id="4f73b-193">如果只提供事件源名称，该命令将删除仅该事件源部分的所有活动。</span><span class="sxs-lookup"><span data-stu-id="4f73b-193">If only an event source name is provided, the command removes only that event source portion for all activities.</span></span>  
  
 <span data-ttu-id="4f73b-194">**示例**</span><span class="sxs-lookup"><span data-stu-id="4f73b-194">**Example**</span></span>  
  
```  
bm.exe remove-interceptor   
```  
  
## <a name="see-also"></a><span data-ttu-id="4f73b-195">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f73b-195">See Also</span></span>  
 [<span data-ttu-id="4f73b-196">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="4f73b-196">BAM Management Utility</span></span>](../core/bam-management-utility.md)
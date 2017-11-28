---
title: "部署的 BAM 定义 （观察模式） 命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df7914f3-7a92-4ab2-bd0e-94a2eed4825e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 847dd40bc7d0e8fe9ec225ad8af45d06c92d7b63
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-of-bam-definition-observation-model-commands"></a><span data-ttu-id="78741-102">部署的 BAM 定义 （观察模式） 命令</span><span class="sxs-lookup"><span data-stu-id="78741-102">Deployment of BAM Definition (Observation Model) Commands</span></span>
<span data-ttu-id="78741-103">您可借助 BAM 管理实用程序部署命令来应用、修改和删除定义。</span><span class="sxs-lookup"><span data-stu-id="78741-103">The BAM management utility deployment commands allow you to apply, modify, and remove definitions.</span></span>  
  
-   <span data-ttu-id="78741-104">部署所有： 将部署的 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="78741-104">deploy-all: Deploys a BAM definition.</span></span>  
  
-   <span data-ttu-id="78741-105">更新所有： BAM 定义更新。</span><span class="sxs-lookup"><span data-stu-id="78741-105">update-all: Updates a BAM definition.</span></span>  
  
-   <span data-ttu-id="78741-106">删除 all： 删除 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="78741-106">remove-all: Removes a BAM definition.</span></span>  
  
-   <span data-ttu-id="78741-107">更新 livedataworkbook： 更新实时数据工作簿中的数据库连接信息。</span><span class="sxs-lookup"><span data-stu-id="78741-107">update-livedataworkbook: Updates the database connection information in a live data workbook.</span></span>  
  
-   <span data-ttu-id="78741-108">重新生成 livedataworkbook： 重新生成服务器上的实时数据工作簿。</span><span class="sxs-lookup"><span data-stu-id="78741-108">regenerate-livedataworkbook: Regenerates the live data workbook on the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78741-109">你可以通过包括启用任何 BM 实用工具命令的跟踪**-跟踪： 在 &#124; 关闭**参数交换机。</span><span class="sxs-lookup"><span data-stu-id="78741-109">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="78741-110">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="78741-110">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="78741-111">该开关可与所有标准 BM 命令一起使用。</span><span class="sxs-lookup"><span data-stu-id="78741-111">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78741-112">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="78741-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="deploy-all-command"></a><span data-ttu-id="78741-113">deploy-all 命令</span><span class="sxs-lookup"><span data-stu-id="78741-113">deploy-all Command</span></span>  
 <span data-ttu-id="78741-114">**用法**</span><span class="sxs-lookup"><span data-stu-id="78741-114">**Usage**</span></span>  
  
 <span data-ttu-id="78741-115">**bm.exe 部署所有-DefinitionFile:\<def 文件 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="78741-115">**bm.exe deploy-all -DefinitionFile:\<def file>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="78741-116">**参数**</span><span class="sxs-lookup"><span data-stu-id="78741-116">**Parameters**</span></span>  
  
|<span data-ttu-id="78741-117">参数</span><span class="sxs-lookup"><span data-stu-id="78741-117">Parameter</span></span>|<span data-ttu-id="78741-118">Description</span><span class="sxs-lookup"><span data-stu-id="78741-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78741-119">DefinitionFile:\<def 文件 ></span><span class="sxs-lookup"><span data-stu-id="78741-119">DefinitionFile:\<def file></span></span>|<span data-ttu-id="78741-120">包含要部署的定义的文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="78741-120">The path and name of the file containing the definitions to deploy.</span></span>|  
|<span data-ttu-id="78741-121">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="78741-121">Server:\<server></span></span>|<span data-ttu-id="78741-122">可选： 要将定义部署到服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="78741-122">Optional: The name of the server to which to deploy the definitions.</span></span> <span data-ttu-id="78741-123">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="78741-123">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="78741-124">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="78741-124">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="78741-125">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="78741-125">Database:\<database></span></span>|<span data-ttu-id="78741-126">可选： 要将定义部署到数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="78741-126">Optional: The name of the database to which to deploy the definitions.</span></span> <span data-ttu-id="78741-127">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="78741-127">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="78741-128">将指定 BAM 定义 XML 文件中的所有项目部署到指定的服务器和数据库。</span><span class="sxs-lookup"><span data-stu-id="78741-128">Deploys all artifacts from the specified BAM definition XML file to the specified server and database.</span></span> <span data-ttu-id="78741-129">该文件可以是包含 BAM 定义 XML 的文本文件，也可以是 BAM Excel 工作簿。</span><span class="sxs-lookup"><span data-stu-id="78741-129">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="78741-130">该定义文件必须仅包含新项目。</span><span class="sxs-lookup"><span data-stu-id="78741-130">The definition file must include only new artifacts.</span></span> <span data-ttu-id="78741-131">如果该文件包含已部署的项目，部署将会失败并报告错误。</span><span class="sxs-lookup"><span data-stu-id="78741-131">If the file contains artifacts that have already been deployed, the deployment will fail and report an error.</span></span>  
  
 <span data-ttu-id="78741-132">**部署 BAM 定义注意事项**</span><span class="sxs-lookup"><span data-stu-id="78741-132">**Considerations for deploying BAM definitions**</span></span>  
  
 <span data-ttu-id="78741-133">在部署警报订阅时，必须以“域\用户”格式指定订户的用户 ID。</span><span class="sxs-lookup"><span data-stu-id="78741-133">When deploying alert subscriptions, user IDs of the subscribers must be specified in a domain\user format.</span></span>  
  
 <span data-ttu-id="78741-134">必须在其上的计算机上运行的分布式的事务协调器 (DTC) 服务**部署所有**发出命令。</span><span class="sxs-lookup"><span data-stu-id="78741-134">The distributed transaction coordinator (DTC) service must be running on the computer on which the **deploy-all** command is issued.</span></span>  
  
 <span data-ttu-id="78741-135">在部署定义时，BAM 管理实用程序仅在实时聚合 (RTA) 视图中支持 14 个维度级别。</span><span class="sxs-lookup"><span data-stu-id="78741-135">When deploying a definition the BAM Management utility only supports 14 dimension levels in Real-Time Aggregation (RTA) view.</span></span> <span data-ttu-id="78741-136">部署超过此数量的级别将返回部署失败的错误。</span><span class="sxs-lookup"><span data-stu-id="78741-136">Deploying additional levels returns a Deployment failed error.</span></span>  
  
 <span data-ttu-id="78741-137">如果定义了多个视图，它们使用不同的语言设置，然后将解决方案部署到使用单一语言的服务器中，则这些视图将无法部署。</span><span class="sxs-lookup"><span data-stu-id="78741-137">If you define multiple views that use different language settings and deploy your solution to a server that uses a single language, the views will be undeployable.</span></span> <span data-ttu-id="78741-138">这种方案只在没有计划聚合需要 BAM 定义中包含 OLAP 的情况下才支持。</span><span class="sxs-lookup"><span data-stu-id="78741-138">This scenario is supported only in a case where you don't have scheduled aggregations that require OLAP as part of the BAM definition.</span></span>  
  
 <span data-ttu-id="78741-139">启用 BAM 警报后，BAM 管理实用程序将已部署的活动视图限制为 49 个。</span><span class="sxs-lookup"><span data-stu-id="78741-139">The BAM management utility limits you to 49 deployed activity views when BAM Alerts are enabled.</span></span> <span data-ttu-id="78741-140">活动视图数的计算方法如下：各视图（1 至 N）乘以相应父活动的数量，然后将所得结果相加。</span><span class="sxs-lookup"><span data-stu-id="78741-140">The number of activity views is calculated as the Summation 1..N of View(n) multiplied by the number of parent activities.</span></span>  <span data-ttu-id="78741-141">例如，如果部署了一个基于两个活动的视图，则结果为两个活动视图。</span><span class="sxs-lookup"><span data-stu-id="78741-141">For example, if you deploy a view that is based on two activities, you get two activity views.</span></span>  <span data-ttu-id="78741-142">如果部署了两个视图，其中一个视图涉及两个活动，另一个视图基于一个活动，则您有 3 个活动视图。</span><span class="sxs-lookup"><span data-stu-id="78741-142">If you deploy two views, one of which spans two activities and the other based on a single activity, you have 3 activity views.</span></span>  
  
 <span data-ttu-id="78741-143">对于具有多个数据透视表的 BAM 定义，如果这些数据透视表是在相同 RTA 和多维数据集名称组合的基础上定义的，则 BAM 管理实用程序不允许部署这种 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="78741-143">The BAM Management utility blocks deployment of BAM definitions which have multiple PivotTable reports which are defined on the same RTA and cube name combination.</span></span> <span data-ttu-id="78741-144">Bm.exe 将终止部署并返回以下错误：</span><span class="sxs-lookup"><span data-stu-id="78741-144">Bm.exe will terminate the deployment and return the following error:</span></span>  
  
 <span data-ttu-id="78741-145">正在部署视图...错误： BAM 部署失败。</span><span class="sxs-lookup"><span data-stu-id="78741-145">Deploying View... ERROR: The BAM deployment failed.</span></span>  
  
 <span data-ttu-id="78741-146">对于一个给定的 RTA 和多维数据集，只能定义一个数据透视表视图。</span><span class="sxs-lookup"><span data-stu-id="78741-146">Only one PivotTable view can be defined on a given RTA and cube.</span></span>  
  
 <span data-ttu-id="78741-147">下列名称是保留名称，如果使用会导致定义部署失败：</span><span class="sxs-lookup"><span data-stu-id="78741-147">The following list of names are reserved and will cause the definition deployment to fail:</span></span>  
  
-   <span data-ttu-id="78741-148">RecordID</span><span class="sxs-lookup"><span data-stu-id="78741-148">RecordID</span></span>  
  
-   <span data-ttu-id="78741-149">ActivityID</span><span class="sxs-lookup"><span data-stu-id="78741-149">ActivityID</span></span>  
  
-   <span data-ttu-id="78741-150">IsVisible</span><span class="sxs-lookup"><span data-stu-id="78741-150">IsVisible</span></span>  
  
-   <span data-ttu-id="78741-151">IsComplete</span><span class="sxs-lookup"><span data-stu-id="78741-151">IsComplete</span></span>  
  
-   <span data-ttu-id="78741-152">LastModified</span><span class="sxs-lookup"><span data-stu-id="78741-152">LastModified</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78741-153">如果 bm.exe 在部署过程中遇到错误，部署将终止，对视图和活动的更改也会回滚。</span><span class="sxs-lookup"><span data-stu-id="78741-153">If bm.exe encounters an error during the deployment, the deployment is terminated and changes to the views and activities are rolled back.</span></span> <span data-ttu-id="78741-154">对 OLAP 多维数据集的更改不会回滚，这是因为 OLAP 不支持事务性部署。</span><span class="sxs-lookup"><span data-stu-id="78741-154">Changes to OLAP cubes are not rolled back since OLAP does not support transactional deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78741-155">在使用一种区域设置的计算机上创建的 BAM 定义无法部署到配置为另一种区域设置的计算机上。</span><span class="sxs-lookup"><span data-stu-id="78741-155">BAM definitions created on a computer using one locale setting cannot be deployed to a computer configured with a different locale setting.</span></span> <span data-ttu-id="78741-156">例如，在配置为英语区域设置的计算机上用英文版 Microsoft Excel 生成的 BAM 定义，无法部署到用日语区域设置配置为日文的计算机上。</span><span class="sxs-lookup"><span data-stu-id="78741-156">For example, a BAM definition generated using an English language version of Microsoft Excel on a computer configured with a EN locale setting cannot be deployed on a computer configured for Japanese using a JA locale setting.</span></span>  
  
 <span data-ttu-id="78741-157">**示例**</span><span class="sxs-lookup"><span data-stu-id="78741-157">**Examples**</span></span>  
  
```  
bm.exe deploy-all -DefinitionFile:MyDef.xml  
bm.exe deploy-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-all-command"></a><span data-ttu-id="78741-158">update-all 命令</span><span class="sxs-lookup"><span data-stu-id="78741-158">update-all Command</span></span>  
 <span data-ttu-id="78741-159">**用法**</span><span class="sxs-lookup"><span data-stu-id="78741-159">**Usage**</span></span>  
  
 <span data-ttu-id="78741-160">**bm.exe 更新所有-DefinitionFile:\<def 文件 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="78741-160">**bm.exe update-all -DefinitionFile:\<def file>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="78741-161">**参数**</span><span class="sxs-lookup"><span data-stu-id="78741-161">**Parameters**</span></span>  
  
|<span data-ttu-id="78741-162">参数</span><span class="sxs-lookup"><span data-stu-id="78741-162">Parameter</span></span>|<span data-ttu-id="78741-163">Description</span><span class="sxs-lookup"><span data-stu-id="78741-163">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78741-164">DefinitionFile:\<def 文件 ></span><span class="sxs-lookup"><span data-stu-id="78741-164">DefinitionFile:\<def file></span></span>|<span data-ttu-id="78741-165">包含执行更新所用定义的文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="78741-165">The path and name of the file containing the definitions from which to perform the update.</span></span>|  
|<span data-ttu-id="78741-166">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="78741-166">Server:\<server></span></span>|<span data-ttu-id="78741-167">可选： 要将定义更新部署到服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="78741-167">Optional: The name of the server to which to deploy the definition updates.</span></span> <span data-ttu-id="78741-168">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="78741-168">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="78741-169">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="78741-169">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="78741-170">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="78741-170">Database:\<database></span></span>|<span data-ttu-id="78741-171">可选： 要将定义更新部署到数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="78741-171">Optional: The name of the database to which to deploy the definition updates.</span></span> <span data-ttu-id="78741-172">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="78741-172">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="78741-173">更新 BAM 定义 XML 中的某些项目。</span><span class="sxs-lookup"><span data-stu-id="78741-173">Updates certain artifacts from the BAM definition XML.</span></span> <span data-ttu-id="78741-174">该文件可以是包含 BAM 定义 XML 的文本文件，也可以是 BAM Excel 工作簿。</span><span class="sxs-lookup"><span data-stu-id="78741-174">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="78741-175">更新不会删除当前定义文件中没有描述的项目。</span><span class="sxs-lookup"><span data-stu-id="78741-175">The update does not delete artifacts that are not described in the current definition file.</span></span> <span data-ttu-id="78741-176">更新可以将新检查点添加到活动中，但是不能从已部署的活动中删除检查点。</span><span class="sxs-lookup"><span data-stu-id="78741-176">It can add new checkpoints to activities, but cannot drop checkpoints from deployed activities.</span></span> <span data-ttu-id="78741-177">更新既不能重命名检查点，也不能更改检查点的属性。</span><span class="sxs-lookup"><span data-stu-id="78741-177">The update can neither rename checkpoints nor change checkpoint properties.</span></span>  
  
 <span data-ttu-id="78741-178">部署某个活动后，对该活动可执行的操作就会受到限制。</span><span class="sxs-lookup"><span data-stu-id="78741-178">Once an activity has been deployed, the actions you can take on an activity become restricted.</span></span> <span data-ttu-id="78741-179">具体而言，除非准备让管理员取消部署整个 BAM 活动和视图集，然后重新部署它们，否则，您无法从活动中删除项。</span><span class="sxs-lookup"><span data-stu-id="78741-179">Specifically, you cannot delete items from an activity unless you are prepared to have your administrator undeploy the entire BAM activity and view sets and then redeploy them.</span></span> <span data-ttu-id="78741-180">这可能导致查看中断和数据丢失，除非管理员进行数据备份和还原。</span><span class="sxs-lookup"><span data-stu-id="78741-180">This can cause an interruption of visibility and loss of data unless the administrator does a backup and restore of the data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78741-181">您不能使用此命令向现有视图添加新活动。</span><span class="sxs-lookup"><span data-stu-id="78741-181">You cannot use this command to add new activities to an existing view.</span></span> <span data-ttu-id="78741-182">若要将视图添加到活动中，必须创建包含新活动的新视图。</span><span class="sxs-lookup"><span data-stu-id="78741-182">To add a view to an activity you must create a new view that includes the new activity.</span></span> <span data-ttu-id="78741-183">然后可以取消部署旧视图，但是要知道，您将丢失 OLAP 数据历史记录。</span><span class="sxs-lookup"><span data-stu-id="78741-183">You can then undeploy the old view, but be aware that you will then lose your OLAP data history.</span></span>  
  
 <span data-ttu-id="78741-184">**示例**</span><span class="sxs-lookup"><span data-stu-id="78741-184">**Examples**</span></span>  
  
```  
bm.exe update-all -DefinitionFile:MyDef.xml  
bm.exe update-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="remove-all-command"></a><span data-ttu-id="78741-185">remove-all 命令</span><span class="sxs-lookup"><span data-stu-id="78741-185">remove-all Command</span></span>  
 <span data-ttu-id="78741-186">**用法**</span><span class="sxs-lookup"><span data-stu-id="78741-186">**Usage**</span></span>  
  
 <span data-ttu-id="78741-187">**bm.exe 删除全部 DefinitionFile:\<def 文件 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="78741-187">**bm.exe remove-all DefinitionFile:\<def file> [ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="78741-188">**参数**</span><span class="sxs-lookup"><span data-stu-id="78741-188">**Parameters**</span></span>  
  
|<span data-ttu-id="78741-189">参数</span><span class="sxs-lookup"><span data-stu-id="78741-189">Parameter</span></span>|<span data-ttu-id="78741-190">Description</span><span class="sxs-lookup"><span data-stu-id="78741-190">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78741-191">DefinitionFile:\<def 文件 ></span><span class="sxs-lookup"><span data-stu-id="78741-191">DefinitionFile:\<def file></span></span>|<span data-ttu-id="78741-192">包含要删除的定义的文件的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="78741-192">The path and name of the file containing the definitions to remove.</span></span>|  
|<span data-ttu-id="78741-193">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="78741-193">Server:\<server></span></span>|<span data-ttu-id="78741-194">可选： 将从中删除定义的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="78741-194">Optional: The name of the server from which the definitions will be removed.</span></span> <span data-ttu-id="78741-195">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="78741-195">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="78741-196">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="78741-196">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="78741-197">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="78741-197">Database:\<database></span></span>|<span data-ttu-id="78741-198">可选： 定义将从中删除数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="78741-198">Optional: The name of the database from which the definitions will be removed.</span></span> <span data-ttu-id="78741-199">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="78741-199">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="78741-200">删除在 BAM 定义 XML 文件中指定的所有项目。</span><span class="sxs-lookup"><span data-stu-id="78741-200">Removes all artifacts specified in the BAM definition XML file.</span></span> <span data-ttu-id="78741-201">该文件可以是包含 BAM 定义 XML 的文本文件，也可以是 BAM Excel 工作簿。</span><span class="sxs-lookup"><span data-stu-id="78741-201">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="78741-202">每个项目的定义必须与部署所用的初始定义完全匹配。</span><span class="sxs-lookup"><span data-stu-id="78741-202">The definition for each artifact must exactly match the original definition that was used for deployment.</span></span>  
  
 <span data-ttu-id="78741-203">**示例**</span><span class="sxs-lookup"><span data-stu-id="78741-203">**Examples**</span></span>  
  
```  
bm.exe remove-all -DefinitionFile:MyDef.xml  
bm.exe remove-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-livedataworkbook-command"></a><span data-ttu-id="78741-204">update-livedataworkbook 命令</span><span class="sxs-lookup"><span data-stu-id="78741-204">update-livedataworkbook Command</span></span>  
 <span data-ttu-id="78741-205">**用法**</span><span class="sxs-lookup"><span data-stu-id="78741-205">**Usage**</span></span>  
  
 <span data-ttu-id="78741-206">**bm.exe 更新 livedataworkbook-名称：\<livedata 工作簿文件名称 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="78741-206">**bm.exe update-livedataworkbook -Name:\<livedata workbook file name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="78741-207">**参数**</span><span class="sxs-lookup"><span data-stu-id="78741-207">**Parameters**</span></span>  
  
|<span data-ttu-id="78741-208">参数</span><span class="sxs-lookup"><span data-stu-id="78741-208">Parameter</span></span>|<span data-ttu-id="78741-209">Description</span><span class="sxs-lookup"><span data-stu-id="78741-209">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78741-210">名称：\<livedata 工作簿 ></span><span class="sxs-lookup"><span data-stu-id="78741-210">Name:\<livedata workbook></span></span>|<span data-ttu-id="78741-211">要更新的现有活动工作簿的名称。</span><span class="sxs-lookup"><span data-stu-id="78741-211">The name of the existing live workbook to update.</span></span>|  
|<span data-ttu-id="78741-212">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="78741-212">Server:\<server></span></span>|<span data-ttu-id="78741-213">可选： 工作簿所驻留的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="78741-213">Optional: The name of the server on which the workbook resides.</span></span> <span data-ttu-id="78741-214">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="78741-214">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="78741-215">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="78741-215">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="78741-216">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="78741-216">Database:\<database></span></span>|<span data-ttu-id="78741-217">可选： 在其上工作簿所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="78741-217">Optional: The name of the database on which the workbook resides.</span></span> <span data-ttu-id="78741-218">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="78741-218">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="78741-219">更新指定 BAM 实时数据工作簿中的 BAM 主导入数据库连接信息。</span><span class="sxs-lookup"><span data-stu-id="78741-219">Updates the BAM Primary Import database connection information in the specified BAM live data workbook.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78741-220">配置新连接字符串时，必须重新启动 TDDS 服务，才能确保服务能够识别出该更改。</span><span class="sxs-lookup"><span data-stu-id="78741-220">When configuring new connection string, you must restart the TDDS service to ensure that the service recognizes the change.</span></span> <span data-ttu-id="78741-221">TDDS 服务的详细信息，请参阅[BAM 事件总线服务存储过程](../core/bam-event-bus-service-stored-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="78741-221">For more information on the TDDS service, see [BAM Event Bus Service Stored Procedures](../core/bam-event-bus-service-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="78741-222">**示例**</span><span class="sxs-lookup"><span data-stu-id="78741-222">**Examples**</span></span>  
  
```  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls -Server:SalesSrv  
```  
  
## <a name="regenerate-livedataworkbook-command"></a><span data-ttu-id="78741-223">regenerate-livedataworkbook 命令</span><span class="sxs-lookup"><span data-stu-id="78741-223">regenerate-livedataworkbook Command</span></span>  
 <span data-ttu-id="78741-224">**用法**</span><span class="sxs-lookup"><span data-stu-id="78741-224">**Usage**</span></span>  
  
 <span data-ttu-id="78741-225">**bm.exe 重新生成 livedataworkbook WorkbookName:\<livedata 工作簿文件名称 > [-Server:\<服务器 >] [-数据库：\<数据库 >]**</span><span class="sxs-lookup"><span data-stu-id="78741-225">**bm.exe regenerate-livedataworkbook -WorkbookName:\<livedata workbook file name>[ -Server:\<server> ][ -Database:\<database> ]**</span></span>  
  
 <span data-ttu-id="78741-226">**参数**</span><span class="sxs-lookup"><span data-stu-id="78741-226">**Parameters**</span></span>  
  
|<span data-ttu-id="78741-227">参数</span><span class="sxs-lookup"><span data-stu-id="78741-227">Parameter</span></span>|<span data-ttu-id="78741-228">Description</span><span class="sxs-lookup"><span data-stu-id="78741-228">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="78741-229">WorkbookName:\<livedata 工作簿文件名称 ></span><span class="sxs-lookup"><span data-stu-id="78741-229">WorkbookName:\<livedata workbook file name></span></span>|<span data-ttu-id="78741-230">要更新的工作簿的名称。</span><span class="sxs-lookup"><span data-stu-id="78741-230">The name of the workbook to update.</span></span>|  
|<span data-ttu-id="78741-231">服务器：\<服务器 ></span><span class="sxs-lookup"><span data-stu-id="78741-231">Server:\<server></span></span>|<span data-ttu-id="78741-232">可选： 工作簿所驻留的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="78741-232">Optional: The name of the server on which the workbook resides.</span></span> <span data-ttu-id="78741-233">服务器必须是从中运行 bm.exe 计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="78741-233">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="78741-234">如果未指定服务器名称，bm.exe 使用 localhost 的默认名称。</span><span class="sxs-lookup"><span data-stu-id="78741-234">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="78741-235">数据库：\<数据库 ></span><span class="sxs-lookup"><span data-stu-id="78741-235">Database:\<database></span></span>|<span data-ttu-id="78741-236">可选： 在其上工作簿所在的数据库名称。</span><span class="sxs-lookup"><span data-stu-id="78741-236">Optional: The name of the database on which the workbook resides.</span></span> <span data-ttu-id="78741-237">如果未指定该名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="78741-237">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="78741-238">生成 BAM 实时数据工作簿，但不部署该工作簿。</span><span class="sxs-lookup"><span data-stu-id="78741-238">Generates a BAM live data workbook but does not deploy the workbook.</span></span>  
  
 <span data-ttu-id="78741-239">示例</span><span class="sxs-lookup"><span data-stu-id="78741-239">Examples</span></span>  
  
```  
bm.exe regenerate-livedataworkbook -WorkbookName:SalesManager_Live.xls  
bm.exe regenerate-livedataworkbook -WorkbookName:SM_Live.xls -Server:S1  
```  
  
## <a name="see-also"></a><span data-ttu-id="78741-240">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78741-240">See Also</span></span>  
 [<span data-ttu-id="78741-241">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="78741-241">BAM Management Utility</span></span>](../core/bam-management-utility.md)
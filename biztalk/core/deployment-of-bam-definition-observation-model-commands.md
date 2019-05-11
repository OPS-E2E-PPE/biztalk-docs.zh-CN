---
title: 部署 BAM 定义 （观察模型） 命令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df7914f3-7a92-4ab2-bd0e-94a2eed4825e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 506b563136fec86fdde9aebab31ad9bb4435736b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351742"
---
# <a name="deployment-of-bam-definition-observation-model-commands"></a><span data-ttu-id="4b7e3-102">部署的 BAM 定义 （观察模型） 命令</span><span class="sxs-lookup"><span data-stu-id="4b7e3-102">Deployment of BAM Definition (Observation Model) Commands</span></span>
<span data-ttu-id="4b7e3-103">BAM 管理实用程序部署命令，可将应用、 修改和删除定义。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-103">The BAM management utility deployment commands allow you to apply, modify, and remove definitions.</span></span>  
  
-   <span data-ttu-id="4b7e3-104">部署所有：部署 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-104">deploy-all: Deploys a BAM definition.</span></span>  
  
-   <span data-ttu-id="4b7e3-105">更新所有：更新 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-105">update-all: Updates a BAM definition.</span></span>  
  
-   <span data-ttu-id="4b7e3-106">全部删除：删除 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-106">remove-all: Removes a BAM definition.</span></span>  
  
-   <span data-ttu-id="4b7e3-107">更新 livedataworkbook:更新实时数据工作簿中的数据库连接信息。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-107">update-livedataworkbook: Updates the database connection information in a live data workbook.</span></span>  
  
-   <span data-ttu-id="4b7e3-108">重新生成 livedataworkbook:重新生成实时数据工作簿的服务器上。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-108">regenerate-livedataworkbook: Regenerates the live data workbook on the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b7e3-109">通过将可以启用任何 BM 实用工具命令的跟踪 **-跟踪： 在&#124;关闭**参数开关。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-109">You can enable tracing on any BM utility command by including the **-Trace:on&#124;off** parameter switch.</span></span> <span data-ttu-id="4b7e3-110">使用 Trace 开关将重写配置文件中的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-110">Using the Trace switch overrides the tracing settings in the configuration file.</span></span> <span data-ttu-id="4b7e3-111">此开关可以与所有标准 BM 命令结合使用。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-111">The switch can be used in conjunction with any normal BM command.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b7e3-112">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-112">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="deploy-all-command"></a><span data-ttu-id="4b7e3-113">deploy-all 命令</span><span class="sxs-lookup"><span data-stu-id="4b7e3-113">deploy-all Command</span></span>  
 <span data-ttu-id="4b7e3-114">**Usage**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-114">**Usage**</span></span>  
  
 <span data-ttu-id="4b7e3-115">**bm.exe deploy-all -DefinitionFile:\<def file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-115">**bm.exe deploy-all -DefinitionFile:\<def file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="4b7e3-116">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-116">**Parameters**</span></span>  
  
|<span data-ttu-id="4b7e3-117">参数</span><span class="sxs-lookup"><span data-stu-id="4b7e3-117">Parameter</span></span>|<span data-ttu-id="4b7e3-118">Description</span><span class="sxs-lookup"><span data-stu-id="4b7e3-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b7e3-119">DefinitionFile:\<def 文件\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-119">DefinitionFile:\<def file\></span></span>|<span data-ttu-id="4b7e3-120">路径和包含要部署的定义文件的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-120">The path and name of the file containing the definitions to deploy.</span></span>|  
|<span data-ttu-id="4b7e3-121">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-121">Server:\<server\></span></span>|<span data-ttu-id="4b7e3-122">可选：向其部署定义的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-122">Optional: The name of the server to which to deploy the definitions.</span></span> <span data-ttu-id="4b7e3-123">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-123">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="4b7e3-124">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-124">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="4b7e3-125">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-125">Database:\<database\></span></span>|<span data-ttu-id="4b7e3-126">可选：向其部署定义的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-126">Optional: The name of the database to which to deploy the definitions.</span></span> <span data-ttu-id="4b7e3-127">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-127">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="4b7e3-128">将部署到指定的服务器和数据库指定 BAM 定义 XML 文件中的所有项目。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-128">Deploys all artifacts from the specified BAM definition XML file to the specified server and database.</span></span> <span data-ttu-id="4b7e3-129">文件可以是包含 BAM 定义 XML 文件或 BAM Excel 工作簿的文本文件。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-129">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="4b7e3-130">定义文件必须仅包含新项目。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-130">The definition file must include only new artifacts.</span></span> <span data-ttu-id="4b7e3-131">如果该文件包含已部署的项目，部署将失败并报告错误。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-131">If the file contains artifacts that have already been deployed, the deployment will fail and report an error.</span></span>  
  
 <span data-ttu-id="4b7e3-132">**部署 BAM 定义的注意事项**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-132">**Considerations for deploying BAM definitions**</span></span>  
  
 <span data-ttu-id="4b7e3-133">在部署警报订阅时，必须以 domain\user 格式指定用户的订阅服务器的 Id。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-133">When deploying alert subscriptions, user IDs of the subscribers must be specified in a domain\user format.</span></span>  
  
 <span data-ttu-id="4b7e3-134">分布式的事务处理协调器 (DTC) 服务必须在其上的计算机上运行**部署所有**发出命令。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-134">The distributed transaction coordinator (DTC) service must be running on the computer on which the **deploy-all** command is issued.</span></span>  
  
 <span data-ttu-id="4b7e3-135">部署定义时，BAM 管理实用程序仅在实时聚合 (RTA) 视图中支持 14 个维度级别。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-135">When deploying a definition the BAM Management utility only supports 14 dimension levels in Real-Time Aggregation (RTA) view.</span></span> <span data-ttu-id="4b7e3-136">部署其他级别返回部署失败的错误。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-136">Deploying additional levels returns a Deployment failed error.</span></span>  
  
 <span data-ttu-id="4b7e3-137">如果定义多个使用不同的语言设置并将你的解决方案部署到使用一种语言的服务器的视图，视图将无法部署。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-137">If you define multiple views that use different language settings and deploy your solution to a server that uses a single language, the views will be undeployable.</span></span> <span data-ttu-id="4b7e3-138">仅在您不需要计划的聚合需要 BAM 定义的一部分的 OLAP 的情况下支持此方案。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-138">This scenario is supported only in a case where you don't have scheduled aggregations that require OLAP as part of the BAM definition.</span></span>  
  
 <span data-ttu-id="4b7e3-139">BAM 管理实用程序限制为 49 已部署的活动视图启用 BAM 警报时也是如此。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-139">The BAM management utility limits you to 49 deployed activity views when BAM Alerts are enabled.</span></span> <span data-ttu-id="4b7e3-140">活动视图数计算为求和方法 1..N 乘以的父活动数。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-140">The number of activity views is calculated as the Summation 1..N of View(n) multiplied by the number of parent activities.</span></span>  <span data-ttu-id="4b7e3-141">例如，如果部署基于两个活动的视图，您将获得两个活动视图。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-141">For example, if you deploy a view that is based on two activities, you get two activity views.</span></span>  <span data-ttu-id="4b7e3-142">如果部署两个视图，其中一个跨越两个活动和其他基于单个活动，您有 3 个活动视图。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-142">If you deploy two views, one of which spans two activities and the other based on a single activity, you have 3 activity views.</span></span>  
  
 <span data-ttu-id="4b7e3-143">BAM 管理实用程序块部署 BAM 定义具有多个数据透视表报告上的相同 RTA 和多维数据集名称组合所定义。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-143">The BAM Management utility blocks deployment of BAM definitions which have multiple PivotTable reports which are defined on the same RTA and cube name combination.</span></span> <span data-ttu-id="4b7e3-144">Bm.exe 将终止部署并返回以下错误：</span><span class="sxs-lookup"><span data-stu-id="4b7e3-144">Bm.exe will terminate the deployment and return the following error:</span></span>  
  
 <span data-ttu-id="4b7e3-145">正在部署视图...错误：BAM 部署失败。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-145">Deploying View... ERROR: The BAM deployment failed.</span></span>  
  
 <span data-ttu-id="4b7e3-146">可以在给定的 RTA 和多维数据集上定义只有一个数据透视表视图。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-146">Only one PivotTable view can be defined on a given RTA and cube.</span></span>  
  
 <span data-ttu-id="4b7e3-147">下面的列表的名称是保留，并将导致定义部署失败：</span><span class="sxs-lookup"><span data-stu-id="4b7e3-147">The following list of names are reserved and will cause the definition deployment to fail:</span></span>  
  
-   <span data-ttu-id="4b7e3-148">RecordID</span><span class="sxs-lookup"><span data-stu-id="4b7e3-148">RecordID</span></span>  
  
-   <span data-ttu-id="4b7e3-149">ActivityID</span><span class="sxs-lookup"><span data-stu-id="4b7e3-149">ActivityID</span></span>  
  
-   <span data-ttu-id="4b7e3-150">IsVisible</span><span class="sxs-lookup"><span data-stu-id="4b7e3-150">IsVisible</span></span>  
  
-   <span data-ttu-id="4b7e3-151">IsComplete</span><span class="sxs-lookup"><span data-stu-id="4b7e3-151">IsComplete</span></span>  
  
-   <span data-ttu-id="4b7e3-152">LastModified</span><span class="sxs-lookup"><span data-stu-id="4b7e3-152">LastModified</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b7e3-153">如果 bm.exe 在部署过程中遇到错误，部署将终止并回滚对视图和活动的更改。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-153">If bm.exe encounters an error during the deployment, the deployment is terminated and changes to the views and activities are rolled back.</span></span> <span data-ttu-id="4b7e3-154">对 OLAP 多维数据集的更改不会回滚，因为 OLAP 不支持事务性部署。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-154">Changes to OLAP cubes are not rolled back since OLAP does not support transactional deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b7e3-155">使用一种区域设置的计算机上创建的 BAM 定义无法部署到使用不同的区域设置设置配置的计算机。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-155">BAM definitions created on a computer using one locale setting cannot be deployed to a computer configured with a different locale setting.</span></span> <span data-ttu-id="4b7e3-156">例如，不能配置为日文使用日语区域设置的计算机上部署生成配置为英语区域设置的计算机上使用英语语言版本的 Microsoft Excel 的 BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-156">For example, a BAM definition generated using an English language version of Microsoft Excel on a computer configured with a EN locale setting cannot be deployed on a computer configured for Japanese using a JA locale setting.</span></span>  
  
 <span data-ttu-id="4b7e3-157">**示例**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-157">**Examples**</span></span>  
  
```  
bm.exe deploy-all -DefinitionFile:MyDef.xml  
bm.exe deploy-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-all-command"></a><span data-ttu-id="4b7e3-158">update-all 命令</span><span class="sxs-lookup"><span data-stu-id="4b7e3-158">update-all Command</span></span>  
 <span data-ttu-id="4b7e3-159">**Usage**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-159">**Usage**</span></span>  
  
 <span data-ttu-id="4b7e3-160">**bm.exe update-all -DefinitionFile:\<def file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-160">**bm.exe update-all -DefinitionFile:\<def file\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="4b7e3-161">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-161">**Parameters**</span></span>  
  
|<span data-ttu-id="4b7e3-162">参数</span><span class="sxs-lookup"><span data-stu-id="4b7e3-162">Parameter</span></span>|<span data-ttu-id="4b7e3-163">Description</span><span class="sxs-lookup"><span data-stu-id="4b7e3-163">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b7e3-164">DefinitionFile:\<def 文件\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-164">DefinitionFile:\<def file\></span></span>|<span data-ttu-id="4b7e3-165">路径和包含要执行更新定义的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-165">The path and name of the file containing the definitions from which to perform the update.</span></span>|  
|<span data-ttu-id="4b7e3-166">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-166">Server:\<server\></span></span>|<span data-ttu-id="4b7e3-167">可选：要将定义更新部署到服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-167">Optional: The name of the server to which to deploy the definition updates.</span></span> <span data-ttu-id="4b7e3-168">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-168">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="4b7e3-169">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-169">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="4b7e3-170">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-170">Database:\<database\></span></span>|<span data-ttu-id="4b7e3-171">可选：向其部署定义更新的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-171">Optional: The name of the database to which to deploy the definition updates.</span></span> <span data-ttu-id="4b7e3-172">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-172">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="4b7e3-173">更新 BAM 定义 XML 中的某些项目。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-173">Updates certain artifacts from the BAM definition XML.</span></span> <span data-ttu-id="4b7e3-174">文件可以是包含 BAM 定义 XML 文件或 BAM Excel 工作簿的文本文件。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-174">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="4b7e3-175">更新不会删除当前定义文件中未描述的项目。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-175">The update does not delete artifacts that are not described in the current definition file.</span></span> <span data-ttu-id="4b7e3-176">它可以将新的检查点添加到活动，但无法从已部署的活动中删除检查点。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-176">It can add new checkpoints to activities, but cannot drop checkpoints from deployed activities.</span></span> <span data-ttu-id="4b7e3-177">更新既不重命名检查点也不能更改检查点属性。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-177">The update can neither rename checkpoints nor change checkpoint properties.</span></span>  
  
 <span data-ttu-id="4b7e3-178">活动部署后，可在活动执行的操作就会受到限制。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-178">Once an activity has been deployed, the actions you can take on an activity become restricted.</span></span> <span data-ttu-id="4b7e3-179">具体而言，除非你已准备好让管理员取消部署整个 BAM 活动和视图集，然后重新部署它们，否则您不能从活动中删除项目。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-179">Specifically, you cannot delete items from an activity unless you are prepared to have your administrator undeploy the entire BAM activity and view sets and then redeploy them.</span></span> <span data-ttu-id="4b7e3-180">除非管理员进行备份，这可能导致查看中断和数据丢失的数据和还原。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-180">This can cause an interruption of visibility and loss of data unless the administrator does a backup and restore of the data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b7e3-181">不能使用此命令将新活动添加到现有视图。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-181">You cannot use this command to add new activities to an existing view.</span></span> <span data-ttu-id="4b7e3-182">若要向活动中添加一个视图，必须创建一个包含新活动的新视图。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-182">To add a view to an activity you must create a new view that includes the new activity.</span></span> <span data-ttu-id="4b7e3-183">然后，您可以取消部署旧视图，但请注意，您将丢失 OLAP 数据历史记录。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-183">You can then undeploy the old view, but be aware that you will then lose your OLAP data history.</span></span>  
  
 <span data-ttu-id="4b7e3-184">**示例**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-184">**Examples**</span></span>  
  
```  
bm.exe update-all -DefinitionFile:MyDef.xml  
bm.exe update-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="remove-all-command"></a><span data-ttu-id="4b7e3-185">remove-all 命令</span><span class="sxs-lookup"><span data-stu-id="4b7e3-185">remove-all Command</span></span>  
 <span data-ttu-id="4b7e3-186">**Usage**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-186">**Usage**</span></span>  
  
 <span data-ttu-id="4b7e3-187">**bm.exe remove-all DefinitionFile:\<def file\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-187">**bm.exe remove-all DefinitionFile:\<def file\> [ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="4b7e3-188">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-188">**Parameters**</span></span>  
  
|<span data-ttu-id="4b7e3-189">参数</span><span class="sxs-lookup"><span data-stu-id="4b7e3-189">Parameter</span></span>|<span data-ttu-id="4b7e3-190">Description</span><span class="sxs-lookup"><span data-stu-id="4b7e3-190">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b7e3-191">DefinitionFile:\<def 文件\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-191">DefinitionFile:\<def file\></span></span>|<span data-ttu-id="4b7e3-192">路径和包含要删除的定义文件的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-192">The path and name of the file containing the definitions to remove.</span></span>|  
|<span data-ttu-id="4b7e3-193">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-193">Server:\<server\></span></span>|<span data-ttu-id="4b7e3-194">可选：要从中删除定义的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-194">Optional: The name of the server from which the definitions will be removed.</span></span> <span data-ttu-id="4b7e3-195">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-195">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="4b7e3-196">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-196">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="4b7e3-197">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-197">Database:\<database\></span></span>|<span data-ttu-id="4b7e3-198">可选：要从中删除定义的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-198">Optional: The name of the database from which the definitions will be removed.</span></span> <span data-ttu-id="4b7e3-199">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-199">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="4b7e3-200">删除 BAM 定义 XML 文件中指定的所有项目。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-200">Removes all artifacts specified in the BAM definition XML file.</span></span> <span data-ttu-id="4b7e3-201">文件可以是包含 BAM 定义 XML 文件或 BAM Excel 工作簿的文本文件。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-201">The file can be a text file containing the BAM definition XML or a BAM Excel workbook.</span></span> <span data-ttu-id="4b7e3-202">每个项目的定义必须与部署所用的原始定义完全匹配。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-202">The definition for each artifact must exactly match the original definition that was used for deployment.</span></span>  
  
 <span data-ttu-id="4b7e3-203">**示例**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-203">**Examples**</span></span>  
  
```  
bm.exe remove-all -DefinitionFile:MyDef.xml  
bm.exe remove-all -DefinitionFile:MyWorkbook.xls -Server:machine1  
```  
  
## <a name="update-livedataworkbook-command"></a><span data-ttu-id="4b7e3-204">update-livedataworkbook 命令</span><span class="sxs-lookup"><span data-stu-id="4b7e3-204">update-livedataworkbook Command</span></span>  
 <span data-ttu-id="4b7e3-205">**Usage**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-205">**Usage**</span></span>  
  
 <span data-ttu-id="4b7e3-206">**bm.exe update-livedataworkbook -Name:\<livedata workbook file name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-206">**bm.exe update-livedataworkbook -Name:\<livedata workbook file name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="4b7e3-207">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-207">**Parameters**</span></span>  
  
|<span data-ttu-id="4b7e3-208">参数</span><span class="sxs-lookup"><span data-stu-id="4b7e3-208">Parameter</span></span>|<span data-ttu-id="4b7e3-209">Description</span><span class="sxs-lookup"><span data-stu-id="4b7e3-209">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b7e3-210">名称：\<实时数据工作簿\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-210">Name:\<livedata workbook\></span></span>|<span data-ttu-id="4b7e3-211">要更新的现有实时工作簿的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-211">The name of the existing live workbook to update.</span></span>|  
|<span data-ttu-id="4b7e3-212">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-212">Server:\<server\></span></span>|<span data-ttu-id="4b7e3-213">可选：该工作簿所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-213">Optional: The name of the server on which the workbook resides.</span></span> <span data-ttu-id="4b7e3-214">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-214">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="4b7e3-215">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-215">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="4b7e3-216">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-216">Database:\<database\></span></span>|<span data-ttu-id="4b7e3-217">可选：该工作簿所驻留的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-217">Optional: The name of the database on which the workbook resides.</span></span> <span data-ttu-id="4b7e3-218">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-218">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="4b7e3-219">更新指定 BAM 实时数据工作簿中的 BAM 主导入数据库连接信息。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-219">Updates the BAM Primary Import database connection information in the specified BAM live data workbook.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b7e3-220">配置新的连接字符串时，必须重新启动 TDDS 服务，以确保服务识别出该更改。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-220">When configuring new connection string, you must restart the TDDS service to ensure that the service recognizes the change.</span></span> <span data-ttu-id="4b7e3-221">有关 TDDS 服务的详细信息，请参阅[BAM 事件总线服务存储过程](../core/bam-event-bus-service-stored-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-221">For more information on the TDDS service, see [BAM Event Bus Service Stored Procedures](../core/bam-event-bus-service-stored-procedures.md).</span></span>  
  
 <span data-ttu-id="4b7e3-222">**示例**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-222">**Examples**</span></span>  
  
```  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls  
bm.exe update-livedataworkbook -Name:SalesManager_Live.xls -Server:SalesSrv  
```  
  
## <a name="regenerate-livedataworkbook-command"></a><span data-ttu-id="4b7e3-223">regenerate-livedataworkbook 命令</span><span class="sxs-lookup"><span data-stu-id="4b7e3-223">regenerate-livedataworkbook Command</span></span>  
 <span data-ttu-id="4b7e3-224">**Usage**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-224">**Usage**</span></span>  
  
 <span data-ttu-id="4b7e3-225">**bm.exe regenerate-livedataworkbook -WorkbookName:\<livedata workbook file name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-225">**bm.exe regenerate-livedataworkbook -WorkbookName:\<livedata workbook file name\>[ -Server:\<server\> ][ -Database:\<database\> ]**</span></span>  
  
 <span data-ttu-id="4b7e3-226">**Parameters**</span><span class="sxs-lookup"><span data-stu-id="4b7e3-226">**Parameters**</span></span>  
  
|<span data-ttu-id="4b7e3-227">参数</span><span class="sxs-lookup"><span data-stu-id="4b7e3-227">Parameter</span></span>|<span data-ttu-id="4b7e3-228">Description</span><span class="sxs-lookup"><span data-stu-id="4b7e3-228">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b7e3-229">WorkbookName:\<实时数据工作簿文件名称\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-229">WorkbookName:\<livedata workbook file name\></span></span>|<span data-ttu-id="4b7e3-230">要更新的工作簿的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-230">The name of the workbook to update.</span></span>|  
|<span data-ttu-id="4b7e3-231">服务器：\<服务器\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-231">Server:\<server\></span></span>|<span data-ttu-id="4b7e3-232">可选：该工作簿所驻留的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-232">Optional: The name of the server on which the workbook resides.</span></span> <span data-ttu-id="4b7e3-233">服务器必须位于与运行 bm.exe 的计算机位于同一域中。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-233">The server must be in the same domain as the computer from which you are running bm.exe.</span></span> <span data-ttu-id="4b7e3-234">如果未指定服务器名称，则 bm.exe 将使用默认名称 localhost。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-234">If the server name is not specified, bm.exe uses the default name of localhost.</span></span>|  
|<span data-ttu-id="4b7e3-235">数据库：\<数据库\></span><span class="sxs-lookup"><span data-stu-id="4b7e3-235">Database:\<database\></span></span>|<span data-ttu-id="4b7e3-236">可选：该工作簿所驻留的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-236">Optional: The name of the database on which the workbook resides.</span></span> <span data-ttu-id="4b7e3-237">如果未指定名称，则 bm.exe 将使用默认名称 BamPrimaryImport。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-237">If the name is not specified, bm.exe uses the default name BamPrimaryImport.</span></span>|  
  
 <span data-ttu-id="4b7e3-238">生成 BAM 实时数据工作簿，但不部署该工作簿。</span><span class="sxs-lookup"><span data-stu-id="4b7e3-238">Generates a BAM live data workbook but does not deploy the workbook.</span></span>  
  
 <span data-ttu-id="4b7e3-239">示例</span><span class="sxs-lookup"><span data-stu-id="4b7e3-239">Examples</span></span>  
  
```  
bm.exe regenerate-livedataworkbook -WorkbookName:SalesManager_Live.xls  
bm.exe regenerate-livedataworkbook -WorkbookName:SM_Live.xls -Server:S1  
```  
  
## <a name="see-also"></a><span data-ttu-id="4b7e3-240">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b7e3-240">See Also</span></span>  
 [<span data-ttu-id="4b7e3-241">BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="4b7e3-241">BAM Management Utility</span></span>](../core/bam-management-utility.md)
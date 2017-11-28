---
title: "使用策略资源管理器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, Policy Explorer
- policies, Policy Explorer
- business rules, Policy Explorer
- Policy Explorer [Business Rule Composer]
ms.assetid: 249b1b72-ba84-4695-ba2b-16f081710b20
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 66b88618f10bf204701e6fcd68d7d95007966c50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-policy-explorer"></a><span data-ttu-id="92aa4-102">使用策略资源管理器</span><span class="sxs-lookup"><span data-stu-id="92aa4-102">Using Policy Explorer</span></span>
<span data-ttu-id="92aa4-103">使用策略浏览器可以管理规则存储中的策略和规则。</span><span class="sxs-lookup"><span data-stu-id="92aa4-103">You can use the Policy Explorer to manage policies and rules in the rule store.</span></span> <span data-ttu-id="92aa4-104">可以创建、修改和删除策略和规则，也可以测试、发布、部署和取消部署策略。</span><span class="sxs-lookup"><span data-stu-id="92aa4-104">You can create, modify, and delete policies and rules, and you can test, publish, deploy, and undeploy policies.</span></span>  
  
 <span data-ttu-id="92aa4-105">下表对策略浏览器中可在开发新策略和规则的过程中使用的命令进行了说明：</span><span class="sxs-lookup"><span data-stu-id="92aa4-105">The following table describes the commands within the Policy Explorer that can be used in the process of developing new policies and rules.</span></span>  
  
|<span data-ttu-id="92aa4-106">使用此选项</span><span class="sxs-lookup"><span data-stu-id="92aa4-106">Use this</span></span>|<span data-ttu-id="92aa4-107">执行的操作</span><span class="sxs-lookup"><span data-stu-id="92aa4-107">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="92aa4-108">**添加新策略**</span><span class="sxs-lookup"><span data-stu-id="92aa4-108">**Add New Policy**</span></span>|<span data-ttu-id="92aa4-109">创建新的策略（规则集）。</span><span class="sxs-lookup"><span data-stu-id="92aa4-109">Create a new policy (rule set).</span></span>|  
|<span data-ttu-id="92aa4-110">**添加新的版本**</span><span class="sxs-lookup"><span data-stu-id="92aa4-110">**Add New Version**</span></span>|<span data-ttu-id="92aa4-111">新建所选策略的空版本。</span><span class="sxs-lookup"><span data-stu-id="92aa4-111">Create a new empty version of the selected policy.</span></span> <span data-ttu-id="92aa4-112">可以从其他版本复制规则并将它们粘贴到新版本中。</span><span class="sxs-lookup"><span data-stu-id="92aa4-112">You can copy rules from other versions and paste them into the new version.</span></span>|  
|<span data-ttu-id="92aa4-113">**副本 （策略版本）**</span><span class="sxs-lookup"><span data-stu-id="92aa4-113">**Copy (Policy Version)**</span></span>|<span data-ttu-id="92aa4-114">将所选策略版本复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="92aa4-114">Copy the selected policy version to the Clipboard.</span></span>|  
|<span data-ttu-id="92aa4-115">**副本 （规则）**</span><span class="sxs-lookup"><span data-stu-id="92aa4-115">**Copy (Rule)**</span></span>|<span data-ttu-id="92aa4-116">将所选规则复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="92aa4-116">Copy the selected rule to the Clipboard.</span></span>|  
|<span data-ttu-id="92aa4-117">**剪切 （规则）**</span><span class="sxs-lookup"><span data-stu-id="92aa4-117">**Cut (Rule)**</span></span>|<span data-ttu-id="92aa4-118">将所选规则复制到剪贴板并将其删除。</span><span class="sxs-lookup"><span data-stu-id="92aa4-118">Copy the selected rule to the Clipboard and delete it.</span></span>|  
|<span data-ttu-id="92aa4-119">**粘贴 （策略版本）**</span><span class="sxs-lookup"><span data-stu-id="92aa4-119">**Paste (Policy Version)**</span></span>|<span data-ttu-id="92aa4-120">将策略版本及其内容粘贴到所选策略中。</span><span class="sxs-lookup"><span data-stu-id="92aa4-120">Paste a policy version and its contents into a selected policy.</span></span>|  
|<span data-ttu-id="92aa4-121">**粘贴 （规则）**</span><span class="sxs-lookup"><span data-stu-id="92aa4-121">**Paste (Rule)**</span></span>|<span data-ttu-id="92aa4-122">将规则粘贴到所选策略版本中。</span><span class="sxs-lookup"><span data-stu-id="92aa4-122">Paste a rule into the selected policy version.</span></span>|  
|<span data-ttu-id="92aa4-123">**删除 （策略版本）**</span><span class="sxs-lookup"><span data-stu-id="92aa4-123">**Delete (Policy Version)**</span></span>|<span data-ttu-id="92aa4-124">删除所选策略版本。</span><span class="sxs-lookup"><span data-stu-id="92aa4-124">Delete the selected policy version.</span></span>|  
|<span data-ttu-id="92aa4-125">**删除 （规则）**</span><span class="sxs-lookup"><span data-stu-id="92aa4-125">**Delete (Rule)**</span></span>|<span data-ttu-id="92aa4-126">删除所选规则。</span><span class="sxs-lookup"><span data-stu-id="92aa4-126">Delete the selected rule.</span></span>|  
|<span data-ttu-id="92aa4-127">**删除**</span><span class="sxs-lookup"><span data-stu-id="92aa4-127">**Delete**</span></span>|<span data-ttu-id="92aa4-128">删除所选策略及其所有版本。</span><span class="sxs-lookup"><span data-stu-id="92aa4-128">Delete the selected policy and all its versions.</span></span>|  
|<span data-ttu-id="92aa4-129">**添加新规则**</span><span class="sxs-lookup"><span data-stu-id="92aa4-129">**Add New Rule**</span></span>|<span data-ttu-id="92aa4-130">在所选策略版本中创建新规则。</span><span class="sxs-lookup"><span data-stu-id="92aa4-130">Create a new rule in the selected policy version.</span></span>|  
|<span data-ttu-id="92aa4-131">**保存**</span><span class="sxs-lookup"><span data-stu-id="92aa4-131">**Save**</span></span>|<span data-ttu-id="92aa4-132">保存对所选版本及其规则所做的所有更改。</span><span class="sxs-lookup"><span data-stu-id="92aa4-132">Save any changes made to the selected version and its rules.</span></span>|  
|<span data-ttu-id="92aa4-133">**发布**</span><span class="sxs-lookup"><span data-stu-id="92aa4-133">**Publish**</span></span>|<span data-ttu-id="92aa4-134">发布所选的策略版本。</span><span class="sxs-lookup"><span data-stu-id="92aa4-134">Publish the selected policy version.</span></span> <span data-ttu-id="92aa4-135">请注意，不能直接修改已发布的版本。</span><span class="sxs-lookup"><span data-stu-id="92aa4-135">Note that you cannot directly modify a published version.</span></span> <span data-ttu-id="92aa4-136">可以将其复制并粘贴到新的策略版本中。</span><span class="sxs-lookup"><span data-stu-id="92aa4-136">You can copy and paste it to a new version on the policy.</span></span>|  
|<span data-ttu-id="92aa4-137">**重新加载**</span><span class="sxs-lookup"><span data-stu-id="92aa4-137">**Reload**</span></span>|<span data-ttu-id="92aa4-138">重新加载所选策略版本及其规则，可以选择放弃当前对该版本所做的全部更改和从规则存储恢复内容。</span><span class="sxs-lookup"><span data-stu-id="92aa4-138">Reload the selected policy version and its rules, with the option to discard any current changes made in that version and restore the contents from the rule store.</span></span>|  
|<span data-ttu-id="92aa4-139">**部署**</span><span class="sxs-lookup"><span data-stu-id="92aa4-139">**Deploy**</span></span>|<span data-ttu-id="92aa4-140">部署已发布的策略版本。</span><span class="sxs-lookup"><span data-stu-id="92aa4-140">Deploy a published policy version.</span></span> <span data-ttu-id="92aa4-141">必须在部署策略版本后，基于规则的应用程序才能使用它。</span><span class="sxs-lookup"><span data-stu-id="92aa4-141">You must deploy a policy version to make it available to rule-based applications.</span></span>|  
|<span data-ttu-id="92aa4-142">**取消部署**</span><span class="sxs-lookup"><span data-stu-id="92aa4-142">**Undeploy**</span></span>|<span data-ttu-id="92aa4-143">取消部署策略版本。</span><span class="sxs-lookup"><span data-stu-id="92aa4-143">Undeploy a policy version.</span></span> <span data-ttu-id="92aa4-144">取消部署一个版本后，基于规则的应用程序就不能继续使用它。</span><span class="sxs-lookup"><span data-stu-id="92aa4-144">After a version is undeployed, it is no longer available to rule-based applications.</span></span>|  
|<span data-ttu-id="92aa4-145">**测试策略**</span><span class="sxs-lookup"><span data-stu-id="92aa4-145">**Test Policy**</span></span>|<span data-ttu-id="92aa4-146">在部署前测试所选的策略版本。</span><span class="sxs-lookup"><span data-stu-id="92aa4-146">Test the selected policy version before deployment.</span></span>|  
  
## <a name="properties-window"></a><span data-ttu-id="92aa4-147">属性窗口</span><span class="sxs-lookup"><span data-stu-id="92aa4-147">Properties window</span></span>  
 <span data-ttu-id="92aa4-148">下表对策略版本的属性进行了说明：</span><span class="sxs-lookup"><span data-stu-id="92aa4-148">The following table describes the properties for a policy version.</span></span>  
  
|<span data-ttu-id="92aa4-149">属性</span><span class="sxs-lookup"><span data-stu-id="92aa4-149">Property</span></span>|<span data-ttu-id="92aa4-150">值</span><span class="sxs-lookup"><span data-stu-id="92aa4-150">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="92aa4-151">**名称**</span><span class="sxs-lookup"><span data-stu-id="92aa4-151">**Name**</span></span>|<span data-ttu-id="92aa4-152">策略的名称。</span><span class="sxs-lookup"><span data-stu-id="92aa4-152">Name of the policy.</span></span><br /><br /> <span data-ttu-id="92aa4-153">仅可以通过更改来更改此值**名称**的策略 （而非策略版本） 的属性。</span><span class="sxs-lookup"><span data-stu-id="92aa4-153">You can only change this value by changing the **Name** property of the policy (not policy version).</span></span>|  
|<span data-ttu-id="92aa4-154">**事实检索器**</span><span class="sxs-lookup"><span data-stu-id="92aa4-154">**Fact Retriever**</span></span>|<span data-ttu-id="92aa4-155">有关策略版本的事实检索器的信息。</span><span class="sxs-lookup"><span data-stu-id="92aa4-155">Information about the fact retriever for the policy version.</span></span>|  
|<span data-ttu-id="92aa4-156">**最大执行循环深度**</span><span class="sxs-lookup"><span data-stu-id="92aa4-156">**Maximum Execution Loop Depth**</span></span>|<span data-ttu-id="92aa4-157">引发执行循环异常前允许的最大正向链接算法深度。</span><span class="sxs-lookup"><span data-stu-id="92aa4-157">Maximum depth of the forward-chaining algorithm before an execution loop exception is thrown.</span></span><br /><br /> <span data-ttu-id="92aa4-158">默认的循环次数是 65536。</span><span class="sxs-lookup"><span data-stu-id="92aa4-158">The default loop count is 65536.</span></span>|  
|<span data-ttu-id="92aa4-159">**转换持续时间**</span><span class="sxs-lookup"><span data-stu-id="92aa4-159">**Translation Duration**</span></span>|<span data-ttu-id="92aa4-160">引发转换超时异常前允许的最长规则转换时间。</span><span class="sxs-lookup"><span data-stu-id="92aa4-160">Maximum amount of time to translate the rules before a translation time-out exception is thrown.</span></span><br /><br /> <span data-ttu-id="92aa4-161">默认值为 60000 毫秒。</span><span class="sxs-lookup"><span data-stu-id="92aa4-161">The default is 60000 milliseconds.</span></span>|  
|<span data-ttu-id="92aa4-162">**在线翻译**</span><span class="sxs-lookup"><span data-stu-id="92aa4-162">**Translator**</span></span>|<span data-ttu-id="92aa4-163">有关用于转换规则的转换器的信息。</span><span class="sxs-lookup"><span data-stu-id="92aa4-163">Information about the translator used to translate the rules.</span></span>|  
|<span data-ttu-id="92aa4-164">**当前版本**</span><span class="sxs-lookup"><span data-stu-id="92aa4-164">**Current Version**</span></span>|<span data-ttu-id="92aa4-165">在策略浏览器中当前所选的策略的版本。</span><span class="sxs-lookup"><span data-stu-id="92aa4-165">The version of policy currently selected in the Policy Explorer.</span></span>|  
|<span data-ttu-id="92aa4-166">**版本说明**</span><span class="sxs-lookup"><span data-stu-id="92aa4-166">**Version Description**</span></span>|<span data-ttu-id="92aa4-167">当前版本的说明。</span><span class="sxs-lookup"><span data-stu-id="92aa4-167">The description of the current version.</span></span>|  
  
 <span data-ttu-id="92aa4-168">下表对规则的属性进行了说明：</span><span class="sxs-lookup"><span data-stu-id="92aa4-168">The following table describes the properties for a rule.</span></span>  
  
|<span data-ttu-id="92aa4-169">属性</span><span class="sxs-lookup"><span data-stu-id="92aa4-169">Property</span></span>|<span data-ttu-id="92aa4-170">值</span><span class="sxs-lookup"><span data-stu-id="92aa4-170">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="92aa4-171">**在职**</span><span class="sxs-lookup"><span data-stu-id="92aa4-171">**Active**</span></span>|<span data-ttu-id="92aa4-172">指示规则是启用状态还是禁用状态</span><span class="sxs-lookup"><span data-stu-id="92aa4-172">Indicates whether the rule is enabled or disabled</span></span>|  
|<span data-ttu-id="92aa4-173">**名称**</span><span class="sxs-lookup"><span data-stu-id="92aa4-173">**Name**</span></span>|<span data-ttu-id="92aa4-174">规则的名称。</span><span class="sxs-lookup"><span data-stu-id="92aa4-174">Name of the rule.</span></span>|  
|<span data-ttu-id="92aa4-175">**Priority**</span><span class="sxs-lookup"><span data-stu-id="92aa4-175">**Priority**</span></span>|<span data-ttu-id="92aa4-176">策略中规则的优先级。</span><span class="sxs-lookup"><span data-stu-id="92aa4-176">Priority of the rule within the policy.</span></span> <span data-ttu-id="92aa4-177">索引越高，规则优先级就越高。</span><span class="sxs-lookup"><span data-stu-id="92aa4-177">The higher the index, the higher the rule priority.</span></span> <span data-ttu-id="92aa4-178">较高优先级规则的操作将首先触发。</span><span class="sxs-lookup"><span data-stu-id="92aa4-178">Actions of a higher priority rule will fire first.</span></span><br /><br /> <span data-ttu-id="92aa4-179">默认值是 0，表示中等优先级。</span><span class="sxs-lookup"><span data-stu-id="92aa4-179">The default is 0 and represents the middle priority.</span></span>|
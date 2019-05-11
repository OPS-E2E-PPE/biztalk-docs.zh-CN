---
title: 使用策略浏览器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, Policy Explorer
- policies, Policy Explorer
- business rules, Policy Explorer
- Policy Explorer [Business Rule Composer]
ms.assetid: 249b1b72-ba84-4695-ba2b-16f081710b20
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77c1366f47b16f48fdd362a83e5b63219a352933
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396569"
---
# <a name="using-policy-explorer"></a><span data-ttu-id="c1cf6-102">使用策略浏览器</span><span class="sxs-lookup"><span data-stu-id="c1cf6-102">Using Policy Explorer</span></span>
<span data-ttu-id="c1cf6-103">策略浏览器可用于管理策略和规则存储中的规则。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-103">You can use the Policy Explorer to manage policies and rules in the rule store.</span></span> <span data-ttu-id="c1cf6-104">您可以创建、 修改和删除策略和规则，并可以测试、 发布、 部署和取消部署策略。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-104">You can create, modify, and delete policies and rules, and you can test, publish, deploy, and undeploy policies.</span></span>  
  
 <span data-ttu-id="c1cf6-105">下表介绍可以在开发新的策略和规则过程中使用策略浏览器中的命令。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-105">The following table describes the commands within the Policy Explorer that can be used in the process of developing new policies and rules.</span></span>  
  
|<span data-ttu-id="c1cf6-106">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c1cf6-106">Use this</span></span>|<span data-ttu-id="c1cf6-107">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c1cf6-107">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="c1cf6-108">**添加新策略**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-108">**Add New Policy**</span></span>|<span data-ttu-id="c1cf6-109">创建新的策略 （规则集）。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-109">Create a new policy (rule set).</span></span>|  
|<span data-ttu-id="c1cf6-110">**添加新版本**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-110">**Add New Version**</span></span>|<span data-ttu-id="c1cf6-111">创建所选策略的新空版本。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-111">Create a new empty version of the selected policy.</span></span> <span data-ttu-id="c1cf6-112">可以从其他版本复制规则并将其粘贴到新版本。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-112">You can copy rules from other versions and paste them into the new version.</span></span>|  
|<span data-ttu-id="c1cf6-113">**复制 （策略版本）**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-113">**Copy (Policy Version)**</span></span>|<span data-ttu-id="c1cf6-114">将所选的策略版本复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-114">Copy the selected policy version to the Clipboard.</span></span>|  
|<span data-ttu-id="c1cf6-115">**复制 （规则）**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-115">**Copy (Rule)**</span></span>|<span data-ttu-id="c1cf6-116">将所选的规则复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-116">Copy the selected rule to the Clipboard.</span></span>|  
|<span data-ttu-id="c1cf6-117">**剪切 （规则）**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-117">**Cut (Rule)**</span></span>|<span data-ttu-id="c1cf6-118">将所选的规则复制到剪贴板并将其删除。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-118">Copy the selected rule to the Clipboard and delete it.</span></span>|  
|<span data-ttu-id="c1cf6-119">**粘贴 （策略版本）**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-119">**Paste (Policy Version)**</span></span>|<span data-ttu-id="c1cf6-120">将策略版本和其内容粘贴到所选的策略。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-120">Paste a policy version and its contents into a selected policy.</span></span>|  
|<span data-ttu-id="c1cf6-121">**粘贴 （规则）**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-121">**Paste (Rule)**</span></span>|<span data-ttu-id="c1cf6-122">将规则粘贴到所选的策略版本。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-122">Paste a rule into the selected policy version.</span></span>|  
|<span data-ttu-id="c1cf6-123">**删除 （策略版本）**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-123">**Delete (Policy Version)**</span></span>|<span data-ttu-id="c1cf6-124">删除所选的策略版本。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-124">Delete the selected policy version.</span></span>|  
|<span data-ttu-id="c1cf6-125">**删除 （规则）**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-125">**Delete (Rule)**</span></span>|<span data-ttu-id="c1cf6-126">删除所选的规则。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-126">Delete the selected rule.</span></span>|  
|<span data-ttu-id="c1cf6-127">**删除**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-127">**Delete**</span></span>|<span data-ttu-id="c1cf6-128">删除所选的策略及其所有版本。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-128">Delete the selected policy and all its versions.</span></span>|  
|<span data-ttu-id="c1cf6-129">**添加新规则**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-129">**Add New Rule**</span></span>|<span data-ttu-id="c1cf6-130">在所选的策略版本中创建新的规则。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-130">Create a new rule in the selected policy version.</span></span>|  
|<span data-ttu-id="c1cf6-131">**保存**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-131">**Save**</span></span>|<span data-ttu-id="c1cf6-132">保存对所选的版本及其规则所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-132">Save any changes made to the selected version and its rules.</span></span>|  
|<span data-ttu-id="c1cf6-133">**Publish**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-133">**Publish**</span></span>|<span data-ttu-id="c1cf6-134">发布所选的策略版本。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-134">Publish the selected policy version.</span></span> <span data-ttu-id="c1cf6-135">请注意，不能直接修改已发布的版本。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-135">Note that you cannot directly modify a published version.</span></span> <span data-ttu-id="c1cf6-136">可以复制并将其粘贴到新版本的策略。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-136">You can copy and paste it to a new version on the policy.</span></span>|  
|<span data-ttu-id="c1cf6-137">**重新加载**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-137">**Reload**</span></span>|<span data-ttu-id="c1cf6-138">重新加载所选的策略版本及其规则，可以选择放弃当前对该版本所做的全部更改和从规则存储恢复内容。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-138">Reload the selected policy version and its rules, with the option to discard any current changes made in that version and restore the contents from the rule store.</span></span>|  
|<span data-ttu-id="c1cf6-139">**部署**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-139">**Deploy**</span></span>|<span data-ttu-id="c1cf6-140">部署已发布的策略版本。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-140">Deploy a published policy version.</span></span> <span data-ttu-id="c1cf6-141">您必须部署策略版本，以使其可供基于规则的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-141">You must deploy a policy version to make it available to rule-based applications.</span></span>|  
|<span data-ttu-id="c1cf6-142">**Undeploy**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-142">**Undeploy**</span></span>|<span data-ttu-id="c1cf6-143">取消部署策略版本。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-143">Undeploy a policy version.</span></span> <span data-ttu-id="c1cf6-144">已取消部署的版本后，就不再可用于基于规则的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-144">After a version is undeployed, it is no longer available to rule-based applications.</span></span>|  
|<span data-ttu-id="c1cf6-145">**测试策略**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-145">**Test Policy**</span></span>|<span data-ttu-id="c1cf6-146">测试之前部署的所选的策略版本。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-146">Test the selected policy version before deployment.</span></span>|  
  
## <a name="properties-window"></a><span data-ttu-id="c1cf6-147">属性窗口</span><span class="sxs-lookup"><span data-stu-id="c1cf6-147">Properties window</span></span>  
 <span data-ttu-id="c1cf6-148">下表介绍用于将策略版本属性。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-148">The following table describes the properties for a policy version.</span></span>  
  
|<span data-ttu-id="c1cf6-149">属性</span><span class="sxs-lookup"><span data-stu-id="c1cf6-149">Property</span></span>|<span data-ttu-id="c1cf6-150">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="c1cf6-150">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="c1cf6-151">**名称**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-151">**Name**</span></span>|<span data-ttu-id="c1cf6-152">策略的名称。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-152">Name of the policy.</span></span><br /><br /> <span data-ttu-id="c1cf6-153">您可以只更改此值，通过更改**名称**策略 （不是策略版本） 的属性。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-153">You can only change this value by changing the **Name** property of the policy (not policy version).</span></span>|  
|<span data-ttu-id="c1cf6-154">**事实检索器**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-154">**Fact Retriever**</span></span>|<span data-ttu-id="c1cf6-155">有关策略版本的事实检索器的信息。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-155">Information about the fact retriever for the policy version.</span></span>|  
|<span data-ttu-id="c1cf6-156">**最大执行循环深度**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-156">**Maximum Execution Loop Depth**</span></span>|<span data-ttu-id="c1cf6-157">正向链接算法引发执行循环异常前的最大深度。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-157">Maximum depth of the forward-chaining algorithm before an execution loop exception is thrown.</span></span><br /><br /> <span data-ttu-id="c1cf6-158">默认的循环次数是 65536。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-158">The default loop count is 65536.</span></span>|  
|<span data-ttu-id="c1cf6-159">**转换持续时间**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-159">**Translation Duration**</span></span>|<span data-ttu-id="c1cf6-160">最长时间之前转换超时异常规则转换会引发。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-160">Maximum amount of time to translate the rules before a translation time-out exception is thrown.</span></span><br /><br /> <span data-ttu-id="c1cf6-161">默认值为 60000 毫秒。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-161">The default is 60000 milliseconds.</span></span>|  
|<span data-ttu-id="c1cf6-162">**在线翻译**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-162">**Translator**</span></span>|<span data-ttu-id="c1cf6-163">有关转换器用于将转换规则的信息。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-163">Information about the translator used to translate the rules.</span></span>|  
|<span data-ttu-id="c1cf6-164">**当前版本**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-164">**Current Version**</span></span>|<span data-ttu-id="c1cf6-165">策略浏览器中当前所选策略版本。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-165">The version of policy currently selected in the Policy Explorer.</span></span>|  
|<span data-ttu-id="c1cf6-166">**版本说明**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-166">**Version Description**</span></span>|<span data-ttu-id="c1cf6-167">当前版本的说明。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-167">The description of the current version.</span></span>|  
  
 <span data-ttu-id="c1cf6-168">下表介绍的规则的属性。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-168">The following table describes the properties for a rule.</span></span>  
  
|<span data-ttu-id="c1cf6-169">属性</span><span class="sxs-lookup"><span data-stu-id="c1cf6-169">Property</span></span>|<span data-ttu-id="c1cf6-170">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="c1cf6-170">Value</span></span>|  
|--------------|-----------|  
|<span data-ttu-id="c1cf6-171">**在职**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-171">**Active**</span></span>|<span data-ttu-id="c1cf6-172">指示是否启用或禁用规则</span><span class="sxs-lookup"><span data-stu-id="c1cf6-172">Indicates whether the rule is enabled or disabled</span></span>|  
|<span data-ttu-id="c1cf6-173">**名称**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-173">**Name**</span></span>|<span data-ttu-id="c1cf6-174">规则的名称。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-174">Name of the rule.</span></span>|  
|<span data-ttu-id="c1cf6-175">**Priority**</span><span class="sxs-lookup"><span data-stu-id="c1cf6-175">**Priority**</span></span>|<span data-ttu-id="c1cf6-176">在策略中规则的优先级。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-176">Priority of the rule within the policy.</span></span> <span data-ttu-id="c1cf6-177">索引越高，规则优先级越高。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-177">The higher the index, the higher the rule priority.</span></span> <span data-ttu-id="c1cf6-178">更高的优先级规则的操作将首先触发。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-178">Actions of a higher priority rule will fire first.</span></span><br /><br /> <span data-ttu-id="c1cf6-179">默认值为 0，表示中等优先级。</span><span class="sxs-lookup"><span data-stu-id="c1cf6-179">The default is 0 and represents the middle priority.</span></span>|
---
title: "使用 PIP 规范创建过程配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PIPs, PIP settings
- PIPs, PIP secifications
- process configuration, PIPs
- PIPs, process configuration
ms.assetid: 64f0f5fb-f880-4ef1-95d7-2575b8d0bcff
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 777f32e5a9e035f6009f5450eb48ae8286159f05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-pip-specification-to-create-a-process-configuration"></a><span data-ttu-id="d2100-102">使用 PIP 规范创建过程配置</span><span class="sxs-lookup"><span data-stu-id="d2100-102">Using the PIP Specification to Create a Process Configuration</span></span>
<span data-ttu-id="d2100-103">从 RosettaNet 组织 （从 RosettaNet.org) 下载伙伴接口过程 (PIP) 后，下载包包括 PIP 规范文档。</span><span class="sxs-lookup"><span data-stu-id="d2100-103">After you download a Partner Interface Process (PIP) from the RosettaNet organization (from RosettaNet.org), the download package includes a PIP specification document.</span></span> <span data-ttu-id="d2100-104">本文档包含要在创建中的过程配置时使用哪些设置的指导[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="d2100-104">This document contains guidance on what settings to use when you create a process configuration in the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console.</span></span>  
  
## <a name="how-pip-settings-map-to-the-pip-specification"></a><span data-ttu-id="d2100-105">如何 PIP 设置映射到 PIP 规范</span><span class="sxs-lookup"><span data-stu-id="d2100-105">How PIP Settings Map to the PIP Specification</span></span>  
 <span data-ttu-id="d2100-106">下表介绍 PIP 设置如何映射到 RosettaNet PIP 规范中的信息。</span><span class="sxs-lookup"><span data-stu-id="d2100-106">The following table describes how PIP settings map to information in the RosettaNet PIP specification.</span></span>  
  
|<span data-ttu-id="d2100-107">过程配置设置</span><span class="sxs-lookup"><span data-stu-id="d2100-107">Process Configuration setting</span></span>|<span data-ttu-id="d2100-108">PIP 规范中的信息</span><span class="sxs-lookup"><span data-stu-id="d2100-108">Information in the PIP specification</span></span>|  
|-----------------------------------|------------------------------------------|  
|<span data-ttu-id="d2100-109">进程代码</span><span class="sxs-lookup"><span data-stu-id="d2100-109">Process Code</span></span>|<span data-ttu-id="d2100-110">在标题页上，例如，"PIP3A4"副标题</span><span class="sxs-lookup"><span data-stu-id="d2100-110">Subheading on the title page, for example, "PIP3A4"</span></span>|  
|<span data-ttu-id="d2100-111">版本</span><span class="sxs-lookup"><span data-stu-id="d2100-111">Version</span></span>|<span data-ttu-id="d2100-112">在标题页上，例如，"02.02.00"PIP 版本标识符副标题</span><span class="sxs-lookup"><span data-stu-id="d2100-112">PIP Version Identifier subheading on the title page, for example, "02.02.00"</span></span>|  
|<span data-ttu-id="d2100-113">进程名称</span><span class="sxs-lookup"><span data-stu-id="d2100-113">Process name</span></span>|<span data-ttu-id="d2100-114">在标题页上，例如，"请求采购订单"副标题</span><span class="sxs-lookup"><span data-stu-id="d2100-114">Subheading on the title page, for example, "Request Purchase Order"</span></span>|  
|<span data-ttu-id="d2100-115">说明 （常规选项卡）</span><span class="sxs-lookup"><span data-stu-id="d2100-115">Description (General tab)</span></span>|<span data-ttu-id="d2100-116">第 3.1 节业务过程定义</span><span class="sxs-lookup"><span data-stu-id="d2100-116">Section 3.1, Business Process Definition</span></span>|  
|<span data-ttu-id="d2100-117">不可否认性所需</span><span class="sxs-lookup"><span data-stu-id="d2100-117">Non-Repudiation Required</span></span>|<span data-ttu-id="d2100-118">表 3-3： 业务活动性能控件</span><span class="sxs-lookup"><span data-stu-id="d2100-118">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="d2100-119">时间以确认 （秒）</span><span class="sxs-lookup"><span data-stu-id="d2100-119">Time to Acknowledge (Seconds)</span></span>|<span data-ttu-id="d2100-120">表 3-3： 业务活动性能控件</span><span class="sxs-lookup"><span data-stu-id="d2100-120">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="d2100-121">是否要求授权？</span><span class="sxs-lookup"><span data-stu-id="d2100-121">Is Authorization Required?</span></span>|<span data-ttu-id="d2100-122">表 3-3： 业务活动性能控件</span><span class="sxs-lookup"><span data-stu-id="d2100-122">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="d2100-123">要求永久保密</span><span class="sxs-lookup"><span data-stu-id="d2100-123">Is Persistent Confidentiality Required</span></span>|<span data-ttu-id="d2100-124">（PIP 规范中未引用）</span><span class="sxs-lookup"><span data-stu-id="d2100-124">(No reference from the PIP specification)</span></span>|  
|<span data-ttu-id="d2100-125">是所需的安全传输？</span><span class="sxs-lookup"><span data-stu-id="d2100-125">Is Secure Transport Required?</span></span>|<span data-ttu-id="d2100-126">表 4-3： 消息 Exchange 控件</span><span class="sxs-lookup"><span data-stu-id="d2100-126">Table 4-3: Message Exchange Controls</span></span>|  
|<span data-ttu-id="d2100-127">是单个操作</span><span class="sxs-lookup"><span data-stu-id="d2100-127">Is Single Action</span></span>|<span data-ttu-id="d2100-128">部分 4.3，业务事务对话框规范</span><span class="sxs-lookup"><span data-stu-id="d2100-128">Section 4.3, Business Transaction Dialog Specification</span></span>|  
|<span data-ttu-id="d2100-129">不可否认性的源和内容</span><span class="sxs-lookup"><span data-stu-id="d2100-129">Non-Repudiation of Origin and Content</span></span>|<span data-ttu-id="d2100-130">表 3-3： 业务活动性能控件</span><span class="sxs-lookup"><span data-stu-id="d2100-130">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="d2100-131">重试计数</span><span class="sxs-lookup"><span data-stu-id="d2100-131">Retry Count</span></span>|<span data-ttu-id="d2100-132">表 3-3： 业务活动性能控件</span><span class="sxs-lookup"><span data-stu-id="d2100-132">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="d2100-133">执行时间</span><span class="sxs-lookup"><span data-stu-id="d2100-133">Time to Perform</span></span>|<span data-ttu-id="d2100-134">表 3-3： 业务活动性能控件</span><span class="sxs-lookup"><span data-stu-id="d2100-134">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="d2100-135">Name</span><span class="sxs-lookup"><span data-stu-id="d2100-135">Name</span></span>|<span data-ttu-id="d2100-136">表 3-3： 业务活动性能控件 （活动名称）</span><span class="sxs-lookup"><span data-stu-id="d2100-136">Table 3-3: Business Activity Performance Controls (Activity Name)</span></span>|  
|<span data-ttu-id="d2100-137">类型</span><span class="sxs-lookup"><span data-stu-id="d2100-137">Type</span></span>|<span data-ttu-id="d2100-138">（从 PIP 规格-供以后使用未引用）</span><span class="sxs-lookup"><span data-stu-id="d2100-138">(No reference from the PIP specification - for future use)</span></span>|  
|<span data-ttu-id="d2100-139">说明 （发起方和响应选项卡）</span><span class="sxs-lookup"><span data-stu-id="d2100-139">Description (Initiator and Response tabs)</span></span>|<span data-ttu-id="d2100-140">表 3-4: PIP 商业文档</span><span class="sxs-lookup"><span data-stu-id="d2100-140">Table 3-4: PIP Business Documents</span></span>|  
|<span data-ttu-id="d2100-141">名称 （发起方和响应选项卡）</span><span class="sxs-lookup"><span data-stu-id="d2100-141">Name (Initiator and Response tabs)</span></span>|<span data-ttu-id="d2100-142">表 3-4: PIP 商业文档</span><span class="sxs-lookup"><span data-stu-id="d2100-142">Table 3-4: PIP Business Documents</span></span>|  
|<span data-ttu-id="d2100-143">角色 （发起方和响应选项卡）</span><span class="sxs-lookup"><span data-stu-id="d2100-143">Role (Initiator and Response tabs)</span></span>|<span data-ttu-id="d2100-144">表 3-1： 伙伴角色描述</span><span class="sxs-lookup"><span data-stu-id="d2100-144">Table 3-1: Partner Role Descriptions</span></span>|  
|<span data-ttu-id="d2100-145">角色描述 （发起方和响应选项卡）</span><span class="sxs-lookup"><span data-stu-id="d2100-145">Role Description (Initiator and Response tabs)</span></span>|<span data-ttu-id="d2100-146">表 3-1： 伙伴角色描述</span><span class="sxs-lookup"><span data-stu-id="d2100-146">Table 3-1: Partner Role Descriptions</span></span>|  
|<span data-ttu-id="d2100-147">角色类型 （发起方和响应选项卡）</span><span class="sxs-lookup"><span data-stu-id="d2100-147">Role Type (Initiator and Response tabs)</span></span>|<span data-ttu-id="d2100-148">表 3-1： 伙伴角色描述</span><span class="sxs-lookup"><span data-stu-id="d2100-148">Table 3-1: Partner Role Descriptions</span></span>|  
|<span data-ttu-id="d2100-149">服务</span><span class="sxs-lookup"><span data-stu-id="d2100-149">Service</span></span>|<span data-ttu-id="d2100-150">表 4-1： 网络组件规范</span><span class="sxs-lookup"><span data-stu-id="d2100-150">Table 4-1: Network Component Specification</span></span>|  
|<span data-ttu-id="d2100-151">服务分类</span><span class="sxs-lookup"><span data-stu-id="d2100-151">Service Classification</span></span>|<span data-ttu-id="d2100-152">表 4-1： 网络组件规范</span><span class="sxs-lookup"><span data-stu-id="d2100-152">Table 4-1: Network Component Specification</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2100-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2100-153">See Also</span></span>  
 [<span data-ttu-id="d2100-154">如何创建或编辑过程配置</span><span class="sxs-lookup"><span data-stu-id="d2100-154">How to Create or Edit a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)
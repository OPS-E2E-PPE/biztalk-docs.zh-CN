---
title: 使用 PIP 规范创建流程配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, PIP settings
- PIPs, PIP secifications
- process configuration, PIPs
- PIPs, process configuration
ms.assetid: 64f0f5fb-f880-4ef1-95d7-2575b8d0bcff
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21933797f37b32a4131c57181829f2380bafe061
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299915"
---
# <a name="using-the-pip-specification-to-create-a-process-configuration"></a><span data-ttu-id="aa0b7-102">使用 PIP 规范创建流程配置</span><span class="sxs-lookup"><span data-stu-id="aa0b7-102">Using the PIP Specification to Create a Process Configuration</span></span>
<span data-ttu-id="aa0b7-103">从 RosettaNet 组织 （从 rosettanet.org 下载得到） 下载合作伙伴接口流程 (PIP) 后，下载包包括 PIP 规范文档。</span><span class="sxs-lookup"><span data-stu-id="aa0b7-103">After you download a Partner Interface Process (PIP) from the RosettaNet organization (from RosettaNet.org), the download package includes a PIP specification document.</span></span> <span data-ttu-id="aa0b7-104">本文档包含有关要创建在流程配置时使用哪些设置[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="aa0b7-104">This document contains guidance on what settings to use when you create a process configuration in the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console.</span></span>  
  
## <a name="how-pip-settings-map-to-the-pip-specification"></a><span data-ttu-id="aa0b7-105">如何 PIP 设置映射到 PIP 规范</span><span class="sxs-lookup"><span data-stu-id="aa0b7-105">How PIP Settings Map to the PIP Specification</span></span>  
 <span data-ttu-id="aa0b7-106">下表描述了如何将 PIP 设置映射到 RosettaNet PIP 规范中的信息。</span><span class="sxs-lookup"><span data-stu-id="aa0b7-106">The following table describes how PIP settings map to information in the RosettaNet PIP specification.</span></span>  
  
|<span data-ttu-id="aa0b7-107">流程配置设置</span><span class="sxs-lookup"><span data-stu-id="aa0b7-107">Process Configuration setting</span></span>|<span data-ttu-id="aa0b7-108">PIP 规范中的信息</span><span class="sxs-lookup"><span data-stu-id="aa0b7-108">Information in the PIP specification</span></span>|  
|-----------------------------------|------------------------------------------|  
|<span data-ttu-id="aa0b7-109">流程代码</span><span class="sxs-lookup"><span data-stu-id="aa0b7-109">Process Code</span></span>|<span data-ttu-id="aa0b7-110">在标题页上，例如，"PIP3A4"副标题</span><span class="sxs-lookup"><span data-stu-id="aa0b7-110">Subheading on the title page, for example, "PIP3A4"</span></span>|  
|<span data-ttu-id="aa0b7-111">版本</span><span class="sxs-lookup"><span data-stu-id="aa0b7-111">Version</span></span>|<span data-ttu-id="aa0b7-112">在标题页上，例如，"02.02.00"PIP 版本标识符副标题</span><span class="sxs-lookup"><span data-stu-id="aa0b7-112">PIP Version Identifier subheading on the title page, for example, "02.02.00"</span></span>|  
|<span data-ttu-id="aa0b7-113">进程名称</span><span class="sxs-lookup"><span data-stu-id="aa0b7-113">Process name</span></span>|<span data-ttu-id="aa0b7-114">在标题页上，例如，"请求采购订单"副标题</span><span class="sxs-lookup"><span data-stu-id="aa0b7-114">Subheading on the title page, for example, "Request Purchase Order"</span></span>|  
|<span data-ttu-id="aa0b7-115">说明 （常规选项卡）</span><span class="sxs-lookup"><span data-stu-id="aa0b7-115">Description (General tab)</span></span>|<span data-ttu-id="aa0b7-116">第 3.1 节业务过程定义</span><span class="sxs-lookup"><span data-stu-id="aa0b7-116">Section 3.1, Business Process Definition</span></span>|  
|<span data-ttu-id="aa0b7-117">要求不可否认性</span><span class="sxs-lookup"><span data-stu-id="aa0b7-117">Non-Repudiation Required</span></span>|<span data-ttu-id="aa0b7-118">表 3-3:业务活动性能控件</span><span class="sxs-lookup"><span data-stu-id="aa0b7-118">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="aa0b7-119">若要确认 （秒） 的时间</span><span class="sxs-lookup"><span data-stu-id="aa0b7-119">Time to Acknowledge (Seconds)</span></span>|<span data-ttu-id="aa0b7-120">表 3-3:业务活动性能控件</span><span class="sxs-lookup"><span data-stu-id="aa0b7-120">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="aa0b7-121">是否要求授权</span><span class="sxs-lookup"><span data-stu-id="aa0b7-121">Is Authorization Required?</span></span>|<span data-ttu-id="aa0b7-122">表 3-3:业务活动性能控件</span><span class="sxs-lookup"><span data-stu-id="aa0b7-122">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="aa0b7-123">要求永久保密</span><span class="sxs-lookup"><span data-stu-id="aa0b7-123">Is Persistent Confidentiality Required</span></span>|<span data-ttu-id="aa0b7-124">（从 PIP 规范没有引用）</span><span class="sxs-lookup"><span data-stu-id="aa0b7-124">(No reference from the PIP specification)</span></span>|  
|<span data-ttu-id="aa0b7-125">是否要求安全传输？</span><span class="sxs-lookup"><span data-stu-id="aa0b7-125">Is Secure Transport Required?</span></span>|<span data-ttu-id="aa0b7-126">表 4-3:消息交换控制</span><span class="sxs-lookup"><span data-stu-id="aa0b7-126">Table 4-3: Message Exchange Controls</span></span>|  
|<span data-ttu-id="aa0b7-127">为单一操作</span><span class="sxs-lookup"><span data-stu-id="aa0b7-127">Is Single Action</span></span>|<span data-ttu-id="aa0b7-128">部分 4.3，业务事务对话框规范</span><span class="sxs-lookup"><span data-stu-id="aa0b7-128">Section 4.3, Business Transaction Dialog Specification</span></span>|  
|<span data-ttu-id="aa0b7-129">不可否认性和内容的</span><span class="sxs-lookup"><span data-stu-id="aa0b7-129">Non-Repudiation of Origin and Content</span></span>|<span data-ttu-id="aa0b7-130">表 3-3:业务活动性能控件</span><span class="sxs-lookup"><span data-stu-id="aa0b7-130">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="aa0b7-131">重试次数</span><span class="sxs-lookup"><span data-stu-id="aa0b7-131">Retry Count</span></span>|<span data-ttu-id="aa0b7-132">表 3-3:业务活动性能控件</span><span class="sxs-lookup"><span data-stu-id="aa0b7-132">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="aa0b7-133">若要执行的时间</span><span class="sxs-lookup"><span data-stu-id="aa0b7-133">Time to Perform</span></span>|<span data-ttu-id="aa0b7-134">表 3-3:业务活动性能控件</span><span class="sxs-lookup"><span data-stu-id="aa0b7-134">Table 3-3: Business Activity Performance Controls</span></span>|  
|<span data-ttu-id="aa0b7-135">“属性”</span><span class="sxs-lookup"><span data-stu-id="aa0b7-135">Name</span></span>|<span data-ttu-id="aa0b7-136">表 3-3:业务活动性能控件 （活动名称）</span><span class="sxs-lookup"><span data-stu-id="aa0b7-136">Table 3-3: Business Activity Performance Controls (Activity Name)</span></span>|  
|<span data-ttu-id="aa0b7-137">类型</span><span class="sxs-lookup"><span data-stu-id="aa0b7-137">Type</span></span>|<span data-ttu-id="aa0b7-138">（从 PIP 规范-供将来使用不引用）</span><span class="sxs-lookup"><span data-stu-id="aa0b7-138">(No reference from the PIP specification - for future use)</span></span>|  
|<span data-ttu-id="aa0b7-139">说明 （发起方和响应选项卡）</span><span class="sxs-lookup"><span data-stu-id="aa0b7-139">Description (Initiator and Response tabs)</span></span>|<span data-ttu-id="aa0b7-140">表 3-4:PIP 的业务文档</span><span class="sxs-lookup"><span data-stu-id="aa0b7-140">Table 3-4: PIP Business Documents</span></span>|  
|<span data-ttu-id="aa0b7-141">名称 （发起方和响应选项卡）</span><span class="sxs-lookup"><span data-stu-id="aa0b7-141">Name (Initiator and Response tabs)</span></span>|<span data-ttu-id="aa0b7-142">表 3-4:PIP 的业务文档</span><span class="sxs-lookup"><span data-stu-id="aa0b7-142">Table 3-4: PIP Business Documents</span></span>|  
|<span data-ttu-id="aa0b7-143">角色 （发起方和响应选项卡）</span><span class="sxs-lookup"><span data-stu-id="aa0b7-143">Role (Initiator and Response tabs)</span></span>|<span data-ttu-id="aa0b7-144">表 3-1:合作伙伴角色描述</span><span class="sxs-lookup"><span data-stu-id="aa0b7-144">Table 3-1: Partner Role Descriptions</span></span>|  
|<span data-ttu-id="aa0b7-145">角色说明 （发起方和响应选项卡）</span><span class="sxs-lookup"><span data-stu-id="aa0b7-145">Role Description (Initiator and Response tabs)</span></span>|<span data-ttu-id="aa0b7-146">表 3-1:合作伙伴角色描述</span><span class="sxs-lookup"><span data-stu-id="aa0b7-146">Table 3-1: Partner Role Descriptions</span></span>|  
|<span data-ttu-id="aa0b7-147">角色类型 （发起方和响应选项卡）</span><span class="sxs-lookup"><span data-stu-id="aa0b7-147">Role Type (Initiator and Response tabs)</span></span>|<span data-ttu-id="aa0b7-148">表 3-1:合作伙伴角色描述</span><span class="sxs-lookup"><span data-stu-id="aa0b7-148">Table 3-1: Partner Role Descriptions</span></span>|  
|<span data-ttu-id="aa0b7-149">服务</span><span class="sxs-lookup"><span data-stu-id="aa0b7-149">Service</span></span>|<span data-ttu-id="aa0b7-150">表 4-1:网络组件规范</span><span class="sxs-lookup"><span data-stu-id="aa0b7-150">Table 4-1: Network Component Specification</span></span>|  
|<span data-ttu-id="aa0b7-151">服务分类</span><span class="sxs-lookup"><span data-stu-id="aa0b7-151">Service Classification</span></span>|<span data-ttu-id="aa0b7-152">表 4-1:网络组件规范</span><span class="sxs-lookup"><span data-stu-id="aa0b7-152">Table 4-1: Network Component Specification</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa0b7-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa0b7-153">See Also</span></span>  
 [<span data-ttu-id="aa0b7-154">如何创建或编辑流程配置</span><span class="sxs-lookup"><span data-stu-id="aa0b7-154">How to Create or Edit a Process Configuration</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)
---
title: "程序集和项目安装异常管理示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af580992-73d4-4b16-a1cc-fa819b441fca
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65bcb2681cceb450995b18b7dc00d3d8f5a44d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="assemblies-and-artifacts-installed-by-the-exception-management-samples"></a><span data-ttu-id="a44ff-102">程序集和项目安装异常管理示例</span><span class="sxs-lookup"><span data-stu-id="a44ff-102">Assemblies and Artifacts Installed by the Exception Management Samples</span></span>
<span data-ttu-id="a44ff-103">下表列出的程序集和 ESB 异常管理示例安装其他项目。</span><span class="sxs-lookup"><span data-stu-id="a44ff-103">The following table lists the assemblies and other artifacts installed for the ESB Exception Management sample.</span></span>  
  
|<span data-ttu-id="a44ff-104">位置</span><span class="sxs-lookup"><span data-stu-id="a44ff-104">Location</span></span>|<span data-ttu-id="a44ff-105">类别</span><span class="sxs-lookup"><span data-stu-id="a44ff-105">Category</span></span>|<span data-ttu-id="a44ff-106">名称和版本的组件</span><span class="sxs-lookup"><span data-stu-id="a44ff-106">Name and version of the component</span></span>|  
|--------------|--------------|---------------------------------------|  
|<span data-ttu-id="a44ff-107">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a44ff-107">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a44ff-108">业务流程</span><span class="sxs-lookup"><span data-stu-id="a44ff-108">Orchestrations</span></span>|<span data-ttu-id="a44ff-109">GlobalBank.ESB.ExceptionHandling.Processes.EAIProcess</span><span class="sxs-lookup"><span data-stu-id="a44ff-109">GlobalBank.ESB.ExceptionHandling.Processes.EAIProcess</span></span>|  
|||<span data-ttu-id="a44ff-110">GlobalBank.ESB.ExceptionHandling.Handlers.EAIGenericHandler</span><span class="sxs-lookup"><span data-stu-id="a44ff-110">GlobalBank.ESB.ExceptionHandling.Handlers.EAIGenericHandler</span></span>|  
|||<span data-ttu-id="a44ff-111">GlobalBank.ESB.ExceptionHandling.Handlers.EAIProcessHandler</span><span class="sxs-lookup"><span data-stu-id="a44ff-111">GlobalBank.ESB.ExceptionHandling.Handlers.EAIProcessHandler</span></span>|  
|<span data-ttu-id="a44ff-112">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a44ff-112">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a44ff-113">发送端口</span><span class="sxs-lookup"><span data-stu-id="a44ff-113">Send Ports</span></span>|<span data-ttu-id="a44ff-114">EAIProcessHandler.RepairSubmit</span><span class="sxs-lookup"><span data-stu-id="a44ff-114">EAIProcessHandler.RepairSubmit</span></span>|  
|||<span data-ttu-id="a44ff-115">EAIGenericHandler.PostTmpMsg</span><span class="sxs-lookup"><span data-stu-id="a44ff-115">EAIGenericHandler.PostTmpMsg</span></span>|  
|||<span data-ttu-id="a44ff-116">EAIProcess.PostApproval</span><span class="sxs-lookup"><span data-stu-id="a44ff-116">EAIProcess.PostApproval</span></span>|  
|||<span data-ttu-id="a44ff-117">EAIProcessHandler.PostDecline</span><span class="sxs-lookup"><span data-stu-id="a44ff-117">EAIProcessHandler.PostDecline</span></span>|  
|||<span data-ttu-id="a44ff-118">所有。Exceptions_FILE （引用 GlobalFaultProcessor 管道）</span><span class="sxs-lookup"><span data-stu-id="a44ff-118">ALL.Exceptions_FILE (references the GlobalFaultProcessor pipeline)</span></span>|  
|<span data-ttu-id="a44ff-119">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a44ff-119">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a44ff-120">接收端口</span><span class="sxs-lookup"><span data-stu-id="a44ff-120">Receive Ports</span></span>|<span data-ttu-id="a44ff-121">EAIProcess.RequestPort</span><span class="sxs-lookup"><span data-stu-id="a44ff-121">EAIProcess.RequestPort</span></span>|  
|<span data-ttu-id="a44ff-122">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a44ff-122">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a44ff-123">接收位置</span><span class="sxs-lookup"><span data-stu-id="a44ff-123">Receive Locations</span></span>|<span data-ttu-id="a44ff-124">EAIProcess.RequestPort_FILE</span><span class="sxs-lookup"><span data-stu-id="a44ff-124">EAIProcess.RequestPort_FILE</span></span>|  
|||<span data-ttu-id="a44ff-125">EAIProcess.ReSubmit_HTTP</span><span class="sxs-lookup"><span data-stu-id="a44ff-125">EAIProcess.ReSubmit_HTTP</span></span>|  
|<span data-ttu-id="a44ff-126">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a44ff-126">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a44ff-127">架构</span><span class="sxs-lookup"><span data-stu-id="a44ff-127">Schemas</span></span>|<span data-ttu-id="a44ff-128">GlobalBank.ESB.ExceptionHandling.Schemas.System_Properties 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a44ff-128">GlobalBank.ESB.ExceptionHandling.Schemas.System_Properties Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="a44ff-129">GlobalBank.ESB.ExceptionHandling.Schemas.Request 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a44ff-129">GlobalBank.ESB.ExceptionHandling.Schemas.Request Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="a44ff-130">GlobalBank.ESB.ExceptionHandling.Schemas.RequestDenied 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a44ff-130">GlobalBank.ESB.ExceptionHandling.Schemas.RequestDenied Version 2.0.0.0</span></span>|  
|<span data-ttu-id="a44ff-131">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a44ff-131">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a44ff-132">管道</span><span class="sxs-lookup"><span data-stu-id="a44ff-132">Pipelines</span></span>|<span data-ttu-id="a44ff-133">GlobalBank.ESB.ExceptionHandling.Pipelines.GlobalFaultProcessor 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a44ff-133">GlobalBank.ESB.ExceptionHandling.Pipelines.GlobalFaultProcessor Version 2.0.0.0</span></span>|  
|<span data-ttu-id="a44ff-134">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a44ff-134">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a44ff-135">Resources</span><span class="sxs-lookup"><span data-stu-id="a44ff-135">Resources</span></span>|<span data-ttu-id="a44ff-136">GlobalBank.ESB.ExceptionHandling.Handlers 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a44ff-136">GlobalBank.ESB.ExceptionHandling.Handlers Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="a44ff-137">GlobalBank.ESB.ExceptionHandling.Processes 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a44ff-137">GlobalBank.ESB.ExceptionHandling.Processes Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="a44ff-138">GlobalBank.ESB.ExceptionHandling.Schemas 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a44ff-138">GlobalBank.ESB.ExceptionHandling.Schemas Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="a44ff-139">GlobalBank.ESB.ExceptionHandling.Pipelines 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a44ff-139">GlobalBank.ESB.ExceptionHandling.Pipelines Version 2.0.0.0</span></span>|  
|<span data-ttu-id="a44ff-140">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a44ff-140">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a44ff-141">策略</span><span class="sxs-lookup"><span data-stu-id="a44ff-141">Policies</span></span>||  
|<span data-ttu-id="a44ff-142">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="a44ff-142">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="a44ff-143">地图</span><span class="sxs-lookup"><span data-stu-id="a44ff-143">Maps</span></span>|<span data-ttu-id="a44ff-144">GlobalBank.ESB.ExceptionHandling.Schemas.MapToReqDenied 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a44ff-144">GlobalBank.ESB.ExceptionHandling.Schemas.MapToReqDenied Version 2.0.0.0</span></span>|  
|<span data-ttu-id="a44ff-145">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="a44ff-145">Global assembly cache</span></span>|<span data-ttu-id="a44ff-146">程序集</span><span class="sxs-lookup"><span data-stu-id="a44ff-146">Assemblies</span></span>|<span data-ttu-id="a44ff-147">GlobalBank.ESB.ExceptionHandling.Handlers 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a44ff-147">GlobalBank.ESB.ExceptionHandling.Handlers Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="a44ff-148">GlobalBank.ESB.ExceptionHandling.Processes 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a44ff-148">GlobalBank.ESB.ExceptionHandling.Processes Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="a44ff-149">GlobalBank.ESB.ExceptionHandling.Schemas 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a44ff-149">GlobalBank.ESB.ExceptionHandling.Schemas Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="a44ff-150">GlobalBank.ESB.ExceptionHandling.Pipelines 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="a44ff-150">GlobalBank.ESB.ExceptionHandling.Pipelines Version 2.0.0.0</span></span>|  
|<span data-ttu-id="a44ff-151">%Program 文件 %\\[!INCLUDE[prague](../includes/prague-md.md)]\Pipeline 组件</span><span class="sxs-lookup"><span data-stu-id="a44ff-151">%Program Files%\\[!INCLUDE[prague](../includes/prague-md.md)]\Pipeline Components</span></span>|<span data-ttu-id="a44ff-152">管道组件</span><span class="sxs-lookup"><span data-stu-id="a44ff-152">Pipeline components</span></span>||
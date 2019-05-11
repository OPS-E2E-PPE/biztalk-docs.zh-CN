---
title: 程序集和项目由异常管理示例安装 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af580992-73d4-4b16-a1cc-fa819b441fca
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac0a14eeb6eaca71cf346c901b33b03f590ca563
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392294"
---
# <a name="assemblies-and-artifacts-installed-by-the-exception-management-samples"></a><span data-ttu-id="0dbee-102">程序集和项目安装异常管理示例</span><span class="sxs-lookup"><span data-stu-id="0dbee-102">Assemblies and Artifacts Installed by the Exception Management Samples</span></span>
<span data-ttu-id="0dbee-103">下表列出了程序集和为 ESB 异常管理示例安装的其他项目。</span><span class="sxs-lookup"><span data-stu-id="0dbee-103">The following table lists the assemblies and other artifacts installed for the ESB Exception Management sample.</span></span>  
  
|<span data-ttu-id="0dbee-104">Location</span><span class="sxs-lookup"><span data-stu-id="0dbee-104">Location</span></span>|<span data-ttu-id="0dbee-105">Category</span><span class="sxs-lookup"><span data-stu-id="0dbee-105">Category</span></span>|<span data-ttu-id="0dbee-106">名称和版本的组件</span><span class="sxs-lookup"><span data-stu-id="0dbee-106">Name and version of the component</span></span>|  
|--------------|--------------|---------------------------------------|  
|<span data-ttu-id="0dbee-107">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0dbee-107">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0dbee-108">业务流程</span><span class="sxs-lookup"><span data-stu-id="0dbee-108">Orchestrations</span></span>|<span data-ttu-id="0dbee-109">GlobalBank.ESB.ExceptionHandling.Processes.EAIProcess</span><span class="sxs-lookup"><span data-stu-id="0dbee-109">GlobalBank.ESB.ExceptionHandling.Processes.EAIProcess</span></span>|  
|||<span data-ttu-id="0dbee-110">GlobalBank.ESB.ExceptionHandling.Handlers.EAIGenericHandler</span><span class="sxs-lookup"><span data-stu-id="0dbee-110">GlobalBank.ESB.ExceptionHandling.Handlers.EAIGenericHandler</span></span>|  
|||<span data-ttu-id="0dbee-111">GlobalBank.ESB.ExceptionHandling.Handlers.EAIProcessHandler</span><span class="sxs-lookup"><span data-stu-id="0dbee-111">GlobalBank.ESB.ExceptionHandling.Handlers.EAIProcessHandler</span></span>|  
|<span data-ttu-id="0dbee-112">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0dbee-112">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0dbee-113">发送端口</span><span class="sxs-lookup"><span data-stu-id="0dbee-113">Send Ports</span></span>|<span data-ttu-id="0dbee-114">EAIProcessHandler.RepairSubmit</span><span class="sxs-lookup"><span data-stu-id="0dbee-114">EAIProcessHandler.RepairSubmit</span></span>|  
|||<span data-ttu-id="0dbee-115">EAIGenericHandler.PostTmpMsg</span><span class="sxs-lookup"><span data-stu-id="0dbee-115">EAIGenericHandler.PostTmpMsg</span></span>|  
|||<span data-ttu-id="0dbee-116">EAIProcess.PostApproval</span><span class="sxs-lookup"><span data-stu-id="0dbee-116">EAIProcess.PostApproval</span></span>|  
|||<span data-ttu-id="0dbee-117">EAIProcessHandler.PostDecline</span><span class="sxs-lookup"><span data-stu-id="0dbee-117">EAIProcessHandler.PostDecline</span></span>|  
|||<span data-ttu-id="0dbee-118">所有。Exceptions_FILE （引用 GlobalFaultProcessor 管道）</span><span class="sxs-lookup"><span data-stu-id="0dbee-118">ALL.Exceptions_FILE (references the GlobalFaultProcessor pipeline)</span></span>|  
|<span data-ttu-id="0dbee-119">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0dbee-119">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0dbee-120">接收端口</span><span class="sxs-lookup"><span data-stu-id="0dbee-120">Receive Ports</span></span>|<span data-ttu-id="0dbee-121">EAIProcess.RequestPort</span><span class="sxs-lookup"><span data-stu-id="0dbee-121">EAIProcess.RequestPort</span></span>|  
|<span data-ttu-id="0dbee-122">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0dbee-122">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0dbee-123">接收位置</span><span class="sxs-lookup"><span data-stu-id="0dbee-123">Receive Locations</span></span>|<span data-ttu-id="0dbee-124">EAIProcess.RequestPort_FILE</span><span class="sxs-lookup"><span data-stu-id="0dbee-124">EAIProcess.RequestPort_FILE</span></span>|  
|||<span data-ttu-id="0dbee-125">EAIProcess.ReSubmit_HTTP</span><span class="sxs-lookup"><span data-stu-id="0dbee-125">EAIProcess.ReSubmit_HTTP</span></span>|  
|<span data-ttu-id="0dbee-126">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0dbee-126">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0dbee-127">架构</span><span class="sxs-lookup"><span data-stu-id="0dbee-127">Schemas</span></span>|<span data-ttu-id="0dbee-128">GlobalBank.ESB.ExceptionHandling.Schemas.System_Properties 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0dbee-128">GlobalBank.ESB.ExceptionHandling.Schemas.System_Properties Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="0dbee-129">GlobalBank.ESB.ExceptionHandling.Schemas.Request 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0dbee-129">GlobalBank.ESB.ExceptionHandling.Schemas.Request Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="0dbee-130">GlobalBank.ESB.ExceptionHandling.Schemas.RequestDenied 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0dbee-130">GlobalBank.ESB.ExceptionHandling.Schemas.RequestDenied Version 2.0.0.0</span></span>|  
|<span data-ttu-id="0dbee-131">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0dbee-131">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0dbee-132">管道</span><span class="sxs-lookup"><span data-stu-id="0dbee-132">Pipelines</span></span>|<span data-ttu-id="0dbee-133">GlobalBank.ESB.ExceptionHandling.Pipelines.GlobalFaultProcessor 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0dbee-133">GlobalBank.ESB.ExceptionHandling.Pipelines.GlobalFaultProcessor Version 2.0.0.0</span></span>|  
|<span data-ttu-id="0dbee-134">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0dbee-134">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0dbee-135">资源</span><span class="sxs-lookup"><span data-stu-id="0dbee-135">Resources</span></span>|<span data-ttu-id="0dbee-136">GlobalBank.ESB.ExceptionHandling.Handlers 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0dbee-136">GlobalBank.ESB.ExceptionHandling.Handlers Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="0dbee-137">GlobalBank.ESB.ExceptionHandling.Processes Version 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0dbee-137">GlobalBank.ESB.ExceptionHandling.Processes Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="0dbee-138">GlobalBank.ESB.ExceptionHandling.Schemas 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0dbee-138">GlobalBank.ESB.ExceptionHandling.Schemas Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="0dbee-139">GlobalBank.ESB.ExceptionHandling.Pipelines 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0dbee-139">GlobalBank.ESB.ExceptionHandling.Pipelines Version 2.0.0.0</span></span>|  
|<span data-ttu-id="0dbee-140">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0dbee-140">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0dbee-141">策略</span><span class="sxs-lookup"><span data-stu-id="0dbee-141">Policies</span></span>||  
|<span data-ttu-id="0dbee-142">BizTalk 应用程序 GlobalBank.ESB</span><span class="sxs-lookup"><span data-stu-id="0dbee-142">BizTalk application GlobalBank.ESB</span></span>|<span data-ttu-id="0dbee-143">地图</span><span class="sxs-lookup"><span data-stu-id="0dbee-143">Maps</span></span>|<span data-ttu-id="0dbee-144">GlobalBank.ESB.ExceptionHandling.Schemas.MapToReqDenied 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0dbee-144">GlobalBank.ESB.ExceptionHandling.Schemas.MapToReqDenied Version 2.0.0.0</span></span>|  
|<span data-ttu-id="0dbee-145">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="0dbee-145">Global assembly cache</span></span>|<span data-ttu-id="0dbee-146">程序集</span><span class="sxs-lookup"><span data-stu-id="0dbee-146">Assemblies</span></span>|<span data-ttu-id="0dbee-147">GlobalBank.ESB.ExceptionHandling.Handlers 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0dbee-147">GlobalBank.ESB.ExceptionHandling.Handlers Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="0dbee-148">GlobalBank.ESB.ExceptionHandling.Processes Version 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0dbee-148">GlobalBank.ESB.ExceptionHandling.Processes Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="0dbee-149">GlobalBank.ESB.ExceptionHandling.Schemas 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0dbee-149">GlobalBank.ESB.ExceptionHandling.Schemas Version 2.0.0.0</span></span>|  
|||<span data-ttu-id="0dbee-150">GlobalBank.ESB.ExceptionHandling.Pipelines 版本 2.0.0.0</span><span class="sxs-lookup"><span data-stu-id="0dbee-150">GlobalBank.ESB.ExceptionHandling.Pipelines Version 2.0.0.0</span></span>|  
|<span data-ttu-id="0dbee-151">%Program Files %\\BizTalk Server\Pipeline 组件</span><span class="sxs-lookup"><span data-stu-id="0dbee-151">%Program Files%\\BizTalk Server\Pipeline Components</span></span>|<span data-ttu-id="0dbee-152">管道组件</span><span class="sxs-lookup"><span data-stu-id="0dbee-152">Pipeline components</span></span>||
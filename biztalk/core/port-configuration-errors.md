---
title: "端口配置错误 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 92eae0d8-a0c4-4f8c-b91a-fd98b9f6931a
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f0e51c06fab9dadb60fc43a003108e50bbb0fab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="port-configuration-errors"></a><span data-ttu-id="1245d-102">端口配置错误</span><span class="sxs-lookup"><span data-stu-id="1245d-102">Port Configuration Errors</span></span>
<span data-ttu-id="1245d-103">用于诊断和解决 WCF 端口配置错误的信息。</span><span class="sxs-lookup"><span data-stu-id="1245d-103">Information for diagnosing and resolving WCF Port Configuration errors.</span></span>  

## <a name="cannot-merge-operation-due-to-communication-pattern-conflict"></a><span data-ttu-id="1245d-104">由于通信模式冲突，无法合并操作</span><span class="sxs-lookup"><span data-stu-id="1245d-104">Cannot merge operation due to communication pattern conflict</span></span>
  
||<span data-ttu-id="1245d-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="1245d-105">Details</span></span>|  
|-|-|  
|<span data-ttu-id="1245d-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="1245d-106">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1245d-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="1245d-107">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="1245d-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1245d-108">Event ID</span></span>|<span data-ttu-id="1245d-109">0</span><span class="sxs-lookup"><span data-stu-id="1245d-109">0</span></span>|  
|<span data-ttu-id="1245d-110">事件源</span><span class="sxs-lookup"><span data-stu-id="1245d-110">Event Source</span></span>|<span data-ttu-id="1245d-111">0</span><span class="sxs-lookup"><span data-stu-id="1245d-111">0</span></span>|  
|<span data-ttu-id="1245d-112">组件</span><span class="sxs-lookup"><span data-stu-id="1245d-112">Component</span></span>|<span data-ttu-id="1245d-113">0</span><span class="sxs-lookup"><span data-stu-id="1245d-113">0</span></span>|  
|<span data-ttu-id="1245d-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="1245d-114">Symbolic Name</span></span>|<span data-ttu-id="1245d-115">0</span><span class="sxs-lookup"><span data-stu-id="1245d-115">0</span></span>|  
|<span data-ttu-id="1245d-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="1245d-116">Message Text</span></span>|<span data-ttu-id="1245d-117">由于通信模式冲突而无法合并操作“{0}”。</span><span class="sxs-lookup"><span data-stu-id="1245d-117">Cannot merge operation "{0}" due to communication pattern conflict.</span></span>  <span data-ttu-id="1245d-118">所有操作都必须是单向或请求响应模式</span><span class="sxs-lookup"><span data-stu-id="1245d-118">All operations must be one-way or request-response</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="1245d-119">解释</span><span class="sxs-lookup"><span data-stu-id="1245d-119">Explanation</span></span>  
 <span data-ttu-id="1245d-120">此错误表示 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 正尝试合并端口类型具有不同通信模式的端口。</span><span class="sxs-lookup"><span data-stu-id="1245d-120">This error indicates [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is attempting to merge ports with port types that have different communication patterns.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="1245d-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="1245d-121">User Action</span></span>  
 <span data-ttu-id="1245d-122">使用端口配置向导，确保要合并的所有端口都拥有相同的通信方向，即单向或请求响应模式。</span><span class="sxs-lookup"><span data-stu-id="1245d-122">Using the Port Configuration Wizard, ensure that all the ports that are being merged have the same communication direction, either one-way or request-response.</span></span>  
  
 <span data-ttu-id="1245d-123">有关端口配置的其他信息，请参阅[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="1245d-123">For additional information on port configuration, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>
 
## <a name="port-types-that-have-a-combination-of-one-way-and-request-response-operations-are-not-allowed"></a><span data-ttu-id="1245d-124">端口类型拥有的单向组合，不允许请求-响应操作</span><span class="sxs-lookup"><span data-stu-id="1245d-124">Port types that have a combination of one-way and request-response operations are not allowed</span></span> 
  
||<span data-ttu-id="1245d-125">详细信息</span><span class="sxs-lookup"><span data-stu-id="1245d-125">Details</span></span>|  
|-|-|  
|<span data-ttu-id="1245d-126">产品名称</span><span class="sxs-lookup"><span data-stu-id="1245d-126">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1245d-127">产品版本</span><span class="sxs-lookup"><span data-stu-id="1245d-127">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="1245d-128">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1245d-128">Event ID</span></span>|<span data-ttu-id="1245d-129">0</span><span class="sxs-lookup"><span data-stu-id="1245d-129">0</span></span>|  
|<span data-ttu-id="1245d-130">事件源</span><span class="sxs-lookup"><span data-stu-id="1245d-130">Event Source</span></span>|<span data-ttu-id="1245d-131">0</span><span class="sxs-lookup"><span data-stu-id="1245d-131">0</span></span>|  
|<span data-ttu-id="1245d-132">组件</span><span class="sxs-lookup"><span data-stu-id="1245d-132">Component</span></span>|<span data-ttu-id="1245d-133">0</span><span class="sxs-lookup"><span data-stu-id="1245d-133">0</span></span>|  
|<span data-ttu-id="1245d-134">符号名称</span><span class="sxs-lookup"><span data-stu-id="1245d-134">Symbolic Name</span></span>|<span data-ttu-id="1245d-135">0</span><span class="sxs-lookup"><span data-stu-id="1245d-135">0</span></span>|  
|<span data-ttu-id="1245d-136">消息正文</span><span class="sxs-lookup"><span data-stu-id="1245d-136">Message Text</span></span>|<span data-ttu-id="1245d-137">端口类型拥有的单向组合，不允许请求-响应操作。</span><span class="sxs-lookup"><span data-stu-id="1245d-137">Port types that have a combination of one-way and request-response operations are not allowed.</span></span> <span data-ttu-id="1245d-138">更正服务说明"{0}"端口类型"{1}"，然后重新运行该向导</span><span class="sxs-lookup"><span data-stu-id="1245d-138">Correct service description "{0}" port type "{1}" and rerun the wizard</span></span>|  
  
### <a name="explanation"></a><span data-ttu-id="1245d-139">解释</span><span class="sxs-lookup"><span data-stu-id="1245d-139">Explanation</span></span>  
 <span data-ttu-id="1245d-140">此错误表示尝试使用的服务，也没有操作的单向和双向 （请求-响应）。</span><span class="sxs-lookup"><span data-stu-id="1245d-140">This error indicates the service trying to be consumed has operations that are both one-way and two-way (or request-response).</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="1245d-141">用户操作</span><span class="sxs-lookup"><span data-stu-id="1245d-141">User Action</span></span>  
 <span data-ttu-id="1245d-142">将服务更正为具有合适的操作（单向或请求响应，但不是同时具有两者），并尝试使用该服务（如果拥有要尝试使用的 WCF 服务）。</span><span class="sxs-lookup"><span data-stu-id="1245d-142">Correct the service with the appropriate operations (either one-way or request-response but not both) and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="1245d-143">否则，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="1245d-143">Otherwise, contact the service provider.</span></span>

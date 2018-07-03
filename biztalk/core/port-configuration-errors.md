---
title: 端口配置错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92eae0d8-a0c4-4f8c-b91a-fd98b9f6931a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8cc3c8763115e93387bed5195f234bf4a070b9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986902"
---
# <a name="port-configuration-errors"></a><span data-ttu-id="460af-102">端口配置错误</span><span class="sxs-lookup"><span data-stu-id="460af-102">Port Configuration Errors</span></span>
<span data-ttu-id="460af-103">诊断和解决 WCF 端口配置错误的信息。</span><span class="sxs-lookup"><span data-stu-id="460af-103">Information for diagnosing and resolving WCF Port Configuration errors.</span></span>  

## <a name="cannot-merge-operation-due-to-communication-pattern-conflict"></a><span data-ttu-id="460af-104">由于通信模式冲突，无法合并操作</span><span class="sxs-lookup"><span data-stu-id="460af-104">Cannot merge operation due to communication pattern conflict</span></span>
  
|                 |                                                         <span data-ttu-id="460af-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="460af-105">Details</span></span>                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="460af-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="460af-106">Product Name</span></span>   |                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                    |
| <span data-ttu-id="460af-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="460af-107">Product Version</span></span> |                               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                |
|    <span data-ttu-id="460af-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="460af-108">Event ID</span></span>     |                                                            <span data-ttu-id="460af-109">0</span><span class="sxs-lookup"><span data-stu-id="460af-109">0</span></span>                                                            |
|  <span data-ttu-id="460af-110">事件源</span><span class="sxs-lookup"><span data-stu-id="460af-110">Event Source</span></span>   |                                                            <span data-ttu-id="460af-111">0</span><span class="sxs-lookup"><span data-stu-id="460af-111">0</span></span>                                                            |
|    <span data-ttu-id="460af-112">组件</span><span class="sxs-lookup"><span data-stu-id="460af-112">Component</span></span>    |                                                            <span data-ttu-id="460af-113">0</span><span class="sxs-lookup"><span data-stu-id="460af-113">0</span></span>                                                            |
|  <span data-ttu-id="460af-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="460af-114">Symbolic Name</span></span>  |                                                            <span data-ttu-id="460af-115">0</span><span class="sxs-lookup"><span data-stu-id="460af-115">0</span></span>                                                            |
|  <span data-ttu-id="460af-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="460af-116">Message Text</span></span>   | <span data-ttu-id="460af-117">无法合并操作"{0}"由于通信模式冲突。</span><span class="sxs-lookup"><span data-stu-id="460af-117">Cannot merge operation "{0}" due to communication pattern conflict.</span></span>  <span data-ttu-id="460af-118">所有操作都必须是单向或请求响应模式</span><span class="sxs-lookup"><span data-stu-id="460af-118">All operations must be one-way or request-response</span></span> |
  
### <a name="explanation"></a><span data-ttu-id="460af-119">解释</span><span class="sxs-lookup"><span data-stu-id="460af-119">Explanation</span></span>  
 <span data-ttu-id="460af-120">此错误表示 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 正尝试合并端口类型具有不同通信模式的端口。</span><span class="sxs-lookup"><span data-stu-id="460af-120">This error indicates [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is attempting to merge ports with port types that have different communication patterns.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="460af-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="460af-121">User Action</span></span>  
 <span data-ttu-id="460af-122">使用端口配置向导，确保要合并的所有端口都拥有相同的通信方向，即单向或请求响应模式。</span><span class="sxs-lookup"><span data-stu-id="460af-122">Using the Port Configuration Wizard, ensure that all the ports that are being merged have the same communication direction, either one-way or request-response.</span></span>  
  
 <span data-ttu-id="460af-123">有关端口配置的其他信息，请参阅[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="460af-123">For additional information on port configuration, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>
 
## <a name="port-types-that-have-a-combination-of-one-way-and-request-response-operations-are-not-allowed"></a><span data-ttu-id="460af-124">端口类型具有的单向组合和不允许请求-响应操作</span><span class="sxs-lookup"><span data-stu-id="460af-124">Port types that have a combination of one-way and request-response operations are not allowed</span></span> 
  
|                 |                                                                                <span data-ttu-id="460af-125">详细信息</span><span class="sxs-lookup"><span data-stu-id="460af-125">Details</span></span>                                                                                |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="460af-126">产品名称</span><span class="sxs-lookup"><span data-stu-id="460af-126">Product Name</span></span>   |                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                           |
| <span data-ttu-id="460af-127">产品版本</span><span class="sxs-lookup"><span data-stu-id="460af-127">Product Version</span></span> |                                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                       |
|    <span data-ttu-id="460af-128">事件 ID</span><span class="sxs-lookup"><span data-stu-id="460af-128">Event ID</span></span>     |                                                                                   <span data-ttu-id="460af-129">0</span><span class="sxs-lookup"><span data-stu-id="460af-129">0</span></span>                                                                                   |
|  <span data-ttu-id="460af-130">事件源</span><span class="sxs-lookup"><span data-stu-id="460af-130">Event Source</span></span>   |                                                                                   <span data-ttu-id="460af-131">0</span><span class="sxs-lookup"><span data-stu-id="460af-131">0</span></span>                                                                                   |
|    <span data-ttu-id="460af-132">组件</span><span class="sxs-lookup"><span data-stu-id="460af-132">Component</span></span>    |                                                                                   <span data-ttu-id="460af-133">0</span><span class="sxs-lookup"><span data-stu-id="460af-133">0</span></span>                                                                                   |
|  <span data-ttu-id="460af-134">符号名称</span><span class="sxs-lookup"><span data-stu-id="460af-134">Symbolic Name</span></span>  |                                                                                   <span data-ttu-id="460af-135">0</span><span class="sxs-lookup"><span data-stu-id="460af-135">0</span></span>                                                                                   |
|  <span data-ttu-id="460af-136">消息正文</span><span class="sxs-lookup"><span data-stu-id="460af-136">Message Text</span></span>   | <span data-ttu-id="460af-137">端口类型具有的单向组合和不允许请求-响应操作。</span><span class="sxs-lookup"><span data-stu-id="460af-137">Port types that have a combination of one-way and request-response operations are not allowed.</span></span> <span data-ttu-id="460af-138">更正服务说明"{0}"端口类型"{1}"，然后重新运行向导</span><span class="sxs-lookup"><span data-stu-id="460af-138">Correct service description "{0}" port type "{1}" and rerun the wizard</span></span> |
  
### <a name="explanation"></a><span data-ttu-id="460af-139">解释</span><span class="sxs-lookup"><span data-stu-id="460af-139">Explanation</span></span>  
 <span data-ttu-id="460af-140">此错误表示尝试使用该服务有单向和双向操作 （或请求-响应）。</span><span class="sxs-lookup"><span data-stu-id="460af-140">This error indicates the service trying to be consumed has operations that are both one-way and two-way (or request-response).</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="460af-141">用户操作</span><span class="sxs-lookup"><span data-stu-id="460af-141">User Action</span></span>  
 <span data-ttu-id="460af-142">将服务更正为具有合适的操作（单向或请求响应，但不是同时具有两者），并尝试使用该服务（如果拥有要尝试使用的 WCF 服务）。</span><span class="sxs-lookup"><span data-stu-id="460af-142">Correct the service with the appropriate operations (either one-way or request-response but not both) and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="460af-143">否则，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="460af-143">Otherwise, contact the service provider.</span></span>

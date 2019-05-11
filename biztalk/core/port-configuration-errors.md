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
ms.openlocfilehash: 773741699d040a909ef56bf2034a3b52fddee79f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394896"
---
# <a name="port-configuration-errors"></a><span data-ttu-id="728e5-102">端口配置错误</span><span class="sxs-lookup"><span data-stu-id="728e5-102">Port Configuration Errors</span></span>
<span data-ttu-id="728e5-103">诊断和解决 WCF 端口配置错误的信息。</span><span class="sxs-lookup"><span data-stu-id="728e5-103">Information for diagnosing and resolving WCF Port Configuration errors.</span></span>  

## <a name="cannot-merge-operation-due-to-communication-pattern-conflict"></a><span data-ttu-id="728e5-104">无法合并操作由于通信模式冲突</span><span class="sxs-lookup"><span data-stu-id="728e5-104">Cannot merge operation due to communication pattern conflict</span></span>
  
|                 |                                                         <span data-ttu-id="728e5-105">详细信息</span><span class="sxs-lookup"><span data-stu-id="728e5-105">Details</span></span>                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="728e5-106">产品名称</span><span class="sxs-lookup"><span data-stu-id="728e5-106">Product Name</span></span>   |                   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                    |
| <span data-ttu-id="728e5-107">产品版本</span><span class="sxs-lookup"><span data-stu-id="728e5-107">Product Version</span></span> |                               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                |
|    <span data-ttu-id="728e5-108">事件 ID</span><span class="sxs-lookup"><span data-stu-id="728e5-108">Event ID</span></span>     |                                                            <span data-ttu-id="728e5-109">0</span><span class="sxs-lookup"><span data-stu-id="728e5-109">0</span></span>                                                            |
|  <span data-ttu-id="728e5-110">事件源</span><span class="sxs-lookup"><span data-stu-id="728e5-110">Event Source</span></span>   |                                                            <span data-ttu-id="728e5-111">0</span><span class="sxs-lookup"><span data-stu-id="728e5-111">0</span></span>                                                            |
|    <span data-ttu-id="728e5-112">组件</span><span class="sxs-lookup"><span data-stu-id="728e5-112">Component</span></span>    |                                                            <span data-ttu-id="728e5-113">0</span><span class="sxs-lookup"><span data-stu-id="728e5-113">0</span></span>                                                            |
|  <span data-ttu-id="728e5-114">符号名称</span><span class="sxs-lookup"><span data-stu-id="728e5-114">Symbolic Name</span></span>  |                                                            <span data-ttu-id="728e5-115">0</span><span class="sxs-lookup"><span data-stu-id="728e5-115">0</span></span>                                                            |
|  <span data-ttu-id="728e5-116">消息正文</span><span class="sxs-lookup"><span data-stu-id="728e5-116">Message Text</span></span>   | <span data-ttu-id="728e5-117">无法合并操作"{0}"由于通信模式冲突。</span><span class="sxs-lookup"><span data-stu-id="728e5-117">Cannot merge operation "{0}" due to communication pattern conflict.</span></span>  <span data-ttu-id="728e5-118">所有操作都必须是单向或请求响应模式</span><span class="sxs-lookup"><span data-stu-id="728e5-118">All operations must be one-way or request-response</span></span> |
  
### <a name="explanation"></a><span data-ttu-id="728e5-119">解释</span><span class="sxs-lookup"><span data-stu-id="728e5-119">Explanation</span></span>  
 <span data-ttu-id="728e5-120">此错误表示 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 正尝试合并端口类型具有不同通信模式的端口。</span><span class="sxs-lookup"><span data-stu-id="728e5-120">This error indicates [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is attempting to merge ports with port types that have different communication patterns.</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="728e5-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="728e5-121">User Action</span></span>  
 <span data-ttu-id="728e5-122">使用端口配置向导，确保要合并的所有端口都拥有相同的通信方向，即单向或请求响应模式。</span><span class="sxs-lookup"><span data-stu-id="728e5-122">Using the Port Configuration Wizard, ensure that all the ports that are being merged have the same communication direction, either one-way or request-response.</span></span>  
  
 <span data-ttu-id="728e5-123">有关端口配置的其他信息，请参阅[如何运行端口配置向导](../core/how-to-run-the-port-configuration-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="728e5-123">For additional information on port configuration, see [How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md).</span></span>
 
## <a name="port-types-that-have-a-combination-of-one-way-and-request-response-operations-are-not-allowed"></a><span data-ttu-id="728e5-124">端口类型具有的单向组合和不允许请求-响应操作</span><span class="sxs-lookup"><span data-stu-id="728e5-124">Port types that have a combination of one-way and request-response operations are not allowed</span></span> 
  
|                 |                                                                                <span data-ttu-id="728e5-125">详细信息</span><span class="sxs-lookup"><span data-stu-id="728e5-125">Details</span></span>                                                                                |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="728e5-126">产品名称</span><span class="sxs-lookup"><span data-stu-id="728e5-126">Product Name</span></span>   |                                          [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                           |
| <span data-ttu-id="728e5-127">产品版本</span><span class="sxs-lookup"><span data-stu-id="728e5-127">Product Version</span></span> |                                                      [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                       |
|    <span data-ttu-id="728e5-128">事件 ID</span><span class="sxs-lookup"><span data-stu-id="728e5-128">Event ID</span></span>     |                                                                                   <span data-ttu-id="728e5-129">0</span><span class="sxs-lookup"><span data-stu-id="728e5-129">0</span></span>                                                                                   |
|  <span data-ttu-id="728e5-130">事件源</span><span class="sxs-lookup"><span data-stu-id="728e5-130">Event Source</span></span>   |                                                                                   <span data-ttu-id="728e5-131">0</span><span class="sxs-lookup"><span data-stu-id="728e5-131">0</span></span>                                                                                   |
|    <span data-ttu-id="728e5-132">组件</span><span class="sxs-lookup"><span data-stu-id="728e5-132">Component</span></span>    |                                                                                   <span data-ttu-id="728e5-133">0</span><span class="sxs-lookup"><span data-stu-id="728e5-133">0</span></span>                                                                                   |
|  <span data-ttu-id="728e5-134">符号名称</span><span class="sxs-lookup"><span data-stu-id="728e5-134">Symbolic Name</span></span>  |                                                                                   <span data-ttu-id="728e5-135">0</span><span class="sxs-lookup"><span data-stu-id="728e5-135">0</span></span>                                                                                   |
|  <span data-ttu-id="728e5-136">消息正文</span><span class="sxs-lookup"><span data-stu-id="728e5-136">Message Text</span></span>   | <span data-ttu-id="728e5-137">端口类型具有的单向组合和不允许请求-响应操作。</span><span class="sxs-lookup"><span data-stu-id="728e5-137">Port types that have a combination of one-way and request-response operations are not allowed.</span></span> <span data-ttu-id="728e5-138">更正服务说明"{0}"端口类型"{1}"，然后重新运行向导</span><span class="sxs-lookup"><span data-stu-id="728e5-138">Correct service description "{0}" port type "{1}" and rerun the wizard</span></span> |
  
### <a name="explanation"></a><span data-ttu-id="728e5-139">解释</span><span class="sxs-lookup"><span data-stu-id="728e5-139">Explanation</span></span>  
 <span data-ttu-id="728e5-140">此错误表示尝试使用该服务有单向和双向操作 （或请求-响应）。</span><span class="sxs-lookup"><span data-stu-id="728e5-140">This error indicates the service trying to be consumed has operations that are both one-way and two-way (or request-response).</span></span>  
  
### <a name="user-action"></a><span data-ttu-id="728e5-141">用户操作</span><span class="sxs-lookup"><span data-stu-id="728e5-141">User Action</span></span>  
 <span data-ttu-id="728e5-142">更正服务具有合适的操作 (是单向或请求-响应但不是能同时) 并尝试使用 （如果您拥有要尝试使用的 WCF 服务）。</span><span class="sxs-lookup"><span data-stu-id="728e5-142">Correct the service with the appropriate operations (either one-way or request-response but not both) and try to consume (if you own the WCF services that you are trying to consume).</span></span> <span data-ttu-id="728e5-143">否则，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="728e5-143">Otherwise, contact the service provider.</span></span>

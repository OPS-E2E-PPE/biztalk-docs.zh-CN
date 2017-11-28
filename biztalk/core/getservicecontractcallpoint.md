---
title: "GetServiceContractCallPoint |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be03d100-0cba-4b80-8056-b582a2cd74ce
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e291bcf733129991f6d3b5000ca8e9bc1353057
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getservicecontractcallpoint"></a><span data-ttu-id="b629f-102">GetServiceContractCallPoint</span><span class="sxs-lookup"><span data-stu-id="b629f-102">GetServiceContractCallPoint</span></span>
<span data-ttu-id="b629f-103">推送到堆栈的当前服务协定调用点的名称。</span><span class="sxs-lookup"><span data-stu-id="b629f-103">Pushes the name of the current service contract call point onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b629f-104">语法</span><span class="sxs-lookup"><span data-stu-id="b629f-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="GetServiceContractCallPoint" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b629f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b629f-105">Parameters</span></span>  
 <span data-ttu-id="b629f-106">无。</span><span class="sxs-lookup"><span data-stu-id="b629f-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="b629f-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="b629f-107">Pushed Value</span></span>  
 <span data-ttu-id="b629f-108">包含当前协定调用点字符串。</span><span class="sxs-lookup"><span data-stu-id="b629f-108">String containing the current contract call point.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b629f-109">注释</span><span class="sxs-lookup"><span data-stu-id="b629f-109">Remarks</span></span>  
 <span data-ttu-id="b629f-110">Windows Communication Framework 的服务可以截获的不同位置中的生存期内的服务协定中。</span><span class="sxs-lookup"><span data-stu-id="b629f-110">A Windows Communication Framework service can be intercepted at different points in the lifetime of the service contract.</span></span> <span data-ttu-id="b629f-111">这些位置可由`System.BizTalk.Bam.Interceptors.Wcf.ContractCallPoint`枚举：</span><span class="sxs-lookup"><span data-stu-id="b629f-111">These locations are defined by the `System.BizTalk.Bam.Interceptors.Wcf.ContractCallPoint` enumeration:</span></span>  
  
|<span data-ttu-id="b629f-112">协定调用点</span><span class="sxs-lookup"><span data-stu-id="b629f-112">Contract call point</span></span>|<span data-ttu-id="b629f-113">Description</span><span class="sxs-lookup"><span data-stu-id="b629f-113">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="b629f-114">ClientReply</span><span class="sxs-lookup"><span data-stu-id="b629f-114">ClientReply</span></span>|<span data-ttu-id="b629f-115">客户端答复调用点。</span><span class="sxs-lookup"><span data-stu-id="b629f-115">Client reply call point.</span></span>|  
|<span data-ttu-id="b629f-116">ClientRequest</span><span class="sxs-lookup"><span data-stu-id="b629f-116">ClientRequest</span></span>|<span data-ttu-id="b629f-117">客户端请求调用点。</span><span class="sxs-lookup"><span data-stu-id="b629f-117">Client request call point.</span></span>|  
|<span data-ttu-id="b629f-118">ClientFault</span><span class="sxs-lookup"><span data-stu-id="b629f-118">ClientFault</span></span>|<span data-ttu-id="b629f-119">客户端故障点。</span><span class="sxs-lookup"><span data-stu-id="b629f-119">Client fault point.</span></span>|  
|<span data-ttu-id="b629f-120">ServiceReply</span><span class="sxs-lookup"><span data-stu-id="b629f-120">ServiceReply</span></span>|<span data-ttu-id="b629f-121">服务答复调用点。</span><span class="sxs-lookup"><span data-stu-id="b629f-121">Service reply call point.</span></span>|  
|<span data-ttu-id="b629f-122">serviceRequest</span><span class="sxs-lookup"><span data-stu-id="b629f-122">ServiceRequest</span></span>|<span data-ttu-id="b629f-123">服务请求调用点。</span><span class="sxs-lookup"><span data-stu-id="b629f-123">Service request call point.</span></span>|  
|<span data-ttu-id="b629f-124">ServiceFault</span><span class="sxs-lookup"><span data-stu-id="b629f-124">ServiceFault</span></span>|<span data-ttu-id="b629f-125">服务故障点。</span><span class="sxs-lookup"><span data-stu-id="b629f-125">Service fault point.</span></span>|  
|<span data-ttu-id="b629f-126">CallbackRequest</span><span class="sxs-lookup"><span data-stu-id="b629f-126">CallbackRequest</span></span>|<span data-ttu-id="b629f-127">回调请求调用点。</span><span class="sxs-lookup"><span data-stu-id="b629f-127">Callback request call point.</span></span>|  
|<span data-ttu-id="b629f-128">CallbackReply</span><span class="sxs-lookup"><span data-stu-id="b629f-128">CallbackReply</span></span>|<span data-ttu-id="b629f-129">回调答复调用点。</span><span class="sxs-lookup"><span data-stu-id="b629f-129">Callback reply call point.</span></span>|  
|<span data-ttu-id="b629f-130">CallbackFault</span><span class="sxs-lookup"><span data-stu-id="b629f-130">CallbackFault</span></span>|<span data-ttu-id="b629f-131">回调故障点。</span><span class="sxs-lookup"><span data-stu-id="b629f-131">Callback fault point.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b629f-132">示例</span><span class="sxs-lookup"><span data-stu-id="b629f-132">Example</span></span>  
 <span data-ttu-id="b629f-133">以下示例包含为在客户端答复状态中查找特定操作（“Receive”）而配置的事件筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="b629f-133">The following sample contains an event filter expression configured to find a specific operation ("Receive") in the client reply state.</span></span> <span data-ttu-id="b629f-134">这可通过使用的操作包括组合`GetOperationName`， `GetServiceContractCallPoint`，和逻辑运算。</span><span class="sxs-lookup"><span data-stu-id="b629f-134">This is done by using a combination of operations including `GetOperationName`, `GetServiceContractCallPoint`, and logical operations.</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Receive</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wcf:Operation Name="GetServiceContractCallPoint" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ClientReply</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b629f-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b629f-135">See Also</span></span>  
 [<span data-ttu-id="b629f-136">Windows Communication Foundation 中的操作</span><span class="sxs-lookup"><span data-stu-id="b629f-136">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)
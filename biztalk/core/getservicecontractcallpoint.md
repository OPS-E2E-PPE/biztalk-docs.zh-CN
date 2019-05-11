---
title: GetServiceContractCallPoint | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be03d100-0cba-4b80-8056-b582a2cd74ce
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53ebac10c1d690f47ab79c12affa3505b22f2e49
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345195"
---
# <a name="getservicecontractcallpoint"></a><span data-ttu-id="46650-102">GetServiceContractCallPoint</span><span class="sxs-lookup"><span data-stu-id="46650-102">GetServiceContractCallPoint</span></span>
<span data-ttu-id="46650-103">将推送到堆栈上的当前服务约定调用点的名称。</span><span class="sxs-lookup"><span data-stu-id="46650-103">Pushes the name of the current service contract call point onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46650-104">语法</span><span class="sxs-lookup"><span data-stu-id="46650-104">Syntax</span></span>  
  
```  
  
<wcf:Operation Name="GetServiceContractCallPoint" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="46650-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="46650-105">Parameters</span></span>  
 <span data-ttu-id="46650-106">无。</span><span class="sxs-lookup"><span data-stu-id="46650-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="46650-107">推送的值</span><span class="sxs-lookup"><span data-stu-id="46650-107">Pushed Value</span></span>  
 <span data-ttu-id="46650-108">包含当前的约定调用点的字符串。</span><span class="sxs-lookup"><span data-stu-id="46650-108">String containing the current contract call point.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46650-109">备注</span><span class="sxs-lookup"><span data-stu-id="46650-109">Remarks</span></span>  
 <span data-ttu-id="46650-110">Windows Communication Framework 服务可以在不同时间点截获生存期内的服务协定。</span><span class="sxs-lookup"><span data-stu-id="46650-110">A Windows Communication Framework service can be intercepted at different points in the lifetime of the service contract.</span></span> <span data-ttu-id="46650-111">这些位置定义的`System.BizTalk.Bam.Interceptors.Wcf.ContractCallPoint`枚举：</span><span class="sxs-lookup"><span data-stu-id="46650-111">These locations are defined by the `System.BizTalk.Bam.Interceptors.Wcf.ContractCallPoint` enumeration:</span></span>  
  
|<span data-ttu-id="46650-112">约定调用点</span><span class="sxs-lookup"><span data-stu-id="46650-112">Contract call point</span></span>|<span data-ttu-id="46650-113">Description</span><span class="sxs-lookup"><span data-stu-id="46650-113">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="46650-114">ClientReply</span><span class="sxs-lookup"><span data-stu-id="46650-114">ClientReply</span></span>|<span data-ttu-id="46650-115">客户端答复调用点。</span><span class="sxs-lookup"><span data-stu-id="46650-115">Client reply call point.</span></span>|  
|<span data-ttu-id="46650-116">ClientRequest</span><span class="sxs-lookup"><span data-stu-id="46650-116">ClientRequest</span></span>|<span data-ttu-id="46650-117">客户端请求调用点。</span><span class="sxs-lookup"><span data-stu-id="46650-117">Client request call point.</span></span>|  
|<span data-ttu-id="46650-118">ClientFault</span><span class="sxs-lookup"><span data-stu-id="46650-118">ClientFault</span></span>|<span data-ttu-id="46650-119">客户端故障点。</span><span class="sxs-lookup"><span data-stu-id="46650-119">Client fault point.</span></span>|  
|<span data-ttu-id="46650-120">ServiceReply</span><span class="sxs-lookup"><span data-stu-id="46650-120">ServiceReply</span></span>|<span data-ttu-id="46650-121">服务答复调用点。</span><span class="sxs-lookup"><span data-stu-id="46650-121">Service reply call point.</span></span>|  
|<span data-ttu-id="46650-122">ServiceRequest</span><span class="sxs-lookup"><span data-stu-id="46650-122">ServiceRequest</span></span>|<span data-ttu-id="46650-123">服务请求调用点。</span><span class="sxs-lookup"><span data-stu-id="46650-123">Service request call point.</span></span>|  
|<span data-ttu-id="46650-124">ServiceFault</span><span class="sxs-lookup"><span data-stu-id="46650-124">ServiceFault</span></span>|<span data-ttu-id="46650-125">服务故障点。</span><span class="sxs-lookup"><span data-stu-id="46650-125">Service fault point.</span></span>|  
|<span data-ttu-id="46650-126">CallbackRequest</span><span class="sxs-lookup"><span data-stu-id="46650-126">CallbackRequest</span></span>|<span data-ttu-id="46650-127">回调请求调用点。</span><span class="sxs-lookup"><span data-stu-id="46650-127">Callback request call point.</span></span>|  
|<span data-ttu-id="46650-128">CallbackReply</span><span class="sxs-lookup"><span data-stu-id="46650-128">CallbackReply</span></span>|<span data-ttu-id="46650-129">回调答复调用点。</span><span class="sxs-lookup"><span data-stu-id="46650-129">Callback reply call point.</span></span>|  
|<span data-ttu-id="46650-130">CallbackFault</span><span class="sxs-lookup"><span data-stu-id="46650-130">CallbackFault</span></span>|<span data-ttu-id="46650-131">回调故障点。</span><span class="sxs-lookup"><span data-stu-id="46650-131">Callback fault point.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="46650-132">示例</span><span class="sxs-lookup"><span data-stu-id="46650-132">Example</span></span>  
 <span data-ttu-id="46650-133">下面的示例包含配置为在客户端答复状态中查找特定操作 ("Receive") 的事件筛选器表达式。</span><span class="sxs-lookup"><span data-stu-id="46650-133">The following sample contains an event filter expression configured to find a specific operation ("Receive") in the client reply state.</span></span> <span data-ttu-id="46650-134">这是通过使用的操作，包括组合`GetOperationName`， `GetServiceContractCallPoint`，和逻辑运算。</span><span class="sxs-lookup"><span data-stu-id="46650-134">This is done by using a combination of operations including `GetOperationName`, `GetServiceContractCallPoint`, and logical operations.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="46650-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="46650-135">See Also</span></span>  
 [<span data-ttu-id="46650-136">Windows Communication Foundation 中的操作</span><span class="sxs-lookup"><span data-stu-id="46650-136">Operations in Windows Communication Foundation</span></span>](../core/operations-in-windows-communication-foundation.md)
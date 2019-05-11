---
title: 在你的代码中使用冲突解决程序组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d197cb28-78a9-4c8a-872b-f61ef15e6622
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 901ade5dd611c047c480f05ef0da8271150139d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396390"
---
# <a name="using-the-resolver-components-in-your-code"></a><span data-ttu-id="a5a74-102">在你的代码中使用冲突解决程序组件</span><span class="sxs-lookup"><span data-stu-id="a5a74-102">Using the Resolver Components in Your Code</span></span>
<span data-ttu-id="a5a74-103">动态转换代理从下面的代码段显示了默认在实时 (JIT) 解析功能。</span><span class="sxs-lookup"><span data-stu-id="a5a74-103">The following code fragment from the dynamic transformation agent shows the default just-in-time (JIT) resolution functionality.</span></span> <span data-ttu-id="a5a74-104">通过使用类似的代码，可以轻松在自己的应用程序中实现解决方法。</span><span class="sxs-lookup"><span data-stu-id="a5a74-104">You can easily implement resolution in your own application by using similar code.</span></span>  
  
```  
  
//XLANGs  
itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
resolvers = step.ItineraryStep.ResolverCollection;  
resolvers.MoveNext();  
resolver = resolvers.Current;  
  
// Pass the resolver configuration to the Resolver mgr for resolution.  
resolverDictionary = Microsoft.Practices.ESB.Resolver.ResolverMgr.Resolve(InboundMessage, resolver);  
  
// Set the transform type.  
transformType = resolverDictionary.Item("Resolver.TransformType");  
```  
  
 <span data-ttu-id="a5a74-105">在前面的列表中，**解决**方法**ResolverMgr**类返回**字典**对象，其中包含所有默认解析属性及其解析的值。</span><span class="sxs-lookup"><span data-stu-id="a5a74-105">In the preceding listing, the **Resolve** method of the **ResolverMgr** class returns a **Dictionary** object that contains all the default resolution properties and their resolved values.</span></span> <span data-ttu-id="a5a74-106">任何自定义冲突解决程序可以添加到自定义属性**字典**对象; 不采取这使这些属性可用于任何自定义路线服务。</span><span class="sxs-lookup"><span data-stu-id="a5a74-106">Any custom resolver can add custom properties to the **Dictionary** object; doing this makes those properties available to any custom itinerary service.</span></span>  
  
 <span data-ttu-id="a5a74-107">下表显示了通过包含在冲突解决程序可以根据需要填充属性[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a5a74-107">The following table shows the properties that can be optionally populated by the resolvers included in the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="a5a74-108">任何路线服务可以检索这些属性值由从返回提取这些**字典**对象。</span><span class="sxs-lookup"><span data-stu-id="a5a74-108">Any itinerary service can retrieve these property values by extracting them from the returned **Dictionary** object.</span></span>  
  
 <span data-ttu-id="a5a74-109">**属性**：</span><span class="sxs-lookup"><span data-stu-id="a5a74-109">**Properties**:</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="a5a74-110">**Resolver.Action**</span><span class="sxs-lookup"><span data-stu-id="a5a74-110">**Resolver.Action**</span></span>|<span data-ttu-id="a5a74-111">**Resolver.ActionField**</span><span class="sxs-lookup"><span data-stu-id="a5a74-111">**Resolver.ActionField**</span></span>|<span data-ttu-id="a5a74-112">**Resolver.DocumentSpecName**</span><span class="sxs-lookup"><span data-stu-id="a5a74-112">**Resolver.DocumentSpecName**</span></span>|  
|<span data-ttu-id="a5a74-113">**Resolver.Success**</span><span class="sxs-lookup"><span data-stu-id="a5a74-113">**Resolver.Success**</span></span>|<span data-ttu-id="a5a74-114">**Resolver.EndpointConfig**</span><span class="sxs-lookup"><span data-stu-id="a5a74-114">**Resolver.EndpointConfig**</span></span>|<span data-ttu-id="a5a74-115">**Resolver.DocumentSpecStrongName**</span><span class="sxs-lookup"><span data-stu-id="a5a74-115">**Resolver.DocumentSpecStrongName**</span></span>|  
|<span data-ttu-id="a5a74-116">**Resolver.FixJaxRpc**</span><span class="sxs-lookup"><span data-stu-id="a5a74-116">**Resolver.FixJaxRpc**</span></span>|<span data-ttu-id="a5a74-117">**Resolver.InboundTransportType**</span><span class="sxs-lookup"><span data-stu-id="a5a74-117">**Resolver.InboundTransportType**</span></span>|<span data-ttu-id="a5a74-118">**Resolver.EpmRRCorrelationToken**</span><span class="sxs-lookup"><span data-stu-id="a5a74-118">**Resolver.EpmRRCorrelationToken**</span></span>|  
|<span data-ttu-id="a5a74-119">**Resolver.InterchangeId**</span><span class="sxs-lookup"><span data-stu-id="a5a74-119">**Resolver.InterchangeId**</span></span>|<span data-ttu-id="a5a74-120">**Resolver.IsRequestResponse**</span><span class="sxs-lookup"><span data-stu-id="a5a74-120">**Resolver.IsRequestResponse**</span></span>|<span data-ttu-id="a5a74-121">**Resolver.InboundTransportLocation**</span><span class="sxs-lookup"><span data-stu-id="a5a74-121">**Resolver.InboundTransportLocation**</span></span>|  
|<span data-ttu-id="a5a74-122">**Resolver.MessageType**</span><span class="sxs-lookup"><span data-stu-id="a5a74-122">**Resolver.MessageType**</span></span>|<span data-ttu-id="a5a74-123">**Resolver.MethodName**</span><span class="sxs-lookup"><span data-stu-id="a5a74-123">**Resolver.MethodName**</span></span>|<span data-ttu-id="a5a74-124">**Resolver.MessageExchangePattern**</span><span class="sxs-lookup"><span data-stu-id="a5a74-124">**Resolver.MessageExchangePattern**</span></span>|  
|<span data-ttu-id="a5a74-125">**Resolver.ReceivePortName**</span><span class="sxs-lookup"><span data-stu-id="a5a74-125">**Resolver.ReceivePortName**</span></span>|<span data-ttu-id="a5a74-126">**Resolver.TransportLocation**</span><span class="sxs-lookup"><span data-stu-id="a5a74-126">**Resolver.TransportLocation**</span></span>|<span data-ttu-id="a5a74-127">**Resolver.OutboundTransportCLSID**</span><span class="sxs-lookup"><span data-stu-id="a5a74-127">**Resolver.OutboundTransportCLSID**</span></span>|  
|<span data-ttu-id="a5a74-128">**Resolver.TransformType**</span><span class="sxs-lookup"><span data-stu-id="a5a74-128">**Resolver.TransformType**</span></span>|<span data-ttu-id="a5a74-129">**Resolver.TargetNamespace**</span><span class="sxs-lookup"><span data-stu-id="a5a74-129">**Resolver.TargetNamespace**</span></span>|<span data-ttu-id="a5a74-130">**Resolver.ReceiveLocationName**</span><span class="sxs-lookup"><span data-stu-id="a5a74-130">**Resolver.ReceiveLocationName**</span></span>|  
|<span data-ttu-id="a5a74-131">**Resolver.TransportType**</span><span class="sxs-lookup"><span data-stu-id="a5a74-131">**Resolver.TransportType**</span></span>|<span data-ttu-id="a5a74-132">**Resolver.TransportNamespace**</span><span class="sxs-lookup"><span data-stu-id="a5a74-132">**Resolver.TransportNamespace**</span></span>|<span data-ttu-id="a5a74-133">**Resolver.WindowUserField**</span><span class="sxs-lookup"><span data-stu-id="a5a74-133">**Resolver.WindowUserField**</span></span>|  
|<span data-ttu-id="a5a74-134">**Resolver.CacheTimeout**</span><span class="sxs-lookup"><span data-stu-id="a5a74-134">**Resolver.CacheTimeout**</span></span>|||  
  
 <span data-ttu-id="a5a74-135">之后冲突解决程序管理器返回**字典**对象实例，适配器管理器设置特定的 BizTalk 适配器上下文属性的消息。</span><span class="sxs-lookup"><span data-stu-id="a5a74-135">After the resolver manager returns the **Dictionary** object instance, the adapter manager sets the specific BizTalk Adapter Context properties of the message.</span></span> <span data-ttu-id="a5a74-136">从路由代理的以下代码片段演示如何使用适配器管理器来设置传出消息的终结点属性。</span><span class="sxs-lookup"><span data-stu-id="a5a74-136">The following code fragment from the routing agent demonstrates how you can use the adapter manager to set the endpoint properties of the outgoing message.</span></span>  
  
```  
  
//XLANGs  
// Set the transport properties.  
transportLocation = resolverDictionary.Item("Resolver.TransportLocation");  
transportType = resolverDictionary.Item("Resolver.TransportType");  
  
// Create the delivery message.  
DeliveryMessage = InboundMessage;  
  
// Call the adapter manager to set all necessary properties on the message.  
Microsoft.Practices.ESB.Adapter.AdapterMgr.SetEndpoint(  
                                resolverDictionary,DeliveryMessage);  
  
// Set the delivery port address.  
DeliveryPort(Microsoft.XLANGs.BaseTypes.Address) = transportLocation;  
DeliveryPort(Microsoft.XLANGs.BaseTypes.TransportType) = transportType;  
```  
  
 <span data-ttu-id="a5a74-137">从路由代理的以下代码片段演示如何使用适配器管理器从自定义管道组件中的设置传出消息的终结点属性。</span><span class="sxs-lookup"><span data-stu-id="a5a74-137">The following code fragment from the routing agent demonstrates how to use the adapter manager from within a custom pipeline component to set the endpoint properties of an outgoing message.</span></span>  
  
```csharp  
// Resolve the configuration for routing.  
ResolverDictionary = ResolverMgr.Resolve(info, pInMsg, pContext);  
  
// Call the adapter manager to set all required message properties.  
AdapterMgr.SetEndpoint(ResolverDictionary, pInMsg.Context);  
```
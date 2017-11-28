---
title: "ESB 路线的选择器组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2cd8a85-e036-4817-9541-3fd720ca04ef
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c83cdd0b2022eb7dc4ad78e5702f5c21e4c4f432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-itinerary-selector-component"></a><span data-ttu-id="0ef56-102">ESB 路线的选择器组件</span><span class="sxs-lookup"><span data-stu-id="0ef56-102">The ESB Itinerary Selector Component</span></span>
<span data-ttu-id="0ef56-103">ESB 路线选择器组件允许没有路线 SOAP 标头来通过 ESB，通过选择冲突解决程序的帮助消息相应服务器端路线的传入消息。</span><span class="sxs-lookup"><span data-stu-id="0ef56-103">The ESB Itinerary Selector component allows incoming messages that do not have the itinerary SOAP header to pass through the ESB by selecting an appropriate server-side itinerary for the message with the help of a resolver.</span></span> <span data-ttu-id="0ef56-104">组件还用于使用 SOAP 标头来定义的名称和版本的一条路线，如客户端请求的消息。</span><span class="sxs-lookup"><span data-stu-id="0ef56-104">The component is also used for messages that use a SOAP header to define the name and version of an itinerary, as requested by the client.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="0ef56-105">安装</span><span class="sxs-lookup"><span data-stu-id="0ef56-105">Installation</span></span>  
 <span data-ttu-id="0ef56-106">自动安装 ESB 核心安装**ItinerarySelector**组件 BizTalk Server 管道组件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="0ef56-106">Installing the ESB Core automatically installs the **ItinerarySelector** component in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="0ef56-107">它是如何工作</span><span class="sxs-lookup"><span data-stu-id="0ef56-107">How It Works</span></span>  
 <span data-ttu-id="0ef56-108">ESB 路线选择器组件是可以仅位于接收管道的 Microsoft BizTalk 管道组件。</span><span class="sxs-lookup"><span data-stu-id="0ef56-108">The ESB Itinerary Selector component is a Microsoft BizTalk pipeline component that can reside only in a receive pipeline.</span></span> <span data-ttu-id="0ef56-109">组件选择使用服务器端路线中处理消息。</span><span class="sxs-lookup"><span data-stu-id="0ef56-109">The component selects a server-side itinerary for use in processing a message.</span></span> <span data-ttu-id="0ef56-110">消息传递中接收管道的组件，组件读取其配置和使用**ResolverConnectionString**调用正确的冲突解决程序，以查找相应路线时要使用的属性处理消息。</span><span class="sxs-lookup"><span data-stu-id="0ef56-110">As the message passes through the component in a receive pipeline, the component reads its configuration and uses the **ResolverConnectionString** property to call the correct resolver to look up the appropriate itinerary to use when processing the message.</span></span> <span data-ttu-id="0ef56-111">路线选择器组件然后执行与路线管道组件，以验证消息，并将提升确保消息继续到下一个处理阶段所需的属性相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="0ef56-111">The Itinerary Selector component then performs the same steps as the Itinerary pipeline component to validate the message and promote the properties necessary to ensure the message continues to the next processing stage.</span></span>  
  
## <a name="using-the-esb-itinerary-selector-component"></a><span data-ttu-id="0ef56-112">使用 ESB 路线的选择器组件</span><span class="sxs-lookup"><span data-stu-id="0ef56-112">Using the ESB Itinerary Selector Component</span></span>  
 <span data-ttu-id="0ef56-113">你可以将 ESB 路线组件添加到接收管道，然后在接收位置使用管道。</span><span class="sxs-lookup"><span data-stu-id="0ef56-113">You can add the ESB Itinerary component to a receive pipeline and then use the pipeline in a receive location.</span></span> <span data-ttu-id="0ef56-114">当使用在 WCF 提升、 名称和版本的客户端 （如在 SOAP 标头中表示） 请求路线路线静态解析程序配置此组件将可从消息上下文中检索并用于选择相应路线。</span><span class="sxs-lookup"><span data-stu-id="0ef56-114">When this component is configured with the ITINERARY-STATIC resolver in WCF on-ramp, the name and version of the itinerary requested by the client (as represented in the SOAP header) will be retrieved from the message context and used to select the appropriate itinerary.</span></span>  
  
## <a name="component-properties"></a><span data-ttu-id="0ef56-115">组件属性</span><span class="sxs-lookup"><span data-stu-id="0ef56-115">Component Properties</span></span>  
 <span data-ttu-id="0ef56-116">ESB 路线选择器组件公开三个公共属性：</span><span class="sxs-lookup"><span data-stu-id="0ef56-116">The ESB Itinerary Selector component exposes three public properties:</span></span>  
  
-   <span data-ttu-id="0ef56-117">**IgnoreErrorKey**。</span><span class="sxs-lookup"><span data-stu-id="0ef56-117">**IgnoreErrorKey**.</span></span> <span data-ttu-id="0ef56-118">此属性定义是否，如果由解析程序返回错误，消息应处理没有路线的情况下 (当设置为**True**) 或挂起。</span><span class="sxs-lookup"><span data-stu-id="0ef56-118">This property defines whether, if an error is returned by the resolver, the message should be processed without the itinerary (when set to **True**) or suspended.</span></span>  
  
-   <span data-ttu-id="0ef56-119">**ItineraryFactKey**。</span><span class="sxs-lookup"><span data-stu-id="0ef56-119">**ItineraryFactKey**.</span></span> <span data-ttu-id="0ef56-120">这表示由包含选择路线的实际 XML 解析程序返回的字典中的键。</span><span class="sxs-lookup"><span data-stu-id="0ef56-120">This represents the key in the dictionary returned by the resolver that contains the actual XML of the Itinerary selected.</span></span> <span data-ttu-id="0ef56-121">通常情况下， **Resolver.Itinerary**，除非使用自定义解析程序。</span><span class="sxs-lookup"><span data-stu-id="0ef56-121">Generally, **Resolver.Itinerary**, unless a custom resolver is used.</span></span>  
  
-   <span data-ttu-id="0ef56-122">**ResolverConnectionString**。</span><span class="sxs-lookup"><span data-stu-id="0ef56-122">**ResolverConnectionString**.</span></span> <span data-ttu-id="0ef56-123">这是一个包含一个冲突解决程序可以使用选择的名称-值对的冲突解决程序连接字符串和/或查找路线。</span><span class="sxs-lookup"><span data-stu-id="0ef56-123">This is a resolver connection string that contains name-value pairs that a resolver can use to select and/or look-up an itinerary.</span></span>
---
title: ESB 路线选择器组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2cd8a85-e036-4817-9541-3fd720ca04ef
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcce1fb4ab067e4620bbbca9134e5ac5f5c58889
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399764"
---
# <a name="the-esb-itinerary-selector-component"></a><span data-ttu-id="92638-102">ESB 路线选择器组件</span><span class="sxs-lookup"><span data-stu-id="92638-102">The ESB Itinerary Selector Component</span></span>
<span data-ttu-id="92638-103">ESB 路线选择器组件允许不具有 SOAP 标头通过选择相应的服务器端路线的冲突解决程序帮助的消息通过 ESB 路线的传入消息。</span><span class="sxs-lookup"><span data-stu-id="92638-103">The ESB Itinerary Selector component allows incoming messages that do not have the itinerary SOAP header to pass through the ESB by selecting an appropriate server-side itinerary for the message with the help of a resolver.</span></span> <span data-ttu-id="92638-104">该组件还用于使用 SOAP 标头来定义的名称和版本的路线，如客户端请求的消息。</span><span class="sxs-lookup"><span data-stu-id="92638-104">The component is also used for messages that use a SOAP header to define the name and version of an itinerary, as requested by the client.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="92638-105">安装</span><span class="sxs-lookup"><span data-stu-id="92638-105">Installation</span></span>  
 <span data-ttu-id="92638-106">自动安装 ESB 核心安装**ItinerarySelector**组件的 BizTalk Server 管道组件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="92638-106">Installing the ESB Core automatically installs the **ItinerarySelector** component in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="92638-107">其工作原理</span><span class="sxs-lookup"><span data-stu-id="92638-107">How It Works</span></span>  
 <span data-ttu-id="92638-108">ESB 路线选择器组件是可以仅在接收管道中驻留的 Microsoft BizTalk 管道组件。</span><span class="sxs-lookup"><span data-stu-id="92638-108">The ESB Itinerary Selector component is a Microsoft BizTalk pipeline component that can reside only in a receive pipeline.</span></span> <span data-ttu-id="92638-109">该组件选择使用服务器端路线中处理消息。</span><span class="sxs-lookup"><span data-stu-id="92638-109">The component selects a server-side itinerary for use in processing a message.</span></span> <span data-ttu-id="92638-110">消息通过接收管道中的组件，该组件读取其配置，并使用**ResolverConnectionString**属性来调用要查找适当的路线时要使用的正确解析程序处理消息。</span><span class="sxs-lookup"><span data-stu-id="92638-110">As the message passes through the component in a receive pipeline, the component reads its configuration and uses the **ResolverConnectionString** property to call the correct resolver to look up the appropriate itinerary to use when processing the message.</span></span> <span data-ttu-id="92638-111">然后，路线选择器组件执行路线管道组件以验证消息，并将提升以确保该消息将持续到下一个处理阶段所必需的属性与相同的步骤。</span><span class="sxs-lookup"><span data-stu-id="92638-111">The Itinerary Selector component then performs the same steps as the Itinerary pipeline component to validate the message and promote the properties necessary to ensure the message continues to the next processing stage.</span></span>  
  
## <a name="using-the-esb-itinerary-selector-component"></a><span data-ttu-id="92638-112">使用 ESB 路线选择器组件</span><span class="sxs-lookup"><span data-stu-id="92638-112">Using the ESB Itinerary Selector Component</span></span>  
 <span data-ttu-id="92638-113">您可以将 ESB 路线组件添加到接收管道，然后在接收位置使用管道。</span><span class="sxs-lookup"><span data-stu-id="92638-113">You can add the ESB Itinerary component to a receive pipeline and then use the pipeline in a receive location.</span></span> <span data-ttu-id="92638-114">当此组件配置有中 WCF 接入点、 名称和版本 （如 SOAP 标头中所示），客户端请求路线的旅行计划静态解析程序将从消息上下文中检索并用于选择相应路线。</span><span class="sxs-lookup"><span data-stu-id="92638-114">When this component is configured with the ITINERARY-STATIC resolver in WCF on-ramp, the name and version of the itinerary requested by the client (as represented in the SOAP header) will be retrieved from the message context and used to select the appropriate itinerary.</span></span>  
  
## <a name="component-properties"></a><span data-ttu-id="92638-115">组件属性</span><span class="sxs-lookup"><span data-stu-id="92638-115">Component Properties</span></span>  
 <span data-ttu-id="92638-116">ESB 路线选择器组件公开三个公共属性：</span><span class="sxs-lookup"><span data-stu-id="92638-116">The ESB Itinerary Selector component exposes three public properties:</span></span>  
  
-   <span data-ttu-id="92638-117">**IgnoreErrorKey**。</span><span class="sxs-lookup"><span data-stu-id="92638-117">**IgnoreErrorKey**.</span></span> <span data-ttu-id="92638-118">此属性定义是否，如果由解析程序返回错误，消息应处理没有路线的情况下 (当设置为 **，则返回 True**) 或已挂起。</span><span class="sxs-lookup"><span data-stu-id="92638-118">This property defines whether, if an error is returned by the resolver, the message should be processed without the itinerary (when set to **True**) or suspended.</span></span>  
  
-   <span data-ttu-id="92638-119">**ItineraryFactKey**。</span><span class="sxs-lookup"><span data-stu-id="92638-119">**ItineraryFactKey**.</span></span> <span data-ttu-id="92638-120">这表示由包含所选路线的实际 XML 解析程序返回的字典中的项。</span><span class="sxs-lookup"><span data-stu-id="92638-120">This represents the key in the dictionary returned by the resolver that contains the actual XML of the Itinerary selected.</span></span> <span data-ttu-id="92638-121">通常情况下， **Resolver.Itinerary**，除非使用自定义冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="92638-121">Generally, **Resolver.Itinerary**, unless a custom resolver is used.</span></span>  
  
-   <span data-ttu-id="92638-122">**ResolverConnectionString**。</span><span class="sxs-lookup"><span data-stu-id="92638-122">**ResolverConnectionString**.</span></span> <span data-ttu-id="92638-123">这是一个包含冲突解决程序可以使用选择的名称 / 值对的冲突解决程序连接字符串和/或查找路线。</span><span class="sxs-lookup"><span data-stu-id="92638-123">This is a resolver connection string that contains name-value pairs that a resolver can use to select and/or look-up an itinerary.</span></span>
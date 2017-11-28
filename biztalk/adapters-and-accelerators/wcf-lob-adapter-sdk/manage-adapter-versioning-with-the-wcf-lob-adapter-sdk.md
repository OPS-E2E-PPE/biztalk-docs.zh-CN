---
title: "管理使用 WCF LOB 适配器 SDK 适配器进行版本控制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb596fdd-251c-4978-9f33-cf2883d281d8
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf8d5d13c37f683a118484c9c08fa90c13a95533
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manage-adapter-versioning-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="cfed3-102">管理使用 WCF LOB 适配器 SDK 适配器进行版本控制</span><span class="sxs-lookup"><span data-stu-id="cfed3-102">Manage adapter versioning with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="cfed3-103">初始部署之后的适配器和在其生存期期间可能多次，可能需要更改的原因有多种多样适配器 （和它们公开的终结点）。</span><span class="sxs-lookup"><span data-stu-id="cfed3-103">After initial deployment of adapters and potentially several times during their lifetime, adapters (and the endpoints they expose) may need to be changed for a variety of reasons.</span></span> <span data-ttu-id="cfed3-104">这些原因包括更改业务需求、 信息技术要求或与业务系统或适配器本身的行的问题。</span><span class="sxs-lookup"><span data-stu-id="cfed3-104">These reasons include changing business needs, information technology requirements, or issues with the line of business system or the adapter itself.</span></span> <span data-ttu-id="cfed3-105">本主题讨论不同的策略来处理使用编写的适配器的版本控制[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cfed3-105">This topic discusses different strategies for handling versioning for adapters that are written using the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span>  
  
## <a name="versioning-and-windows-communication-foundation"></a><span data-ttu-id="cfed3-106">版本控制和 Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="cfed3-106">Versioning and Windows Communication Foundation</span></span>  
 <span data-ttu-id="cfed3-107">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]基于[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]，并依赖于其基础结构，以便系统之间交换消息。</span><span class="sxs-lookup"><span data-stu-id="cfed3-107">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is built upon  [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] and relies on its infrastructure for exchanging messages between systems.</span></span> <span data-ttu-id="cfed3-108">使用机制，[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]公开，你可以版本服务和数据协定。</span><span class="sxs-lookup"><span data-stu-id="cfed3-108">Using mechanisms that  [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] exposes, you can version both services and data contracts.</span></span> <span data-ttu-id="cfed3-109">有关详细信息，包括服务版本控制的最佳实践，请参阅[服务版本控制](http://go.microsoft.com/fwlink/?LinkId=85497)中[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]联机引用。</span><span class="sxs-lookup"><span data-stu-id="cfed3-109">For more information, including best practices for service versioning, see [Service Versioning](http://go.microsoft.com/fwlink/?LinkId=85497) in the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] online reference.</span></span> <span data-ttu-id="cfed3-110">有关详细信息，包括最佳实践数据协定版本管理，请参阅[数据协定版本管理](http://go.microsoft.com/fwlink/?LinkId=120177)中[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]联机引用。</span><span class="sxs-lookup"><span data-stu-id="cfed3-110">For more information, including best practices for data contract versioning, see [Data Contract Versioning](http://go.microsoft.com/fwlink/?LinkId=120177) in the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] online reference.</span></span>  
  
## <a name="versioning-scenarios"></a><span data-ttu-id="cfed3-111">版本控制方案</span><span class="sxs-lookup"><span data-stu-id="cfed3-111">Versioning Scenarios</span></span>  
 <span data-ttu-id="cfed3-112">有两个主版本控制方案：</span><span class="sxs-lookup"><span data-stu-id="cfed3-112">There are two primary versioning scenarios:</span></span>  
  
-   <span data-ttu-id="cfed3-113">一个适配器版本支持目标系统的多个的版本。</span><span class="sxs-lookup"><span data-stu-id="cfed3-113">One adapter version supports multiple versions of the target system.</span></span>  
  
-   <span data-ttu-id="cfed3-114">两个或多个适配器版本支持相同的系统或两个或多个不同的系统。</span><span class="sxs-lookup"><span data-stu-id="cfed3-114">Two or more adapter versions support the same system or two or more different systems.</span></span>  
  
 <span data-ttu-id="cfed3-115">你可能还需要发布你的适配器的新版本，如果更新到[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]影响现有功能。</span><span class="sxs-lookup"><span data-stu-id="cfed3-115">You may also need to release a new version of your adapter if updates to the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] affect existing functionality.</span></span>  
  
 <span data-ttu-id="cfed3-116">每种方案需要有一个不同的版本控制策略。</span><span class="sxs-lookup"><span data-stu-id="cfed3-116">Each of these scenarios requires a different versioning strategy.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfed3-117">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]不强制实施任何特定版本管理方案。</span><span class="sxs-lookup"><span data-stu-id="cfed3-117">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] does not enforce any specific versioning scenarios.</span></span> <span data-ttu-id="cfed3-118">它是从左到开发人员确定适配器的版本控制要求。</span><span class="sxs-lookup"><span data-stu-id="cfed3-118">It is left to the developer to determine versioning requirements for an adapter.</span></span>  
  
### <a name="one-adapter-supports-multiple-versions-of-target-system"></a><span data-ttu-id="cfed3-119">一个适配器支持多个版本的目标系统</span><span class="sxs-lookup"><span data-stu-id="cfed3-119">One adapter supports multiple versions of target system</span></span>  
 <span data-ttu-id="cfed3-120">当适配器支持多个版本的目标系统时，应公开可用于标识所需的版本的一个或多个绑定属性。</span><span class="sxs-lookup"><span data-stu-id="cfed3-120">When the adapter supports multiple versions of the target system, you should expose one or more binding properties that can be used to identify the desired version.</span></span> <span data-ttu-id="cfed3-121">例如，一个适配器可能支持目标系统的供应商提供的多个通信库。</span><span class="sxs-lookup"><span data-stu-id="cfed3-121">For example, an adapter might support multiple communication libraries supplied by the target system's vendor.</span></span> <span data-ttu-id="cfed3-122">适配器使用者使用名为"LibraryVersion"的自定义绑定属性，可以选择要使用其中库基于部署环境或其他需求。</span><span class="sxs-lookup"><span data-stu-id="cfed3-122">Using a custom binding property named "LibraryVersion," the adapter consumer could choose which library to use based on the deployment environment or other requirements.</span></span>  
  
### <a name="two-or-more-adapters-support-one-version-of-target-system"></a><span data-ttu-id="cfed3-123">两个或多个适配器支持目标系统的一个的版本</span><span class="sxs-lookup"><span data-stu-id="cfed3-123">Two or more adapters support one version of target system</span></span>  
 <span data-ttu-id="cfed3-124">在这种情况下，每个适配器应使用唯一的方案 (ContosoV1: / / 和 ContosoV2: / /) 和一个唯一的绑定名称 （ContosoV1Binding 和 ContosoV2Binding）。</span><span class="sxs-lookup"><span data-stu-id="cfed3-124">In this case, each adapter should use a unique scheme (ContosoV1:// and ContosoV2://) and a unique binding name (ContosoV1Binding and ContosoV2Binding).</span></span> <span data-ttu-id="cfed3-125">供应商应考虑使用中的方案和绑定名称以及 （例如，Microsoft.ContosoV1:// 和 Microsoft.ContosoV1Binding） 其名称。</span><span class="sxs-lookup"><span data-stu-id="cfed3-125">Vendors should consider using their name in the scheme and binding name as well (for example, Microsoft.ContosoV1:// and Microsoft.ContosoV1Binding).</span></span>  
  
### <a name="new-versions-of-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="cfed3-126">新版本的 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="cfed3-126">New versions of the WCF LOB Adapter SDK</span></span>  
 <span data-ttu-id="cfed3-127">当新版本的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是发布，你将能够安装新版本，而无需重新编译你的适配器，因为[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]版本都是向后兼容。</span><span class="sxs-lookup"><span data-stu-id="cfed3-127">When new versions of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] are released, you will be able to install the new version without having to recompile your adapter, since [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] releases are be backward-compatible.</span></span> <span data-ttu-id="cfed3-128">但是，应评估新的版本，以确定是否更改的功能，你的适配器依赖或者如果你的适配器会带来好处实现的新功能。</span><span class="sxs-lookup"><span data-stu-id="cfed3-128">However, you should evaluate new releases to determine if there is a change in functionality that your adapter depends on, or if there is new functionality that your adapter would benefit from implementing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfed3-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfed3-129">See Also</span></span>  
 [<span data-ttu-id="cfed3-130">使用 WCF LOB 适配器 SDK 开发最佳做法</span><span class="sxs-lookup"><span data-stu-id="cfed3-130">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)
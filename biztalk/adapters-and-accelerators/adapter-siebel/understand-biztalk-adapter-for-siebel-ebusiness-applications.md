---
title: 了解用于 Siebel eBusiness 应用程序的 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- features of Siebel adapters
- adapters, features
- adapter, overview
ms.assetid: 3249fb74-9ca1-4b81-971d-5151a2e354fe
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 788db9ba048141256cfaa3cc5017fa48bd6ec7de
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999230"
---
# <a name="understand-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="8f083-102">了解用于 Siebel eBusiness 应用程序的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="8f083-102">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="8f083-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统进行交互，以面向服务的编程访问。</span><span class="sxs-lookup"><span data-stu-id="8f083-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="8f083-104">适配器向客户端提供以下优势：</span><span class="sxs-lookup"><span data-stu-id="8f083-104">The adapters provide the following advantages to clients:</span></span>  
  
- <span data-ttu-id="8f083-105">**一致的设计时体验**。</span><span class="sxs-lookup"><span data-stu-id="8f083-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="8f083-106">适配器提供用于浏览、 搜索和检索元数据的 LOB 项目的常见和用户友好的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="8f083-106">The adapters provide a common and user-friendly design time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
- <span data-ttu-id="8f083-107">**不同的编程选项**。</span><span class="sxs-lookup"><span data-stu-id="8f083-107">**Varied programming options**.</span></span> <span data-ttu-id="8f083-108">适配器提供了一种编程模型包括 Windows Communication Foundation (WCF) 通道模型，WCF 服务模型中，ADO.NET 中，Web 服务或 BizTalk 支持的模型。</span><span class="sxs-lookup"><span data-stu-id="8f083-108">The adapters provide a choice of programming model including Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, Web services, or BizTalk supported models.</span></span>  
  
- <span data-ttu-id="8f083-109">**跨 Lob 的统一体验**。</span><span class="sxs-lookup"><span data-stu-id="8f083-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="8f083-110">使用 WCF 适配器标准化和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]并因此提供获取访问权的任何 LOB 系统的统一的体验。</span><span class="sxs-lookup"><span data-stu-id="8f083-110">The adapters standardize on using the WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
  <span data-ttu-id="8f083-111">如前文所述，基于 WCF LOB 适配器 SDK 构建适配器。</span><span class="sxs-lookup"><span data-stu-id="8f083-111">As mentioned, the adapters are built on top of the WCF LOB Adapter SDK.</span></span> <span data-ttu-id="8f083-112">WCF LOB 适配器 SDK 提供用于生成各种 BizTalk Server 和 Microsoft Office 等客户端应用程序可以使用的集成适配器公共基础。</span><span class="sxs-lookup"><span data-stu-id="8f083-112">The WCF LOB Adapter SDK provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="8f083-113">WCF LOB 适配器 SDK 通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道对齐适配器策略与 Microsoft 服务策略。</span><span class="sxs-lookup"><span data-stu-id="8f083-113">The WCF LOB Adapter SDK aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="8f083-114">有关 WCF LOB 适配器 SDK 的详细信息，请参阅[WCF LOB 适配器 SDK 文档](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)。</span><span class="sxs-lookup"><span data-stu-id="8f083-114">For more information about the WCF LOB Adapter SDK, see [WCF LOB Adapter SDK documentation](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).</span></span>
  
  <span data-ttu-id="8f083-115">若要执行 Siebel 系统的操作，适配器客户端必须具有对业务服务公开的 Siebel 系统的访问。</span><span class="sxs-lookup"><span data-stu-id="8f083-115">To perform operations on a Siebel system, adapter clients must have access to business services exposed by the Siebel system.</span></span> <span data-ttu-id="8f083-116">Siebel 应用程序公开数据作为业务组件和业务对象。</span><span class="sxs-lookup"><span data-stu-id="8f083-116">A Siebel application exposes data as business components and business objects.</span></span> <span data-ttu-id="8f083-117">Siebel*业务组件*是将一个或多个表中的列的单个结构相关联的逻辑实体。</span><span class="sxs-lookup"><span data-stu-id="8f083-117">A Siebel *business component* is a logical entity that associates columns from one or more tables into a single structure.</span></span> <span data-ttu-id="8f083-118">Siebel*业务对象*通过将在一起的一组相互关联的业务组件中实现的业务模型。</span><span class="sxs-lookup"><span data-stu-id="8f083-118">A Siebel *business object* implements a business model by tying together a set of interrelated business components.</span></span> <span data-ttu-id="8f083-119">使用[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]，Siebel 业务对象和业务组件，可能会出现适配器客户端。</span><span class="sxs-lookup"><span data-stu-id="8f083-119">With the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)], adapter clients can surface Siebel business objects and business components.</span></span>  
  
  <span data-ttu-id="8f083-120">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]还包括[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="8f083-120">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] also includes the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span></span> <span data-ttu-id="8f083-121">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]通过扩展 ADO.NET 接口提供到 Siebel 系统的 ADO 接口。</span><span class="sxs-lookup"><span data-stu-id="8f083-121">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] provides an ADO interface to a Siebel system by extending ADO.NET interfaces.</span></span>  
  
  <span data-ttu-id="8f083-122">本部分讨论的功能[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]和[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8f083-122">This section discusses the features of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f083-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="8f083-123">In This Section</span></span>  
  
-   [<span data-ttu-id="8f083-124">用于 Siebel eBusiness 应用程序的 BizTalk 适配器概述</span><span class="sxs-lookup"><span data-stu-id="8f083-124">Overview of BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [<span data-ttu-id="8f083-125">Siebel 适配器的主要功能</span><span class="sxs-lookup"><span data-stu-id="8f083-125">Key Features in the Siebel Adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/key-features-in-the-siebel-adapter.md) 
  
-   [<span data-ttu-id="8f083-126">用于 Siebel eBusiness 应用程序的 BizTalk 适配器的限制</span><span class="sxs-lookup"><span data-stu-id="8f083-126">Limitations of BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [<span data-ttu-id="8f083-127">关于 Siebel 的数据提供程序</span><span class="sxs-lookup"><span data-stu-id="8f083-127">About the Data Provider for Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/about-the-data-provider-for-siebel.md)
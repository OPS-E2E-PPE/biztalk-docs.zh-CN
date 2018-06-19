---
title: 了解 BizTalk 适配器的 Siebel eBusiness Applications |Microsoft 文档
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
ms.openlocfilehash: 51c3576df5f62a0350f85d79b603c9f1cbda8a60
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962611"
---
# <a name="understand-biztalk-adapter-for-siebel-ebusiness-applications"></a><span data-ttu-id="e4037-102">为 Siebel eBusiness 应用程序了解的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="e4037-102">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>
<span data-ttu-id="e4037-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统交互，以面向服务的编程访问。</span><span class="sxs-lookup"><span data-stu-id="e4037-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="e4037-104">适配器向客户端提供以下优势：</span><span class="sxs-lookup"><span data-stu-id="e4037-104">The adapters provide the following advantages to clients:</span></span>  
  
-   <span data-ttu-id="e4037-105">**一致的设计时体验**。</span><span class="sxs-lookup"><span data-stu-id="e4037-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="e4037-106">适配器提供用于浏览、 搜索和检索元数据的 LOB 项目的常见和用户友好的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="e4037-106">The adapters provide a common and user-friendly design time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
-   <span data-ttu-id="e4037-107">**各种编程选项**。</span><span class="sxs-lookup"><span data-stu-id="e4037-107">**Varied programming options**.</span></span> <span data-ttu-id="e4037-108">适配器均提供一种编程模型，包括 Windows Communication Foundation (WCF) 通道模型，WCF 服务模型中，ADO.NET 中，Web 服务，或 BizTalk 支持模型。</span><span class="sxs-lookup"><span data-stu-id="e4037-108">The adapters provide a choice of programming model including Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, Web services, or BizTalk supported models.</span></span>  
  
-   <span data-ttu-id="e4037-109">**跨 Lob 的统一体验**。</span><span class="sxs-lookup"><span data-stu-id="e4037-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="e4037-110">适配器上使用的是 WCF 标准化和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并因此提供获得对任何 LOB 系统的访问的统一体验。</span><span class="sxs-lookup"><span data-stu-id="e4037-110">The adapters standardize on using the WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
 <span data-ttu-id="e4037-111">如前文所述，适配器均构建在之上[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e4037-111">As mentioned, the adapters are built on top of the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> <span data-ttu-id="e4037-112">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]为生成各种如 BizTalk Server 和 Microsoft Office 的客户端应用程序可以使用的集成适配器提供了常见的基础。</span><span class="sxs-lookup"><span data-stu-id="e4037-112">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="e4037-113">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道结合适配器策略与 Microsoft 服务策略。</span><span class="sxs-lookup"><span data-stu-id="e4037-113">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="e4037-114">有关详细信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，请参阅[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="e4037-114">For more information about the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], see the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentation.</span></span> <span data-ttu-id="e4037-115">文档安装连同[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，通常在\<安装驱动器\>: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents。</span><span class="sxs-lookup"><span data-stu-id="e4037-115">The documentation is installed along with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], typically under \<installation drive\>:\Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents.</span></span>  
  
 <span data-ttu-id="e4037-116">若要执行 Siebel 系统的操作，适配器客户端必须有权公开的 Siebel 系统的业务服务。</span><span class="sxs-lookup"><span data-stu-id="e4037-116">To perform operations on a Siebel system, adapter clients must have access to business services exposed by the Siebel system.</span></span> <span data-ttu-id="e4037-117">Siebel 应用程序将数据公开为业务组件和业务对象。</span><span class="sxs-lookup"><span data-stu-id="e4037-117">A Siebel application exposes data as business components and business objects.</span></span> <span data-ttu-id="e4037-118">Siebel*在业务组件*是将一个或多个表中的列到单个结构相关联的逻辑实体。</span><span class="sxs-lookup"><span data-stu-id="e4037-118">A Siebel *business component* is a logical entity that associates columns from one or more tables into a single structure.</span></span> <span data-ttu-id="e4037-119">Siebel*业务对象*通过将在一起的一组相关的业务组件中实现的业务模型。</span><span class="sxs-lookup"><span data-stu-id="e4037-119">A Siebel *business object* implements a business model by tying together a set of interrelated business components.</span></span> <span data-ttu-id="e4037-120">与[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]，适配器客户端可以外围 Siebel 业务对象和业务组件。</span><span class="sxs-lookup"><span data-stu-id="e4037-120">With the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)], adapter clients can surface Siebel business objects and business components.</span></span>  
  
 <span data-ttu-id="e4037-121">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]还包括[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="e4037-121">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] also includes the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span></span> <span data-ttu-id="e4037-122">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] Siebel 系统为 ADO 接口提供通过扩展 ADO.NET 接口。</span><span class="sxs-lookup"><span data-stu-id="e4037-122">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] provides an ADO interface to a Siebel system by extending ADO.NET interfaces.</span></span>  
  
 <span data-ttu-id="e4037-123">本部分讨论的功能[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]和[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e4037-123">This section discusses the features of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] and the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4037-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="e4037-124">In This Section</span></span>  
  
-   [<span data-ttu-id="e4037-125">用于 Siebel eBusiness 应用程序的 BizTalk 适配器概述</span><span class="sxs-lookup"><span data-stu-id="e4037-125">Overview of BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [<span data-ttu-id="e4037-126">Siebel 适配器中的主要功能</span><span class="sxs-lookup"><span data-stu-id="e4037-126">Key Features in the Siebel Adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/key-features-in-the-siebel-adapter.md) 
  
-   [<span data-ttu-id="e4037-127">用于 Siebel eBusiness 应用程序的 BizTalk 适配器的限制</span><span class="sxs-lookup"><span data-stu-id="e4037-127">Limitations of BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
  
-   [<span data-ttu-id="e4037-128">关于 Siebel 的数据提供程序</span><span class="sxs-lookup"><span data-stu-id="e4037-128">About the Data Provider for Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/about-the-data-provider-for-siebel.md)
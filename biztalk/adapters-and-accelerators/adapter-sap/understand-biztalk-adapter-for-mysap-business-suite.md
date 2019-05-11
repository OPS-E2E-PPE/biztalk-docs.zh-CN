---
title: 了解用于 mySAP Business Suite 的 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- adapters, features
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- features of SAP adapter
- adapters, about SAP ADO Provider
ms.assetid: 136ca828-2724-454b-9d4d-a491d45e1eda
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2a4b611184962138c102dfadc6f33250ce16a29
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372242"
---
# <a name="understand-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="e7c76-102">了解用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="e7c76-102">Understand BizTalk Adapter for mySAP Business Suite</span></span>
<span data-ttu-id="e7c76-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统进行交互，以面向服务的编程访问。</span><span class="sxs-lookup"><span data-stu-id="e7c76-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="e7c76-104">适配器向客户端提供以下优势：</span><span class="sxs-lookup"><span data-stu-id="e7c76-104">The adapters provide the following advantages to clients:</span></span>  
  
- <span data-ttu-id="e7c76-105">**一致的设计时体验**。</span><span class="sxs-lookup"><span data-stu-id="e7c76-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="e7c76-106">适配器提供用于浏览、 搜索和检索元数据的 LOB 项目的常见和用户友好的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="e7c76-106">The adapters provide a common and user-friendly design time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
- <span data-ttu-id="e7c76-107">**不同的编程选项**。</span><span class="sxs-lookup"><span data-stu-id="e7c76-107">**Varied programming options**.</span></span> <span data-ttu-id="e7c76-108">适配器提供了一种编程模型包括 Windows Communication Foundation (WCF) 通道模型、 WCF 服务模型、 ADO.NET、 web 服务或 BizTalk 支持模型。</span><span class="sxs-lookup"><span data-stu-id="e7c76-108">The adapters provide a choice of programming model including Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, web services, or BizTalk supported models.</span></span>  
  
- <span data-ttu-id="e7c76-109">**跨 Lob 的统一体验**。</span><span class="sxs-lookup"><span data-stu-id="e7c76-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="e7c76-110">使用 WCF 适配器标准化和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]并因此提供获取访问权的任何 LOB 系统的统一的体验。</span><span class="sxs-lookup"><span data-stu-id="e7c76-110">The adapters standardize on using the WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
  <span data-ttu-id="e7c76-111">如前文所述，基于 WCF LOB 适配器 SDK 构建适配器。</span><span class="sxs-lookup"><span data-stu-id="e7c76-111">As mentioned, the adapters are built on top of the WCF LOB Adapter SDK.</span></span> <span data-ttu-id="e7c76-112">WCF LOB 适配器 SDK 提供用于生成各种 BizTalk Server 和 Microsoft Office 等客户端应用程序可以使用的集成适配器公共基础。</span><span class="sxs-lookup"><span data-stu-id="e7c76-112">The WCF LOB Adapter SDK provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="e7c76-113">WCF LOB 适配器 SDK 通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道对齐适配器策略与 Microsoft 服务策略。</span><span class="sxs-lookup"><span data-stu-id="e7c76-113">The WCF LOB Adapter SDK aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="e7c76-114">有关 WCF LOB 适配器 SDK 的详细信息，请参阅[WCF LOB 适配器 SDK 文档](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)。</span><span class="sxs-lookup"><span data-stu-id="e7c76-114">For more information about the WCF LOB Adapter SDK, see [WCF LOB Adapter SDK documentation](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).</span></span>
  
  <span data-ttu-id="e7c76-115">若要执行 SAP 系统的操作，适配器客户端必须有权相关远程函数调用 (Rfc)、 业务应用程序编程接口 (Bapi) 和 Idoc （或中间文档）。</span><span class="sxs-lookup"><span data-stu-id="e7c76-115">To perform operations on an SAP system, adapter clients must have access to the relevant Remote Function Calls (RFCs), Business Application Programming Interfaces (BAPIs), and IDOCs (or intermediate documents).</span></span> <span data-ttu-id="e7c76-116">SAP R/3 系统公开 Rfc 和 Bapi，Idoc 的业务集成。</span><span class="sxs-lookup"><span data-stu-id="e7c76-116">An SAP R/3 system exposes RFCs, BAPIs, and IDOCs for business integration.</span></span> <span data-ttu-id="e7c76-117">Rfc 是实现特定的业务逻辑的远程函数模块。</span><span class="sxs-lookup"><span data-stu-id="e7c76-117">RFCs are remote function modules that implement specific business logic.</span></span> <span data-ttu-id="e7c76-118">可以从 BizTalk Server 之类的外部应用程序或.NET 应用程序调用此逻辑。</span><span class="sxs-lookup"><span data-stu-id="e7c76-118">This logic can be invoked from an external application such as BizTalk Server or a .NET application.</span></span> <span data-ttu-id="e7c76-119">Bapi 是方法的接口连接到 SAP 业务对象，进而通过标准 RFC 接口公开的。</span><span class="sxs-lookup"><span data-stu-id="e7c76-119">BAPIs are method interfaces to SAP business objects, which are in turn exposed through standard RFC interfaces.</span></span> <span data-ttu-id="e7c76-120">Idoc 是一种机制来抽象 SAP 和非 SAP 系统之间的通信的电子数据交换 (EDI) 通信层。</span><span class="sxs-lookup"><span data-stu-id="e7c76-120">IDOCs are a mechanism to abstract the electronic data interchange (EDI) communication layer for communication between SAP and non-SAP systems.</span></span> <span data-ttu-id="e7c76-121">使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]，可以访问的 Rfc Bapi，以及 Idoc 公开的 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="e7c76-121">With [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)], you can access the RFCs, BAPIs, and IDOCs exposed by an SAP system.</span></span>  
  
  <span data-ttu-id="e7c76-122">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还包括[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]，其中提供了 SAP 系统的 ADO 接口。</span><span class="sxs-lookup"><span data-stu-id="e7c76-122">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] also includes [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], which provides an ADO interface to the SAP system.</span></span>  
  
  <span data-ttu-id="e7c76-123">本部分列出的功能[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]和[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e7c76-123">This section lists the features for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7c76-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="e7c76-124">In This Section</span></span>  
  
-   [<span data-ttu-id="e7c76-125">用于 mySAP Business Suite 的 BizTalk 适配器的体系结构概述</span><span class="sxs-lookup"><span data-stu-id="e7c76-125">Architecture overview of BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [<span data-ttu-id="e7c76-126">SAP 适配器的主要功能</span><span class="sxs-lookup"><span data-stu-id="e7c76-126">Key Features in the SAP Adapter</span></span>](../../adapters-and-accelerators/adapter-sap/key-features-in-the-sap-adapter.md)  
  
-   [<span data-ttu-id="e7c76-127">用于 mySAP Business Suite 的 BizTalk 适配器限制</span><span class="sxs-lookup"><span data-stu-id="e7c76-127">Limitations of BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/limitations-of-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [<span data-ttu-id="e7c76-128">关于 mySAP Business Suite 的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="e7c76-128">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)  
  
## <a name="see-also"></a><span data-ttu-id="e7c76-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7c76-129">See Also</span></span>  
[<span data-ttu-id="e7c76-130">开始使用用于 mySAP Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="e7c76-130">Get started with the BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)
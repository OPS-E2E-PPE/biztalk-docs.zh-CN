---
title: 了解为 mySAP Business Suite 的 BizTalk Adapter |Microsoft 文档
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
ms.openlocfilehash: b5d04c435208e316c343ac7b307943e0f91b8af7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962195"
---
# <a name="understand-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="c0c99-102">为 mySAP Business Suite 了解 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="c0c99-102">Understand BizTalk Adapter for mySAP Business Suite</span></span>
<span data-ttu-id="c0c99-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统交互，以面向服务的编程访问。</span><span class="sxs-lookup"><span data-stu-id="c0c99-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="c0c99-104">适配器向客户端提供以下优势：</span><span class="sxs-lookup"><span data-stu-id="c0c99-104">The adapters provide the following advantages to clients:</span></span>  
  
-   <span data-ttu-id="c0c99-105">**一致的设计时体验**。</span><span class="sxs-lookup"><span data-stu-id="c0c99-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="c0c99-106">适配器提供用于浏览、 搜索和检索元数据的 LOB 项目的常见和用户友好的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="c0c99-106">The adapters provide a common and user-friendly design time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
-   <span data-ttu-id="c0c99-107">**各种编程选项**。</span><span class="sxs-lookup"><span data-stu-id="c0c99-107">**Varied programming options**.</span></span> <span data-ttu-id="c0c99-108">适配器均提供一种编程模型包括 Windows Communication Foundation (WCF) 通道模型、 WCF 服务模型、 ADO.NET、 web 服务或支持的 BizTalk 模型。</span><span class="sxs-lookup"><span data-stu-id="c0c99-108">The adapters provide a choice of programming model including Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, web services, or BizTalk supported models.</span></span>  
  
-   <span data-ttu-id="c0c99-109">**跨 Lob 的统一体验**。</span><span class="sxs-lookup"><span data-stu-id="c0c99-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="c0c99-110">适配器上使用的是 WCF 标准化和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并因此提供获得对任何 LOB 系统的访问的统一体验。</span><span class="sxs-lookup"><span data-stu-id="c0c99-110">The adapters standardize on using the WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
 <span data-ttu-id="c0c99-111">如前文所述，适配器均构建在之上[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c0c99-111">As mentioned, the adapters are built on top of the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> <span data-ttu-id="c0c99-112">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]为生成各种如 BizTalk Server 和 Microsoft Office 的客户端应用程序可以使用的集成适配器提供了常见的基础。</span><span class="sxs-lookup"><span data-stu-id="c0c99-112">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="c0c99-113">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道结合适配器策略与 Microsoft 服务策略。</span><span class="sxs-lookup"><span data-stu-id="c0c99-113">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="c0c99-114">有关详细信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，请参阅[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="c0c99-114">For more information about the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], see the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentation.</span></span> <span data-ttu-id="c0c99-115">文档安装连同[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，通常在\<安装驱动器\>: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents。</span><span class="sxs-lookup"><span data-stu-id="c0c99-115">The documentation is installed along with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], typically under \<installation drive\>:\Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents.</span></span>  
  
 <span data-ttu-id="c0c99-116">若要对某个 SAP 系统执行操作，适配器客户端必须有权相关远程函数调用 (文档 Rfc)、 业务应用程序编程接口 (BAPIs) 和 Idoc （或中间的文档）。</span><span class="sxs-lookup"><span data-stu-id="c0c99-116">To perform operations on an SAP system, adapter clients must have access to the relevant Remote Function Calls (RFCs), Business Application Programming Interfaces (BAPIs), and IDOCs (or intermediate documents).</span></span> <span data-ttu-id="c0c99-117">SAP / 3 系统公开的业务集成 Rfc、 BAPIs 和 Idoc。</span><span class="sxs-lookup"><span data-stu-id="c0c99-117">An SAP R/3 system exposes RFCs, BAPIs, and IDOCs for business integration.</span></span> <span data-ttu-id="c0c99-118">Rfc 是实现特定的业务逻辑的远程函数模块。</span><span class="sxs-lookup"><span data-stu-id="c0c99-118">RFCs are remote function modules that implement specific business logic.</span></span> <span data-ttu-id="c0c99-119">从 BizTalk Server 之类的外部应用程序或.NET 应用程序可以调用此逻辑。</span><span class="sxs-lookup"><span data-stu-id="c0c99-119">This logic can be invoked from an external application such as BizTalk Server or a .NET application.</span></span> <span data-ttu-id="c0c99-120">BAPIs 都是与通过标准 RFC 接口反过来公开的 SAP 业务对象的方法接口。</span><span class="sxs-lookup"><span data-stu-id="c0c99-120">BAPIs are method interfaces to SAP business objects, which are in turn exposed through standard RFC interfaces.</span></span> <span data-ttu-id="c0c99-121">Idoc 是一种机制，抽象 SAP 和非 SAP 系统之间的通信的电子数据交换 (EDI) 通信层。</span><span class="sxs-lookup"><span data-stu-id="c0c99-121">IDOCs are a mechanism to abstract the electronic data interchange (EDI) communication layer for communication between SAP and non-SAP systems.</span></span> <span data-ttu-id="c0c99-122">与[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]，你可以访问 Rfc BAPIs，以及 Idoc 公开的 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="c0c99-122">With [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)], you can access the RFCs, BAPIs, and IDOCs exposed by an SAP system.</span></span>  
  
 <span data-ttu-id="c0c99-123">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还包括[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]，它提供到 SAP 系统 ADO 界面。</span><span class="sxs-lookup"><span data-stu-id="c0c99-123">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] also includes [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], which provides an ADO interface to the SAP system.</span></span>  
  
 <span data-ttu-id="c0c99-124">本部分列出的功能[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]和[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c0c99-124">This section lists the features for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0c99-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="c0c99-125">In This Section</span></span>  
  
-   [<span data-ttu-id="c0c99-126">为 mySAP Business Suite 的 BizTalk Adapter 的体系结构概述</span><span class="sxs-lookup"><span data-stu-id="c0c99-126">Architecture overview of BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [<span data-ttu-id="c0c99-127">SAP 适配器中的主要功能</span><span class="sxs-lookup"><span data-stu-id="c0c99-127">Key Features in the SAP Adapter</span></span>](../../adapters-and-accelerators/adapter-sap/key-features-in-the-sap-adapter.md)  
  
-   [<span data-ttu-id="c0c99-128">用于 mySAP Business Suite 的 BizTalk 适配器限制</span><span class="sxs-lookup"><span data-stu-id="c0c99-128">Limitations of BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/limitations-of-biztalk-adapter-for-mysap-business-suite.md)  
  
-   [<span data-ttu-id="c0c99-129">关于 mySAP Business Suite 的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="c0c99-129">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)  
  
## <a name="see-also"></a><span data-ttu-id="c0c99-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0c99-130">See Also</span></span>  
[<span data-ttu-id="c0c99-131">要开始使用用于 mySAP Business Suite 的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="c0c99-131">Get started with the BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/get-started-with-the-biztalk-adapter-for-mysap-business-suite.md)
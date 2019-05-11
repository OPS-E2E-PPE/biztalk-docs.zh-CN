---
title: 了解用于 Oracle 数据库的 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF LOB Adapter SDK
- features of Oracle database adapter
- table
- adapter client
- service model
- WCF
- artifacts
- database tables
- adapters, features
- Windows Communication Foundation
- adapter features
- channel model
ms.assetid: a8691957-0430-4cba-83f8-b60c21a86849
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6233044306df0ae03d3d1dd6b1a65b75129d1c37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375880"
---
# <a name="understand-the-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="1f969-102">了解用于 Oracle 数据库的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="1f969-102">Understand the BizTalk Adapter for Oracle Database</span></span>
<span data-ttu-id="1f969-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统进行交互，以面向服务的编程访问。</span><span class="sxs-lookup"><span data-stu-id="1f969-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="1f969-104">适配器向客户端提供以下优势：</span><span class="sxs-lookup"><span data-stu-id="1f969-104">The adapters provide the following advantages to clients:</span></span>  
  
- <span data-ttu-id="1f969-105">**一致的设计时体验**。</span><span class="sxs-lookup"><span data-stu-id="1f969-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="1f969-106">适配器提供了常见用户友好设计时体验，用于浏览、 搜索和检索 LOB 项目的元数据。</span><span class="sxs-lookup"><span data-stu-id="1f969-106">The adapters provide a common and user-friendly design-time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
- <span data-ttu-id="1f969-107">**不同的编程选项**。</span><span class="sxs-lookup"><span data-stu-id="1f969-107">**Varied programming options**.</span></span> <span data-ttu-id="1f969-108">适配器提供了一种编程模型包括 Windows Communication Foundation (WCF) 通道模型，WCF 服务模型中，ADO.NET 中，Web 服务或 BizTalk 支持的模型。</span><span class="sxs-lookup"><span data-stu-id="1f969-108">The adapters provide a choice of programming model including the Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, Web services, or BizTalk supported models.</span></span>  
  
- <span data-ttu-id="1f969-109">**跨 Lob 的统一体验**。</span><span class="sxs-lookup"><span data-stu-id="1f969-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="1f969-110">使用 WCF 适配器标准化和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并因此提供获取访问权的任何 LOB 系统的统一的体验。</span><span class="sxs-lookup"><span data-stu-id="1f969-110">The adapters standardize on using WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
  <span data-ttu-id="1f969-111">如前文所述，基于 WCF LOB 适配器 SDK 构建适配器。</span><span class="sxs-lookup"><span data-stu-id="1f969-111">As mentioned, the adapters are built on top of the WCF LOB Adapter SDK.</span></span> <span data-ttu-id="1f969-112">WCF LOB 适配器 SDK 提供用于生成各种 BizTalk Server 和 Microsoft Office 等客户端应用程序可以使用的集成适配器公共基础。</span><span class="sxs-lookup"><span data-stu-id="1f969-112">The WCF LOB Adapter SDK provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="1f969-113">WCF LOB 适配器 SDK 通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道对齐适配器策略与 Microsoft 服务策略。</span><span class="sxs-lookup"><span data-stu-id="1f969-113">The WCF LOB Adapter SDK aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="1f969-114">有关 WCF LOB 适配器 SDK 的详细信息，请参阅[WCF LOB 适配器 SDK 文档](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)。</span><span class="sxs-lookup"><span data-stu-id="1f969-114">For more information about the WCF LOB Adapter SDK, see [WCF LOB Adapter SDK documentation](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).</span></span>
  
  <span data-ttu-id="1f969-115">若要对 Oracle 数据库执行操作，适配器客户端必须有权相关表、 函数和过程。</span><span class="sxs-lookup"><span data-stu-id="1f969-115">To perform operations on an Oracle database, adapter clients must have access to relevant tables, functions, and procedures.</span></span> <span data-ttu-id="1f969-116">数据库表是在 Oracle 数据库中存储的基本单位。</span><span class="sxs-lookup"><span data-stu-id="1f969-116">Database tables are the basic unit of storage in the Oracle database.</span></span> <span data-ttu-id="1f969-117">外部应用程序可以添加或通过使用 SQL 语句从表中删除数据。</span><span class="sxs-lookup"><span data-stu-id="1f969-117">External applications can add or remove data from a table by using SQL statements.</span></span> <span data-ttu-id="1f969-118">应用程序还可以通过使用视图、 函数和过程访问表中的数据。</span><span class="sxs-lookup"><span data-stu-id="1f969-118">Applications can also access data in the tables by using views, functions, and procedures.</span></span> <span data-ttu-id="1f969-119">使用[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]，适配器客户端可以浏览的项目，例如表、 过程、 包、 视图和 Oracle 数据库中的其他此类项。</span><span class="sxs-lookup"><span data-stu-id="1f969-119">With [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)], adapter clients can browse the artifacts such as tables, procedures, packages, views, and other such items in an Oracle database.</span></span> <span data-ttu-id="1f969-120">适配器客户端可以选择他们需要为他们的解决方案和检索这些项目的元数据的项目。</span><span class="sxs-lookup"><span data-stu-id="1f969-120">Adapter clients can select the artifacts they require for their solution and retrieve metadata for those artifacts.</span></span> <span data-ttu-id="1f969-121">这使用户可以访问和 Oracle 数据库中执行项目上的操作。</span><span class="sxs-lookup"><span data-stu-id="1f969-121">This enables users to access and execute the operations on the artifacts in the Oracle database.</span></span>  
  
  <span data-ttu-id="1f969-122">本部分中列出的功能[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1f969-122">This section lists the features of the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f969-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="1f969-123">In This Section</span></span>  
  
-   [<span data-ttu-id="1f969-124">用于 Oracle 数据库的 BizTalk 适配器概述</span><span class="sxs-lookup"><span data-stu-id="1f969-124">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)  
  
-   [<span data-ttu-id="1f969-125">用于 Oracle 数据库的 BizTalk 适配器的主要功能</span><span class="sxs-lookup"><span data-stu-id="1f969-125">Key Features in BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)  
  
-   [<span data-ttu-id="1f969-126">用于 Oracle 数据库的 BizTalk 适配器的限制</span><span class="sxs-lookup"><span data-stu-id="1f969-126">Limitations of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/limitations-of-biztalk-adapter-for-oracle-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="1f969-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f969-127">See Also</span></span>  
[<span data-ttu-id="1f969-128">BizTalk Server 入门</span><span class="sxs-lookup"><span data-stu-id="1f969-128">Getting started with BizTalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)
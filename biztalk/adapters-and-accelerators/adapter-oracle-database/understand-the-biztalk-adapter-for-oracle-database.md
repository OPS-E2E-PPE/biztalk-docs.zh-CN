---
title: "了解用于 Oracle 数据库的 BizTalk Adapter |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aee5761ad466f755e2eb944dcfb2526729bea07c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="understand-the-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="2be4b-102">了解 BizTalk 适配器用于 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="2be4b-102">Understand the BizTalk Adapter for Oracle Database</span></span>
<span data-ttu-id="2be4b-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]还支持与外部系统交互，以面向服务的编程访问。</span><span class="sxs-lookup"><span data-stu-id="2be4b-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access in order to interact with an external system.</span></span> <span data-ttu-id="2be4b-104">适配器向客户端提供以下优势：</span><span class="sxs-lookup"><span data-stu-id="2be4b-104">The adapters provide the following advantages to clients:</span></span>  
  
-   <span data-ttu-id="2be4b-105">**一致的设计时体验**。</span><span class="sxs-lookup"><span data-stu-id="2be4b-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="2be4b-106">适配器提供用于浏览、 搜索和检索元数据的 LOB 项目的设计时体验常见和用户友好。</span><span class="sxs-lookup"><span data-stu-id="2be4b-106">The adapters provide a common and user-friendly design-time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
-   <span data-ttu-id="2be4b-107">**各种编程选项**。</span><span class="sxs-lookup"><span data-stu-id="2be4b-107">**Varied programming options**.</span></span> <span data-ttu-id="2be4b-108">适配器均提供一种编程模型，包括 Windows Communication Foundation (WCF) 通道模型，WCF 服务模型中，ADO.NET 中，Web 服务，或 BizTalk 支持模型。</span><span class="sxs-lookup"><span data-stu-id="2be4b-108">The adapters provide a choice of programming model including the Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, Web services, or BizTalk supported models.</span></span>  
  
-   <span data-ttu-id="2be4b-109">**跨 Lob 的统一体验**。</span><span class="sxs-lookup"><span data-stu-id="2be4b-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="2be4b-110">适配器标准化上使用 WCF 和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并因此提供统一的体验的获得对任何 LOB 系统的访问。</span><span class="sxs-lookup"><span data-stu-id="2be4b-110">The adapters standardize on using WCF and [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
 <span data-ttu-id="2be4b-111">如前文所述，适配器均构建在之上[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2be4b-111">As mentioned, the adapters are built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="2be4b-112">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]为生成各种如 BizTalk Server 和 Microsoft Office 的客户端应用程序可以使用的集成适配器提供了常见的基础。</span><span class="sxs-lookup"><span data-stu-id="2be4b-112">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="2be4b-113">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道结合适配器策略与 Microsoft 服务策略。</span><span class="sxs-lookup"><span data-stu-id="2be4b-113">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="2be4b-114">有关详细信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，请参阅[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档。</span><span class="sxs-lookup"><span data-stu-id="2be4b-114">For more information about the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], see the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentation.</span></span> <span data-ttu-id="2be4b-115">[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]文档安装连同[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，通常在\<安装驱动器 >: \Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents。</span><span class="sxs-lookup"><span data-stu-id="2be4b-115">The [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentation is installed along with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], typically under \<installation drive>:\Program Files\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents.</span></span>  
  
 <span data-ttu-id="2be4b-116">要对 Oracle 数据库执行操作，适配器客户端必须具有对相关表、 函数和过程的访问。</span><span class="sxs-lookup"><span data-stu-id="2be4b-116">To perform operations on an Oracle database, adapter clients must have access to relevant tables, functions, and procedures.</span></span> <span data-ttu-id="2be4b-117">数据库表是 Oracle 数据库中存储的基本单元。</span><span class="sxs-lookup"><span data-stu-id="2be4b-117">Database tables are the basic unit of storage in the Oracle database.</span></span> <span data-ttu-id="2be4b-118">外部应用程序可以添加或从表中删除数据，通过使用 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="2be4b-118">External applications can add or remove data from a table by using SQL statements.</span></span> <span data-ttu-id="2be4b-119">应用程序还可以通过使用视图、 函数和过程访问表中的数据。</span><span class="sxs-lookup"><span data-stu-id="2be4b-119">Applications can also access data in the tables by using views, functions, and procedures.</span></span> <span data-ttu-id="2be4b-120">与[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]，适配器客户端可以浏览如表、 过程、 包、 视图和其他此类项 Oracle 数据库中的项目。</span><span class="sxs-lookup"><span data-stu-id="2be4b-120">With [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)], adapter clients can browse the artifacts such as tables, procedures, packages, views, and other such items in an Oracle database.</span></span> <span data-ttu-id="2be4b-121">适配器客户端可以选择他们需要用其解决方案和检索元数据的这些项目的项目。</span><span class="sxs-lookup"><span data-stu-id="2be4b-121">Adapter clients can select the artifacts they require for their solution and retrieve metadata for those artifacts.</span></span> <span data-ttu-id="2be4b-122">这使用户可以访问和 Oracle 数据库中执行的操作的项目。</span><span class="sxs-lookup"><span data-stu-id="2be4b-122">This enables users to access and execute the operations on the artifacts in the Oracle database.</span></span>  
  
 <span data-ttu-id="2be4b-123">本部分列出的功能[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2be4b-123">This section lists the features of the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2be4b-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="2be4b-124">In This Section</span></span>  
  
-   [<span data-ttu-id="2be4b-125">用于 Oracle 数据库的 BizTalk Adapter 的概述</span><span class="sxs-lookup"><span data-stu-id="2be4b-125">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)  
  
-   [<span data-ttu-id="2be4b-126">用于 Oracle 数据库的 BizTalk Adapter 中的主要功能</span><span class="sxs-lookup"><span data-stu-id="2be4b-126">Key Features in BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/key-features-in-biztalk-adapter-for-oracle-database.md)  
  
-   [<span data-ttu-id="2be4b-127">用于 Oracle 数据库的 BizTalk Adapter 限制</span><span class="sxs-lookup"><span data-stu-id="2be4b-127">Limitations of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/limitations-of-biztalk-adapter-for-oracle-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="2be4b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2be4b-128">See Also</span></span>  
[<span data-ttu-id="2be4b-129">BizTalk Server 入门</span><span class="sxs-lookup"><span data-stu-id="2be4b-129">Getting started with BizTalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)
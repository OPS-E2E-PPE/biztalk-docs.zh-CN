---
title: 了解适用于 SQL Server 的 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 302a7f20-ffa2-49f1-a4c4-dd713adc23e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9db0cc843d67a032113e159dd5301c54e92e1be0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367445"
---
# <a name="understand-biztalk-adapter-for-sql-server"></a><span data-ttu-id="8c492-102">了解适用于 SQL Server 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="8c492-102">Understand BizTalk Adapter for SQL Server</span></span>
<span data-ttu-id="8c492-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]实现面向服务的编程访问从而可以与外部系统进行交互。</span><span class="sxs-lookup"><span data-stu-id="8c492-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] enables service-oriented programmatic access making it possible to interact with an external system.</span></span> <span data-ttu-id="8c492-104">适配器向客户端提供以下优势：</span><span class="sxs-lookup"><span data-stu-id="8c492-104">The adapters provide the following advantages to clients:</span></span>  
  
- <span data-ttu-id="8c492-105">**一致的设计时体验**。</span><span class="sxs-lookup"><span data-stu-id="8c492-105">**Consistent design-time experience**.</span></span> <span data-ttu-id="8c492-106">适配器提供了常见用户友好设计时体验，用于浏览、 搜索和检索 LOB 项目的元数据。</span><span class="sxs-lookup"><span data-stu-id="8c492-106">The adapters provide a common and user-friendly design-time experience for browsing, searching, and retrieving metadata of LOB artifacts.</span></span>  
  
- <span data-ttu-id="8c492-107">**不同的编程选项**。</span><span class="sxs-lookup"><span data-stu-id="8c492-107">**Varied programming options**.</span></span> <span data-ttu-id="8c492-108">适配器提供了一种编程模型包括 Windows Communication Foundation (WCF) 通道模型，WCF 服务模型中，ADO.NET 中，Web 服务或 BizTalk 支持的模型。</span><span class="sxs-lookup"><span data-stu-id="8c492-108">The adapters provide a choice of programming model including the Windows Communication Foundation (WCF) channel model, WCF service model, ADO.NET, Web services, or BizTalk supported models.</span></span>  
  
- <span data-ttu-id="8c492-109">**跨 Lob 的统一体验**。</span><span class="sxs-lookup"><span data-stu-id="8c492-109">**Uniform experience across LOBs**.</span></span> <span data-ttu-id="8c492-110">使用 WCF 适配器标准化和[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，并因此提供获取访问权的任何 LOB 系统的统一的体验。</span><span class="sxs-lookup"><span data-stu-id="8c492-110">The adapters standardize on using WCF and the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], and hence provide a uniform experience of gaining access to any LOB system.</span></span>  
  
  <span data-ttu-id="8c492-111">如前文所述，基于 WCF LOB 适配器 SDK 构建适配器。</span><span class="sxs-lookup"><span data-stu-id="8c492-111">As mentioned, the adapters are built on top of the WCF LOB Adapter SDK.</span></span> <span data-ttu-id="8c492-112">WCF LOB 适配器 SDK 提供用于生成各种 BizTalk Server 和 Microsoft Office 等客户端应用程序可以使用的集成适配器公共基础。</span><span class="sxs-lookup"><span data-stu-id="8c492-112">The WCF LOB Adapter SDK provides a common basis for building integration adapters that a variety of client applications such as BizTalk Server and Microsoft Office can consume.</span></span> <span data-ttu-id="8c492-113">WCF LOB 适配器 SDK 通过公开集成适配器作为 Windows Communication Foundation (WCF) 通道对齐适配器策略与 Microsoft 服务策略。</span><span class="sxs-lookup"><span data-stu-id="8c492-113">The WCF LOB Adapter SDK aligns the adapter strategy with the Microsoft Services strategy by exposing integration adapters as Windows Communication Foundation (WCF) channels.</span></span> <span data-ttu-id="8c492-114">有关 WCF LOB 适配器 SDK 的详细信息，请参阅[WCF LOB 适配器 SDK 文档](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md)。</span><span class="sxs-lookup"><span data-stu-id="8c492-114">For more information about the WCF LOB Adapter SDK, see [WCF LOB Adapter SDK documentation](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).</span></span>
  
  <span data-ttu-id="8c492-115">若要执行的 SQL Server 数据库上的操作，适配器客户端必须有权访问相关的表、 过程、 视图、 标量函数和表值的函数。</span><span class="sxs-lookup"><span data-stu-id="8c492-115">To perform operations on a SQL Server database, adapter clients must have access to relevant tables, procedures, views, scalar functions, and table valued functions.</span></span> <span data-ttu-id="8c492-116">数据库表是 SQL Server 数据库中存储的基本单位。</span><span class="sxs-lookup"><span data-stu-id="8c492-116">Database tables are the basic unit of storage in the SQL Server database.</span></span> <span data-ttu-id="8c492-117">外部应用程序可以选择、 插入、 删除和使用 SQL 语句更新表中的数据。</span><span class="sxs-lookup"><span data-stu-id="8c492-117">External applications can select, insert, delete, and update data from a table by using SQL statements.</span></span> <span data-ttu-id="8c492-118">应用程序还可以通过使用过程、 视图、 标量函数和表值函数访问表中的数据。</span><span class="sxs-lookup"><span data-stu-id="8c492-118">Applications can also access data in the tables by using procedures, views, scalar functions, and table valued functions.</span></span> <span data-ttu-id="8c492-119">使用[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]，适配器客户端可以浏览项目，例如表、 过程、 视图和 SQL Server 数据库中的其他此类项。</span><span class="sxs-lookup"><span data-stu-id="8c492-119">With [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)], adapter clients can browse artifacts such as tables, procedures, views, and other such items in a SQL Server database.</span></span> <span data-ttu-id="8c492-120">适配器客户端可以选择为他们的解决方案，它们需要的项目并检索这些项目的元数据。</span><span class="sxs-lookup"><span data-stu-id="8c492-120">Adapter clients can select the artifacts they require for their solution, and retrieve metadata for those artifacts.</span></span> <span data-ttu-id="8c492-121">这使用户可以访问和执行 SQL Server 数据库中的项目上的操作。</span><span class="sxs-lookup"><span data-stu-id="8c492-121">This enables users to access and execute the operations on the artifacts in the SQL Server database.</span></span>  
  
  <span data-ttu-id="8c492-122">本部分中列出的功能[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8c492-122">This section lists the features of the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c492-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="8c492-123">In This Section</span></span>  
  
-   [<span data-ttu-id="8c492-124">用于 SQL Server 的 BizTalk 适配器概述</span><span class="sxs-lookup"><span data-stu-id="8c492-124">Overview of BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)  
  
-   [<span data-ttu-id="8c492-125">用于 SQL Server 的 BizTalk 适配器的主要功能</span><span class="sxs-lookup"><span data-stu-id="8c492-125">Key features in BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/key-features-in-biztalk-adapter-for-sql-server.md) 
  
-   [<span data-ttu-id="8c492-126">适用于 SQL Server 的 BizTalk 适配器的限制</span><span class="sxs-lookup"><span data-stu-id="8c492-126">Limitations of BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/limitations-of-biztalk-adapter-for-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="8c492-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c492-127">See Also</span></span>  
[<span data-ttu-id="8c492-128">开始使用的 BizTalk 适配器进行 SQL</span><span class="sxs-lookup"><span data-stu-id="8c492-128">Get started with the BizTalk adapter for SQL</span></span>](../../adapters-and-accelerators/adapter-sql/get-started-with-the-biztalk-adapter-for-sql.md)
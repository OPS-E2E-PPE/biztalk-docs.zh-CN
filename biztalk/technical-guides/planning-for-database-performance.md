---
title: 规划数据库性能 |Microsoft Docs
ms.custom: ''
ms.date: 11/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7212fa37-88e0-4b5f-af97-c72063357645
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbbf9c072289b177779ed8ae3a991f58b9f26efe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394611"
---
# <a name="planning-for-database-performance"></a><span data-ttu-id="6d207-102">规划数据库性能</span><span class="sxs-lookup"><span data-stu-id="6d207-102">Planning for Database Performance</span></span>

## <a name="overview"></a><span data-ttu-id="6d207-103">概述</span><span class="sxs-lookup"><span data-stu-id="6d207-103">Overview</span></span>
<span data-ttu-id="6d207-104">Microsoft BizTalk Server 是极其数据库密集型应用程序可能要求的 Microsoft SQL Server 中最多 13 个单独的数据库创建的。</span><span class="sxs-lookup"><span data-stu-id="6d207-104">Microsoft BizTalk Server is an extremely database intensive application that may require the creation of up to 13 separate databases in Microsoft SQL Server.</span></span> <span data-ttu-id="6d207-105">由于 BizTalk Server 的数据库密集型性质，它是至关重要的任务选择适当的版本和版本的 SQL Server 来存放 BizTalk Server 数据库问题。</span><span class="sxs-lookup"><span data-stu-id="6d207-105">Because of the database intensive nature of BizTalk Server, it is of critical importance that you choose the appropriate version and edition of SQL Server that will house the BizTalk Server databases.</span></span> <span data-ttu-id="6d207-106">若要优化运行 SQL Server 的计算机承载 BizTalk Server 数据库的性能，请按照建议在本主题并在[BizTalk Server 数据库优化](optimizing-database-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="6d207-106">To optimize the performance of the computers running SQL Server that house the BizTalk Server databases, follow the recommendations in this topic and in the [BizTalk Server Database Optimization](optimizing-database-performance.md).</span></span>
  

> [!NOTE]  
>  <span data-ttu-id="6d207-107">虽然本指南针对其他版本的 BizTalk Server 和 SQL Server 编写的您可能可以较新版本使用相同的建议。</span><span class="sxs-lookup"><span data-stu-id="6d207-107">While this guide is written for other versions of BizTalk Server and SQL Server, you can probably use the same recommendations for newer versions.</span></span>
  
## <a name="considerations-for-sql-server-editions"></a><span data-ttu-id="6d207-108">SQL Server 版本的注意事项</span><span class="sxs-lookup"><span data-stu-id="6d207-108">Considerations for SQL Server Editions</span></span>  
 <span data-ttu-id="6d207-109">应将 BizTalk Server 数据库配置为只要有可能的专用 SQL Server 实例上运行。</span><span class="sxs-lookup"><span data-stu-id="6d207-109">BizTalk Server databases should be configured to run on a dedicated SQL Server instance whenever possible.</span></span> <span data-ttu-id="6d207-110">BizTalk Server 是数据库密集型应用程序，因此，分离的 BizTalk Server 计算机和承载 BizTalk Server 数据库的 SQL Server 计算机将提高性能，应考虑生产 BizTalk Server 中的最佳做法环境。</span><span class="sxs-lookup"><span data-stu-id="6d207-110">BizTalk Server is a database intensive application, so separation of the BizTalk Server computers and the SQL Server computers that house the BizTalk Server databases will improve performance and should be considered a best practice in a production BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="6d207-111">各种版本的 SQL Server 提供不同的功能，这可能会影响 BizTalk Server 环境的性能。</span><span class="sxs-lookup"><span data-stu-id="6d207-111">Various editions of SQL Server provide different features which can affect the performance of your BizTalk Server environment.</span></span> <span data-ttu-id="6d207-112">例如，在高负载情况下是可用于 32 位版本的 SQL Server 的可用的数据库锁的数目可能会被超出，这是对 BizTalk 解决方案的性能造成不利影响。</span><span class="sxs-lookup"><span data-stu-id="6d207-112">For example, under high-load conditions, the number of available database locks that are available for the 32-bit version of SQL Server may be exceeded, which is detrimental to the performance of the BizTalk solution.</span></span> <span data-ttu-id="6d207-113">请考虑保存 MessageBox 数据库上的 SQL Server 的 64 位版本，如果您在测试环境中遇到"内存不足"错误。</span><span class="sxs-lookup"><span data-stu-id="6d207-113">Consider housing your MessageBox database on a 64-bit version of SQL Server if you are experiencing "out of lock" errors in your test environment.</span></span> <span data-ttu-id="6d207-114">可用锁的数目是 64 位版本的 SQL Server 上高得多。</span><span class="sxs-lookup"><span data-stu-id="6d207-114">The number of available locks is significantly higher on the 64-bit version of SQL Server.</span></span>  
  
 <span data-ttu-id="6d207-115">请考虑下时确定数据库引擎功能的表将需要为您的 BizTalk 环境。</span><span class="sxs-lookup"><span data-stu-id="6d207-115">Consider the table below when deciding on the database engine features that you will need for your BizTalk environment.</span></span> <span data-ttu-id="6d207-116">对于小规模的解决方案，例如当运行 BizTalk Server 分支版，SQL Server Workgroup Edition 可以满足用于容纳 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="6d207-116">For small-scale solutions, for example when running BizTalk Server Branch Edition, SQL Server Workgroup Edition may be adequate for housing the BizTalk Server databases.</span></span> <span data-ttu-id="6d207-117">较大的比例，需要群集的支持，企业级解决方案的 BizTalk 日志传送支持或 Analysis Services 支持，则需要 SQL Server Enterprise Edition 来承载数据库。</span><span class="sxs-lookup"><span data-stu-id="6d207-117">For large scale, enterprise-level solutions that require clustering support, BizTalk log shipping support, or Analysis Services support, then you need SQL Server Enterprise Edition to host the databases.</span></span>  
  
|<span data-ttu-id="6d207-118">版本的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="6d207-118">Edition of SQL Server</span></span>|<span data-ttu-id="6d207-119">64 位支持</span><span class="sxs-lookup"><span data-stu-id="6d207-119">64-bit support</span></span>|<span data-ttu-id="6d207-120">多实例支持</span><span class="sxs-lookup"><span data-stu-id="6d207-120">Multi-Instance Support</span></span>|<span data-ttu-id="6d207-121">群集的支持</span><span class="sxs-lookup"><span data-stu-id="6d207-121">Clustering support</span></span>|<span data-ttu-id="6d207-122">Analysis Services</span><span class="sxs-lookup"><span data-stu-id="6d207-122">Analysis Services</span></span>|  
|---|---|---|---|---|  
|<span data-ttu-id="6d207-123">SQL Server 企业版</span><span class="sxs-lookup"><span data-stu-id="6d207-123">SQL Server Enterprise Edition</span></span>|<span data-ttu-id="6d207-124">是</span><span class="sxs-lookup"><span data-stu-id="6d207-124">Yes</span></span>|<span data-ttu-id="6d207-125">是</span><span class="sxs-lookup"><span data-stu-id="6d207-125">Yes</span></span>|<span data-ttu-id="6d207-126">是</span><span class="sxs-lookup"><span data-stu-id="6d207-126">Yes</span></span>|<span data-ttu-id="6d207-127">是</span><span class="sxs-lookup"><span data-stu-id="6d207-127">Yes</span></span>|  
|<span data-ttu-id="6d207-128">SQL Server 标准版</span><span class="sxs-lookup"><span data-stu-id="6d207-128">SQL Server Standard Edition</span></span>|<span data-ttu-id="6d207-129">是</span><span class="sxs-lookup"><span data-stu-id="6d207-129">Yes</span></span>|<span data-ttu-id="6d207-130">是</span><span class="sxs-lookup"><span data-stu-id="6d207-130">Yes</span></span>|<span data-ttu-id="6d207-131">是 （2 个节点）</span><span class="sxs-lookup"><span data-stu-id="6d207-131">Yes (2 node)</span></span>|<span data-ttu-id="6d207-132">是</span><span class="sxs-lookup"><span data-stu-id="6d207-132">Yes</span></span>|  
|<span data-ttu-id="6d207-133">SQL Server Workgroup Edition</span><span class="sxs-lookup"><span data-stu-id="6d207-133">SQL Server Workgroup Edition</span></span>|<span data-ttu-id="6d207-134">是</span><span class="sxs-lookup"><span data-stu-id="6d207-134">Yes</span></span>|<span data-ttu-id="6d207-135">是</span><span class="sxs-lookup"><span data-stu-id="6d207-135">Yes</span></span>|<span data-ttu-id="6d207-136">否</span><span class="sxs-lookup"><span data-stu-id="6d207-136">No</span></span>|<span data-ttu-id="6d207-137">否</span><span class="sxs-lookup"><span data-stu-id="6d207-137">No</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="6d207-138">BAM RTA 需要 SQL Server Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="6d207-138">BAM RTA requires SQL Server Enterprise Edition.</span></span>  
  
 <span data-ttu-id="6d207-139">有关各个版本支持的功能的完整列表，请参阅[SQL server 各个版本支持的功能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="6d207-139">For a complete list of the features supported by the editions, see [Features Supported by the Editions of SQL Server](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016).</span></span>
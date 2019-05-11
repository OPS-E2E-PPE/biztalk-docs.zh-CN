---
title: Oracle 数据库中的 LOB 数据类型的流式处理支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- streaming, node-value
- streaming
- LOB data
- streaming, node
ms.assetid: a4943cdf-8336-48ac-b592-52ec514e7300
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a6e5f842efd8c5d4778d5920c82f99302c82ec7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375964"
---
# <a name="streaming-support-for-lob-data-types-in-oracle-database"></a><span data-ttu-id="62754-102">Oracle 数据库中的 LOB 数据类型的流支持</span><span class="sxs-lookup"><span data-stu-id="62754-102">Streaming Support for LOB Data Types in Oracle Database</span></span>
<span data-ttu-id="62754-103">Oracle database 支持流式处理大型对象 (LOB) 数据类型。</span><span class="sxs-lookup"><span data-stu-id="62754-103">The Oracle database supports streaming on large object (LOB) data types.</span></span> <span data-ttu-id="62754-104">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持消息流式处理，这样就可以进行流式处理 LOB 数据端到端 Oracle 数据库和适配器客户端之间。</span><span class="sxs-lookup"><span data-stu-id="62754-104">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]supports message streaming, which makes it possible to stream LOB data end-to-end between the Oracle database and an adapter client.</span></span> <span data-ttu-id="62754-105">但是，流式处理不支持相同的方式跨所有编程模型时使用的适配器。</span><span class="sxs-lookup"><span data-stu-id="62754-105">However, streaming is not supported in the same manner across all programming models when you use the adapter.</span></span>  
  
 <span data-ttu-id="62754-106">跨不同的编程模型，适配器支持以下显示了如何端到端 LOB 数据类型的流式处理。</span><span class="sxs-lookup"><span data-stu-id="62754-106">The following shows how end-to-end streaming of LOB data types is supported by the adapter across different programming models.</span></span>  
  
|<span data-ttu-id="62754-107">操作</span><span class="sxs-lookup"><span data-stu-id="62754-107">Operation</span></span>|<span data-ttu-id="62754-108">WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="62754-108">WCF Channel Model</span></span>|<span data-ttu-id="62754-109">WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="62754-109">WCF Service Model</span></span>|<span data-ttu-id="62754-110">BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="62754-110">BizTalk Server</span></span>|  
|---------------|-----------------------|-----------------------|--------------------|  
|<span data-ttu-id="62754-111">表/视图插入操作</span><span class="sxs-lookup"><span data-stu-id="62754-111">Table/View Insert operation</span></span>|<span data-ttu-id="62754-112">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-112">Not supported</span></span>|<span data-ttu-id="62754-113">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-113">Not supported</span></span>|<span data-ttu-id="62754-114">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-114">Not supported</span></span>|  
|<span data-ttu-id="62754-115">表/视图中，选择操作</span><span class="sxs-lookup"><span data-stu-id="62754-115">Table/View Select operation</span></span>|<span data-ttu-id="62754-116">支持</span><span class="sxs-lookup"><span data-stu-id="62754-116">Supported</span></span>|<span data-ttu-id="62754-117">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-117">Not supported</span></span>|<span data-ttu-id="62754-118">支持</span><span class="sxs-lookup"><span data-stu-id="62754-118">Supported</span></span>|  
|<span data-ttu-id="62754-119">表/视图更新操作</span><span class="sxs-lookup"><span data-stu-id="62754-119">Table/View Update operation</span></span>|<span data-ttu-id="62754-120">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-120">Not supported</span></span>|<span data-ttu-id="62754-121">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-121">Not supported</span></span>|<span data-ttu-id="62754-122">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-122">Not supported</span></span>|  
|<span data-ttu-id="62754-123">表/视图删除操作</span><span class="sxs-lookup"><span data-stu-id="62754-123">Table/View Delete operation</span></span>|<span data-ttu-id="62754-124">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-124">Not supported</span></span>|<span data-ttu-id="62754-125">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-125">Not supported</span></span>|<span data-ttu-id="62754-126">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-126">Not supported</span></span>|  
|<span data-ttu-id="62754-127">表/视图 ReadLOB 操作</span><span class="sxs-lookup"><span data-stu-id="62754-127">Table/View ReadLOB operation</span></span>|<span data-ttu-id="62754-128">受支持;但是，主要用于支持 WCF 服务模型中的流式处理可以找出 ReadLOB 操作，建议不要在 WCF 通道模型中使用。</span><span class="sxs-lookup"><span data-stu-id="62754-128">Supported; however, the ReadLOB operations is surfaced primarily to support streaming in the WCF service model, it is not recommended for use in the WCF channel model.</span></span> <span data-ttu-id="62754-129">改为使用选择操作或 SQLEXECUTE 操作。</span><span class="sxs-lookup"><span data-stu-id="62754-129">Use a Select operation or the SQLEXECUTE operation instead.</span></span>|<span data-ttu-id="62754-130">支持</span><span class="sxs-lookup"><span data-stu-id="62754-130">Supported</span></span>|<span data-ttu-id="62754-131">为 BizTalk Server 不支持 ReadLOB 操作。</span><span class="sxs-lookup"><span data-stu-id="62754-131">The ReadLOB operation is not supported for BizTalk Server.</span></span> <span data-ttu-id="62754-132">改为使用选择操作。</span><span class="sxs-lookup"><span data-stu-id="62754-132">Use a Select operation instead.</span></span>|  
|<span data-ttu-id="62754-133">表/视图 UpdateLOB 操作</span><span class="sxs-lookup"><span data-stu-id="62754-133">Table/View UpdateLOB operation</span></span>|<span data-ttu-id="62754-134">支持</span><span class="sxs-lookup"><span data-stu-id="62754-134">Supported</span></span>|<span data-ttu-id="62754-135">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-135">Not Supported</span></span>|<span data-ttu-id="62754-136">支持</span><span class="sxs-lookup"><span data-stu-id="62754-136">Supported</span></span>|  
|<span data-ttu-id="62754-137">SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="62754-137">SQLEXECUTE operation</span></span>|<span data-ttu-id="62754-138">在响应中受支持</span><span class="sxs-lookup"><span data-stu-id="62754-138">Supported in the response</span></span>|<span data-ttu-id="62754-139">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-139">Not Supported</span></span>|<span data-ttu-id="62754-140">在响应中受支持</span><span class="sxs-lookup"><span data-stu-id="62754-140">Supported in the response</span></span>|  
|<span data-ttu-id="62754-141">存储的过程和函数操作</span><span class="sxs-lookup"><span data-stu-id="62754-141">Stored procedure and function operation</span></span>|<span data-ttu-id="62754-142">在响应中受支持</span><span class="sxs-lookup"><span data-stu-id="62754-142">Supported in the response</span></span>|<span data-ttu-id="62754-143">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-143">Not Supported</span></span>|<span data-ttu-id="62754-144">在响应中受支持</span><span class="sxs-lookup"><span data-stu-id="62754-144">Supported in the response</span></span>|  
|<span data-ttu-id="62754-145">POLLINGSTMT 操作</span><span class="sxs-lookup"><span data-stu-id="62754-145">POLLINGSTMT operation</span></span>|<span data-ttu-id="62754-146">支持</span><span class="sxs-lookup"><span data-stu-id="62754-146">Supported</span></span>|<span data-ttu-id="62754-147">不支持</span><span class="sxs-lookup"><span data-stu-id="62754-147">Not Supported</span></span>|<span data-ttu-id="62754-148">支持</span><span class="sxs-lookup"><span data-stu-id="62754-148">Supported</span></span>|  
  
 <span data-ttu-id="62754-149">有关如何流式处理 LOB 数据类型的适配器是否支持和您的适配器使用各种编程模型时的支持方式的更全面信息，请参阅[流式处理大型对象数据类型](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="62754-149">For more comprehensive information about how streaming of LOB data types is supported by the adapter and how it is supported when you use various programming models with the adapter, see [Streaming large object data types](../../adapters-and-accelerators/adapter-oracle-database/streaming-large-object-data-types-in-oracle-database-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62754-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="62754-150">See Also</span></span>  
 [<span data-ttu-id="62754-151">用于 Oracle 数据库的 BizTalk 适配器概述</span><span class="sxs-lookup"><span data-stu-id="62754-151">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)
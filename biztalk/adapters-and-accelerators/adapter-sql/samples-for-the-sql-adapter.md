---
title: "SQL 适配器示例 |Microsoft 文档"
description: "可以用于 BizTalk Server、 WCF 服务模型和 WCF 通道模型的 SQL WCF 适配器示例"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2438696-bc51-46df-81ca-00c17a52736e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0729b18dc900800ed39ccae31acfdd37b38b4573
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="samples-for-the-sql-adapter"></a><span data-ttu-id="dc286-103">有关 SQL 适配器的示例</span><span class="sxs-lookup"><span data-stu-id="dc286-103">Samples for the SQL adapter</span></span>

<span data-ttu-id="dc286-104">示例[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]分为：</span><span class="sxs-lookup"><span data-stu-id="dc286-104">Samples for [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] are categorized into:</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="dc286-105"> 示例</span><span class="sxs-lookup"><span data-stu-id="dc286-105"> samples</span></span>  
  
-   <span data-ttu-id="dc286-106">WCF 服务模型示例</span><span class="sxs-lookup"><span data-stu-id="dc286-106">WCF service model samples</span></span>  
  
-   <span data-ttu-id="dc286-107">WCF 通道模型示例</span><span class="sxs-lookup"><span data-stu-id="dc286-107">WCF channel model samples</span></span>  
  
<span data-ttu-id="dc286-108">这些示例位于[BizTalk 适配器包 2010年: SQL 适配器示例](https://www.microsoft.com/download/details.aspx?id=22455)。</span><span class="sxs-lookup"><span data-stu-id="dc286-108">The samples are available at [BizTalk Adapter Pack 2010: SQL adapter samples](https://www.microsoft.com/download/details.aspx?id=22455).</span></span> <span data-ttu-id="dc286-109">包含表，在示例中，例如，数据库，使用用于创建对象的 SQL 脚本和过程。</span><span class="sxs-lookup"><span data-stu-id="dc286-109">The SQL scripts for creating the objects used in the samples, such as database, tables, and procedures are included.</span></span> 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
<span data-ttu-id="dc286-110">以下列表介绍这些示例。</span><span class="sxs-lookup"><span data-stu-id="dc286-110">The following list describes the samples.</span></span>
  
## <a name="biztalk-server-samples"></a><span data-ttu-id="dc286-111">BizTalk Server 示例</span><span class="sxs-lookup"><span data-stu-id="dc286-111">BizTalk Server samples</span></span>  
  
|<span data-ttu-id="dc286-112">示例目录名称</span><span class="sxs-lookup"><span data-stu-id="dc286-112">Sample Directory Name</span></span>|<span data-ttu-id="dc286-113">Description</span><span class="sxs-lookup"><span data-stu-id="dc286-113">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="dc286-114">ExecuteStoredProcedure</span><span class="sxs-lookup"><span data-stu-id="dc286-114">ExecuteStoredProcedure</span></span>|<span data-ttu-id="dc286-115">演示如何调用存储的过程在 SQL Server 数据库中使用的适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dc286-115">Demonstrates how to invoke a stored procedure in SQL Server database using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] .</span></span>|  
|<span data-ttu-id="dc286-116">SelectTable</span><span class="sxs-lookup"><span data-stu-id="dc286-116">SelectTable</span></span>|<span data-ttu-id="dc286-117">演示如何执行上使用的适配器的 SQL Server 数据库表选择操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dc286-117">Demonstrates how to perform a Select operation on a SQL Server database table using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>|  
|<span data-ttu-id="dc286-118">CompositeOperations</span><span class="sxs-lookup"><span data-stu-id="dc286-118">CompositeOperations</span></span>|<span data-ttu-id="dc286-119">演示如何执行 SQL Server 数据库使用的适配器上的复合操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dc286-119">Demonstrates how to perform composite operations on a SQL Server database using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>|  
|<span data-ttu-id="dc286-120">TypedPolling</span><span class="sxs-lookup"><span data-stu-id="dc286-120">TypedPolling</span></span>|<span data-ttu-id="dc286-121">演示如何在 SQL Server 数据库使用的适配器上执行强类型轮询[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dc286-121">Demonstrates how to perform strongly-typed polling on a SQL Server database using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>|  
|<span data-ttu-id="dc286-122">FILESTREAMOperation</span><span class="sxs-lookup"><span data-stu-id="dc286-122">FILESTREAMOperation</span></span>|<span data-ttu-id="dc286-123">演示如何执行上使用的适配器的 SQL Server 2008 数据库的 FILESTREAM 操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dc286-123">Demonstrates how to perform FILESTREAM operations on a SQL Server 2008 database using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>|  
|<span data-ttu-id="dc286-124">IncrementalNotification</span><span class="sxs-lookup"><span data-stu-id="dc286-124">IncrementalNotification</span></span>|<span data-ttu-id="dc286-125">演示如何从 SQL Server 数据库使用的适配器接收增量通知[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dc286-125">Demonstrates how to receive incremental notification from a SQL Server database using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>|  
|<span data-ttu-id="dc286-126">Employee_PurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="dc286-126">Employee_PurchaseOrder</span></span>|<span data-ttu-id="dc286-127">示例基于[教程 2： 员工-采购订单过程使用 SQL 适配器](tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="dc286-127">Sample based on [Tutorial 2: Employee - Purchase Order Process using the SQL adapter](tutorial-2-employee-purchase-order-process-using-the-sql-adapter.md).</span></span>|  
  
## <a name="wcf-service-model-samples"></a><span data-ttu-id="dc286-128">WCF 服务模型示例</span><span class="sxs-lookup"><span data-stu-id="dc286-128">WCF service model samples</span></span>   
  
|<span data-ttu-id="dc286-129">示例目录名称</span><span class="sxs-lookup"><span data-stu-id="dc286-129">Sample Directory Name</span></span>|<span data-ttu-id="dc286-130">Description</span><span class="sxs-lookup"><span data-stu-id="dc286-130">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="dc286-131">EmployeeBasicOps</span><span class="sxs-lookup"><span data-stu-id="dc286-131">EmployeeBasicOps</span></span>|<span data-ttu-id="dc286-132">演示如何执行插入、 选择、 更新和删除使用该适配器的 SQL Server 数据库上的操作。</span><span class="sxs-lookup"><span data-stu-id="dc286-132">Demonstrates how to perform Insert, Select, Update, and Delete operation on a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="dc286-133">ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="dc286-133">ExecuteReader</span></span>|<span data-ttu-id="dc286-134">演示如何调用 ExecuteReader 操作使用该适配器的 SQL Server 数据库上。</span><span class="sxs-lookup"><span data-stu-id="dc286-134">Demonstrates how to invoke an ExecuteReader operation on a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="dc286-135">Execute_StoredProc</span><span class="sxs-lookup"><span data-stu-id="dc286-135">Execute_StoredProc</span></span>|<span data-ttu-id="dc286-136">演示如何调用使用适配器的 SQL Server 数据库中的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="dc286-136">Demonstrates how to invoke a stored procedure in SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="dc286-137">Execute_TypedStoredProcedure</span><span class="sxs-lookup"><span data-stu-id="dc286-137">Execute_TypedStoredProcedure</span></span>|<span data-ttu-id="dc286-138">演示如何调用中使用该适配器的 SQL Server 数据库的强类型的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="dc286-138">Demonstrates how to invoke a strongly-typed stored procedure in SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="dc286-139">Records_FILESTREAM_Op</span><span class="sxs-lookup"><span data-stu-id="dc286-139">Records_FILESTREAM_Op</span></span>|<span data-ttu-id="dc286-140">演示如何更新使用适配器的 SQL Server 数据库表中的 FILESTREAM 数据。</span><span class="sxs-lookup"><span data-stu-id="dc286-140">Demonstrates how to update FILESTREAM data in a SQL Server database table using the adapter.</span></span>|  
|<span data-ttu-id="dc286-141">ScalarFunction_ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dc286-141">ScalarFunction_ServiceModel</span></span>|<span data-ttu-id="dc286-142">演示如何调用中使用该适配器的 SQL Server 数据库的标量函数。</span><span class="sxs-lookup"><span data-stu-id="dc286-142">Demonstrates how to invoke scalar functions in a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="dc286-143">TableFunction_ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dc286-143">TableFunction_ServiceModel</span></span>|<span data-ttu-id="dc286-144">演示如何调用中使用该适配器的 SQL Server 数据库表值函数。</span><span class="sxs-lookup"><span data-stu-id="dc286-144">Demonstrates how to invoke table-valued functions in a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="dc286-145">Polling_ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dc286-145">Polling_ServiceModel</span></span>|<span data-ttu-id="dc286-146">演示如何从 SQL Server 数据库使用适配器接收基于轮询的数据更改消息。</span><span class="sxs-lookup"><span data-stu-id="dc286-146">Demonstrates how to receive polling-based data-changed messages from a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="dc286-147">TypedPolling_ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dc286-147">TypedPolling_ServiceModel</span></span>|<span data-ttu-id="dc286-148">演示如何从 SQL Server 数据库使用适配器接收强类型基于轮询的数据更改消息。</span><span class="sxs-lookup"><span data-stu-id="dc286-148">Demonstrates how to receive strongly-typed polling-based data-changed messages from a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="dc286-149">Notification_ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dc286-149">Notification_ServiceModel</span></span>|<span data-ttu-id="dc286-150">演示如何从 SQL Server 数据库使用适配器接收查询通知。</span><span class="sxs-lookup"><span data-stu-id="dc286-150">Demonstrates how to receive query notifications from a SQL Server database using the adapter.</span></span>|  
  
## <a name="wcf-channel-model-samples"></a><span data-ttu-id="dc286-151">WCF 通道模型示例</span><span class="sxs-lookup"><span data-stu-id="dc286-151">WCF channel model samples</span></span> 
  
|<span data-ttu-id="dc286-152">示例目录名称</span><span class="sxs-lookup"><span data-stu-id="dc286-152">Sample Directory Name</span></span>|<span data-ttu-id="dc286-153">Description</span><span class="sxs-lookup"><span data-stu-id="dc286-153">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="dc286-154">EmployeeInsertOp</span><span class="sxs-lookup"><span data-stu-id="dc286-154">EmployeeInsertOp</span></span>|<span data-ttu-id="dc286-155">演示如何执行插入操作使用该适配器的 SQL Server 数据库上。</span><span class="sxs-lookup"><span data-stu-id="dc286-155">Demonstrates how to perform an Insert operation on a SQL Server database using the adapter.</span></span>|  
|<span data-ttu-id="dc286-156">Polling_ChannelModel</span><span class="sxs-lookup"><span data-stu-id="dc286-156">Polling_ChannelModel</span></span>|<span data-ttu-id="dc286-157">演示如何从 SQL Server 数据库使用适配器接收基于轮询的数据更改消息。</span><span class="sxs-lookup"><span data-stu-id="dc286-157">Demonstrates how to receive polling-based data-changed messages from a SQL Server database using the adapter.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc286-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc286-158">See Also</span></span>  
[<span data-ttu-id="dc286-159">开发 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="dc286-159">Develop your SQL applications</span></span>](develop-your-sql-applications.md)
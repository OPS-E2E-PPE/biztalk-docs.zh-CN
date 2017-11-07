---
title: "Oracle 数据库适配器示例 |Microsoft 文档"
description: "可以用于 BizTalk Server、 WCF 服务模型和 WCF 通道模型的 oracle DB WCF 适配器示例"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 744f19ce-3126-4745-92dd-4f68443180fc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5bfef9fcfce65d8aede1cd905a53469c565977f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="samples-for-the-oracle-database-adapter"></a><span data-ttu-id="be689-103">Oracle 数据库适配器的的示例</span><span class="sxs-lookup"><span data-stu-id="be689-103">Samples for the Oracle Database adapter</span></span>
<span data-ttu-id="be689-104">示例[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]分为：</span><span class="sxs-lookup"><span data-stu-id="be689-104">Samples for [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] are categorized into:</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="be689-105"> 示例</span><span class="sxs-lookup"><span data-stu-id="be689-105"> samples</span></span>  
  
-   <span data-ttu-id="be689-106">WCF 服务模型示例</span><span class="sxs-lookup"><span data-stu-id="be689-106">WCF service model samples</span></span>  
  
-   <span data-ttu-id="be689-107">WCF 通道模型示例</span><span class="sxs-lookup"><span data-stu-id="be689-107">WCF channel model samples</span></span>  

  
<span data-ttu-id="be689-108">这些示例位于[BizTalk 适配器包 2010年: Oracle 数据库适配器示例](https://www.microsoft.com/download/details.aspx?id=4675)。</span><span class="sxs-lookup"><span data-stu-id="be689-108">The samples are available at [BizTalk Adapter Pack 2010: Oracle Database adapter samples](https://www.microsoft.com/download/details.aspx?id=4675).</span></span> <span data-ttu-id="be689-109">用于创建表和在这些示例中使用的包的 SQL 脚本是包含。</span><span class="sxs-lookup"><span data-stu-id="be689-109">The SQL scripts for creating the tables and packages used in the samples are included.</span></span> 

> [!NOTE]
> [!INCLUDE[files-need-updated](../../includes/files-need-updated.md)]
  
<span data-ttu-id="be689-110">以下列表介绍这些示例。</span><span class="sxs-lookup"><span data-stu-id="be689-110">The following list describes the samples.</span></span>
  
## <a name="biztalk-server-samples"></a><span data-ttu-id="be689-111">BizTalk Server 示例</span><span class="sxs-lookup"><span data-stu-id="be689-111">BizTalk Server samples</span></span>
  
|<span data-ttu-id="be689-112">示例目录名称</span><span class="sxs-lookup"><span data-stu-id="be689-112">Sample Directory Name</span></span>|<span data-ttu-id="be689-113">Description</span><span class="sxs-lookup"><span data-stu-id="be689-113">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="be689-114">Func_RecordTypes</span><span class="sxs-lookup"><span data-stu-id="be689-114">Func_RecordTypes</span></span>|<span data-ttu-id="be689-115">演示如何使用记录类型参数和返回值函数和过程使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="be689-115">Demonstrates how to use RECORD type parameters and return values in functions and procedures using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="be689-116">Func_RefCursor</span><span class="sxs-lookup"><span data-stu-id="be689-116">Func_RefCursor</span></span>|<span data-ttu-id="be689-117">演示如何使用函数和使用的过程中的 REF CURSOR 参数[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="be689-117">Demonstrates how to use REF CURSOR parameters in functions and procedures using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="be689-118">InvokeFunction</span><span class="sxs-lookup"><span data-stu-id="be689-118">InvokeFunction</span></span>|<span data-ttu-id="be689-119">演示如何调用在 Oracle 数据库中使用函数[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="be689-119">Demonstrates how to invoke a function in Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="be689-120">InvokeOverloadedProc</span><span class="sxs-lookup"><span data-stu-id="be689-120">InvokeOverloadedProc</span></span>|<span data-ttu-id="be689-121">演示如何使用重载的函数和在 Oracle 数据库中使用的过程调用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="be689-121">Demonstrates how to invoke with overloaded functions and procedures in Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="be689-122">Operate_BFILE</span><span class="sxs-lookup"><span data-stu-id="be689-122">Operate_BFILE</span></span>|<span data-ttu-id="be689-123">演示如何使用 Oracle 过程中使用 Oracle BFILE 类型[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="be689-123">Demonstrates how to use Oracle BFILE types in Oracle procedures using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="be689-124">Operate_LOB</span><span class="sxs-lookup"><span data-stu-id="be689-124">Operate_LOB</span></span>|<span data-ttu-id="be689-125">演示如何 ReadLOB 和 UpdateLOB 对表执行操作的 LOB 数据类型使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="be689-125">Demonstrates how to perform ReadLOB and UpdateLOB operations on tables with LOB data types using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="be689-126">PollingQuery</span><span class="sxs-lookup"><span data-stu-id="be689-126">PollingQuery</span></span>|<span data-ttu-id="be689-127">演示如何配置轮询查询和接收使用对结果[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="be689-127">Demonstrates how to configure a polling query and receive the results using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="be689-128">SelectAccTable</span><span class="sxs-lookup"><span data-stu-id="be689-128">SelectAccTable</span></span>|<span data-ttu-id="be689-129">演示如何在使用 Oracle 数据库表上执行 select 查询[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="be689-129">Demonstrates how to perform a select query on an Oracle database table using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
|<span data-ttu-id="be689-130">SqlExec</span><span class="sxs-lookup"><span data-stu-id="be689-130">SqlExec</span></span>|<span data-ttu-id="be689-131">演示如何执行参数化的查询使用在上 Oracle 数据库通过 SQLEXECUTE 操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="be689-131">Demonstrates how to perform parameterized queries using the SQLEXECUTE operation on an Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>|  
  
## <a name="wcf-service-model-samples"></a><span data-ttu-id="be689-132">WCF 服务模型示例</span><span class="sxs-lookup"><span data-stu-id="be689-132">WCF service model samples</span></span>  
  
|<span data-ttu-id="be689-133">示例目录名称</span><span class="sxs-lookup"><span data-stu-id="be689-133">Sample Directory Name</span></span>|<span data-ttu-id="be689-134">Description</span><span class="sxs-lookup"><span data-stu-id="be689-134">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="be689-135">OracleBfileTypeSM</span><span class="sxs-lookup"><span data-stu-id="be689-135">OracleBfileTypeSM</span></span>|<span data-ttu-id="be689-136">演示如何提供给 Oracle 过程的 Oracle 表和作为参数的基本 SQL 操作中使用 Oracle BFILE 类型。</span><span class="sxs-lookup"><span data-stu-id="be689-136">Demonstrates how to use Oracle BFILE types in basic SQL operations surfaced for Oracle tables and as parameters to Oracle procedures.</span></span>|  
|<span data-ttu-id="be689-137">OracleOverloadsSM</span><span class="sxs-lookup"><span data-stu-id="be689-137">OracleOverloadsSM</span></span>|<span data-ttu-id="be689-138">演示如何调用重载的函数和包中的过程。</span><span class="sxs-lookup"><span data-stu-id="be689-138">Demonstrates how to invoke overloaded functions and procedures in a package.</span></span>|  
|<span data-ttu-id="be689-139">OraclePollingSM</span><span class="sxs-lookup"><span data-stu-id="be689-139">OraclePollingSM</span></span>|<span data-ttu-id="be689-140">演示如何配置轮询查询和接收的结果。</span><span class="sxs-lookup"><span data-stu-id="be689-140">Demonstrates how to configure a polling query and receive the results.</span></span>|  
|<span data-ttu-id="be689-141">OracleRecordTypesSM</span><span class="sxs-lookup"><span data-stu-id="be689-141">OracleRecordTypesSM</span></span>|<span data-ttu-id="be689-142">演示如何使用记录类型参数和函数和过程中返回值。</span><span class="sxs-lookup"><span data-stu-id="be689-142">Demonstrates how to use RECORD type parameters and return values in functions and procedures.</span></span>|  
|<span data-ttu-id="be689-143">OracleRefCursorsSM</span><span class="sxs-lookup"><span data-stu-id="be689-143">OracleRefCursorsSM</span></span>|<span data-ttu-id="be689-144">演示如何使用 REF CURSOR 参数在函数和过程</span><span class="sxs-lookup"><span data-stu-id="be689-144">Demonstrates how to use REF CURSOR parameters in functions and procedures</span></span>|  
|<span data-ttu-id="be689-145">OracleTransactedDmlSM</span><span class="sxs-lookup"><span data-stu-id="be689-145">OracleTransactedDmlSM</span></span>|<span data-ttu-id="be689-146">演示如何在使用 WCF 服务模型在某个事务中执行对 Oracle 数据库的操作。</span><span class="sxs-lookup"><span data-stu-id="be689-146">Demonstrates how to perform operations on the Oracle database in a transaction using the WCF service model.</span></span>|  
  
## <a name="wcf-channel-model-samples"></a><span data-ttu-id="be689-147">WCF 通道模型示例</span><span class="sxs-lookup"><span data-stu-id="be689-147">WCF channel model samples</span></span>  
  
|<span data-ttu-id="be689-148">示例目录名称</span><span class="sxs-lookup"><span data-stu-id="be689-148">Sample Directory Name</span></span>|<span data-ttu-id="be689-149">Description</span><span class="sxs-lookup"><span data-stu-id="be689-149">Description</span></span>|  
|---------------------------|-----------------|  
|<span data-ttu-id="be689-150">OraclePollingCM</span><span class="sxs-lookup"><span data-stu-id="be689-150">OraclePollingCM</span></span>|<span data-ttu-id="be689-151">演示如何配置轮询查询和接收的结果。</span><span class="sxs-lookup"><span data-stu-id="be689-151">Demonstrates how to configure a polling query and receive the results.</span></span>|  
|<span data-ttu-id="be689-152">OracleStreamingDemo</span><span class="sxs-lookup"><span data-stu-id="be689-152">OracleStreamingDemo</span></span>|<span data-ttu-id="be689-153">演示如何执行端到端对使用 UpdateLOB 和表选择操作的 LOB 数据进行流式处理</span><span class="sxs-lookup"><span data-stu-id="be689-153">Demonstrates how to perform end-to-end streaming of LOB data using the UpdateLOB and table Select operations</span></span>|  
|<span data-ttu-id="be689-154">OracleTransactedDmlCM</span><span class="sxs-lookup"><span data-stu-id="be689-154">OracleTransactedDmlCM</span></span>|<span data-ttu-id="be689-155">演示如何在使用 WCF 通道模型在某个事务中执行对 Oracle 数据库的操作。</span><span class="sxs-lookup"><span data-stu-id="be689-155">Demonstrates how to perform operations on the Oracle database in a transaction using the WCF channel model.</span></span>|  
  

## <a name="see-also"></a><span data-ttu-id="be689-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be689-156">See Also</span></span>  
[<span data-ttu-id="be689-157">开发 Oracle 数据库应用程序</span><span class="sxs-lookup"><span data-stu-id="be689-157">Develop your Oracle Database applications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)
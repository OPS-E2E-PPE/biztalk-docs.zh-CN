---
title: 消息架构的 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar Operations1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aa5fdb2-1e7f-4a34-a1e5-c16d8fb477d5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7078fed7a007eca4dfb3eb5608eb6e688bb74a45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011966"
---
# <a name="message-schemas-for-the-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="9ad88-102">ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="9ad88-102">Message Schemas for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>
<span data-ttu-id="9ad88-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开在根级别，以在 Oracle E-business Suite 中执行任何任意 SQL 语句或 PL/SQL 块的 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 出站操作。</span><span class="sxs-lookup"><span data-stu-id="9ad88-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes the ExecuteNonQuery, ExecuteReader, and ExecuteScalar outbound operations at the root level to execute any arbitrary SQL statements or PL/SQL blocks in Oracle E-Business Suite.</span></span>  
  
 <span data-ttu-id="9ad88-104">有关详细信息：</span><span class="sxs-lookup"><span data-stu-id="9ad88-104">For more information about:</span></span>  
  
- <span data-ttu-id="9ad88-105">这些操作，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="9ad88-105">These operations, see [Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md).</span></span>  
  
- <span data-ttu-id="9ad88-106">执行这些操作使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作中使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="9ad88-106">Performing these operations using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [ExecuteReader, ExecuteScalar, or ExecuteNonQuery Operations in SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).</span></span>  
  
## <a name="message-structure-for-the-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="9ad88-107">ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="9ad88-107">Message Structure for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>  
 <span data-ttu-id="9ad88-108">这些操作中的消息遵循请求-响应消息交换模式，并下表显示了这些请求和响应消息的结构。</span><span class="sxs-lookup"><span data-stu-id="9ad88-108">The messages in these operations follow a request-response message exchange pattern, and the following table shows the structure of these request and response messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ad88-109">实体说明表后进行查看。</span><span class="sxs-lookup"><span data-stu-id="9ad88-109">See entity descriptions after the table.</span></span>  
  
|<span data-ttu-id="9ad88-110">运算</span><span class="sxs-lookup"><span data-stu-id="9ad88-110">Operation</span></span>|<span data-ttu-id="9ad88-111">XML 消息</span><span class="sxs-lookup"><span data-stu-id="9ad88-111">XML Message</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ad88-112">ExecuteNonQuery 请求</span><span class="sxs-lookup"><span data-stu-id="9ad88-112">ExecuteNonQuery Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQuery xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query>   <OutputRefCursorNames>     <string>[stringvalue1]</string>     <string>[stringvalue2]</string>     …   </OutputRefCursorNames> </ExecuteNonQuery>`|  
|<span data-ttu-id="9ad88-113">ExecuteNonQuery 响应</span><span class="sxs-lookup"><span data-stu-id="9ad88-113">ExecuteNonQuery Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteNonQueryResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteNonQueryResult>[value]</ExecuteNonQueryResult>   <OutputRefCursors>     <DataSet>       <Any>[value]</Any>       <Any>[value]</Any>       …     </DataSet>   </OutputRefCursors> </ExecuteNonQueryResponse>`|  
|<span data-ttu-id="9ad88-114">ExecuteReader 请求</span><span class="sxs-lookup"><span data-stu-id="9ad88-114">ExecuteReader Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReader xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteReader>`|  
|<span data-ttu-id="9ad88-115">ExecuteReader 响应</span><span class="sxs-lookup"><span data-stu-id="9ad88-115">ExecuteReader Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteReaderResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteReaderResult>     <Any>[value]</Any>     <Any>[value]</Any>       …   </ExecuteReaderResult> </ExecuteReaderResponse>`|  
|<span data-ttu-id="9ad88-116">ExecuteScalar 请求</span><span class="sxs-lookup"><span data-stu-id="9ad88-116">ExecuteScalar Request</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalar xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <Query>[PL/SQL block]</Query> </ExecuteScalar>`|  
|<span data-ttu-id="9ad88-117">ExecuteScalar 响应</span><span class="sxs-lookup"><span data-stu-id="9ad88-117">ExecuteScalar Response</span></span>|`<?xml version="1.0" encoding="utf-8" ?> <ExecuteScalarResponse xmlns="http://schemas.microsoft.com/OracleEBS/2008/05/GenericOperation/ ">   <ExecuteScalarResult>[value]</ExecuteScalarResult> </ExecuteScalarResponse>`|  
  
 <span data-ttu-id="9ad88-118">实体说明：</span><span class="sxs-lookup"><span data-stu-id="9ad88-118">Entity descriptions:</span></span>  
  
 <span data-ttu-id="9ad88-119">[PL/SQL 块] = 整个 PL/SQL 块执行。</span><span class="sxs-lookup"><span data-stu-id="9ad88-119">[PL/SQL block] = The entire PL/SQL block to be executed.</span></span>  
  
 <span data-ttu-id="9ad88-120">[stringvalue1] = 字符串数组中的值。</span><span class="sxs-lookup"><span data-stu-id="9ad88-120">[stringvalue1] = A value in the array of strings.</span></span>  
  
## <a name="message-action-for-the-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="9ad88-121">ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="9ad88-121">Message Action for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>  
 <span data-ttu-id="9ad88-122">下表显示了使用的 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的消息操作。</span><span class="sxs-lookup"><span data-stu-id="9ad88-122">The following table shows the message actions that are used by the ExecuteNonQuery, ExecuteReader, and ExecuteScalar operations.</span></span>  
  
|<span data-ttu-id="9ad88-123">运算</span><span class="sxs-lookup"><span data-stu-id="9ad88-123">Operation</span></span>|<span data-ttu-id="9ad88-124">操作</span><span class="sxs-lookup"><span data-stu-id="9ad88-124">Action</span></span>|  
|---------------|------------|  
|<span data-ttu-id="9ad88-125">ExecuteNonQuery 请求</span><span class="sxs-lookup"><span data-stu-id="9ad88-125">ExecuteNonQuery Request</span></span>|<span data-ttu-id="9ad88-126">GenericOp/ExecuteNonQuery</span><span class="sxs-lookup"><span data-stu-id="9ad88-126">GenericOp/ExecuteNonQuery</span></span>|  
|<span data-ttu-id="9ad88-127">ExecuteNonQuery 响应</span><span class="sxs-lookup"><span data-stu-id="9ad88-127">ExecuteNonQuery Response</span></span>|<span data-ttu-id="9ad88-128">GenericOp/ExecuteNonQuery/响应</span><span class="sxs-lookup"><span data-stu-id="9ad88-128">GenericOp/ExecuteNonQuery/response</span></span>|  
|<span data-ttu-id="9ad88-129">ExecuteReader 请求</span><span class="sxs-lookup"><span data-stu-id="9ad88-129">ExecuteReader Request</span></span>|<span data-ttu-id="9ad88-130">GenericOp/ExecuteReader</span><span class="sxs-lookup"><span data-stu-id="9ad88-130">GenericOp/ExecuteReader</span></span>|  
|<span data-ttu-id="9ad88-131">ExecuteReader 响应</span><span class="sxs-lookup"><span data-stu-id="9ad88-131">ExecuteReader Response</span></span>|<span data-ttu-id="9ad88-132">GenericOp/ExecuteReader/响应</span><span class="sxs-lookup"><span data-stu-id="9ad88-132">GenericOp/ExecuteReader/response</span></span>|  
|<span data-ttu-id="9ad88-133">ExecuteScalar 请求</span><span class="sxs-lookup"><span data-stu-id="9ad88-133">ExecuteScalar Request</span></span>|<span data-ttu-id="9ad88-134">GenericOp/ExecuteScalar</span><span class="sxs-lookup"><span data-stu-id="9ad88-134">GenericOp/ExecuteScalar</span></span>|  
|<span data-ttu-id="9ad88-135">ExecuteScalar 响应</span><span class="sxs-lookup"><span data-stu-id="9ad88-135">ExecuteScalar Response</span></span>|<span data-ttu-id="9ad88-136">GenericOp/ExecuteScalar/响应</span><span class="sxs-lookup"><span data-stu-id="9ad88-136">GenericOp/ExecuteScalar/response</span></span>|
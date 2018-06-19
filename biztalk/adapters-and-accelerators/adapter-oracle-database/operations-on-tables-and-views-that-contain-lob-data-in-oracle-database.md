---
title: 对表和视图包含 Oracle 数据库中的 LOB 数据的操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data type
- binary file
- UpdateLOB
- ReadLOB
- LOB data types
- NCLOB
- large object
- binary large object
- CLOB
- national character large object
- BFILE
- BLOB
- character large object
ms.assetid: 25afd8c7-8ca3-4855-a231-2bec28c9a5cb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba5e110af598ac75ca9a8b6e7ebf2e5e8acc7aee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214389"
---
# <a name="operations-on-tables-and-views-that-contain-lob-data-in-oracle-database"></a><span data-ttu-id="677f8-102">对表和视图包含 Oracle 数据库中的 LOB 数据的操作</span><span class="sxs-lookup"><span data-stu-id="677f8-102">Operations on tables and views that contain LOB data in Oracle Database</span></span>
<span data-ttu-id="677f8-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]提供对 Oracle 大型对象 (LOB) 数据类型的支持：</span><span class="sxs-lookup"><span data-stu-id="677f8-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] provides support for the Oracle large object (LOB) data types:</span></span>  
  
-   <span data-ttu-id="677f8-104">二进制大型对象 (BLOB)</span><span class="sxs-lookup"><span data-stu-id="677f8-104">Binary large object (BLOB)</span></span>  
  
-   <span data-ttu-id="677f8-105">字符大型对象 (CLOB)</span><span class="sxs-lookup"><span data-stu-id="677f8-105">Character large object (CLOB)</span></span>  
  
-   <span data-ttu-id="677f8-106">国家/地区字符大型对象 (NCLOB)</span><span class="sxs-lookup"><span data-stu-id="677f8-106">National character large object (NCLOB)</span></span>  
  
-   <span data-ttu-id="677f8-107">二进制文件 (BFILE)。</span><span class="sxs-lookup"><span data-stu-id="677f8-107">Binary file (BFILE).</span></span> <span data-ttu-id="677f8-108">有关详细信息，请参阅[对包含 BFILE 数据类型的表的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="677f8-108">For more information, see [Operations on Tables that contains BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
  
 <span data-ttu-id="677f8-109">在 Oracle 数据库上 LOB 数据类型用于存储大量数据 (最多 4 GB)。</span><span class="sxs-lookup"><span data-stu-id="677f8-109">On the Oracle database, LOB data types are used to store large amounts of data (up to 4 GB).</span></span> <span data-ttu-id="677f8-110">LOB 类型支持输入和输出流。</span><span class="sxs-lookup"><span data-stu-id="677f8-110">LOB types support both input and output streaming.</span></span>  
  
 <span data-ttu-id="677f8-111">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现对表和视图包含 LOB 列执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="677f8-111">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces the following operations for tables and views that contain LOB columns:</span></span>  
  
-   <span data-ttu-id="677f8-112">**ReadLOB**。</span><span class="sxs-lookup"><span data-stu-id="677f8-112">**ReadLOB**.</span></span> <span data-ttu-id="677f8-113">ReadLOB 操作显示的表和视图包含 BLOB、 CLOB、 NCLOB、 和 BFILE 列中。</span><span class="sxs-lookup"><span data-stu-id="677f8-113">The ReadLOB operation is surfaced for tables and views that contain BLOB, CLOB, NCLOB, and BFILE columns.</span></span> <span data-ttu-id="677f8-114">通过使用 ReadLOB 操作，适配器客户端可以读取数据流形式的 LOB 列中的值。</span><span class="sxs-lookup"><span data-stu-id="677f8-114">By using the ReadLOB operation, adapter clients can read values in a LOB column as a data stream.</span></span> <span data-ttu-id="677f8-115">此操作将 LOB 数据类型列的名称和一个筛选器字符串作为参数。</span><span class="sxs-lookup"><span data-stu-id="677f8-115">This operation takes the LOB data type column name and a filter string as parameters.</span></span> <span data-ttu-id="677f8-116">适配器客户端必须确保筛选器字符串提取恰好一个匹配行。</span><span class="sxs-lookup"><span data-stu-id="677f8-116">Adapter clients must ensure that the filter string fetches exactly one matching row.</span></span> <span data-ttu-id="677f8-117">如果存在多个匹配的行，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]只返回第一个 （匹配） 行的 LOB 列。</span><span class="sxs-lookup"><span data-stu-id="677f8-117">If there is more than one matching row, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] only returns the LOB column for the first (matching) row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="677f8-118">ReadLOB 操作设计为支持的 WCF 服务模型中的 LOB 数据的输入流。</span><span class="sxs-lookup"><span data-stu-id="677f8-118">The ReadLOB operation is designed to support input streaming of LOB data in the WCF service model.</span></span> <span data-ttu-id="677f8-119">应使用表选择操作从 WCF 通道模型读取 LOB 数据或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="677f8-119">You should use a table Select operation to read LOB data from a WCF Channel Model or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span> <span data-ttu-id="677f8-120">有关流式处理的详细信息，请参阅[流式处理 Oracle 数据库中的 LOB 数据类型的支持](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="677f8-120">For more information about streaming, see [Streaming Support for LOB Data Types in Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/streaming-support-for-lob-data-types-in-oracle-database.md).</span></span>  
  
-   <span data-ttu-id="677f8-121">**UpdateLOB**。</span><span class="sxs-lookup"><span data-stu-id="677f8-121">**UpdateLOB**.</span></span> <span data-ttu-id="677f8-122">UpdateLOB 操作显示的表和视图包含 BLOB、 CLOB、 和 NCLOB 列中。</span><span class="sxs-lookup"><span data-stu-id="677f8-122">The UpdateLOB operation is surfaced for tables and views that contain BLOB, CLOB, and NCLOB columns.</span></span> <span data-ttu-id="677f8-123">通过使用 UpdateLOB 操作，适配器客户端可以更新 LOB 列中的值。</span><span class="sxs-lookup"><span data-stu-id="677f8-123">By using the UpdateLOB operation, adapter clients can update values in a LOB column.</span></span> <span data-ttu-id="677f8-124">此操作采用 LOB 数据类型列名称，筛选器字符串，并 base64binary 编码数据作为参数。</span><span class="sxs-lookup"><span data-stu-id="677f8-124">This operation takes the LOB data type column name, a filter string, and base64binary encoded data as parameters.</span></span> <span data-ttu-id="677f8-125">适配器的客户端必须确保筛选器字符串提取恰好一个匹配行;否则为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]引发 XmlReaderParsingException。</span><span class="sxs-lookup"><span data-stu-id="677f8-125">Adapter clients must ensure that the filter string fetches exactly one matching row; otherwise the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] throws an XmlReaderParsingException.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="677f8-126">UpdateLOB 操作中：</span><span class="sxs-lookup"><span data-stu-id="677f8-126">The UpdateLOB operation:</span></span>  
    >   
    >  -   <span data-ttu-id="677f8-127">不支持 BFILE 数据类型。</span><span class="sxs-lookup"><span data-stu-id="677f8-127">Is not supported for the BFILE data type.</span></span> <span data-ttu-id="677f8-128">适配器客户端或者可以使用更新操作。</span><span class="sxs-lookup"><span data-stu-id="677f8-128">Adapter clients can alternatively use the Update operation.</span></span> <span data-ttu-id="677f8-129">有关详细信息，请参阅[对包含 BFILE 数据类型的表的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)。</span><span class="sxs-lookup"><span data-stu-id="677f8-129">For more information, see [Operations on Tables that contains BFILE Data Types](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md).</span></span>  
    > -   <span data-ttu-id="677f8-130">必须作为事务的一部分执行。</span><span class="sxs-lookup"><span data-stu-id="677f8-130">Must be performed as part of a transaction.</span></span> <span data-ttu-id="677f8-131">若要确保此操作，请**UseAmbientTransaction**绑定属性必须设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="677f8-131">To ensure this, the **UseAmbientTransaction** binding property must be set to **True**.</span></span> <span data-ttu-id="677f8-132">璝惠**UseAmbientTransaction**绑定属性，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="677f8-132">For information about the **UseAmbientTransaction** binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="677f8-133">ReadLOB 和 UpdateLOB 操作中的单个表行的单个 LOB 列。</span><span class="sxs-lookup"><span data-stu-id="677f8-133">ReadLOB and UpdateLOB operate on a single LOB column in a single table row.</span></span> <span data-ttu-id="677f8-134">若要运行多个行中的 LOB 列或单个行中的多个 LOB 列上，必须为每个目标行中每个目标列调用 ReadLOB 或 UpdateLOB。</span><span class="sxs-lookup"><span data-stu-id="677f8-134">To operate on LOB columns in multiple rows or on multiple LOB columns within a single row, you must invoke ReadLOB or UpdateLOB for each target column within each target row.</span></span>  
  
 <span data-ttu-id="677f8-135">有关详细信息：</span><span class="sxs-lookup"><span data-stu-id="677f8-135">For more information about:</span></span>  
  
-   <span data-ttu-id="677f8-136">调用在上 Oracle 数据库表通过 UpdateLOB 操作[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[上具有通过使用 BizTalk Server 的大型对象类型数据的表执行操作](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx)。</span><span class="sxs-lookup"><span data-stu-id="677f8-136">Invoking the UpdateLOB operation on an Oracle database table using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Performing Operations on Tables with Large Object Types Data by Using BizTalk Server](https://msdn.microsoft.com/library/cc185405(v=bts.10).aspx).</span></span> <span data-ttu-id="677f8-137">(你应使用表选择操作读取中的 LOB 数据类型[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。)</span><span class="sxs-lookup"><span data-stu-id="677f8-137">(You should use a table Select operation to read LOB data types in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
-   <span data-ttu-id="677f8-138">调用 ReadLOB 和 UpdateLOB 操作对 Oracle 数据库表使用 WCF 服务模型，请参阅[对具有使用 WCF 服务模型的大型对象类型的表运行操作](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)。</span><span class="sxs-lookup"><span data-stu-id="677f8-138">Invoking ReadLOB and UpdateLOB operations on an Oracle database table using WCF service model, see [Run Operations on Tables with Large Object Types by Using the WCF Service Model](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md).</span></span>  
  
-   <span data-ttu-id="677f8-139">消息结构和用于执行 ReadLOB 和 UpdateLOB 操作的 SOAP 操作，请参阅[特殊 LOB 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)。</span><span class="sxs-lookup"><span data-stu-id="677f8-139">Message structure and SOAP actions for performing ReadLOB and UpdateLOB operations, see [Message Schemas for Special LOB Operations](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="677f8-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="677f8-140">See Also</span></span>  
 <span data-ttu-id="677f8-141">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="677f8-141">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185259(v=bts.10).aspx)</span></span>
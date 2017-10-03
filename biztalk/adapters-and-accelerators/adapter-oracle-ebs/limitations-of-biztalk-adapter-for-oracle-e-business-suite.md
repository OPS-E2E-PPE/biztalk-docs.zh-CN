---
title: "Oracle E-business Suite 的 BizTalk Adapter 限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 149cee03-43cd-4cb3-a937-6565f5e96ce5
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7611c56fbd24c7c7cf09d38d376df585b72b284
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-biztalk-adapter-for-oracle-e-business-suite"></a><span data-ttu-id="29c4c-102">Oracle E-business Suite 的 BizTalk 适配器的限制</span><span class="sxs-lookup"><span data-stu-id="29c4c-102">Limitations of BizTalk Adapter for Oracle E-Business Suite</span></span>
## <a name="general-limitations"></a><span data-ttu-id="29c4c-103">常规限制</span><span class="sxs-lookup"><span data-stu-id="29c4c-103">General Limitations</span></span>  
 <span data-ttu-id="29c4c-104">以下已知的限制[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="29c4c-104">The following are known limitations for [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span></span>  
  
-   <span data-ttu-id="29c4c-105">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 XML 网关、 高级队列和业务事件。</span><span class="sxs-lookup"><span data-stu-id="29c4c-105">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support XML Gateway, Advanced Queuing, and Business Events.</span></span>  
  
     <span data-ttu-id="29c4c-106">但是，你可以将业务事件限制避开方式如下：</span><span class="sxs-lookup"><span data-stu-id="29c4c-106">However, you can get around the Business Events limitation in the following way:</span></span>  
  
    1.  <span data-ttu-id="29c4c-107">在 Oracle 业务事件系统中，创建订阅以业务事件发生时调用自定义的 PL/SQL 过程。</span><span class="sxs-lookup"><span data-stu-id="29c4c-107">In Oracle Business Events System, create a subscription to invoke a custom PL/SQL procedure when a business event occurs.</span></span>  
  
    2.  <span data-ttu-id="29c4c-108">编写一个自定义的 PL/SQL 过程接收业务事件。</span><span class="sxs-lookup"><span data-stu-id="29c4c-108">Write a custom PL/SQL procedure that receives the business event.</span></span>  
  
    3.  <span data-ttu-id="29c4c-109">使用自定义的 PL/SQL 过程来在表中存储 （事件和事件负载），最后生成的数据。</span><span class="sxs-lookup"><span data-stu-id="29c4c-109">Use the custom PL/SQL procedure to store the resultant data (event and event payload) in a table.</span></span>  
  
    4.  <span data-ttu-id="29c4c-110">使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]以轮询和/或从表中接收通知。</span><span class="sxs-lookup"><span data-stu-id="29c4c-110">Use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll or receive notifications from the table.</span></span>  
  
-   <span data-ttu-id="29c4c-111">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 XML 类型。</span><span class="sxs-lookup"><span data-stu-id="29c4c-111">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support XML Types.</span></span>  
  
-   <span data-ttu-id="29c4c-112">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会启用客户端设置中为 NULL VARRAY 的第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="29c4c-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not enable clients to set the value of the first element in a VARRAY to NULL.</span></span>  
  
-   <span data-ttu-id="29c4c-113">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持包含的字段的记录类型的记录类型的 PL/SQL 表。</span><span class="sxs-lookup"><span data-stu-id="29c4c-113">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support records that contain fields of type PL/SQL tables of RECORD type.</span></span>  
  
-   <span data-ttu-id="29c4c-114">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持具有循环引用的用户定义类型 (Udt)。</span><span class="sxs-lookup"><span data-stu-id="29c4c-114">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support User-Defined Types (UDTs) that have circular references.</span></span>  
  
-   <span data-ttu-id="29c4c-115">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持复杂类型 （如记录类型，表类型、 UDT 和 VARRAY） 中的 BFILE 数据类型。</span><span class="sxs-lookup"><span data-stu-id="29c4c-115">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support the BFILE data type inside complex types (such as RECORD type, TABLE type, UDT, and VARRAY).</span></span>  
  
-   <span data-ttu-id="29c4c-116">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持嵌套仅达两个级别的 UDT。</span><span class="sxs-lookup"><span data-stu-id="29c4c-116">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports UDT nesting only up to two levels.</span></span>  
  
-   <span data-ttu-id="29c4c-117">除 PL/SQL 表[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持某个包内定义的 Udt。</span><span class="sxs-lookup"><span data-stu-id="29c4c-117">Except for PL/SQL tables, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that are defined inside a package.</span></span>  
  
-   <span data-ttu-id="29c4c-118">当适配器使用 BizTalk Server 中，如果在 WCF 自定义的凭据发送端口不正确时，不会处理请求消息。</span><span class="sxs-lookup"><span data-stu-id="29c4c-118">When using the adapters with BizTalk Server, if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="29c4c-119">指定正确的凭据后，将消息发送到 Oracle E-business Suite 和收到的响应。</span><span class="sxs-lookup"><span data-stu-id="29c4c-119">After you specify the correct credentials, the message is sent to Oracle E-Business Suite and a response is received.</span></span> <span data-ttu-id="29c4c-120">但是，响应消息不可用到的输出端口。</span><span class="sxs-lookup"><span data-stu-id="29c4c-120">However, the response message is not available to the out port.</span></span> <span data-ttu-id="29c4c-121">在这种情况下，你可能需要重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="29c4c-121">In such scenarios, you may need to restart the host instance.</span></span>  
  
## <a name="limitations-due-to-odpnet"></a><span data-ttu-id="29c4c-122">由于 ODP.NET 的限制</span><span class="sxs-lookup"><span data-stu-id="29c4c-122">Limitations Due to ODP.NET</span></span>  
 <span data-ttu-id="29c4c-123">以下已知的限制[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]由于 ODP.NET 的限制：</span><span class="sxs-lookup"><span data-stu-id="29c4c-123">The following are known limitations for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] due to the limitation of ODP.NET:</span></span>  
  
-   <span data-ttu-id="29c4c-124">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 PL/SQL 表按数值字段不编制索引。</span><span class="sxs-lookup"><span data-stu-id="29c4c-124">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support PL/SQL tables that are not indexed by a numeric field.</span></span>  
  
-   <span data-ttu-id="29c4c-125">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持不包含任何元素的关联阵列。</span><span class="sxs-lookup"><span data-stu-id="29c4c-125">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support associative arrays that do not contain any element.</span></span>  
  
-   <span data-ttu-id="29c4c-126">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持包含使用本地时间区域属性 (TimeStampLTZ) 的时间戳数据类型的 Udt。</span><span class="sxs-lookup"><span data-stu-id="29c4c-126">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain the TimeStamp data type with local time zone attributes (TimeStampLTZ).</span></span>  
  
-   <span data-ttu-id="29c4c-127">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持包含的 Udt"。"</span><span class="sxs-lookup"><span data-stu-id="29c4c-127">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain a “.”</span></span> <span data-ttu-id="29c4c-128">（句点），在其名称中。</span><span class="sxs-lookup"><span data-stu-id="29c4c-128">(period) in their names.</span></span>  
  
-   <span data-ttu-id="29c4c-129">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持为 IN OUT 参数中包含 BLOB、 CLOB、 和 NCLOB 数据类型的 Udt。</span><span class="sxs-lookup"><span data-stu-id="29c4c-129">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain BLOB, CLOB, and NCLOB data types as an IN OUT parameter.</span></span>  
  
-   <span data-ttu-id="29c4c-130">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持以下简单类型的 Varray 的 Varray: BFILE、 IntervalDS、 IntervalYM、 TimeStampLTZ 和 TimeStampTZ。</span><span class="sxs-lookup"><span data-stu-id="29c4c-130">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support Varray of Varray of the following simple types: BFILE, IntervalDS, IntervalYM, TimeStampLTZ, and TimeStampTZ.</span></span>  
  
-   <span data-ttu-id="29c4c-131">由于关联的数组的限制，PL/SQL 表或包含任何以下数据类型的记录的 PL/SQL 表中不支持[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="29c4c-131">Due to the limitation of associative arrays, PL/SQL tables or PL/SQL tables of records that contain any of the following data types are not supported in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span></span>  
  
    -   <span data-ttu-id="29c4c-132">BFILE</span><span class="sxs-lookup"><span data-stu-id="29c4c-132">BFILE</span></span>  
  
    -   <span data-ttu-id="29c4c-133">BLOB</span><span class="sxs-lookup"><span data-stu-id="29c4c-133">BLOB</span></span>  
  
    -   <span data-ttu-id="29c4c-134">CLOB</span><span class="sxs-lookup"><span data-stu-id="29c4c-134">CLOB</span></span>  
  
    -   <span data-ttu-id="29c4c-135">IntervalDS</span><span class="sxs-lookup"><span data-stu-id="29c4c-135">IntervalDS</span></span>  
  
    -   <span data-ttu-id="29c4c-136">IntervalYM</span><span class="sxs-lookup"><span data-stu-id="29c4c-136">IntervalYM</span></span>  
  
    -   <span data-ttu-id="29c4c-137">Long</span><span class="sxs-lookup"><span data-stu-id="29c4c-137">Long</span></span>  
  
    -   <span data-ttu-id="29c4c-138">NCLOB</span><span class="sxs-lookup"><span data-stu-id="29c4c-138">NCLOB</span></span>  
  
    -   <span data-ttu-id="29c4c-139">RowID</span><span class="sxs-lookup"><span data-stu-id="29c4c-139">RowID</span></span>  
  
    -   <span data-ttu-id="29c4c-140">TimeStamp</span><span class="sxs-lookup"><span data-stu-id="29c4c-140">TimeStamp</span></span>  
  
    -   <span data-ttu-id="29c4c-141">TimeStampLTZ</span><span class="sxs-lookup"><span data-stu-id="29c4c-141">TimeStampLTZ</span></span>  
  
    -   <span data-ttu-id="29c4c-142">TimeStampTZ</span><span class="sxs-lookup"><span data-stu-id="29c4c-142">TimeStampTZ</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29c4c-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29c4c-143">See Also</span></span>  
 [<span data-ttu-id="29c4c-144">了解有关 Oracle E-business Suite 的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="29c4c-144">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)
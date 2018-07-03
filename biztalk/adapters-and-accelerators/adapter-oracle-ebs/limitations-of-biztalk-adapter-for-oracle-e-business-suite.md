---
title: 用于 Oracle E-business Suite 的 BizTalk 适配器的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 149cee03-43cd-4cb3-a937-6565f5e96ce5
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6de75a2955632f4f8e0daae2a2035e90f1f2fca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988390"
---
# <a name="limitations-of-biztalk-adapter-for-oracle-e-business-suite"></a><span data-ttu-id="49c63-102">用于 Oracle E-business Suite 的 BizTalk 适配器的限制</span><span class="sxs-lookup"><span data-stu-id="49c63-102">Limitations of BizTalk Adapter for Oracle E-Business Suite</span></span>
## <a name="general-limitations"></a><span data-ttu-id="49c63-103">一般限制</span><span class="sxs-lookup"><span data-stu-id="49c63-103">General Limitations</span></span>  
 <span data-ttu-id="49c63-104">以下已知的限制[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="49c63-104">The following are known limitations for [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]:</span></span>  
  
- <span data-ttu-id="49c63-105">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 XML 网关、 高级队列和业务事件。</span><span class="sxs-lookup"><span data-stu-id="49c63-105">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support XML Gateway, Advanced Queuing, and Business Events.</span></span>  
  
   <span data-ttu-id="49c63-106">但是，就可以绕过业务事件限制如下所示：</span><span class="sxs-lookup"><span data-stu-id="49c63-106">However, you can get around the Business Events limitation in the following way:</span></span>  
  
  1. <span data-ttu-id="49c63-107">在 Oracle 业务事件系统，创建业务事件发生时调用的自定义的 PL/SQL 过程的订阅。</span><span class="sxs-lookup"><span data-stu-id="49c63-107">In Oracle Business Events System, create a subscription to invoke a custom PL/SQL procedure when a business event occurs.</span></span>  
  
  2. <span data-ttu-id="49c63-108">编写一个自定义的 PL/SQL 过程，接收业务事件。</span><span class="sxs-lookup"><span data-stu-id="49c63-108">Write a custom PL/SQL procedure that receives the business event.</span></span>  
  
  3. <span data-ttu-id="49c63-109">使用自定义的 PL/SQL 过程来在表中存储结果的数据 （事件和事件有效负载）。</span><span class="sxs-lookup"><span data-stu-id="49c63-109">Use the custom PL/SQL procedure to store the resultant data (event and event payload) in a table.</span></span>  
  
  4. <span data-ttu-id="49c63-110">使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]来轮询和 / 或从表中接收通知。</span><span class="sxs-lookup"><span data-stu-id="49c63-110">Use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] to poll or receive notifications from the table.</span></span>  
  
- <span data-ttu-id="49c63-111">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 XML 类型。</span><span class="sxs-lookup"><span data-stu-id="49c63-111">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support XML Types.</span></span>  
  
- <span data-ttu-id="49c63-112">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不会启用客户端可以为 NULL VARRAY 中设置的第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="49c63-112">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not enable clients to set the value of the first element in a VARRAY to NULL.</span></span>  
  
- <span data-ttu-id="49c63-113">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]执行不支持记录，其中包含的字段类型的记录类型的 PL/SQL 表。</span><span class="sxs-lookup"><span data-stu-id="49c63-113">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support records that contain fields of type PL/SQL tables of RECORD type.</span></span>  
  
- <span data-ttu-id="49c63-114">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持具有循环引用的用户定义类型 (Udt)。</span><span class="sxs-lookup"><span data-stu-id="49c63-114">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support User-Defined Types (UDTs) that have circular references.</span></span>  
  
- <span data-ttu-id="49c63-115">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持复杂类型 （如记录类型、 表类型、 UDT 和 VARRAY） 的 BFILE 数据类型。</span><span class="sxs-lookup"><span data-stu-id="49c63-115">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support the BFILE data type inside complex types (such as RECORD type, TABLE type, UDT, and VARRAY).</span></span>  
  
- <span data-ttu-id="49c63-116">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持嵌套只有最多两个级别的 UDT。</span><span class="sxs-lookup"><span data-stu-id="49c63-116">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] supports UDT nesting only up to two levels.</span></span>  
  
- <span data-ttu-id="49c63-117">除了 PL/SQL 表[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持包内定义的 Udt。</span><span class="sxs-lookup"><span data-stu-id="49c63-117">Except for PL/SQL tables, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that are defined inside a package.</span></span>  
  
- <span data-ttu-id="49c63-118">当使用适配器与 BizTalk Server，如果在 WCF 自定义凭据的发送端口不正确时，不会处理请求消息。</span><span class="sxs-lookup"><span data-stu-id="49c63-118">When using the adapters with BizTalk Server, if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="49c63-119">指定正确的凭据后，将消息发送到 Oracle E-business Suite 和收到的响应。</span><span class="sxs-lookup"><span data-stu-id="49c63-119">After you specify the correct credentials, the message is sent to Oracle E-Business Suite and a response is received.</span></span> <span data-ttu-id="49c63-120">但是，响应消息不是输出连接到可用的。</span><span class="sxs-lookup"><span data-stu-id="49c63-120">However, the response message is not available to the out port.</span></span> <span data-ttu-id="49c63-121">在这种情况下，可能需要重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="49c63-121">In such scenarios, you may need to restart the host instance.</span></span>  
  
## <a name="limitations-due-to-odpnet"></a><span data-ttu-id="49c63-122">由于 ODP.NET 限制</span><span class="sxs-lookup"><span data-stu-id="49c63-122">Limitations Due to ODP.NET</span></span>  
 <span data-ttu-id="49c63-123">以下已知的限制[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]由于 ODP.NET 的限制：</span><span class="sxs-lookup"><span data-stu-id="49c63-123">The following are known limitations for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] due to the limitation of ODP.NET:</span></span>  
  
- <span data-ttu-id="49c63-124">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持按数值字段不编制索引的 PL/SQL 表。</span><span class="sxs-lookup"><span data-stu-id="49c63-124">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support PL/SQL tables that are not indexed by a numeric field.</span></span>  
  
- <span data-ttu-id="49c63-125">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持不包含任何元素的关联阵列。</span><span class="sxs-lookup"><span data-stu-id="49c63-125">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support associative arrays that do not contain any element.</span></span>  
  
- <span data-ttu-id="49c63-126">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持包含使用本地时间区域属性 (TimeStampLTZ) 的时间戳数据类型的 Udt。</span><span class="sxs-lookup"><span data-stu-id="49c63-126">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain the TimeStamp data type with local time zone attributes (TimeStampLTZ).</span></span>  
  
- <span data-ttu-id="49c63-127">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持包含的 Udt"。"</span><span class="sxs-lookup"><span data-stu-id="49c63-127">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain a “.”</span></span> <span data-ttu-id="49c63-128">（句点），其名称中。</span><span class="sxs-lookup"><span data-stu-id="49c63-128">(period) in their names.</span></span>  
  
- <span data-ttu-id="49c63-129">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持 BLOB、 CLOB、 和 NCLOB 数据类型包含为在 OUT 参数的 Udt。</span><span class="sxs-lookup"><span data-stu-id="49c63-129">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support UDTs that contain BLOB, CLOB, and NCLOB data types as an IN OUT parameter.</span></span>  
  
- <span data-ttu-id="49c63-130">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持以下的简单类型的 Varray Varray: BFILE、 IntervalDS、 IntervalYM、 TimeStampLTZ 和 TimeStampTZ。</span><span class="sxs-lookup"><span data-stu-id="49c63-130">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support Varray of Varray of the following simple types: BFILE, IntervalDS, IntervalYM, TimeStampLTZ, and TimeStampTZ.</span></span>  
  
- <span data-ttu-id="49c63-131">由于关联阵列的限制，PL/SQL 表或包含任何以下数据类型的记录的 PL/SQL 表中不支持[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="49c63-131">Due to the limitation of associative arrays, PL/SQL tables or PL/SQL tables of records that contain any of the following data types are not supported in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:</span></span>  
  
  -   <span data-ttu-id="49c63-132">BFILE</span><span class="sxs-lookup"><span data-stu-id="49c63-132">BFILE</span></span>  
  
  -   <span data-ttu-id="49c63-133">BLOB</span><span class="sxs-lookup"><span data-stu-id="49c63-133">BLOB</span></span>  
  
  -   <span data-ttu-id="49c63-134">CLOB</span><span class="sxs-lookup"><span data-stu-id="49c63-134">CLOB</span></span>  
  
  -   <span data-ttu-id="49c63-135">IntervalDS</span><span class="sxs-lookup"><span data-stu-id="49c63-135">IntervalDS</span></span>  
  
  -   <span data-ttu-id="49c63-136">IntervalYM</span><span class="sxs-lookup"><span data-stu-id="49c63-136">IntervalYM</span></span>  
  
  -   <span data-ttu-id="49c63-137">Long</span><span class="sxs-lookup"><span data-stu-id="49c63-137">Long</span></span>  
  
  -   <span data-ttu-id="49c63-138">NCLOB</span><span class="sxs-lookup"><span data-stu-id="49c63-138">NCLOB</span></span>  
  
  -   <span data-ttu-id="49c63-139">RowID</span><span class="sxs-lookup"><span data-stu-id="49c63-139">RowID</span></span>  
  
  -   <span data-ttu-id="49c63-140">TimeStamp</span><span class="sxs-lookup"><span data-stu-id="49c63-140">TimeStamp</span></span>  
  
  -   <span data-ttu-id="49c63-141">TimeStampLTZ</span><span class="sxs-lookup"><span data-stu-id="49c63-141">TimeStampLTZ</span></span>  
  
  -   <span data-ttu-id="49c63-142">TimeStampTZ</span><span class="sxs-lookup"><span data-stu-id="49c63-142">TimeStampTZ</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49c63-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="49c63-143">See Also</span></span>  
 [<span data-ttu-id="49c63-144">了解用于 Oracle E-Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="49c63-144">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)
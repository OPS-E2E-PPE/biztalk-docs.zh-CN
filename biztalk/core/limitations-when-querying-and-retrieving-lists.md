---
title: 查询和检索列表时的限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JD Edwards OneWorld adapters, querying limitations
- querying, limitations [JD Edwards OneWorld adapters]
ms.assetid: 1b6f5d2a-d1e2-4c78-8f4a-f00d10f008b9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27880dc3f603f39c9cb9f71207edc1926df4df7f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002822"
---
# <a name="limitations-when-querying-and-retrieving-lists"></a><span data-ttu-id="dfb58-102">查询和检索列表时的限制</span><span class="sxs-lookup"><span data-stu-id="dfb58-102">Limitations When Querying and Retrieving Lists</span></span>
<span data-ttu-id="dfb58-103">JD Edwards OneWorld 通信体系结构是一种单消息、 单回复体系结构。</span><span class="sxs-lookup"><span data-stu-id="dfb58-103">The JD Edwards OneWorld communication architecture is a single-message, single-reply architecture.</span></span> <span data-ttu-id="dfb58-104">不能返回数组或消息的列表。</span><span class="sxs-lookup"><span data-stu-id="dfb58-104">You cannot return a list of messages or an array.</span></span> <span data-ttu-id="dfb58-105">基础代码是 c + +，其中具有指向一个结构的指针调用、 在结构中，进行更改，然后退出。</span><span class="sxs-lookup"><span data-stu-id="dfb58-105">The underlying code is C++, which calls with a pointer to a single structure, makes changes in the structure, and then exits.</span></span>  
  
## <a name="querying-and-retrieving-lists"></a><span data-ttu-id="dfb58-106">查询和检索列出</span><span class="sxs-lookup"><span data-stu-id="dfb58-106">Querying and Retrieving Lists</span></span>  
 <span data-ttu-id="dfb58-107">您不能查询和检索的记录使用用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器，由于与 JD Edwards OneWorld 业务函数体系结构的限制的搜索条件的列表。</span><span class="sxs-lookup"><span data-stu-id="dfb58-107">You cannot query and retrieve lists of records based on search criteria using Microsoft BizTalk Adapter for JD Edwards OneWorld due to a limitation with the JD Edwards OneWorld business function architecture.</span></span>  
  
 <span data-ttu-id="dfb58-108">在 JD Edwards OneWorld 数据库连接是通过使用一套专有 （和复杂） 的内部函数调用提供的。</span><span class="sxs-lookup"><span data-stu-id="dfb58-108">In JD Edwards OneWorld, database connectivity is provided by using a set of proprietary (and complex) internal function calls.</span></span> <span data-ttu-id="dfb58-109">这些调用屏蔽基础的数据库版本的要求非常显式和低级别的调用，以创建要检索或更新的列的列表，并创建专用的结构的排序或所选内容。</span><span class="sxs-lookup"><span data-stu-id="dfb58-109">These calls mask the underlying database version by requiring very explicit and low-level calls to create lists of columns to retrieve or update, and create specialized structures for sorting or selection.</span></span> <span data-ttu-id="dfb58-110">未通过 Java （或任何其他） 公开的 Api 集的连接方法;因此，不能通过业务功能处理记录集。</span><span class="sxs-lookup"><span data-stu-id="dfb58-110">The sets of APIs are not exposed through the Java (or any other) connectivity method; therefore, record sets cannot be handled through business functions.</span></span>  
  
 <span data-ttu-id="dfb58-111">JD Edwards OneWorld 工具集，在中，你可以创建业务功能，处理的单个记录或通过使用上一组记录;但是，访问 JD Edwards OneWorld 工具以外的文件项的列表，更加困难。</span><span class="sxs-lookup"><span data-stu-id="dfb58-111">Within the JD Edwards OneWorld toolset, you can create business functions that handle a single record or operate on a group of records; however, accessing lists of items outside the JD Edwards OneWorld tools is more difficult.</span></span>  
  
 <span data-ttu-id="dfb58-112">若要解决此问题，可以创建一个自定义业务函数，返回基于查询的记录密钥的列表。</span><span class="sxs-lookup"><span data-stu-id="dfb58-112">To work around this issue, you can create a custom business function that returns a list of record keys based on a query.</span></span> <span data-ttu-id="dfb58-113">您必须段在列表中，，因为 JDENET （JD Edwards OneWorld 内部消息传递 API 的专有） 具有用于管理大型或不受限制的结果集的消息缓冲区大小限制。</span><span class="sxs-lookup"><span data-stu-id="dfb58-113">You must segment the lists, because JDENET (the JD Edwards OneWorld internal proprietary messaging API) has a limitation on the message buffer size for managing large or unbounded result sets.</span></span> <span data-ttu-id="dfb58-114">客户端代码必须循环访问 （循环） 连续调用业务函数，直到指出该列表完整返回一个指示符。</span><span class="sxs-lookup"><span data-stu-id="dfb58-114">The client code must iterate (loop) through successive calls to the business function, until an indicator is returned stating that the list is complete.</span></span>  
  
## <a name="controlling-iteration"></a><span data-ttu-id="dfb58-115">控制迭代</span><span class="sxs-lookup"><span data-stu-id="dfb58-115">Controlling Iteration</span></span>  
 <span data-ttu-id="dfb58-116">对 JD Edwards OneWorld 业务功能的所有调用都是无状态;因此，业务功能无法维护打开的游标，并在请求中返回更多的行。</span><span class="sxs-lookup"><span data-stu-id="dfb58-116">All calls to JD Edwards OneWorld business functions are stateless; therefore, the business function cannot maintain an open cursor and return more rows on request.</span></span> <span data-ttu-id="dfb58-117">定位信息必须传递到 JD Edwards OneWorld XE 业务功能在每次调用。</span><span class="sxs-lookup"><span data-stu-id="dfb58-117">Positioning information must be passed to the JD Edwards OneWorld XE business function on each call.</span></span>  
  
 <span data-ttu-id="dfb58-118">下面是用于控制迭代技术的列表：</span><span class="sxs-lookup"><span data-stu-id="dfb58-118">The following is a list of techniques for controlling iteration:</span></span>  
  
- <span data-ttu-id="dfb58-119">在 JD Edwards OneWorld 端，编写将结果集返回可以连续调用，以及记录号将游标定位在指定的 ID （如文件名称或作业数） 的临时存储文件。</span><span class="sxs-lookup"><span data-stu-id="dfb58-119">On the JD Edwards OneWorld side, write the result set to a temporary storage file, which returns an ID (such as a file name or job number) that can be given on successive calls, along with the record number to position the cursor.</span></span> <span data-ttu-id="dfb58-120">基于传入的记录数的列表中的定位任何后续调用。</span><span class="sxs-lookup"><span data-stu-id="dfb58-120">Any successive call is positioned within the list based on the passed-in record number.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="dfb58-121">通过用于 JD Edwards OneWorld 的 BizTalk 适配器的调用可以进行负载平衡;但是，它们最终由基于凭据和被调用的业务函数的单个应用程序服务器提供。</span><span class="sxs-lookup"><span data-stu-id="dfb58-121">Calls through BizTalk Adapter for JD Edwards OneWorld can be load-balanced; however, they are eventually served by a single application server based on the credentials and business function being called.</span></span> <span data-ttu-id="dfb58-122">因此，如果调用创建的服务器上的临时文件，其他调用会通过在同一台服务器提供服务。</span><span class="sxs-lookup"><span data-stu-id="dfb58-122">Therefore, if a call creates a temporary file on a server, additional calls are served by the same server.</span></span> <span data-ttu-id="dfb58-123">有关详细信息，请参阅 JD Edwards OneWorld CNC Guides（《JD Edwards OneWorld CNC 指南》）中的 Object Configuration Mapping（“对象配置映射”）。</span><span class="sxs-lookup"><span data-stu-id="dfb58-123">For more information, see Object Configuration Mapping in the JD Edwards OneWorld CNC Guides.</span></span>  
  
- <span data-ttu-id="dfb58-124">位置信息 （如主键值） 可以返回在第二个和后续调用中，并可以基于其他参数作为密钥重新发出查询。</span><span class="sxs-lookup"><span data-stu-id="dfb58-124">Position information (such as a primary key value) can be returned on the second and subsequent calls, and the query can be reissued based on the key as an additional parameter.</span></span> <span data-ttu-id="dfb58-125">用于 JD Edwards OneWorld 的 BizTalk 适配器浏览代码存储库中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="dfb58-125">This method is used in the repository browsing code for BizTalk Adapter for JD Edwards OneWorld.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="dfb58-126">前两个技术的建议的方法是使用主键值，然后重新发出查询。</span><span class="sxs-lookup"><span data-stu-id="dfb58-126">Of the first two techniques, the recommended method is to use primary key values and reissue the query.</span></span> <span data-ttu-id="dfb58-127">此方法要求最小的代码量，并将对数据库的优化和缓存的负担。</span><span class="sxs-lookup"><span data-stu-id="dfb58-127">This method requires the smallest amount of code and places the optimization and caching burden on the database.</span></span>  
  
- <span data-ttu-id="dfb58-128">调用应用程序可以存储 （如的交叉引用） 的主键的列表。</span><span class="sxs-lookup"><span data-stu-id="dfb58-128">The calling application can store a list of primary keys (such as a cross reference).</span></span> <span data-ttu-id="dfb58-129">例如，如果客户关系管理 (CRM) 系统创建客户记录，然后将其添加到使用业务函数调用的 JD Edwards OneWorld 业务函数，用于添加客户记录设置 AN8 字段 （短地址号码） 的值返回缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="dfb58-129">For example, if a customer relationship management (CRM) system creates a customer record and then adds it to JD Edwards OneWorld using a business function call, the business function that adds a customer record sets the value for the AN8 field (short address number) and is visible in the return buffer.</span></span> <span data-ttu-id="dfb58-130">此数字然后可以写入到一个引用字段上的原始客户记录，或存储到一个自定义交叉引用表。</span><span class="sxs-lookup"><span data-stu-id="dfb58-130">This number can then be written to a reference field on the original customer record, or stored into a customized cross-reference table.</span></span>  
  
- <span data-ttu-id="dfb58-131">JD Edwards OneWorld 中的所有主记录的大多数都具有查找或备用键的概念。</span><span class="sxs-lookup"><span data-stu-id="dfb58-131">The majority of all master records in JD Edwards OneWorld have a concept of a lookup, or alternate key.</span></span> <span data-ttu-id="dfb58-132">可以使用此密钥存储在调用系统中的密钥信息。</span><span class="sxs-lookup"><span data-stu-id="dfb58-132">This key can be used to store the key information from the calling system.</span></span> <span data-ttu-id="dfb58-133">在 JD Edwards OneWorld 端业务功能可以执行查找。</span><span class="sxs-lookup"><span data-stu-id="dfb58-133">Business functions can perform the lookup on the JD Edwards OneWorld side.</span></span> <span data-ttu-id="dfb58-134">当传递到业务函数，以创建客户记录的参数时，长的密钥值设置。</span><span class="sxs-lookup"><span data-stu-id="dfb58-134">When parameters are passed to the business function to create a customer record, the long key value is set.</span></span>  
  
  <span data-ttu-id="dfb58-135">有关这些概念的详细信息，请参阅 JD Edwards OneWorld 帮助系统中的“Interoperability”（互操作性）主题。</span><span class="sxs-lookup"><span data-stu-id="dfb58-135">For more information on these concepts, see the Interoperability topic in the JD Edwards OneWorld Help system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb58-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfb58-136">See Also</span></span>  
 [<span data-ttu-id="dfb58-137">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="dfb58-137">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)
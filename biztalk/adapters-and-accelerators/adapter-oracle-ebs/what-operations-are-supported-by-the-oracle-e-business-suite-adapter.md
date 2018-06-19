---
title: Oracle E-business Suite 适配器支持哪些操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64cd124a-5e7f-4ee8-85d3-f9540b25d766
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7236c21f1e298f2ccd4cbb97db481cbd3626d186
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217661"
---
# <a name="what-operations-are-supported-by-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="c8af9-102">Oracle E-business Suite 适配器支持何种操作</span><span class="sxs-lookup"><span data-stu-id="c8af9-102">What operations are supported by the Oracle E-Business Suite adapter</span></span>
## <a name="overview"></a><span data-ttu-id="c8af9-103">概述</span><span class="sxs-lookup"><span data-stu-id="c8af9-103">Overview</span></span>
<span data-ttu-id="c8af9-104">适配器客户端可以在通过 Oracle E-business Suite 执行操作：</span><span class="sxs-lookup"><span data-stu-id="c8af9-104">Adapter clients can perform operations in Oracle E-Business Suite by:</span></span>  
  
-   <span data-ttu-id="c8af9-105">创建 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="c8af9-105">Creating BizTalk projects</span></span>  
  
-   <span data-ttu-id="c8af9-106">使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="c8af9-106">Using the WCF channel model</span></span>  
  
-   <span data-ttu-id="c8af9-107">使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="c8af9-107">Using the WCF service model</span></span>  
  
 <span data-ttu-id="c8af9-108">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开应用程序可以调用它并且它可以反过来，调用应用程序的操作。</span><span class="sxs-lookup"><span data-stu-id="c8af9-108">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="c8af9-109">这些操作都是通过在通道上发送 SOAP 消息中调用。</span><span class="sxs-lookup"><span data-stu-id="c8af9-109">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="c8af9-110">如果需要响应，它将通过相同的通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="c8af9-110">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="c8af9-111">有关消息结构和每个操作与关联的 SOAP 操作的信息，请参阅[消息和消息架构用于 Oracle E-business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="c8af9-111">For information about the message structure and the SOAP action associated with each operation, see [messages and message schemas for BizTalk Adapter for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>  
  
 <span data-ttu-id="c8af9-112">本部分提供有关在 Oracle E-business Suite 中使用支持的操作的信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c8af9-112">This section provides information about the operations supported in Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8af9-113">在本节中</span><span class="sxs-lookup"><span data-stu-id="c8af9-113">In this section</span></span>  
  
-   [<span data-ttu-id="c8af9-114">设置应用程序上下文</span><span class="sxs-lookup"><span data-stu-id="c8af9-114">Set Application Context</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)  
  
-   [<span data-ttu-id="c8af9-115">对接口表和接口视图的操作</span><span class="sxs-lookup"><span data-stu-id="c8af9-115">Operations on Interface Tables and Interface Views</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)  
  
-   [<span data-ttu-id="c8af9-116">PL/SQL api 的操作</span><span class="sxs-lookup"><span data-stu-id="c8af9-116">Operations on PL/SQL APIs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-pl-sql-apis.md)  
  
-   [<span data-ttu-id="c8af9-117">对并发程序操作</span><span class="sxs-lookup"><span data-stu-id="c8af9-117">Operations on Concurrent Programs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)  
  
-   [<span data-ttu-id="c8af9-118">对请求设置的操作</span><span class="sxs-lookup"><span data-stu-id="c8af9-118">Operations on Request Sets</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)  
  
-   [<span data-ttu-id="c8af9-119">对接口表、 界面视图、 表和视图包含 LOB 数据的操作</span><span class="sxs-lookup"><span data-stu-id="c8af9-119">Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)  
  
-   [<span data-ttu-id="c8af9-120">对包含 BFILE 数据类型的表的操作</span><span class="sxs-lookup"><span data-stu-id="c8af9-120">Operations on Tables That Contain BFILE Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [<span data-ttu-id="c8af9-121">对函数和存储的过程的操作</span><span class="sxs-lookup"><span data-stu-id="c8af9-121">Operations on Functions and Stored Procedures</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-stored-procedures1.md)  
  
-   [<span data-ttu-id="c8af9-122">对函数和过程与 REF CURSOR 参数的操作</span><span class="sxs-lookup"><span data-stu-id="c8af9-122">Operations on Functions and Procedures with REF CURSOR Parameters</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)  
  
-   [<span data-ttu-id="c8af9-123">对函数和过程的记录类型的操作</span><span class="sxs-lookup"><span data-stu-id="c8af9-123">Operations on Functions and Procedures with RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
-   [<span data-ttu-id="c8af9-124">对同义词的操作</span><span class="sxs-lookup"><span data-stu-id="c8af9-124">Operations on Synonyms</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-synonyms2.md)  
  
-   [<span data-ttu-id="c8af9-125">接收数据库更改通知时的注意事项</span><span class="sxs-lookup"><span data-stu-id="c8af9-125">Consideration for Receiving Database Change Notifications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [<span data-ttu-id="c8af9-126">使用轮询的入站调用的支持</span><span class="sxs-lookup"><span data-stu-id="c8af9-126">Support for Inbound Calls Using Polling</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)  
  
-   [<span data-ttu-id="c8af9-127">支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作</span><span class="sxs-lookup"><span data-stu-id="c8af9-127">Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)  
  
-   [<span data-ttu-id="c8af9-128">对复合操作的支持</span><span class="sxs-lookup"><span data-stu-id="c8af9-128">Support for Composite Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)  
  
-   [<span data-ttu-id="c8af9-129">对 Oracle 用户定义类型的支持</span><span class="sxs-lookup"><span data-stu-id="c8af9-129">Support for Oracle User-Defined Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-oracle-user-defined-types2.md)  
  
## <a name="see-also"></a><span data-ttu-id="c8af9-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8af9-130">See Also</span></span>  
[<span data-ttu-id="c8af9-131">了解有关 Oracle E-business Suite 的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="c8af9-131">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)
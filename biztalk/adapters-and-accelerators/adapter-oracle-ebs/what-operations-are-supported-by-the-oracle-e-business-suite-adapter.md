---
title: Oracle E-business Suite 适配器支持哪些操作 |Microsoft Docs
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
ms.openlocfilehash: 42651a1ebbca615a0ca9d4aaaf4a3d09c42840ce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374291"
---
# <a name="what-operations-are-supported-by-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="32c97-102">Oracle E-business Suite 适配器支持哪些操作</span><span class="sxs-lookup"><span data-stu-id="32c97-102">What operations are supported by the Oracle E-Business Suite adapter</span></span>
## <a name="overview"></a><span data-ttu-id="32c97-103">概述</span><span class="sxs-lookup"><span data-stu-id="32c97-103">Overview</span></span>
<span data-ttu-id="32c97-104">适配器客户端可以通过 Oracle E-business Suite 中执行操作：</span><span class="sxs-lookup"><span data-stu-id="32c97-104">Adapter clients can perform operations in Oracle E-Business Suite by:</span></span>  
  
- <span data-ttu-id="32c97-105">创建 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="32c97-105">Creating BizTalk projects</span></span>  
  
- <span data-ttu-id="32c97-106">使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="32c97-106">Using the WCF channel model</span></span>  
  
- <span data-ttu-id="32c97-107">使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="32c97-107">Using the WCF service model</span></span>  
  
  <span data-ttu-id="32c97-108">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。</span><span class="sxs-lookup"><span data-stu-id="32c97-108">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="32c97-109">通过通道发送 SOAP 消息来调用这些操作。</span><span class="sxs-lookup"><span data-stu-id="32c97-109">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="32c97-110">如果响应是必需的它通过同一通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="32c97-110">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="32c97-111">有关消息结构和与每个操作关联的 SOAP 操作的信息，请参阅[消息和消息架构用于 Oracle E-business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="32c97-111">For information about the message structure and the SOAP action associated with each operation, see [messages and message schemas for BizTalk Adapter for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>  
  
  <span data-ttu-id="32c97-112">本部分提供有关在 Oracle E-business Suite 中使用支持的操作信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="32c97-112">This section provides information about the operations supported in Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="32c97-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="32c97-113">In this section</span></span>  
  
-   [<span data-ttu-id="32c97-114">设置应用程序上下文</span><span class="sxs-lookup"><span data-stu-id="32c97-114">Set Application Context</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)  
  
-   [<span data-ttu-id="32c97-115">对界面表和界面视图的操作</span><span class="sxs-lookup"><span data-stu-id="32c97-115">Operations on Interface Tables and Interface Views</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)  
  
-   [<span data-ttu-id="32c97-116">对 PL/SQL API 的操作</span><span class="sxs-lookup"><span data-stu-id="32c97-116">Operations on PL/SQL APIs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-pl-sql-apis.md)  
  
-   [<span data-ttu-id="32c97-117">对并发程序的操作</span><span class="sxs-lookup"><span data-stu-id="32c97-117">Operations on Concurrent Programs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-concurrent-programs.md)  
  
-   [<span data-ttu-id="32c97-118">对请求集的操作</span><span class="sxs-lookup"><span data-stu-id="32c97-118">Operations on Request Sets</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-request-sets.md)  
  
-   [<span data-ttu-id="32c97-119">对界面表、界面视图、表和包含 LOB 数据的视图的操作</span><span class="sxs-lookup"><span data-stu-id="32c97-119">Operations on Interface Tables, Interface Views, Tables, and Views That Contain LOB Data</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/read-and-update-on-interface-tables-and-views-with-large-object-data-types.md)  
  
-   [<span data-ttu-id="32c97-120">对包含 BFILE 数据类型的表的操作</span><span class="sxs-lookup"><span data-stu-id="32c97-120">Operations on Tables That Contain BFILE Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [<span data-ttu-id="32c97-121">对函数和存储过程的操作</span><span class="sxs-lookup"><span data-stu-id="32c97-121">Operations on Functions and Stored Procedures</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-stored-procedures1.md)  
  
-   [<span data-ttu-id="32c97-122">对包含 REF CURSOR 参数的函数和过程的操作</span><span class="sxs-lookup"><span data-stu-id="32c97-122">Operations on Functions and Procedures with REF CURSOR Parameters</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)  
  
-   [<span data-ttu-id="32c97-123">对包含 RECORD 类型的函数和过程的操作</span><span class="sxs-lookup"><span data-stu-id="32c97-123">Operations on Functions and Procedures with RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
-   [<span data-ttu-id="32c97-124">对同义词的操作</span><span class="sxs-lookup"><span data-stu-id="32c97-124">Operations on Synonyms</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-synonyms2.md)  
  
-   [<span data-ttu-id="32c97-125">接收数据库更改通知时的注意事项</span><span class="sxs-lookup"><span data-stu-id="32c97-125">Consideration for Receiving Database Change Notifications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [<span data-ttu-id="32c97-126">支持使用轮询的入站调用</span><span class="sxs-lookup"><span data-stu-id="32c97-126">Support for Inbound Calls Using Polling</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)  
  
-   [<span data-ttu-id="32c97-127">支持 ExecuteNonQuery、ExecuteReader 和 ExecuteScalar 操作</span><span class="sxs-lookup"><span data-stu-id="32c97-127">Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)  
  
-   [<span data-ttu-id="32c97-128">支持复合操作</span><span class="sxs-lookup"><span data-stu-id="32c97-128">Support for Composite Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-composite-operations2.md)  
  
-   [<span data-ttu-id="32c97-129">支持 Oracle 用户定义类型</span><span class="sxs-lookup"><span data-stu-id="32c97-129">Support for Oracle User-Defined Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-oracle-user-defined-types2.md)  
  
## <a name="see-also"></a><span data-ttu-id="32c97-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="32c97-130">See Also</span></span>  
[<span data-ttu-id="32c97-131">了解用于 Oracle E-Business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="32c97-131">Understand BizTalk Adapter for Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)
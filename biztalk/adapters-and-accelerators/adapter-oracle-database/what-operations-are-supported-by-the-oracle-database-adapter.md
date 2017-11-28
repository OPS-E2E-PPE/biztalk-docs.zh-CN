---
title: "Oracle 数据库适配器支持哪些操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP
- operations, performing
ms.assetid: d78dbeb8-9dab-4a71-982e-f7ada51472e8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 014b0fc6158c151d510152550c0093f6ffa9031b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-oracle-database-adapter"></a><span data-ttu-id="97105-102">Oracle 数据库适配器支持何种操作</span><span class="sxs-lookup"><span data-stu-id="97105-102">What operations are supported by the Oracle Database adapter</span></span>
<span data-ttu-id="97105-103">创建 BizTalk 项目、 使用 WCF 通道模型，或使用 WCF 服务模型，适配器客户端可以执行对 Oracle 数据库的操作。</span><span class="sxs-lookup"><span data-stu-id="97105-103">Adapter clients can perform operations on the Oracle database by creating BizTalk projects, by using the WCF channel model, or by using the WCF service model.</span></span> <span data-ttu-id="97105-104">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开应用程序可以调用它并且它可以反过来，调用应用程序的操作。</span><span class="sxs-lookup"><span data-stu-id="97105-104">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="97105-105">这些操作都是通过在通道上发送 SOAP 消息中调用。</span><span class="sxs-lookup"><span data-stu-id="97105-105">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="97105-106">如果需要响应，它将通过相同的通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="97105-106">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="97105-107">有关消息结构和每个操作与关联的 SOAP 操作的信息，请参阅[消息和消息架构用于 Oracle 数据库的 BizTalk Adapter](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="97105-107">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
 <span data-ttu-id="97105-108">本部分提供有关使用 Oracle 数据库上支持的操作的信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="97105-108">This section provides information about the operations supported on the Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="97105-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="97105-109">In This Section</span></span>  
  
-   [<span data-ttu-id="97105-110">执行基本的插入、 更新、 删除和 Oracle 表和视图的 Select 操作</span><span class="sxs-lookup"><span data-stu-id="97105-110">Performing Basic Insert, Update, Delete, and Select Operations on Oracle Tables and Views</span></span>](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-and-select-operations-on-oracle-tables-and-views.md)  
  
-   [<span data-ttu-id="97105-111">对表和视图包含 LOB 数据的操作</span><span class="sxs-lookup"><span data-stu-id="97105-111">Operations on Tables and Views That Contain LOB Data</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)  
  
-   [<span data-ttu-id="97105-112">对函数和 Oracle 数据库中的存储的过程的操作</span><span class="sxs-lookup"><span data-stu-id="97105-112">Operations on Functions and Stored Procedures in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-stored-procedures-in-oracle-database.md)  
  
-   [<span data-ttu-id="97105-113">对函数和过程与 Oracle 数据库中的 REF CURSOR 参数的操作</span><span class="sxs-lookup"><span data-stu-id="97105-113">Operations on Functions and Procedures with REF CURSOR Parameters in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/ref-cursor-parameters-in-oracle-database-adapter.md)  
  
-   [<span data-ttu-id="97105-114">对函数和过程与 Oracle 数据库中的记录类型的操作</span><span class="sxs-lookup"><span data-stu-id="97105-114">Operations on Functions and Procedures with RECORD Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-procedures-with-record-types-in-oracle-database.md)  
  
-   [<span data-ttu-id="97105-115">对与 BFILE 数据类型的表的操作</span><span class="sxs-lookup"><span data-stu-id="97105-115">Operations on Tables With BFILE Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [<span data-ttu-id="97105-116">对 Oracle 数据库中的同义词的操作</span><span class="sxs-lookup"><span data-stu-id="97105-116">Operations on Synonyms in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-synonyms-in-oracle-database.md)  
  
-   [<span data-ttu-id="97105-117">Oracle 数据库中的 SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="97105-117">SQLEXECUTE Operation in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)  
  
-   [<span data-ttu-id="97105-118">Oracle 数据库中执行复合操作</span><span class="sxs-lookup"><span data-stu-id="97105-118">Performing Composite Operations in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)  
  
-   [<span data-ttu-id="97105-119">支持 Oracle 数据库中接收基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="97105-119">Support for Receiving Polling-based Data-changed Messages in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)  
  
-   [<span data-ttu-id="97105-120">接收更改通知使用数据库的 Oracle 数据库适配器的注意事项</span><span class="sxs-lookup"><span data-stu-id="97105-120">Considerations for Receiving Database Change Notifications Using the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [<span data-ttu-id="97105-121">对 Oracle Oracle 数据库中的用户定义类型的支持</span><span class="sxs-lookup"><span data-stu-id="97105-121">Support for Oracle User-Defined Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/support-for-oracle-user-defined-types-in-oracle-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="97105-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97105-122">See Also</span></span>  
 [<span data-ttu-id="97105-123">用于 Oracle 数据库的 BizTalk Adapter 的概述</span><span class="sxs-lookup"><span data-stu-id="97105-123">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)
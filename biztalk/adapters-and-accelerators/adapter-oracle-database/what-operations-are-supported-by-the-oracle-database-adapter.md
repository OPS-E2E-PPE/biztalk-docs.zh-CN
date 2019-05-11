---
title: Oracle 数据库适配器支持哪些操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP
- operations, performing
ms.assetid: d78dbeb8-9dab-4a71-982e-f7ada51472e8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed048357b98f8b831f53d00495fb9f9961f6afb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375843"
---
# <a name="what-operations-are-supported-by-the-oracle-database-adapter"></a><span data-ttu-id="3bdc4-102">哪些操作支持的 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="3bdc4-102">What operations are supported by the Oracle Database adapter</span></span>
<span data-ttu-id="3bdc4-103">创建 BizTalk 项目、 使用 WCF 通道模型，或使用 WCF 服务模型，适配器客户端可以执行对 Oracle 数据库的操作。</span><span class="sxs-lookup"><span data-stu-id="3bdc4-103">Adapter clients can perform operations on the Oracle database by creating BizTalk projects, by using the WCF channel model, or by using the WCF service model.</span></span> <span data-ttu-id="3bdc4-104">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。</span><span class="sxs-lookup"><span data-stu-id="3bdc4-104">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="3bdc4-105">通过通道发送 SOAP 消息来调用这些操作。</span><span class="sxs-lookup"><span data-stu-id="3bdc4-105">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="3bdc4-106">如果响应是必需的它通过同一通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="3bdc4-106">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="3bdc4-107">有关消息结构和与每个操作关联的 SOAP 操作的信息，请参阅[消息和消息架构的 Oracle 数据库的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="3bdc4-107">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
 <span data-ttu-id="3bdc4-108">本部分提供有关在 Oracle 数据库使用支持的操作信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3bdc4-108">This section provides information about the operations supported on the Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3bdc4-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="3bdc4-109">In This Section</span></span>  
  
-   [<span data-ttu-id="3bdc4-110">执行基本的 Insert、 Update、 Delete 和 Oracle 表和视图的 Select 操作</span><span class="sxs-lookup"><span data-stu-id="3bdc4-110">Performing Basic Insert, Update, Delete, and Select Operations on Oracle Tables and Views</span></span>](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-and-select-operations-on-oracle-tables-and-views.md)  
  
-   [<span data-ttu-id="3bdc4-111">对包含 LOB 数据的表和视图的操作</span><span class="sxs-lookup"><span data-stu-id="3bdc4-111">Operations on Tables and Views That Contain LOB Data</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-tables-and-views-that-contain-lob-data-in-oracle-database.md)  
  
-   [<span data-ttu-id="3bdc4-112">对函数和 Oracle 数据库中的存储的过程的操作</span><span class="sxs-lookup"><span data-stu-id="3bdc4-112">Operations on Functions and Stored Procedures in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-stored-procedures-in-oracle-database.md)  
  
-   [<span data-ttu-id="3bdc4-113">对 Oracle 数据库中的 REF CURSOR 参数包含函数和过程的操作</span><span class="sxs-lookup"><span data-stu-id="3bdc4-113">Operations on Functions and Procedures with REF CURSOR Parameters in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/ref-cursor-parameters-in-oracle-database-adapter.md)  
  
-   [<span data-ttu-id="3bdc4-114">对函数和过程的 Oracle 数据库中的记录类型的操作</span><span class="sxs-lookup"><span data-stu-id="3bdc4-114">Operations on Functions and Procedures with RECORD Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-functions-and-procedures-with-record-types-in-oracle-database.md)  
  
-   [<span data-ttu-id="3bdc4-115">对包含 BFILE 数据类型的表的操作</span><span class="sxs-lookup"><span data-stu-id="3bdc4-115">Operations on Tables With BFILE Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-tables-that-contain-bfile-data-types.md)  
  
-   [<span data-ttu-id="3bdc4-116">对 Oracle 数据库中的同义词的操作</span><span class="sxs-lookup"><span data-stu-id="3bdc4-116">Operations on Synonyms in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/operations-on-synonyms-in-oracle-database.md)  
  
-   [<span data-ttu-id="3bdc4-117">Oracle 数据库中的 SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="3bdc4-117">SQLEXECUTE Operation in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)  
  
-   [<span data-ttu-id="3bdc4-118">在 Oracle 数据库中执行复合操作</span><span class="sxs-lookup"><span data-stu-id="3bdc4-118">Performing Composite Operations in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-in-oracle-database.md)  
  
-   [<span data-ttu-id="3bdc4-119">支持 Oracle 数据库中接收基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="3bdc4-119">Support for Receiving Polling-based Data-changed Messages in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md)  
  
-   [<span data-ttu-id="3bdc4-120">接收数据库更改通知使用的 Oracle 数据库适配器时的注意事项</span><span class="sxs-lookup"><span data-stu-id="3bdc4-120">Considerations for Receiving Database Change Notifications Using the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)  
  
-   [<span data-ttu-id="3bdc4-121">对 Oracle 数据库中的 Oracle 用户定义类型的支持</span><span class="sxs-lookup"><span data-stu-id="3bdc4-121">Support for Oracle User-Defined Types in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/support-for-oracle-user-defined-types-in-oracle-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="3bdc4-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bdc4-122">See Also</span></span>  
 [<span data-ttu-id="3bdc4-123">用于 Oracle 数据库的 BizTalk 适配器概述</span><span class="sxs-lookup"><span data-stu-id="3bdc4-123">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)
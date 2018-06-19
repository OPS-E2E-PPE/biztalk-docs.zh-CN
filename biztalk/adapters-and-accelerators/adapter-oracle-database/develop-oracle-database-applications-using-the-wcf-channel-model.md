---
title: 开发 Oracle 数据库应用程序使用 WCF 通道模型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF channel model, streaming
- channel programming, streaming
- WCF channel model, performing operations
- developing applications, by using the WCF channel model
- streaming, using the WCF channel model
- WCF channel model, developingn applications
- channel programming, performing operations
ms.assetid: cb6bf5fd-ff90-44bd-a9dd-03b00f12a78d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77fb9b6ca1fc70a55b59c6708450b8d94a01eff8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214981"
---
# <a name="develop-oracle-database-applications-using-the-wcf-channel-model"></a><span data-ttu-id="f227c-102">开发 Oracle 数据库应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="f227c-102">Develop Oracle Database applications using the WCF Channel Model</span></span>
<span data-ttu-id="f227c-103">你可以使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]通道模型来使用[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]通过直接通过使用 Oracle DB 绑定创建的通道实例发送 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="f227c-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] by sending XML messages directly over a channel instance created with the Oracle DB Binding.</span></span>  
  
 <span data-ttu-id="f227c-104">通过使用的强类型类和 WCF 服务模型公开的方法使用 WCF 通道模型的一个优点是通道模型提供更好地细化控制对 Oracle 数据库执行的操作。</span><span class="sxs-lookup"><span data-stu-id="f227c-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the Oracle database.</span></span> <span data-ttu-id="f227c-105">原因是什么？</span><span class="sxs-lookup"><span data-stu-id="f227c-105">Why?</span></span> <span data-ttu-id="f227c-106">WCF 通道模型直接控制通过通道发送的消息的内容。</span><span class="sxs-lookup"><span data-stu-id="f227c-106">In the WCF channel model you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="f227c-107">在某些情况下，此额外级别是控制的有益的。</span><span class="sxs-lookup"><span data-stu-id="f227c-107">In certain scenarios, this extra level of control can be beneficial.</span></span> <span data-ttu-id="f227c-108">例如，当使用 WCF 通道模型来执行更新操作在表上的，你有选择地可以直接更新目标行中的列，通过省略消息中传递的更新模板中的列。</span><span class="sxs-lookup"><span data-stu-id="f227c-108">For example, when you use the WCF channel model to perform an Update operation on a table, you can selectively update columns in the target rows by omitting columns from the update template that you pass in the message.</span></span> <span data-ttu-id="f227c-109">由公开的更新方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端对于表架构中包含的每个列的模板使用强类型的记录参数。</span><span class="sxs-lookup"><span data-stu-id="f227c-109">The update method exposed by a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] client uses a strongly-typed record parameter for the template that includes every column in the table schema.</span></span> <span data-ttu-id="f227c-110">如果某一列具有"nillable = false"在 WSDL，必须更新使用 WCF 服务模型。</span><span class="sxs-lookup"><span data-stu-id="f227c-110">If a column has “nillable=false” in the WSDL, it must be updated using the WCF service model.</span></span>  
  
 <span data-ttu-id="f227c-111">WCF 通道模型提供了对 WCF 服务模型的另一个关键优势是更全面支持的端到端流式处理的 Oracle 大型对象 (LOB) 数据类型。</span><span class="sxs-lookup"><span data-stu-id="f227c-111">Another key advantage that the WCF channel model provides over the WCF service model is more comprehensive support for end-to-end streaming of Oracle large object (LOB) data types.</span></span> <span data-ttu-id="f227c-112">通过使用 WCF 通道模型中，你可以执行端到端流式处理：</span><span class="sxs-lookup"><span data-stu-id="f227c-112">By using the WCF channel model you can perform end-to-end streaming:</span></span>  
  
-   <span data-ttu-id="f227c-113">若要更新表中的 LOB 列或查看使用 UpdateLOB 操作。</span><span class="sxs-lookup"><span data-stu-id="f227c-113">To update an LOB column in a table or view using the UpdateLOB operation.</span></span>  
  
-   <span data-ttu-id="f227c-114">在扩展和 OUT 参数包含 IN LOB 过程和函数返回的数据。</span><span class="sxs-lookup"><span data-stu-id="f227c-114">On OUT and IN OUT parameters containing LOB data that are returned by procedures and functions.</span></span>  
  
-   <span data-ttu-id="f227c-115">SQLEXECUTE 操作的结果中包含的 LOB 数据。</span><span class="sxs-lookup"><span data-stu-id="f227c-115">On LOB data that is contained in the result of a SQLEXECUTE operation.</span></span>  
  
-   <span data-ttu-id="f227c-116">在 POLLINGSTMT 操作中返回的 LOB 数据列。</span><span class="sxs-lookup"><span data-stu-id="f227c-116">On LOB data columns that are returned in the POLLINGSTMT operation.</span></span>  
  
-   <span data-ttu-id="f227c-117">返回由对表或视图的选择操作的 LOB 数据列。</span><span class="sxs-lookup"><span data-stu-id="f227c-117">On LOB data columns that are returned by a Select operation on a table or view.</span></span>  
  
 <span data-ttu-id="f227c-118">这是因为在 WCF 通道模型你直接控制如何提供传出消息的消息正文，并对传入的消息的消息正文的处理方式。</span><span class="sxs-lookup"><span data-stu-id="f227c-118">This is because in the WCF channel model you directly control how you provide the message body on outgoing messages and how you process the message body on incoming messages.</span></span>  
  
 <span data-ttu-id="f227c-119">与此相反，WCF 服务模型仅提供：</span><span class="sxs-lookup"><span data-stu-id="f227c-119">In contrast, the WCF service model only provides:</span></span>  
  
-   <span data-ttu-id="f227c-120">端到端上一个操作，ReadLOB 操作的 LOB 数据流式处理。</span><span class="sxs-lookup"><span data-stu-id="f227c-120">End-to-end streaming for LOB data on one operation, the ReadLOB operation.</span></span>  
  
-   <span data-ttu-id="f227c-121">若要更新在流处理方式中对 Oracle 数据库的 LOB 数据没有任何功能。</span><span class="sxs-lookup"><span data-stu-id="f227c-121">No capability to update LOB data on the Oracle database in a streamed fashion.</span></span>  
  
 <span data-ttu-id="f227c-122">本主题中的各节说明如何执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="f227c-122">The sections in this topic explain how to perform operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f227c-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="f227c-123">In This Section</span></span>  
  
-   [<span data-ttu-id="f227c-124">与 Oracle 数据库适配器的 WCF 通道模型概述</span><span class="sxs-lookup"><span data-stu-id="f227c-124">Overview of the WCF channel model with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-channel-model-with-the-oracle-database-adapter.md) 
  
-   [<span data-ttu-id="f227c-125">创建一个通道，使用 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="f227c-125">Create a channel using Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-channel-using-oracle-database.md) 
  
-   [<span data-ttu-id="f227c-126">调用使用 WCF 通道模型对 Oracle 数据库的操作</span><span class="sxs-lookup"><span data-stu-id="f227c-126">Invoke Operations on the Oracle Database Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/invoke-operations-on-the-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="f227c-127">使用 WCF 通道模型的 Oracle 数据库中运行 SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="f227c-127">Run a SQLEXECUTE Operation in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="f227c-128">使用 WCF 通道模型的 Oracle 数据库中运行插入操作</span><span class="sxs-lookup"><span data-stu-id="f227c-128">Run an Insert Operation in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="f227c-129">调用中使用 WCF 通道模型的 Oracle 数据库的函数</span><span class="sxs-lookup"><span data-stu-id="f227c-129">Invoke a Function in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/invoke-a-function-in-oracle-database-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="f227c-130">使用 WCF 通道模型的 Oracle 数据库中接收基于轮询的数据更改消息</span><span class="sxs-lookup"><span data-stu-id="f227c-130">Receive Polling-based Data-changed Messages in Oracle Database using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-db-using-a-wcf-channel.md)  
  
-   [<span data-ttu-id="f227c-131">使用 WCF 通道模型的流式处理 Oracle 数据库 LOB 数据类型</span><span class="sxs-lookup"><span data-stu-id="f227c-131">Streaming Oracle Database LOB Data Types Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/streaming-oracle-database-lob-data-types-using-the-wcf-channel-model.md)
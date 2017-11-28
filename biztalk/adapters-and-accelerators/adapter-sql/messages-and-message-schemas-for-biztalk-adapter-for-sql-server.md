---
title: "消息和消息架构用于 SQL Server 的 BizTalk Adapter |Microsoft 文档"
description: "SQL Server 适配器用于 BizTalk Server 的消息和数据类型的 XML 结构"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e95c6342-5420-4fb8-9b41-7c87d27b5b68
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b1e45f0a20500253e2ca831138a21efa24df3c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-sql-server"></a><span data-ttu-id="80bd0-103">消息和用于 SQL Server 的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="80bd0-103">Messages and Message Schemas for BizTalk Adapter for SQL Server</span></span>

## <a name="overview"></a><span data-ttu-id="80bd0-104">概述</span><span class="sxs-lookup"><span data-stu-id="80bd0-104">Overview</span></span>
<span data-ttu-id="80bd0-105">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="80bd0-105">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="80bd0-106">它公开应用程序可以调用它并且它可以反过来，调用应用程序的操作。</span><span class="sxs-lookup"><span data-stu-id="80bd0-106">It exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="80bd0-107">这些操作都是通过在通道上发送 SOAP 消息中调用。</span><span class="sxs-lookup"><span data-stu-id="80bd0-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="80bd0-108">如果需要响应，它将通过相同的通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="80bd0-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="80bd0-109">作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开其操作和数据类型的元数据通过使用标准[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]机制。</span><span class="sxs-lookup"><span data-stu-id="80bd0-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="80bd0-110">本主题中的各节描述了消息的 XML 结构和数据类型，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用。</span><span class="sxs-lookup"><span data-stu-id="80bd0-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80bd0-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="80bd0-111">In This Section</span></span>  
  
-   [<span data-ttu-id="80bd0-112">基本的 SQL Server 数据类型</span><span class="sxs-lookup"><span data-stu-id="80bd0-112">Basic SQL Server Data Types</span></span>](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md)  
  
-   [<span data-ttu-id="80bd0-113">消息架构为插入、 更新、 删除和选择表和视图上的操作</span><span class="sxs-lookup"><span data-stu-id="80bd0-113">Message Schemas for Insert, Update, Delete, and Select Operations on Tables and Views</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [<span data-ttu-id="80bd0-114">有关过程和函数的消息架构</span><span class="sxs-lookup"><span data-stu-id="80bd0-114">Message Schemas for Procedures and Functions</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-procedures-and-functions.md)  
  
-   [<span data-ttu-id="80bd0-115">轮询和 TypedPolling 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="80bd0-115">Message Schemas for the Polling and TypedPolling Operations</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-the-polling-and-typedpolling-operations.md)  
  
-   [<span data-ttu-id="80bd0-116">查询通知的消息架构</span><span class="sxs-lookup"><span data-stu-id="80bd0-116">Message Schemas for Query Notification</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-query-notification.md)  
  
-   [<span data-ttu-id="80bd0-117">复合操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="80bd0-117">Message Schemas for Composite Operations</span></span>](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)  
  
-   [<span data-ttu-id="80bd0-118">ExecuteNonQuery、 ExecuteReader，和 ExecuteScalar 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="80bd0-118">Message Schemas for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>](../../adapters-and-accelerators/adapter-sql/executenonquery-executereader-and-executescalar-message-schemas-in-sql.md)  
  

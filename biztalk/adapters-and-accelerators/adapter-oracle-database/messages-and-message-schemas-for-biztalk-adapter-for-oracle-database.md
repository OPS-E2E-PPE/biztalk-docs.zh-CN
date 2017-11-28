---
title: "消息和消息架构用于 Oracle 数据库的 BizTalk Adapter |Microsoft 文档"
description: "Oracle 数据库适配器用于 BizTalk Server 的消息和数据类型的 XML 结构"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fee0a531-b1e6-4b99-bb79-45368c401395
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bda5ed06470e051dc1f0bdf4595a1539aab6e6bc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="78058-103">消息和用于 Oracle 数据库的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="78058-103">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>

## <a name="overview"></a><span data-ttu-id="78058-104">概述</span><span class="sxs-lookup"><span data-stu-id="78058-104">Overview</span></span>
<span data-ttu-id="78058-105">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="78058-105">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="78058-106">它公开应用程序可以调用它并且它可以反过来，调用应用程序的操作。</span><span class="sxs-lookup"><span data-stu-id="78058-106">It exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="78058-107">这些操作都是通过在通道上发送 SOAP 消息中调用。</span><span class="sxs-lookup"><span data-stu-id="78058-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="78058-108">如果需要响应，它将通过相同的通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="78058-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="78058-109">作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开其操作和数据类型的元数据通过使用标准[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]机制。</span><span class="sxs-lookup"><span data-stu-id="78058-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="78058-110">本主题中的各节描述了消息的 XML 结构和数据类型，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用。</span><span class="sxs-lookup"><span data-stu-id="78058-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="78058-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="78058-111">In This Section</span></span>  
  
-   [<span data-ttu-id="78058-112">基本 Oracle 数据类型</span><span class="sxs-lookup"><span data-stu-id="78058-112">Basic Oracle Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-database/basic-oracle-data-types1.md)  
  
-   [<span data-ttu-id="78058-113">消息架构的基本的插入、 更新、 删除和选择表和视图上的操作</span><span class="sxs-lookup"><span data-stu-id="78058-113">Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [<span data-ttu-id="78058-114">特殊 LOB 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="78058-114">Message Schemas for Special LOB Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)  
  
-   [<span data-ttu-id="78058-115">函数和过程的消息架构</span><span class="sxs-lookup"><span data-stu-id="78058-115">Message Schemas for Functions and Procedures</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)  
  
-   [<span data-ttu-id="78058-116">REF CURSOR 的消息架构</span><span class="sxs-lookup"><span data-stu-id="78058-116">Message Schemas for REF CURSORS</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)  
  
-   [<span data-ttu-id="78058-117">记录类型的消息架构</span><span class="sxs-lookup"><span data-stu-id="78058-117">Message Schemas for RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)  
  
-   [<span data-ttu-id="78058-118">SQLEXECUTE 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="78058-118">Message Schemas for the SQLEXECUTE Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)  
  
-   [<span data-ttu-id="78058-119">轮询操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="78058-119">Message Schemas for the Polling Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)  
  
-   [<span data-ttu-id="78058-120">复合操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="78058-120">Message Schemas for the Composite Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)  
  
-   [<span data-ttu-id="78058-121">通知操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="78058-121">Message Schemas for the Notification Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md)  
  

---
title: 消息和消息架构的 BizTalk 适配器用于 Oracle 数据库 |Microsoft Docs
description: 为 BizTalk Server 使用的 Oracle 数据库适配器的消息和数据类型的 XML 结构
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fee0a531-b1e6-4b99-bb79-45368c401395
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804143e55a69f775a6d1391f57cfce8cd12d7b3a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529005"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-oracle-database"></a><span data-ttu-id="f5249-103">消息和消息架构的 Oracle 数据库的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="f5249-103">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>

## <a name="overview"></a><span data-ttu-id="f5249-104">概述</span><span class="sxs-lookup"><span data-stu-id="f5249-104">Overview</span></span>
<span data-ttu-id="f5249-105">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="f5249-105">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="f5249-106">它公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。</span><span class="sxs-lookup"><span data-stu-id="f5249-106">It exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="f5249-107">通过通道发送 SOAP 消息来调用这些操作。</span><span class="sxs-lookup"><span data-stu-id="f5249-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="f5249-108">如果响应是必需的它通过同一通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="f5249-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="f5249-109">作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开其操作和数据类型的元数据通过使用标准[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]机制。</span><span class="sxs-lookup"><span data-stu-id="f5249-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="f5249-110">本主题中的部分描述的消息的 XML 结构和数据类型，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用。</span><span class="sxs-lookup"><span data-stu-id="f5249-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5249-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="f5249-111">In This Section</span></span>  
  
-   [<span data-ttu-id="f5249-112">基本 Oracle 数据类型</span><span class="sxs-lookup"><span data-stu-id="f5249-112">Basic Oracle Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-database/basic-oracle-data-types1.md)  
  
-   [<span data-ttu-id="f5249-113">对表和视图进行基本插入、更新、删除和选择操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="f5249-113">Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)  
  
-   [<span data-ttu-id="f5249-114">特殊 LOB 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="f5249-114">Message Schemas for Special LOB Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-special-lob-operations2.md)  
  
-   [<span data-ttu-id="f5249-115">函数和过程的消息架构</span><span class="sxs-lookup"><span data-stu-id="f5249-115">Message Schemas for Functions and Procedures</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-functions-and-procedures.md)  
  
-   [<span data-ttu-id="f5249-116">REF CURSORS 的消息架构</span><span class="sxs-lookup"><span data-stu-id="f5249-116">Message Schemas for REF CURSORS</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md)  
  
-   [<span data-ttu-id="f5249-117">RECORD 类型的消息架构</span><span class="sxs-lookup"><span data-stu-id="f5249-117">Message Schemas for RECORD Types</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)  
  
-   [<span data-ttu-id="f5249-118">SQLEXECUTE 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="f5249-118">Message Schemas for the SQLEXECUTE Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)  
  
-   [<span data-ttu-id="f5249-119">轮询操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="f5249-119">Message Schemas for the Polling Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-polling-operations2.md)  
  
-   [<span data-ttu-id="f5249-120">复合操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="f5249-120">Message Schemas for the Composite Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)  
  
-   [<span data-ttu-id="f5249-121">通知操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="f5249-121">Message Schemas for the Notification Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-notification-operation1.md)  
  

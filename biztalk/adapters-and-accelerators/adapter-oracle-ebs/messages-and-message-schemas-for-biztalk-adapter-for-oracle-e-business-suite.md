---
title: 消息和用于 Oracle E-business Suite 的 BizTalk 适配器的消息架构 |Microsoft Docs
description: Oracle EBS 适配器用于 BizTalk Server 的消息和数据类型的 XML 结构
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4434b4d4-fbe0-4692-81a5-9883c9a77cf6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0d21fa159295e6b8b38b53a98f18bc9b40c21db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375368"
---
# <a name="messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite"></a><span data-ttu-id="99e82-103">消息和消息架构用于 Oracle E-business Suite 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="99e82-103">Messages and Message Schemas for BizTalk Adapter for Oracle E-Business Suite</span></span>

## <a name="overview"></a><span data-ttu-id="99e82-104">概述</span><span class="sxs-lookup"><span data-stu-id="99e82-104">Overview</span></span>
<span data-ttu-id="99e82-105">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="99e82-105">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="99e82-106">它公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。</span><span class="sxs-lookup"><span data-stu-id="99e82-106">It exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="99e82-107">通过通道发送 SOAP 消息来调用这些操作。</span><span class="sxs-lookup"><span data-stu-id="99e82-107">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="99e82-108">如果响应是必需的它通过同一通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="99e82-108">If a response is required, it is returned in a SOAP message over the same channel.</span></span>  
  
 <span data-ttu-id="99e82-109">作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开其操作和数据类型的元数据通过使用标准[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]机制。</span><span class="sxs-lookup"><span data-stu-id="99e82-109">As a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] exposes metadata for its operations and data types by using standard [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] mechanisms.</span></span> <span data-ttu-id="99e82-110">本主题中的部分描述的消息的 XML 结构和数据类型，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用。</span><span class="sxs-lookup"><span data-stu-id="99e82-110">The sections in this topic describe the XML structure of the messages and data types that the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="99e82-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="99e82-111">In This Section</span></span>  
  
-   [<span data-ttu-id="99e82-112">基本 Oracle 数据类型</span><span class="sxs-lookup"><span data-stu-id="99e82-112">Basic Oracle Data Types</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/basic-oracle-data-types2.md)  
  
-   [<span data-ttu-id="99e82-113">插入、更新、删除和选择操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="99e82-113">Message Schemas for Insert, Update, Delete, and Select Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-insert-update-delete-and-select-operations.md)  
  
-   [<span data-ttu-id="99e82-114">存储过程、函数和 PL/SQL API 的消息架构</span><span class="sxs-lookup"><span data-stu-id="99e82-114">Message Schemas for Stored Procedures, Functions, and PL/SQL APIs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-stored-procedures-functions-and-pl-sql-apis.md)  
  
-   [<span data-ttu-id="99e82-115">并发程序的消息架构</span><span class="sxs-lookup"><span data-stu-id="99e82-115">Message Schemas for Concurrent Programs</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-concurrent-programs.md)  
  
-   [<span data-ttu-id="99e82-116">请求集的消息架构</span><span class="sxs-lookup"><span data-stu-id="99e82-116">Message Schemas for Request Sets</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-request-sets.md)  
  
-   [<span data-ttu-id="99e82-117">特殊 LOB 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="99e82-117">Message Schemas for Special LOB Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-special-lob-operations1.md)  
  
-   [<span data-ttu-id="99e82-118">轮询操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="99e82-118">Message Schemas for the Polling Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-polling-operations1.md)  
  
-   [<span data-ttu-id="99e82-119">通知操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="99e82-119">Message Schemas for the Notification Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-notification-operation2.md)  
  
-   [<span data-ttu-id="99e82-120">ExecuteNonQuery、ExecuteReader 和 ExecuteScalar 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="99e82-120">Message Schemas for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/executenonquery-executereader-and-executescalar-message-schemas.md)  
  
-   [<span data-ttu-id="99e82-121">复合操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="99e82-121">Message Schemas for the Composite Operation</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md)  
  
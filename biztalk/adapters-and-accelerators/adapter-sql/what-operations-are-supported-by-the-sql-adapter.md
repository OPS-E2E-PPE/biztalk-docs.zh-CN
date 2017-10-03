---
title: "哪些操作受 SQL 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b8f4099-df19-48c4-a135-1ec264af3513
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59d413a763823f49b0bf905b42d8513cbbb1e745
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-sql-adapter"></a><span data-ttu-id="e1592-102">哪些操作受 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="e1592-102">What operations are supported by the SQL adapter</span></span>
<span data-ttu-id="e1592-103">可以使用适配器客户端在通过 SQL Server 数据库上执行操作：</span><span class="sxs-lookup"><span data-stu-id="e1592-103">You can use the adapter clients to perform operations on the SQL Server database by:</span></span>  
  
-   <span data-ttu-id="e1592-104">创建 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="e1592-104">Creating BizTalk projects</span></span>  
  
-   <span data-ttu-id="e1592-105">使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="e1592-105">Using the WCF service model</span></span>  
  
-   <span data-ttu-id="e1592-106">使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="e1592-106">Using the WCF channel model</span></span>  
  
 <span data-ttu-id="e1592-107">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开应用程序可以调用它并且它可以反过来，调用应用程序的操作。</span><span class="sxs-lookup"><span data-stu-id="e1592-107">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="e1592-108">这些操作都是通过在通道上发送 SOAP 消息中调用。</span><span class="sxs-lookup"><span data-stu-id="e1592-108">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="e1592-109">如果需要响应，它将通过相同的通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="e1592-109">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="e1592-110">有关消息结构和每个操作与关联的 SOAP 操作的信息，请参阅[消息和消息架构用于 SQL Server 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e1592-110">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).</span></span>  
  
 <span data-ttu-id="e1592-111">本部分提供有关使用 SQL Server 数据库上支持的操作的信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e1592-111">This section provides information about the operations supported on the SQL Server database using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="e1592-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1592-112">See Also</span></span>  
 [<span data-ttu-id="e1592-113">用于 SQL Server 的 BizTalk Adapter 的概述</span><span class="sxs-lookup"><span data-stu-id="e1592-113">Overview of BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)
---
title: 通过 SQL 适配器支持哪些操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b8f4099-df19-48c4-a135-1ec264af3513
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 873b74a253bd96c95ecf3d26be884fe83ac53e7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367432"
---
# <a name="what-operations-are-supported-by-the-sql-adapter"></a><span data-ttu-id="5c992-102">通过 SQL 适配器支持哪些操作</span><span class="sxs-lookup"><span data-stu-id="5c992-102">What operations are supported by the SQL adapter</span></span>
<span data-ttu-id="5c992-103">可以使用适配器客户端在通过 SQL Server 数据库上执行操作：</span><span class="sxs-lookup"><span data-stu-id="5c992-103">You can use the adapter clients to perform operations on the SQL Server database by:</span></span>  
  
- <span data-ttu-id="5c992-104">创建 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="5c992-104">Creating BizTalk projects</span></span>  
  
- <span data-ttu-id="5c992-105">使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="5c992-105">Using the WCF service model</span></span>  
  
- <span data-ttu-id="5c992-106">使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="5c992-106">Using the WCF channel model</span></span>  
  
  <span data-ttu-id="5c992-107">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。</span><span class="sxs-lookup"><span data-stu-id="5c992-107">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="5c992-108">通过通道发送 SOAP 消息来调用这些操作。</span><span class="sxs-lookup"><span data-stu-id="5c992-108">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="5c992-109">如果响应是必需的它通过同一通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="5c992-109">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="5c992-110">有关消息结构和与每个操作关联的 SOAP 操作的信息，请参阅[消息和用于 SQL Server 的 BizTalk 适配器的消息架构](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="5c992-110">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).</span></span>  
  
  <span data-ttu-id="5c992-111">本部分提供有关使用 SQL Server 数据库上支持的操作信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5c992-111">This section provides information about the operations supported on the SQL Server database using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="5c992-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c992-112">See Also</span></span>  
 [<span data-ttu-id="5c992-113">用于 SQL Server 的 BizTalk 适配器概述</span><span class="sxs-lookup"><span data-stu-id="5c992-113">Overview of BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)
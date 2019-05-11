---
title: SQL 适配器客户端的功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f638154b-0a09-4f89-9c52-2a62fafec7dc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35dbd3c6236e1cd17bcfda0b083ef1309d7d9362
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369369"
---
# <a name="features-for-sql-adapter-clients"></a><span data-ttu-id="10641-102">SQL 适配器客户端的功能</span><span class="sxs-lookup"><span data-stu-id="10641-102">Features for SQL adapter clients</span></span>
<span data-ttu-id="10641-103">除了讨论的主题的功能[概述的 BizTalk 适配器适用于 SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)，则[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]还提供了可用于适配器客户端的以下功能：</span><span class="sxs-lookup"><span data-stu-id="10641-103">In addition to the features discussed throughout the topics of [Overview of BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md), the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] also provides the following features that are useful for adapter clients:</span></span>  
  
- <span data-ttu-id="10641-104">**配置使用绑定属性的适配器的支持**。</span><span class="sxs-lookup"><span data-stu-id="10641-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="10641-105">适配器客户端可以配置[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过指定特定绑定属性。</span><span class="sxs-lookup"><span data-stu-id="10641-105">Adapter clients can configure the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="10641-106">例如，客户端可以指定在连接池中允许特定连接字符串通过设置的连接的最大数**MaxConnectionPoolSize**属性绑定。</span><span class="sxs-lookup"><span data-stu-id="10641-106">For example, clients can specify the maximum number of connections allowed in a connection pool for a specific connection string by setting the **MaxConnectionPoolSize** binding property.</span></span> <span data-ttu-id="10641-107">有关详细信息，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="10641-107">For more information, see [Read about the BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
- <span data-ttu-id="10641-108">**操作参数的 null 值的支持**。</span><span class="sxs-lookup"><span data-stu-id="10641-108">**Support for null values for operation parameters**.</span></span> <span data-ttu-id="10641-109">适配器客户端可以使用 XSD"nillable"属性的操作参数提供 null 值。</span><span class="sxs-lookup"><span data-stu-id="10641-109">Adapter clients can provide null values for operation parameters using the XSD "nillable" attribute.</span></span>  
  
- <span data-ttu-id="10641-110">**支持在 BizTalk 中的动态端口**。</span><span class="sxs-lookup"><span data-stu-id="10641-110">**Support for dynamic ports in BizTalk**.</span></span> <span data-ttu-id="10641-111">通过 BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，则[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持动态端口，使动态路由的消息从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]基于消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="10641-111">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="10641-112">有关详细信息，请参阅[配置动态端口](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="10641-112">For more information, see [Configure dynamic ports](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md).</span></span>  
  
- <span data-ttu-id="10641-113">**对性能计数器支持**。</span><span class="sxs-lookup"><span data-stu-id="10641-113">**Support for performance counters**.</span></span> <span data-ttu-id="10641-114">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以供适配器客户端支持的基于 WCF 的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="10641-114">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports WCF-based performance counters for use by adapter clients.</span></span> <span data-ttu-id="10641-115">有关性能计数器的详细信息，请参阅[使用与 SQL 适配器的性能计数器](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="10641-115">For more information about performance counters, see [Use Performance Counters with the SQL adapter](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10641-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="10641-116">See Also</span></span>  
 [<span data-ttu-id="10641-117">用于 SQL Server 的 BizTalk 适配器概述</span><span class="sxs-lookup"><span data-stu-id="10641-117">Overview of BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)
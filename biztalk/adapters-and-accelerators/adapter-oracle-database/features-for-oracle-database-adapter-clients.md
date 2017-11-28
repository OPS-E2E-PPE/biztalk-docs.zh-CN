---
title: "适用于 Oracle 数据库适配器客户端的功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data streaming, support for
- binding properties
- adapter, features
- adapters, configuring
- message versioning, support for
- XML data streaming
- performance counters, support for
- dynamic ports in BizTalk, support for
- data streaming
ms.assetid: 63b52573-80a5-4206-95c3-478b86718fee
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b120c948ef3d9821af0a79e91fd718e3a1f33137
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="features-for-oracle-database-adapter-clients"></a><span data-ttu-id="f42bd-102">适用于 Oracle 数据库适配器客户端的功能</span><span class="sxs-lookup"><span data-stu-id="f42bd-102">Features for Oracle Database adapter clients</span></span>
<span data-ttu-id="f42bd-103">除了对在的主题中讨论的功能[概述的 BizTalk Adapter for Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]还提供了以下功能，可用于适配器客户端：</span><span class="sxs-lookup"><span data-stu-id="f42bd-103">In addition to the features discussed throughout the topics of [Overview of BizTalk Adapter for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md), the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] also provides the following features that are useful for adapter clients:</span></span>  
  
-   <span data-ttu-id="f42bd-104">**配置使用绑定属性的适配器的支持**。</span><span class="sxs-lookup"><span data-stu-id="f42bd-104">**Support for configuring adapters using binding properties**.</span></span> <span data-ttu-id="f42bd-105">适配器客户端可以配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]通过指定特定的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="f42bd-105">Adapter clients can configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] by specifying certain binding properties.</span></span> <span data-ttu-id="f42bd-106">例如，客户端可以配置适配器后，以通过设置使用 ODP.NET 连接池**UseOracleConnectionPool**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="f42bd-106">For example, clients can configure the adapter to use the ODP.NET connection pool by setting the **UseOracleConnectionPool** binding property.</span></span> <span data-ttu-id="f42bd-107">有关详细信息，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="f42bd-107">For more information, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
-   <span data-ttu-id="f42bd-108">**有关操作参数的 null 值的支持**。</span><span class="sxs-lookup"><span data-stu-id="f42bd-108">**Support for null values for operation parameters**.</span></span> <span data-ttu-id="f42bd-109">适配器客户端可以使用输入 XML 中的"nil"属性的操作参数提供 null 值。</span><span class="sxs-lookup"><span data-stu-id="f42bd-109">Adapter clients can provide null values for operation parameters using the “nil” attribute in the input XML.</span></span>  
  
-   <span data-ttu-id="f42bd-110">**BizTalk 中的动态端口支持**。</span><span class="sxs-lookup"><span data-stu-id="f42bd-110">**Support for dynamic ports in BizTalk**.</span></span> <span data-ttu-id="f42bd-111">通过 BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持动态端口，使动态路由的消息从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]基于消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="f42bd-111">Through the BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports a dynamic port that enables dynamic routing of messages from [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] based on the message context properties.</span></span> <span data-ttu-id="f42bd-112">有关详细信息，请参阅[配置动态端口](../../adapters-and-accelerators/adapter-oracle-database/configure-dynamic-ports-in-the-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="f42bd-112">For more information, see [Configure dynamic ports](../../adapters-and-accelerators/adapter-oracle-database/configure-dynamic-ports-in-the-oracle-database-adapter.md).</span></span>  
  
-   <span data-ttu-id="f42bd-113">**对性能计数器支持**。</span><span class="sxs-lookup"><span data-stu-id="f42bd-113">**Support for performance counters**.</span></span> <span data-ttu-id="f42bd-114">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]以适配器客户端使用支持基于 WCF 的性能计数器。</span><span class="sxs-lookup"><span data-stu-id="f42bd-114">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports WCF-based performance counters for use by adapter clients.</span></span> <span data-ttu-id="f42bd-115">有关性能计数器的详细信息，请参阅[性能计数器](../../core/performance-counters.md)。</span><span class="sxs-lookup"><span data-stu-id="f42bd-115">For more information about performance counters, see [Performance Counters](../../core/performance-counters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f42bd-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f42bd-116">See Also</span></span>  
 [<span data-ttu-id="f42bd-117">用于 Oracle 数据库的 BizTalk Adapter 的概述</span><span class="sxs-lookup"><span data-stu-id="f42bd-117">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)
---
title: "使用 Oracle 数据库适配器处理事务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 971c2fba-640c-4ae5-9ab3-2d8227c1627d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5072a49c9edc5dc8ce03ec819d6042b640b94a47
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="handle-transactions-with-the-oracle-database-adapter"></a><span data-ttu-id="279af-102">与 Oracle 数据库适配器的句柄事务</span><span class="sxs-lookup"><span data-stu-id="279af-102">Handle Transactions with the Oracle Database adapter</span></span>
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="279af-103">并不会启动一个事务执行对 Oracle 数据库操作时。</span><span class="sxs-lookup"><span data-stu-id="279af-103"> does not initiate a transaction while performing an operation on the Oracle database.</span></span> <span data-ttu-id="279af-104">相反，适配器执行的操作使用提供的适配器客户端的事务上下文。</span><span class="sxs-lookup"><span data-stu-id="279af-104">Instead, the adapter performs the operations using the transaction context provided by the adapter clients.</span></span> <span data-ttu-id="279af-105">若要执行操作在事务中使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，你必须：</span><span class="sxs-lookup"><span data-stu-id="279af-105">In order to perform operations in a transaction using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], you must:</span></span>  
  
-   <span data-ttu-id="279af-106">启用适配器客户端中的事务。</span><span class="sxs-lookup"><span data-stu-id="279af-106">Enable transactions in the adapter clients.</span></span> <span data-ttu-id="279af-107">例如，若要启用 BizTalk Server 中的事务，必须选择**使用事务**中的复选框**事务**区域**消息**WCF 自定义选项卡或WCF OracleDB 端口。</span><span class="sxs-lookup"><span data-stu-id="279af-107">For example, to enable transactions in BizTalk Server, you must select the **Use Transaction** check box in the **Transactions** area of the **Messages** tab for a WCF-Custom or WCF-OracleDB port.</span></span>  
  
-   <span data-ttu-id="279af-108">设置的值**UseAmbientTransaction**属性绑定到**True**适配器中。</span><span class="sxs-lookup"><span data-stu-id="279af-108">Set the value of the **UseAmbientTransaction** binding property to **True** in the adapter.</span></span> <span data-ttu-id="279af-109">有关绑定属性的详细信息，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="279af-109">For more information about the binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="279af-110">若要使用该适配器上的 Oracle 数据库执行事务，你必须安装**Microsoft Transaction Server 的 Oracle 服务**组件时，运行适配器的计算机上安装 Oracle 客户端，时客户端。</span><span class="sxs-lookup"><span data-stu-id="279af-110">To use the adapter to perform transactions on the Oracle database, you must have installed the **Oracle Services For Microsoft Transaction Server** component, while installing the Oracle client, on the computer running the adapter client.</span></span>  
  
## <a name="transactions-in-the-outbound-operations"></a><span data-ttu-id="279af-111">中的出站操作的事务</span><span class="sxs-lookup"><span data-stu-id="279af-111">Transactions in the Outbound Operations</span></span>  
 <span data-ttu-id="279af-112">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在单个事务中执行的出站操作。</span><span class="sxs-lookup"><span data-stu-id="279af-112">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] performs an outbound operation in a single transaction.</span></span> <span data-ttu-id="279af-113">对于复合操作，所有操作都执行在单个事务，而是使用不同的 ODP.NET 连接。</span><span class="sxs-lookup"><span data-stu-id="279af-113">For composite operations, all the operations are performed in a single transaction but using different ODP.NET connections.</span></span> <span data-ttu-id="279af-114">有关显示的出站操作详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[原理适配器面 Oracle 元数据？](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)。</span><span class="sxs-lookup"><span data-stu-id="279af-114">For more information about the outbound operations surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [How does the Adapter Surface Oracle Metadata?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx).</span></span>  
  
## <a name="transactions-in-the-inbound-operations"></a><span data-ttu-id="279af-115">中的入站操作的事务</span><span class="sxs-lookup"><span data-stu-id="279af-115">Transactions in the Inbound Operations</span></span>  
 <span data-ttu-id="279af-116">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开以下两个入站的操作：</span><span class="sxs-lookup"><span data-stu-id="279af-116">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes the following two inbound operations:</span></span>  
  
-   <span data-ttu-id="279af-117">**轮询**： 轮询语句和后轮询语句 （如果指定） 的执行在事务中，而在不同事务中执行的轮询的数据可用语句。</span><span class="sxs-lookup"><span data-stu-id="279af-117">**Polling**: The polling statement and the post-poll statement (if specified) are executed in a transaction, whereas, the polled data available statement is executed in a different transaction.</span></span> <span data-ttu-id="279af-118">同样，轮询语句后轮询语句执行和使用相同的 ODP.NET 连接，而使用不同的 ODP.NET 连接执行轮询的数据可用语句。</span><span class="sxs-lookup"><span data-stu-id="279af-118">Similarly, the polling statement and the post-poll statement are executed using the same ODP.NET connection, whereas, the polled data available statement is executed using a different ODP.NET connection.</span></span>  
  
-   <span data-ttu-id="279af-119">**通知**： 在使用单个 ODP.NET 连接事务中执行通知操作。</span><span class="sxs-lookup"><span data-stu-id="279af-119">**Notification**: The notification operation is performed in a transaction using a single ODP.NET connection.</span></span>  
  
 <span data-ttu-id="279af-120">有关显示的入站操作详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[原理适配器面 Oracle 元数据？](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx)。</span><span class="sxs-lookup"><span data-stu-id="279af-120">For more information about the inbound operations surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [How does the Adapter Surface Oracle Metadata?](https://msdn.microsoft.com/library/cc185310(v=bts.10).aspx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="279af-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="279af-121">See Also</span></span>  
 [<span data-ttu-id="279af-122">用于 Oracle 数据库的 BizTalk 适配器概述</span><span class="sxs-lookup"><span data-stu-id="279af-122">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)
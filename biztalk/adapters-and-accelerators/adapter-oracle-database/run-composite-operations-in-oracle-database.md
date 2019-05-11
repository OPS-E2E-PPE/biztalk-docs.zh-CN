---
title: 在 Oracle 数据库中运行复合操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b877d8e3-2016-40e8-888f-6b768021d6b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a9728f456e6f3cf3ad95a392a5fdc45d6cf9265
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376121"
---
# <a name="run-composite-operations-in-oracle-database"></a><span data-ttu-id="ee16b-102">在 Oracle 数据库中运行复合操作</span><span class="sxs-lookup"><span data-stu-id="ee16b-102">Run Composite Operations in Oracle Database</span></span>
<span data-ttu-id="ee16b-103">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使适配器客户端能够执行可以包含任意数量的以下操作，并按任何顺序的复合操作：</span><span class="sxs-lookup"><span data-stu-id="ee16b-103">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enables adapter clients to perform composite operations that can include any number of the following operations, and in any order:</span></span>  
  
- <span data-ttu-id="ee16b-104">选择、 插入、 更新和删除表和视图的操作。</span><span class="sxs-lookup"><span data-stu-id="ee16b-104">Select, Insert, Update, and Delete operations on tables and views.</span></span>  
  
- <span data-ttu-id="ee16b-105">存储的过程、 函数和过程或函数中显示为该适配器中的操作的包。</span><span class="sxs-lookup"><span data-stu-id="ee16b-105">Stored procedures, functions, and procedures or functions within packages that are surfaced as operations in the adapter.</span></span>  
  
  <span data-ttu-id="ee16b-106">中的复合运算操作可以针对同一个数据库或不同的数据库中表和视图。</span><span class="sxs-lookup"><span data-stu-id="ee16b-106">The operations in a composite operation can target tables and views in the same database or different databases.</span></span> <span data-ttu-id="ee16b-107">但是，不能共享数据或将其在复合操作中的不同操作中重复使用。</span><span class="sxs-lookup"><span data-stu-id="ee16b-107">However, data cannot be shared or reused across different operations in a composite operation.</span></span> <span data-ttu-id="ee16b-108">例如，在复合操作中，选择操作的结果集不能用作输入参数的存储过程。</span><span class="sxs-lookup"><span data-stu-id="ee16b-108">For example, in a composite operation, the result set of a Select operation cannot be used as the input parameter for a stored procedure.</span></span>  
  
  <span data-ttu-id="ee16b-109">使用单独的连接执行复合操作中的每个操作。</span><span class="sxs-lookup"><span data-stu-id="ee16b-109">Each operation in a composite operation is performed using a separate connection.</span></span> <span data-ttu-id="ee16b-110">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在复合操作中，操作数量作为使用 ODP.NET 连接池中的任意多个连接，并获取在执行操作，然后释放连接。</span><span class="sxs-lookup"><span data-stu-id="ee16b-110">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] consumes as many connections from the ODP.NET connection pool as the number of operations in a composite operation, and then releases the connections as the operations get executed.</span></span> <span data-ttu-id="ee16b-111">但是，如果在复合操作的操作返回结果集，使用消息之后才释放该连接。</span><span class="sxs-lookup"><span data-stu-id="ee16b-111">However, if an operation in the composite operation returns a result set, the connection is released only after the message is consumed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ee16b-112">如果你在执行复合操作时遇到超时问题，则可能是因为连接数低于在复合操作涉及的操作的数目：</span><span class="sxs-lookup"><span data-stu-id="ee16b-112">If you experience time-out issues while executing a composite operation then it could be because the number of connections is less than the number of operations in a composite operation involving:</span></span>  
> 
> - <span data-ttu-id="ee16b-113">存储的过程包含 BFILE、 BLOB、 CLOB、 NCLOB、 和 REF CURSOR 作为 OUT 或 IN OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="ee16b-113">Stored procedures containing BFILE, BLOB, CLOB, NCLOB, and REF CURSOR as OUT or IN OUT parameters.</span></span>  
>   -   <span data-ttu-id="ee16b-114">选择操作。</span><span class="sxs-lookup"><span data-stu-id="ee16b-114">Select operation.</span></span>  
> 
>   <span data-ttu-id="ee16b-115">若要解决此问题，必须确保，如果有此类操作的复合运算中的"n"数，指定的值**MinPoolSize**绑定属性是"n + 1"或更高版本。</span><span class="sxs-lookup"><span data-stu-id="ee16b-115">To resolve this issue, you must ensure that if there are “n” number of such operations in a composite operation, the value specified for the **MinPoolSize** binding property is “n+1” or greater.</span></span> <span data-ttu-id="ee16b-116">有关详细信息**MinPoolSize**绑定属性，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="ee16b-116">For more information about the **MinPoolSize** binding property, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
 <span data-ttu-id="ee16b-117">有关信息：</span><span class="sxs-lookup"><span data-stu-id="ee16b-117">For information about:</span></span>  
  
- <span data-ttu-id="ee16b-118">如何执行中的复合操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[Oracle 数据库使用 BizTalk server 上运行复合操作](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="ee16b-118">How to perform composite operations in [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run Composite Operations on Oracle Database by Using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="ee16b-119">消息复合操作的架构，请参见[复合操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md)。</span><span class="sxs-lookup"><span data-stu-id="ee16b-119">Message schemas for the composite operation, see [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-composite-operation2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee16b-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee16b-120">See Also</span></span>  
 <span data-ttu-id="ee16b-121">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="ee16b-121">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>
---
title: 在使用 SQL 适配器的 SQL Server 中运行复合操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 906c6352-44f3-4624-9e32-aea3fbb7510d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95c7863666317b42fa32b04073244915eae6d7dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367973"
---
# <a name="run-composite-operations-in-sql-server--using-the-sql-adapter"></a><span data-ttu-id="fbed9-102">在使用 SQL 适配器的 SQL Server 中运行复合操作</span><span class="sxs-lookup"><span data-stu-id="fbed9-102">Run composite operations in SQL Server  using the SQL adapter</span></span>
<span data-ttu-id="fbed9-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]使适配器客户端能够执行复合操作上的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="fbed9-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] enables adapter clients to perform composite operations on the SQL Server database.</span></span> <span data-ttu-id="fbed9-104">复合操作可以包含任意数量的以下操作，并按任何顺序：</span><span class="sxs-lookup"><span data-stu-id="fbed9-104">A composite operation can include any number of the following operations, and in any order:</span></span>  
  
- <span data-ttu-id="fbed9-105">对表和视图插入、 更新和删除操作。</span><span class="sxs-lookup"><span data-stu-id="fbed9-105">The Insert, Update, and Delete operations on the tables and views.</span></span>  
  
- <span data-ttu-id="fbed9-106">显示为该适配器中的操作的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="fbed9-106">Stored procedures that are surfaced as operations in the adapter.</span></span>  
  
  <span data-ttu-id="fbed9-107">复合操作中的操作*必须*目标表和视图只能在单个数据库中的。</span><span class="sxs-lookup"><span data-stu-id="fbed9-107">The operations in a composite operation *must* target tables and views only in a single database.</span></span>  
  
  <span data-ttu-id="fbed9-108">有关信息：</span><span class="sxs-lookup"><span data-stu-id="fbed9-108">For information about:</span></span>  
  
- <span data-ttu-id="fbed9-109">如何执行中的复合操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[SQL Server 使用 BizTalk Server 上运行复合操作](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="fbed9-109">How to perform composite operations in [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run Composite Operations on SQL Server Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/run-composite-operations-on-sql-server-using-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="fbed9-110">消息复合操作的架构，请参见[复合操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="fbed9-110">Message schemas for the composite operation, see [Message Schemas for Composite Operations](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fbed9-111">如果有"n"的复合操作返回的操作数目的连接数具有结果集然后"n + 1"所需的复合操作来执行。</span><span class="sxs-lookup"><span data-stu-id="fbed9-111">If there are “n” number of operations in a composite operation that return a result set then “n+1” number of connections are required for the composite operation to be executed.</span></span> <span data-ttu-id="fbed9-112">因此，您必须确保为指定的值**MaxConnectionPoolSize**绑定属性是 n + 1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="fbed9-112">Therefore, you must ensure that the value specified for the **MaxConnectionPoolSize** binding property is n+1 or greater.</span></span> <span data-ttu-id="fbed9-113">有关详细信息**MaxConnectionPoolSize**绑定属性，请参阅[了解适用于 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="fbed9-113">For more information about the **MaxConnectionPoolSize** binding property, see [Read about BizTalk Adapter for SQL Server adapter Binding Properties](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbed9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="fbed9-114">See Also</span></span>  
 <span data-ttu-id="fbed9-115">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="fbed9-115">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span></span>
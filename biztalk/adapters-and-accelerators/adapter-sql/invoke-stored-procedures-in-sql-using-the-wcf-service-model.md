---
title: "调用中使用 WCF 服务模型的 SQL 存储过程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4edd2fac-0b54-4406-932e-e3044a66b2e6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e2d707c37ba92fb6f1d1608ae43d02d1e964cd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invoke-stored-procedures-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="e7d13-102">调用中使用 WCF 服务模型的 SQL 存储过程</span><span class="sxs-lookup"><span data-stu-id="e7d13-102">Invoke Stored Procedures in SQL using the WCF Service Model</span></span>
<span data-ttu-id="e7d13-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]发现的存储的过程作为适配器客户端可以调用 WCF 客户端来调用存储的过程上的操作。</span><span class="sxs-lookup"><span data-stu-id="e7d13-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers the stored procedures as operations that the adapter clients can invoke on the WCF client to invoke the stored procedure.</span></span> <span data-ttu-id="e7d13-104">根据如何存储的过程返回结果集，该适配器将分类为所有存储的过程：</span><span class="sxs-lookup"><span data-stu-id="e7d13-104">Based on how the stored procedure returns the result set, the adapter categorizes all the stored procedures as:</span></span>  
  
-   <span data-ttu-id="e7d13-105">**过程**。</span><span class="sxs-lookup"><span data-stu-id="e7d13-105">**Procedures**.</span></span> <span data-ttu-id="e7d13-106">调用存储的过程从**过程**节点返回数据集的数组。</span><span class="sxs-lookup"><span data-stu-id="e7d13-106">Invoking stored procedures from the **Procedures** node returns an array of DataSet.</span></span>  
  
-   <span data-ttu-id="e7d13-107">**强类型的过程**。</span><span class="sxs-lookup"><span data-stu-id="e7d13-107">**Strongly-Typed Procedures**.</span></span> <span data-ttu-id="e7d13-108">调用存储的过程从**Strongly-Typed 过程**节点返回一个强类型化结果集。</span><span class="sxs-lookup"><span data-stu-id="e7d13-108">Invoking stored procedures from the **Strongly-Typed Procedures** node returns a strongly-typed result set.</span></span>  
  
 <span data-ttu-id="e7d13-109">请注意，相同的存储过程中连接到的数据库集将列出不足**过程**和**Strongly-Typed 过程**节点。</span><span class="sxs-lookup"><span data-stu-id="e7d13-109">Note that the same set of stored procedures in the database you connected to will be listed both under the **Procedures** and **Strongly-Typed Procedures** node.</span></span> <span data-ttu-id="e7d13-110">根据所需的结果集的类型，必须调用存储的过程从相关节点。</span><span class="sxs-lookup"><span data-stu-id="e7d13-110">Based on the kind of result set you want, you must invoke the stored procedure from the relevant node.</span></span> <span data-ttu-id="e7d13-111">有关详细信息，如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持存储的过程，请参阅[中使用 BizTalk Server 的 SQL Server 执行存储过程](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="e7d13-111">For more information about how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports stored procedures, see [Execute Stored Procedures in SQL Server using BizTalk Server](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md).</span></span>  
  
 <span data-ttu-id="e7d13-112">本部分将说明了如何调用存储的过程从这两个**过程**和**Strongly-Typed 过程**使用 WCF 客户端的节点。</span><span class="sxs-lookup"><span data-stu-id="e7d13-112">This section provides instructions on how to invoke stored procedures from both the **Procedures** and **Strongly-Typed Procedures** node by using a WCF client.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e7d13-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="e7d13-113">In This Section</span></span>  
  
-   [<span data-ttu-id="e7d13-114">Involk 弱类型中使用 WCF 服务模型的 SQL 存储过程</span><span class="sxs-lookup"><span data-stu-id="e7d13-114">Involk Weakly-typed Stored Procedures in SQL Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [<span data-ttu-id="e7d13-115">调用 SQL 使用 WCF 服务模型中的强类型化存储的过程</span><span class="sxs-lookup"><span data-stu-id="e7d13-115">Invoke Strongly-typed Stored Procedure in SQL Using WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="e7d13-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7d13-116">See Also</span></span>  
[<span data-ttu-id="e7d13-117">开发应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="e7d13-117">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)
---
title: 调用中使用 WCF 服务模型的 SQL 存储过程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edd2fac-0b54-4406-932e-e3044a66b2e6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 607a9188d53c1f18e40c04f6b7f692098dfc738c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369311"
---
# <a name="invoke-stored-procedures-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="236e9-102">调用中使用 WCF 服务模型的 SQL 存储过程</span><span class="sxs-lookup"><span data-stu-id="236e9-102">Invoke Stored Procedures in SQL using the WCF Service Model</span></span>
<span data-ttu-id="236e9-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]作为操作适配器客户端可以调用来调用存储的过程在 WCF 客户端上发现的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="236e9-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers the stored procedures as operations that the adapter clients can invoke on the WCF client to invoke the stored procedure.</span></span> <span data-ttu-id="236e9-104">如何存储的过程返回的结果集为基础，适配器将分类为所有存储的过程：</span><span class="sxs-lookup"><span data-stu-id="236e9-104">Based on how the stored procedure returns the result set, the adapter categorizes all the stored procedures as:</span></span>  
  
- <span data-ttu-id="236e9-105">**过程**。</span><span class="sxs-lookup"><span data-stu-id="236e9-105">**Procedures**.</span></span> <span data-ttu-id="236e9-106">调用存储的过程从**过程**节点返回数据集的数组。</span><span class="sxs-lookup"><span data-stu-id="236e9-106">Invoking stored procedures from the **Procedures** node returns an array of DataSet.</span></span>  
  
- <span data-ttu-id="236e9-107">**强类型的过程**。</span><span class="sxs-lookup"><span data-stu-id="236e9-107">**Strongly-Typed Procedures**.</span></span> <span data-ttu-id="236e9-108">调用存储的过程从**Strongly-Typed 过程**节点返回强类型化结果集。</span><span class="sxs-lookup"><span data-stu-id="236e9-108">Invoking stored procedures from the **Strongly-Typed Procedures** node returns a strongly-typed result set.</span></span>  
  
  <span data-ttu-id="236e9-109">请注意，同一组中连接到的数据库的存储过程将列出下两者**过程**并**Strongly-Typed 过程**节点。</span><span class="sxs-lookup"><span data-stu-id="236e9-109">Note that the same set of stored procedures in the database you connected to will be listed both under the **Procedures** and **Strongly-Typed Procedures** node.</span></span> <span data-ttu-id="236e9-110">根据所需的结果集的类型，必须调用中的相关节点的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="236e9-110">Based on the kind of result set you want, you must invoke the stored procedure from the relevant node.</span></span> <span data-ttu-id="236e9-111">详细了解如何[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持存储的过程，请参阅[SQL Server 使用 BizTalk Server 中执行存储过程](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="236e9-111">For more information about how the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] supports stored procedures, see [Execute Stored Procedures in SQL Server using BizTalk Server](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-biztalk-server.md).</span></span>  
  
  <span data-ttu-id="236e9-112">本部分说明如何调用存储的过程从这两个**过程**并**Strongly-Typed 过程**使用 WCF 客户端的节点。</span><span class="sxs-lookup"><span data-stu-id="236e9-112">This section provides instructions on how to invoke stored procedures from both the **Procedures** and **Strongly-Typed Procedures** node by using a WCF client.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="236e9-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="236e9-113">In This Section</span></span>  
  
-   [<span data-ttu-id="236e9-114">Involk 弱类型中使用 WCF 服务模型的 SQL 存储过程</span><span class="sxs-lookup"><span data-stu-id="236e9-114">Involk Weakly-typed Stored Procedures in SQL Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-weakly-typed-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [<span data-ttu-id="236e9-115">调用强类型化 SQL 使用 WCF 服务模型中的存储的过程</span><span class="sxs-lookup"><span data-stu-id="236e9-115">Invoke Strongly-typed Stored Procedure in SQL Using WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-strongly-typed-stored-procedures-in-sql-using-wcf-service-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="236e9-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="236e9-116">See Also</span></span>  
[<span data-ttu-id="236e9-117">使用 WCF 服务模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="236e9-117">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)
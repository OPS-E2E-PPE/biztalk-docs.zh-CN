---
title: 支持复合 Operations2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f65cf10-4e27-4872-bc6a-defe6cbab198
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5766adec70c1a1fe7eaabe4ffaf07499e33d210c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216437"
---
# <a name="support-for-composite-operations"></a><span data-ttu-id="7441f-102">对复合操作的支持</span><span class="sxs-lookup"><span data-stu-id="7441f-102">Support for Composite Operations</span></span>
<span data-ttu-id="7441f-103">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]允许适配器客户端执行可以包含任意数量的以下操作，并按任何顺序的复合操作：</span><span class="sxs-lookup"><span data-stu-id="7441f-103">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] enables adapter clients to perform composite operations that can include any number of the following operations, and in any order:</span></span>  
  
-   <span data-ttu-id="7441f-104">选择、 插入、 更新和删除接口表和数据库表上的操作。</span><span class="sxs-lookup"><span data-stu-id="7441f-104">Select, Insert, Update, and Delete operations on an interface table and database table.</span></span>  
  
-   <span data-ttu-id="7441f-105">选择接口视图和数据库视图上的操作。</span><span class="sxs-lookup"><span data-stu-id="7441f-105">Select operation on an interface view and database view.</span></span>  
  
-   <span data-ttu-id="7441f-106">存储的过程、 函数和作为适配器中的操作中加以表示的包内的过程。</span><span class="sxs-lookup"><span data-stu-id="7441f-106">Stored procedures, functions, and procedures within packages that are surfaced as operations in the adapter.</span></span>  
  
 <span data-ttu-id="7441f-107">中的同一个数据库或不同的数据库表和视图，可以面向的复合运算中的操作。</span><span class="sxs-lookup"><span data-stu-id="7441f-107">The operations in a composite operation can target tables and views in the same database or different databases.</span></span> <span data-ttu-id="7441f-108">但是，不能共享数据或将其在不同的操作中的复合运算间重复使用。</span><span class="sxs-lookup"><span data-stu-id="7441f-108">However, data cannot be shared or reused across different operations in a composite operation.</span></span> <span data-ttu-id="7441f-109">例如，在复合操作中，选择操作的结果集不能作为输入参数为存储过程。</span><span class="sxs-lookup"><span data-stu-id="7441f-109">For example, in a composite operation, the result set of a Select operation cannot be used as the input parameter for a stored procedure.</span></span>  
  
 <span data-ttu-id="7441f-110">复合操作中的每个操作是使用单独的连接执行的。</span><span class="sxs-lookup"><span data-stu-id="7441f-110">Each operation in a composite operation is performed using a separate connection.</span></span> <span data-ttu-id="7441f-111">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]在复合操作中，操作的数目与占用 ODP.NET 连接池中的任意多个连接，然后释放连接，获取在执行操作。</span><span class="sxs-lookup"><span data-stu-id="7441f-111">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] consumes as many connections from the ODP.NET connection pool as the number of operations in a composite operation, and then releases the connections as the operations get executed.</span></span> <span data-ttu-id="7441f-112">但是，如果该复合操作中的操作返回的结果集，在处理消息之后才释放连接。</span><span class="sxs-lookup"><span data-stu-id="7441f-112">However, if an operation in the composite operation returns a result set, the connection is released only after the message is consumed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7441f-113">如果您在执行复合操作时遇到超时问题，则可能是因为连接数低于在复合操作涉及的操作的数目：</span><span class="sxs-lookup"><span data-stu-id="7441f-113">If you experience time-out issues while executing a composite operation then it could be because the number of connections is less than the number of operations in a composite operation involving:</span></span>  
>   
>  -   <span data-ttu-id="7441f-114">缩小为包含 BFILE、 BLOB、 CLOB、 NCLOB、 和 REF CURSOR 的存储的过程或 IN OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="7441f-114">Stored procedures containing BFILE, BLOB, CLOB, NCLOB, and REF CURSOR as OUT or IN OUT parameters.</span></span>  
> -   <span data-ttu-id="7441f-115">选择操作。</span><span class="sxs-lookup"><span data-stu-id="7441f-115">Select operation.</span></span>  
>   
>  <span data-ttu-id="7441f-116">若要解决此问题，你必须确保，如果没有此类操作复合操作中的"n"数目，指定的值**MinPoolSize**绑定属性为"n + 1"或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7441f-116">To resolve this issue, you must ensure that if there are “n” number of such operations in a composite operation, the value specified for the **MinPoolSize** binding property is “n+1” or greater.</span></span> <span data-ttu-id="7441f-117">有关详细信息**MinPoolSize**绑定属性，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="7441f-117">For more information about the **MinPoolSize** binding property, see [Read about the BizTalk Adapter for Oracle E-Business Suite binding properties](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).</span></span>  
  
 <span data-ttu-id="7441f-118">有关的信息：</span><span class="sxs-lookup"><span data-stu-id="7441f-118">For information about:</span></span>  
  
-   <span data-ttu-id="7441f-119">如何执行中的复合操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[使用 BizTalk Server 的 Oracle 数据库上运行复合操作](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="7441f-119">How to perform composite operations in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see  [Run Composite Operations on Oracle Database using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-composite-operations-on-oracle-database-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="7441f-120">消息复合操作的架构，请参阅[复合操作的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md)。</span><span class="sxs-lookup"><span data-stu-id="7441f-120">Message schemas for the composite operation, see [Message Schemas for the Composite Operation](../../adapters-and-accelerators/adapter-oracle-ebs/message-schemas-for-the-composite-operation1.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7441f-121">您还可以设置中的复合操作的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7441f-121">You can also set the applications context for composite operations in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="7441f-122">它是一定要设置的复合操作的应用程序上下文，如果对接口表或接口视图执行的任何复合操作中的操作。</span><span class="sxs-lookup"><span data-stu-id="7441f-122">It is mandatory to set the applications context for the composite operations if any of the operations in a composite operation is performed on an interface table or interface view.</span></span> <span data-ttu-id="7441f-123">有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="7441f-123">For information about applications context, and how to set it, see [Set application context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7441f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7441f-124">See Also</span></span>  
 [<span data-ttu-id="7441f-125">Oracle E-business Suite 适配器支持何种操作</span><span class="sxs-lookup"><span data-stu-id="7441f-125">What operations are supported by the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)
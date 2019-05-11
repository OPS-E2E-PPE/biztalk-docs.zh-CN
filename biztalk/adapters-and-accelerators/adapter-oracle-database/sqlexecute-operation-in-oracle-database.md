---
title: Oracle 数据库中的 SQLEXECUTE 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DML
- data manipulation language
- operations, DML
- SQLEXECUTE
ms.assetid: d7f881e4-c668-4f8e-b08a-ea6614b65910
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab419c7009a3072015eee4e20260e4d1c8511a4b
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529554"
---
# <a name="sqlexecute-operation-in-oracle-database"></a><span data-ttu-id="c08a6-102">Oracle 数据库中的 SQLEXECUTE 操作</span><span class="sxs-lookup"><span data-stu-id="c08a6-102">SQLEXECUTE Operation in Oracle Database</span></span>
<span data-ttu-id="c08a6-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]显示一组标准的 Oracle 数据库项目上的操作。</span><span class="sxs-lookup"><span data-stu-id="c08a6-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces a standard set of operations on Oracle database artifacts.</span></span> <span data-ttu-id="c08a6-104">通过使用这些操作，可以执行诸如调用 Oracle 函数或过程，或执行对表的基本 SQL 数据操作语言 (DML) 操作。</span><span class="sxs-lookup"><span data-stu-id="c08a6-104">By using these operations, you can do things like call an Oracle function or procedure, or perform basic SQL data manipulation language (DML) operations on tables.</span></span> <span data-ttu-id="c08a6-105">但是，可能有需要你执行操作的方案由您的业务逻辑驱动的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不能显示。</span><span class="sxs-lookup"><span data-stu-id="c08a6-105">However, there may be scenarios driven by your business logic that require you to perform operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not surface.</span></span> <span data-ttu-id="c08a6-106">例如，您可能希望：</span><span class="sxs-lookup"><span data-stu-id="c08a6-106">For example, you may want to:</span></span>  
  
- <span data-ttu-id="c08a6-107">不显示的数据库项目上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; 例如，获取 CURVAL 或 NEXTVAL Oracle 序列。</span><span class="sxs-lookup"><span data-stu-id="c08a6-107">Perform an operation on database artifacts that are not surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example, get the CURVAL or NEXTVAL of an Oracle SEQUENCE.</span></span>  
  
- <span data-ttu-id="c08a6-108">执行数据定义语言操作;例如，创建一个表。</span><span class="sxs-lookup"><span data-stu-id="c08a6-108">Perform data definition language operations; for example, create a table.</span></span>  
  
- <span data-ttu-id="c08a6-109">如果没有安装在设计时用于数据库项目上执行操作例如，更新您的业务逻辑创建一个临时表中的记录。</span><span class="sxs-lookup"><span data-stu-id="c08a6-109">Perform operations on a database artifact that was not present at design time; for example, update records in a temporary table that is created by your business logic.</span></span>  
  
- <span data-ttu-id="c08a6-110">执行更复杂的表比操作的 DML 操作的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]显示; 例如，若要执行查询，包括对 JOIN 子句。</span><span class="sxs-lookup"><span data-stu-id="c08a6-110">Perform more complex DML operations on tables than the operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces; for example, to perform a query that includes a JOIN clause.</span></span>  
  
  <span data-ttu-id="c08a6-111">对于这些类型的情况下， [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] SQLEXECUTE 操作的图面。</span><span class="sxs-lookup"><span data-stu-id="c08a6-111">For these kinds of scenarios, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces the SQLEXECUTE operation.</span></span> <span data-ttu-id="c08a6-112">SQLEXECUTE 操作 （/） 在根节点下显示在**选择一个类别**窗格中的[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]和[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c08a6-112">The SQLEXECUTE operation is surfaced under the root node (/) in the **Select a category** pane in the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] and [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span>  
  
  <span data-ttu-id="c08a6-113">通过使用 SQLEXECUTE 操作，可以对 Oracle 数据库执行参数化的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="c08a6-113">By using the SQLEXECUTE operation, you can perform a parameterized SQL statement on the Oracle database.</span></span> <span data-ttu-id="c08a6-114">SQLEXECUTE 操作支持的参数集，您可以执行一次为每个集的同一 SQL 语句包含一个输入的参数块。</span><span class="sxs-lookup"><span data-stu-id="c08a6-114">The SQLEXECUTE operation supports an input parameter block consisting of parameter sets that enable you to execute the same SQL statement once for each set.</span></span> <span data-ttu-id="c08a6-115">SQLEXECUTE 操作返回中泛型的记录集的 SQL 语句的结果。</span><span class="sxs-lookup"><span data-stu-id="c08a6-115">The SQLEXECUTE operation returns the results of the SQL statement in a generic record set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c08a6-116">可以将传递在和中 OUT 参数到过程、 函数和 SQLEXECUTE 操作中的包。</span><span class="sxs-lookup"><span data-stu-id="c08a6-116">You can pass IN and IN OUT parameters to procedures, functions, and packages in the SQLEXECUTE operation.</span></span> <span data-ttu-id="c08a6-117">调用的项目将执行与 Oracle 数据库中; 提供的参数但是，SQLEXECUTE 操作不返回输出的值并向客户端在 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="c08a6-117">The invoked artifact will execute with the supplied parameters on the Oracle database; however, the SQLEXECUTE operation does not return the value of OUT and IN OUT parameters to the client.</span></span> <span data-ttu-id="c08a6-118">如果你想要调用过程、 函数或包，我们建议通过调用专用的操作来执行操作的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]针对这些 Oracle 项目公开。</span><span class="sxs-lookup"><span data-stu-id="c08a6-118">If you want to invoke procedures, functions, or packages, we recommend that you do so by invoking the dedicated operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes for these Oracle artifacts.</span></span>  
  
 <span data-ttu-id="c08a6-119">有关详细信息：</span><span class="sxs-lookup"><span data-stu-id="c08a6-119">For more information about:</span></span>  
  
- <span data-ttu-id="c08a6-120">使用执行 SQLEXECUTE 操作的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[通过使用 BizTalk Server 运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c08a6-120">Performing a SQLEXECUTE operation by using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Run SQLEXECUTE Operation by Using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="c08a6-121">执行 SQLEXECUTE 操作的使用 WCF 服务模型，请参阅[通过使用 WCF 服务模型运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="c08a6-121">Performing a SQLEXECUTE operation by using the WCF service model, see [Run SQLEXECUTE Operation by Using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
- <span data-ttu-id="c08a6-122">执行 SQLEXECUTE 操作的使用 WCF 通道模型，请参阅[通过使用 WCF 通道模型运行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="c08a6-122">Performing the SQLEXECUTE operation by using the WCF channel model, see [Run SQLEXECUTE Operation by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/run-a-sqlexecute-operation-in-oracle-database-using-the-wcf-channel-model.md).</span></span>  
  
- <span data-ttu-id="c08a6-123">消息结构和执行 SQLEXECUTE 操作的 SOAP 操作，请参见[SQLEXECUTE 操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="c08a6-123">Message structure and SOAP actions for performing a SQLEXECUTE operation, see [Message Schemas for the SQLEXECUTE Operation](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-the-sqlexecute-operation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c08a6-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c08a6-124">See Also</span></span>  
 <span data-ttu-id="c08a6-125">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="c08a6-125">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>
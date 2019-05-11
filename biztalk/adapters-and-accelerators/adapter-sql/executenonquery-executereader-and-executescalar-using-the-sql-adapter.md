---
title: 运行 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作使用 SQL 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3fda0544-a028-4a95-aae6-1f6a90764c5d
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e4a32828be8fbaaa65263c24aa98ff1cfd957ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65369539"
---
# <a name="run-executenonquery-executereader-and-executescalar-operations-using-the-sql-adapter"></a><span data-ttu-id="5c961-102">运行 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作使用 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="5c961-102">Run ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations using the SQL adapter</span></span>
<span data-ttu-id="5c961-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开根级别上的以下操作：</span><span class="sxs-lookup"><span data-stu-id="5c961-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes the following operations at the root level:</span></span>  
  
- <span data-ttu-id="5c961-104">**ExecuteNonQuery**:此操作用于在 SQL Server 中执行任何任意 SQL 语句，如果不希望任何结果集返回。</span><span class="sxs-lookup"><span data-stu-id="5c961-104">**ExecuteNonQuery**: Use this operation to execute any arbitrary SQL statements in SQL Server if you do not want any result set to be returned.</span></span> <span data-ttu-id="5c961-105">可以使用此操作创建数据库对象或更改数据库中的数据，通过执行 UPDATE、 INSERT 或 DELETE 语句。</span><span class="sxs-lookup"><span data-stu-id="5c961-105">You can use this operation to create database objects or change data in a database by executing UPDATE, INSERT, or DELETE statements.</span></span> <span data-ttu-id="5c961-106">此操作的返回值是 Int32 数据类型的和：</span><span class="sxs-lookup"><span data-stu-id="5c961-106">The return value of this operation is of Int32 data type, and:</span></span>  
  
  -   <span data-ttu-id="5c961-107">对于 UPDATE、 INSERT 和 DELETE 语句中，返回值是由 SQL 语句影响的行数。</span><span class="sxs-lookup"><span data-stu-id="5c961-107">For the UPDATE, INSERT, and DELETE statements, the return value is the number of rows affected by the SQL statement.</span></span>  
  
  -   <span data-ttu-id="5c961-108">对于所有其他类型的语句，返回值是**为-1**。</span><span class="sxs-lookup"><span data-stu-id="5c961-108">For all other types of statements, the return value is **-1**.</span></span>  
  
- <span data-ttu-id="5c961-109">**ExecuteReader**:此操作用于在 SQL Server 中执行任何任意 SQL 语句，如果你想将结果集返回，如果有，作为数据集的数组。</span><span class="sxs-lookup"><span data-stu-id="5c961-109">**ExecuteReader**: Use this operation to execute any arbitrary SQL statements in SQL Server if you want the result set to be returned, if any, as an array of DataSet.</span></span> <span data-ttu-id="5c961-110">有关数据集的信息，请参阅"数据集类"处[ http://go.microsoft.com/fwlink/?LinkID=196853 ](http://go.microsoft.com/fwlink/?LinkID=196853)。</span><span class="sxs-lookup"><span data-stu-id="5c961-110">For information about DataSet, see “DataSet Class” at [http://go.microsoft.com/fwlink/?LinkID=196853](http://go.microsoft.com/fwlink/?LinkID=196853).</span></span>  
  
- <span data-ttu-id="5c961-111">**ExecuteScalar**:使用此操作以返回单个值的 SQL Server 中执行任何任意 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="5c961-111">**ExecuteScalar**: Use this operation to execute any arbitrary SQL statements in SQL Server to return a single value.</span></span> <span data-ttu-id="5c961-112">此操作仅在 SQL 语句返回结果集中的第一行的第一列中返回的值。</span><span class="sxs-lookup"><span data-stu-id="5c961-112">This operation returns the value only in the first column of the first row in the result set returned by the SQL statement.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5c961-113">ExecuteScalar 优于 ExecuteReader 是 ExecuteScalar 操作的响应消息有效负载进行 ExecuteReader 操作返回的一个小得多比较。</span><span class="sxs-lookup"><span data-stu-id="5c961-113">The advantage of ExecuteScalar over ExecuteReader is that the response message payload of the ExecuteScalar operation is much smaller compared to the one returned by the ExecuteReader operation.</span></span> <span data-ttu-id="5c961-114">因此，如果您需要返回一个值，您应使用 ExecuteScalar 而不是 ExecuteReader。</span><span class="sxs-lookup"><span data-stu-id="5c961-114">Therefore, if you require only one value to be returned, you should use ExecuteScalar instead of ExecuteReader.</span></span>  
  
  <span data-ttu-id="5c961-115">ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作可用于执行多个 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="5c961-115">You can use the ExecuteNonQuery, ExecuteReader or ExecuteScalar operation to execute multiple SQL statements.</span></span>  
  
  <span data-ttu-id="5c961-116">有关执行这些操作使用的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery 操作，它可以使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="5c961-116">For more information about performing these operations using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [ExecuteReader, ExecuteScalar, or ExecuteNonQuery Operations by Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c961-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c961-117">See Also</span></span>  
 <span data-ttu-id="5c961-118">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="5c961-118">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span></span>
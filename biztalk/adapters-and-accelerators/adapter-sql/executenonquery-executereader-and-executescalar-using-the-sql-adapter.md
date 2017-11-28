---
title: "运行 ExecuteNonQuery、 ExecuteReader 和使用 SQL 适配器 ExecuteScalar 操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3fda0544-a028-4a95-aae6-1f6a90764c5d
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f68f4378a4d89d2a997f5a78a524e4f6bfca2c18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="run-executenonquery-executereader-and-executescalar-operations-using-the-sql-adapter"></a><span data-ttu-id="1adb0-102">运行 ExecuteNonQuery、 ExecuteReader 和使用 SQL 适配器 ExecuteScalar 操作</span><span class="sxs-lookup"><span data-stu-id="1adb0-102">Run ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations using the SQL adapter</span></span>
<span data-ttu-id="1adb0-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开根级别上的执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1adb0-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes the following operations at the root level:</span></span>  
  
-   <span data-ttu-id="1adb0-104">**ExecuteNonQuery**： 使用此操作在 SQL Server 中执行任何任意的 SQL 语句，如果你不想要设置要返回任何结果。</span><span class="sxs-lookup"><span data-stu-id="1adb0-104">**ExecuteNonQuery**: Use this operation to execute any arbitrary SQL statements in SQL Server if you do not want any result set to be returned.</span></span> <span data-ttu-id="1adb0-105">你可以使用此操作数据库对象通过创建或更改数据库中的数据执行 INSERT、 UPDATE 或 DELETE 语句。</span><span class="sxs-lookup"><span data-stu-id="1adb0-105">You can use this operation to create database objects or change data in a database by executing UPDATE, INSERT, or DELETE statements.</span></span> <span data-ttu-id="1adb0-106">此操作的返回值是 Int32 数据类型和：</span><span class="sxs-lookup"><span data-stu-id="1adb0-106">The return value of this operation is of Int32 data type, and:</span></span>  
  
    -   <span data-ttu-id="1adb0-107">对于 UPDATE、 INSERT 和 DELETE 语句中，返回值是由 SQL 语句影响的行数。</span><span class="sxs-lookup"><span data-stu-id="1adb0-107">For the UPDATE, INSERT, and DELETE statements, the return value is the number of rows affected by the SQL statement.</span></span>  
  
    -   <span data-ttu-id="1adb0-108">对于所有其他类型的语句，则返回值是**-1**。</span><span class="sxs-lookup"><span data-stu-id="1adb0-108">For all other types of statements, the return value is **-1**.</span></span>  
  
-   <span data-ttu-id="1adb0-109">**ExecuteReader**： 使用此操作在 SQL Server 中执行任何任意的 SQL 语句，如果你想要的结果集返回，如果有，作为数据集的数组。</span><span class="sxs-lookup"><span data-stu-id="1adb0-109">**ExecuteReader**: Use this operation to execute any arbitrary SQL statements in SQL Server if you want the result set to be returned, if any, as an array of DataSet.</span></span> <span data-ttu-id="1adb0-110">有关数据集的信息，请参阅"数据集类"在[http://go.microsoft.com/fwlink/?LinkID=196853](http://go.microsoft.com/fwlink/?LinkID=196853)。</span><span class="sxs-lookup"><span data-stu-id="1adb0-110">For information about DataSet, see “DataSet Class” at [http://go.microsoft.com/fwlink/?LinkID=196853](http://go.microsoft.com/fwlink/?LinkID=196853).</span></span>  
  
-   <span data-ttu-id="1adb0-111">**ExecuteScalar**： 使用此操作以返回单个值的 SQL Server 中执行任何任意的 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="1adb0-111">**ExecuteScalar**: Use this operation to execute any arbitrary SQL statements in SQL Server to return a single value.</span></span> <span data-ttu-id="1adb0-112">此操作仅在中返回由 SQL 语句的结果集的第一行的第一列中返回的值。</span><span class="sxs-lookup"><span data-stu-id="1adb0-112">This operation returns the value only in the first column of the first row in the result set returned by the SQL statement.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1adb0-113">通过 ExecuteReader ExecuteScalar 的优点是 ExecuteScalar 操作的响应消息负载得较小相比 ExecuteReader 操作返回的一个。</span><span class="sxs-lookup"><span data-stu-id="1adb0-113">The advantage of ExecuteScalar over ExecuteReader is that the response message payload of the ExecuteScalar operation is much smaller compared to the one returned by the ExecuteReader operation.</span></span> <span data-ttu-id="1adb0-114">因此，如果你需要要返回一个值，你应使用 ExecuteScalar 而不是 ExecuteReader。</span><span class="sxs-lookup"><span data-stu-id="1adb0-114">Therefore, if you require only one value to be returned, you should use ExecuteScalar instead of ExecuteReader.</span></span>  
  
 <span data-ttu-id="1adb0-115">ExecuteNonQuery、 ExecuteReader 或 ExecuteScalar 操作可用于执行多个 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="1adb0-115">You can use the ExecuteNonQuery, ExecuteReader or ExecuteScalar operation to execute multiple SQL statements.</span></span>  
  
 <span data-ttu-id="1adb0-116">有关执行这些操作使用的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[ExecuteReader、 ExecuteScalar 或通过使用 BizTalk Server ExecuteNonQuery 操作](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="1adb0-116">For more information about performing these operations using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [ExecuteReader, ExecuteScalar, or ExecuteNonQuery Operations by Using BizTalk Server](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-or-executenonquery-in-sql-server-using-biztalk.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1adb0-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1adb0-117">See Also</span></span>  
 <span data-ttu-id="1adb0-118">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="1adb0-118">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)</span></span>
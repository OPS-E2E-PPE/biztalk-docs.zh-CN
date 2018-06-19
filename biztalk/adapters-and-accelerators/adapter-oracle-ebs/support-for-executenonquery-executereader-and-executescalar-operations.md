---
title: 支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afdd1a5b-2a6b-48b8-a659-afd81f43f34b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40bad547627669bb22a6b32f05d96c6c7b2f68c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215717"
---
# <a name="support-for-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="dc9cc-102">支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作</span><span class="sxs-lookup"><span data-stu-id="dc9cc-102">Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>
<span data-ttu-id="dc9cc-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]公开在根级别以下的出站操作：</span><span class="sxs-lookup"><span data-stu-id="dc9cc-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes the following outbound operations at the root level:</span></span>  
  
-   <span data-ttu-id="dc9cc-104">**ExecuteNonQuery**： 使用此操作在 Oracle E-business Suite 中执行任何任意 SQL 语句或 PL/SQL 块，如果你想要返回多个结果集。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-104">**ExecuteNonQuery**: Use this operation to execute any arbitrary SQL statements or PL/SQL blocks in Oracle E-Business Suite if you want to return multiple result sets.</span></span> <span data-ttu-id="dc9cc-105">此函数的输入的参数包括字符串参数 （整个 PL/SQL 块中要执行） 和字符串 (OutRefCursorNames) 的数组。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-105">The input parameters of this function include a string parameter (the entire PL/SQL block to be executed) and an array of strings (OutRefCursorNames).</span></span> <span data-ttu-id="dc9cc-106">OutRefCursorNames 中指定每个字符串值假定为 PL/SQL 块返回 REF CURSOR 具有相同的名称与 REF CURSOR 的输出的参数名称。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-106">Each string value specified in OutRefCursorNames is assumed to be the parameter name of an output REF CURSOR with the PL/SQL block returning REF CURSORS with the same names.</span></span> <span data-ttu-id="dc9cc-107">此函数还采用 OUT 参数 (OutRefCursors)，这是数据集的数组。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-107">This function also takes an OUT parameter (OutRefCursors), which is an array of DataSets.</span></span> <span data-ttu-id="dc9cc-108">有关数据集的信息，请参阅 Oracle 文档： [http://go.microsoft.com/fwlink/?LinkId=124538](http://go.microsoft.com/fwlink/?LinkId=124538)。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-108">For information about DataSet, consult the Oracle documentation at [http://go.microsoft.com/fwlink/?LinkId=124538](http://go.microsoft.com/fwlink/?LinkId=124538).</span></span> <span data-ttu-id="dc9cc-109">此操作的返回值的整数数据类型，并指示受影响的行数。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-109">The return value of this operation is of integer data type, and indicates the number of affected rows.</span></span>  
  
-   <span data-ttu-id="dc9cc-110">**ExecuteReader**： 使用此操作在 Oracle E-business Suite 中执行任何任意 SQL 语句或 PL/SQL 块，如果你想要作为数据集返回的结果集。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-110">**ExecuteReader**: Use this operation to execute any arbitrary SQL statements or PL/SQL blocks in Oracle E-Business Suite if you want the result set to be returned as DataSet.</span></span> <span data-ttu-id="dc9cc-111">此操作采用字符串参数作为输入，并返回一个数据集。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-111">This operation takes a string parameter as input, and returns a DataSet.</span></span>  
  
-   <span data-ttu-id="dc9cc-112">**ExecuteScalar**： 使用此操作在 Oracle E-business Suite 中执行任何任意 SQL 语句或 PL/SQL 块，如果你想要返回一个值。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-112">**ExecuteScalar**: Use this operation to execute any arbitrary SQL statements or PL/SQL blocks in Oracle E-Business Suite if you want only one value to be returned.</span></span> <span data-ttu-id="dc9cc-113">如果返回值是一个结果集，仅第一行的第一列中的值则返回以 XML 字符串格式。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-113">If the return value is a result set, only the value in the first column of the first row is returned in a XML string format.</span></span>  
  
> [!NOTE]
>  -   <span data-ttu-id="dc9cc-114">ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作不支持用户定义类型 (Udt)。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-114">The ExecuteNonQuery, ExecuteReader, and ExecuteScalar operations are not supported for the User Defined Types (UDTs).</span></span>  
> -   <span data-ttu-id="dc9cc-115">您还可以设置中的 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的应用程序上下文[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-115">You can also set the applications context for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar operations in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="dc9cc-116">它是必需的设置 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的应用程序上下文，如果任何操作针对的是 Oracle E-business Suite （接口表、 接口视图、 并发程序或请求中的项目设置）。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-116">It is mandatory to set the applications context for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar operations if any of the operation is targeted on an artifact in Oracle E-Business Suite (interface table, interface view, concurrent programs or request sets).</span></span> <span data-ttu-id="dc9cc-117">有关应用程序上下文中，以及如何将其设置的信息，请参阅[设置应用程序上下文](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)。</span><span class="sxs-lookup"><span data-stu-id="dc9cc-117">For information about applications context, and how to set it, see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc9cc-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc9cc-118">See Also</span></span>  
 <span data-ttu-id="dc9cc-119">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="dc9cc-119">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>
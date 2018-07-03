---
title: SQLEXECUTE 操作的消息架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQLEXECUTE operations, message schemas for
ms.assetid: 744645f4-0674-44e0-bf8d-8df70086b0f1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f753d2dcbd5782f456b099174e0369e37cca2e6f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981478"
---
# <a name="message-schemas-for-the-sqlexecute-operation"></a><span data-ttu-id="ad6b3-102">SQLEXECUTE 操作的消息架构</span><span class="sxs-lookup"><span data-stu-id="ad6b3-102">Message Schemas for the SQLEXECUTE Operation</span></span>
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="ad6b3-103"> LOB 系统中的项目的强类型元数据的图面，并公开这些项目上的标准操作。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-103"> surfaces strongly-typed metadata for artifacts present in the LOB system and exposes standard operations on these artifacts.</span></span> <span data-ttu-id="ad6b3-104">但是，有一个应用程序需要由应用程序中的业务逻辑驱动的任意 SQL 语句执行的方案。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-104">However, there are scenarios where an application might require the execution of an arbitrary SQL statement that is driven by the business logic in the application.</span></span> <span data-ttu-id="ad6b3-105">例如，您可能希望：</span><span class="sxs-lookup"><span data-stu-id="ad6b3-105">For example, you may want to:</span></span>  
  
- <span data-ttu-id="ad6b3-106">不显示的数据库项目上执行操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; 例如，获取 CURVAL 或 NEXTVAL Oracle 序列。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-106">Perform an operation on database artifacts that are not surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example, get the CURVAL or NEXTVAL of an Oracle SEQUENCE.</span></span>  
  
- <span data-ttu-id="ad6b3-107">执行数据定义语言操作;例如，创建一个表。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-107">Perform Data Definition Language operations; for example, create a table.</span></span>  
  
- <span data-ttu-id="ad6b3-108">如果没有安装在设计时; 一个数据库项目上执行操作例如，更新您的业务逻辑创建一个临时表中的记录。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-108">Perform operations on a database artifact that was not present at design-time; for example, update records in a temporary table that is created by your business logic.</span></span>  
  
- <span data-ttu-id="ad6b3-109">执行更复杂表上显示的操作比的 DML 操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; 对于范例执行包含 JOIN 子句的查询。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-109">Perform more complex DML operations on tables than the operations surfaced by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]; for example perform a query that includes a JOIN clause.</span></span>  
  
  <span data-ttu-id="ad6b3-110">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]显示名为 SQLEXECUTE 操作来支持这种情况下的特殊操作。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-110">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces a special operation called the SQLEXECUTE operation to support such scenarios.</span></span> <span data-ttu-id="ad6b3-111">通过使用此操作，可以指定任意 SQL 语句为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]Oracle 数据库执行。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-111">By using this operation, you can specify an arbitrary SQL statement for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to execute on the Oracle database.</span></span> <span data-ttu-id="ad6b3-112">此外可以指定多个输入参数的 SQL 语句的块。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-112">You can also specify multiple blocks of input parameters to the SQL statement.</span></span> <span data-ttu-id="ad6b3-113">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]执行每组参数一次的 SQL 语句并返回作为泛型 （弱类型化） 记录集的任何输出。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-113">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] executes the SQL statement once for each set of parameters and returns any output as a generic (weakly-typed) record set.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad6b3-114">可以将传递在和中 OUT 参数到过程、 函数和 SQLEXECUTE 操作中的包。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-114">You can pass IN and IN OUT parameters to procedures, functions, and packages in the SQLEXECUTE operation.</span></span> <span data-ttu-id="ad6b3-115">调用的项目将执行与 Oracle 数据库中; 提供的参数但是，SQLEXECUTE 操作不返回输出的值并向客户端在 OUT 参数。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-115">The invoked artifact will execute with the supplied parameters on the Oracle database; however, the SQLEXECUTE operation does not return the value of OUT and IN OUT parameters to the client.</span></span> <span data-ttu-id="ad6b3-116">如果你想要调用过程、 函数或包，Microsoft 建议您这样做的调用专用的操作，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]针对这些 Oracle 项目公开。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-116">If you want to invoke procedures, functions, or packages, Microsoft recommends that you do so by invoking the dedicated operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes for these Oracle artifacts.</span></span>  
  
 <span data-ttu-id="ad6b3-117">以下 XML 显示了 SQLEXECUTE 操作的结构：</span><span class="sxs-lookup"><span data-stu-id="ad6b3-117">The following XML shows the structure of the SQLEXECUTE operation:</span></span>  
  
```  
<SQLEXECUTE xmlns="SQLEXECUTE">  
  <SQLSTATEMENT> [STATEMENT] </SQLSTATEMENT>  
  <PARAMETERSCHEMA>[PARAM_SPEC]</PARAMETERSCHEMA>  
  <PARAMETERSET>  
    <PARAMETERDATA>  
      <PARAMETER xmlns:c="http://schemas.microsoft.com/2003/10/Serialization/Arrays">  
        <c:string>[PARAM_VAL_1]</c:string>  
      </PARAMETER>  
    </PARAMETERDATA>  
    …  
  </PARAMETERSET>  
</SQLEXECUTE>  
```  
  
 <span data-ttu-id="ad6b3-118">[语句] = 的 SQL 语句来执行;例如，"选择 \* 从 emp WHERE empno =: emp_no"。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-118">[STATEMENT] = The SQL statement to execute; for example, "SELECT \* from emp WHERE empno=:emp_no".</span></span>  
  
 <span data-ttu-id="ad6b3-119">[PARAM_SPEC] = SQL 语句和其数据类型; 中的 IN 参数的列表例如，"emp_no 数"。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-119">[PARAM_SPEC] = The list of the IN parameters in the SQL statement and their data types; for example, "emp_no NUMBER".</span></span>  
  
 <span data-ttu-id="ad6b3-120">[PARAM_VAL_1] = 第一个参数的值。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-120">[PARAM_VAL_1] = The value of the first parameter.</span></span>  
  
 <span data-ttu-id="ad6b3-121">每个\<PARAMETERDATA\>部分包含一组完整的\<参数\>相匹配的架构中的元素\<PARAMETERSCHEMA\>部分。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-121">Each \<PARAMETERDATA\> section contains a complete set of \<PARAMETER\> elements that match the schema in the \<PARAMETERSCHEMA\> section.</span></span> <span data-ttu-id="ad6b3-122">\<PARAMETERSET\>可以包含多个\<PARAMETERDATA\>部分。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-122">The \<PARAMETERSET\> can contain multiple \<PARAMETERDATA\> sections.</span></span> <span data-ttu-id="ad6b3-123">如果这种情况，SQL 语句执行多次，一次针对每个参数集。</span><span class="sxs-lookup"><span data-stu-id="ad6b3-123">If this is the case, the SQL statement is executed multiple times, once against each parameter set.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad6b3-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad6b3-124">See Also</span></span>  
 [<span data-ttu-id="ad6b3-125">Oracle 数据库的 BizTalk 适配器的消息和消息架构</span><span class="sxs-lookup"><span data-stu-id="ad6b3-125">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
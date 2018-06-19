---
title: REF CURSOR 的消息架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- REF CURSORS, message schemas for
- IN REF CURSOR
- OUT REF CURSOR
- IN OUT REF CURSOR
ms.assetid: b62e7a9f-278c-41b3-90f0-2f621a34327b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bddfde0b0897c7d8c21a20126d2fa1d2f0f8c78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214757"
---
# <a name="message-schemas-for-ref-cursors"></a><span data-ttu-id="841a2-102">REF CURSOR 的消息架构</span><span class="sxs-lookup"><span data-stu-id="841a2-102">Message Schemas for REF CURSORS</span></span>
<span data-ttu-id="841a2-103">REF CURSOR 是 Oracle PL/SQL 数据类型对结果集的 Oracle 数据库中表示的指针。</span><span class="sxs-lookup"><span data-stu-id="841a2-103">A REF CURSOR is an Oracle PL/SQL data type that represents a pointer to a result set in the Oracle database.</span></span> <span data-ttu-id="841a2-104">REF CURSOR 类型启用输入和输出流的数据以及适合传输大量数据传入和传出的 PL/SQL 代码块。</span><span class="sxs-lookup"><span data-stu-id="841a2-104">REF CURSOR types enable input and output streaming of data and are ideal for transferring large amounts of data to and from a PL/SQL code block.</span></span> [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]<span data-ttu-id="841a2-105">提供对缩小将强类型和弱类型 REF CURSOR 参数传递给 PL/SQL 过程和函数中，和 IN OUT 参数的支持。</span><span class="sxs-lookup"><span data-stu-id="841a2-105"> provides support for passing strongly-typed and weakly-typed REF CURSOR parameters to PL/SQL procedures and functions as IN, OUT and IN OUT parameters.</span></span>  
  
 <span data-ttu-id="841a2-106">在 Oracle 数据库中，REF CURSOR 类型可以是强类型或弱类型：</span><span class="sxs-lookup"><span data-stu-id="841a2-106">In the Oracle database, a REF CURSOR type can be either strongly-typed or weakly-typed:</span></span>  
  
-   <span data-ttu-id="841a2-107">使用 RETURN 子句中声明强类型化的 REF CURSOR `TYPE StrongCurType IS REF CURSOR RETURN emp%ROWTYPE;`。</span><span class="sxs-lookup"><span data-stu-id="841a2-107">A strongly-typed REF CURSOR is declared with a RETURN clause as in `TYPE StrongCurType IS REF CURSOR RETURN emp%ROWTYPE;`.</span></span> <span data-ttu-id="841a2-108">强类型化的 REF CURSOR 变量只能表示包含数据与其声明其 REF CURSOR 类型的类型相匹配的结果集。</span><span class="sxs-lookup"><span data-stu-id="841a2-108">A strongly-typed REF CURSOR variable can only represent a result set that contains data that matches the type with which its REF CURSOR type is declared.</span></span> <span data-ttu-id="841a2-109">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]返回强类型的结果集为强类型化的 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="841a2-109">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] returns a strongly-typed result set for a strongly-typed REF CURSOR.</span></span>  
  
-   <span data-ttu-id="841a2-110">弱类型化的 REF CURSOR 声明没有返回作为 in 子句`TYPE WeakCurType IS REF CURSOR;`。</span><span class="sxs-lookup"><span data-stu-id="841a2-110">A weakly-typed REF CURSOR is declared without a RETURN clause as in `TYPE WeakCurType IS REF CURSOR;`.</span></span> <span data-ttu-id="841a2-111">Oracle 还提供了一种特殊的 REF CURSOR 类型，调用 SYS_REFCURSOR 可用来声明弱类型 REF CURSOR 变量。</span><span class="sxs-lookup"><span data-stu-id="841a2-111">Oracle also provides a special REF CURSOR type called SYS_REFCURSOR that can be used to declare weakly-typed REF CURSOR variables.</span></span> <span data-ttu-id="841a2-112">弱类型 REF CURSOR 变量可以表示包含任何类型的行数据的结果集。</span><span class="sxs-lookup"><span data-stu-id="841a2-112">Weakly-typed REF CURSOR variables can represent a result set that contains any kind of row data.</span></span> <span data-ttu-id="841a2-113">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]为弱类型化的 REF CURSOR 返回的泛型记录弱类型化结果集。</span><span class="sxs-lookup"><span data-stu-id="841a2-113">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] returns a weakly-typed result set of generic records for a weakly-typed REF CURSOR.</span></span>  
  
## <a name="in-ref-cursor-parameters"></a><span data-ttu-id="841a2-114">在 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="841a2-114">IN REF CURSOR Parameters</span></span>  
 <span data-ttu-id="841a2-115">没有 ODP.NET API 创建 REF CURSOR 在 Oracle 服务器上，因此[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]无法提供客户端程序来创建和维护 REF CURSOR 变量的功能。</span><span class="sxs-lookup"><span data-stu-id="841a2-115">There is no ODP.NET API to create a REF CURSOR on the Oracle server, so the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] cannot provide the capability for a client program to create and maintain REF CURSOR variables.</span></span>  
  
 <span data-ttu-id="841a2-116">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ，但是，让客户端将在 REF CURSOR 参数传递给函数或存储的过程，通过指定的返回 REF CURSOR 的 PL/SQL 代码块。</span><span class="sxs-lookup"><span data-stu-id="841a2-116">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does, however, enable a client to pass IN REF CURSOR parameters to functions or stored procedures by specifying a block of PL/SQL code that returns a REF CURSOR.</span></span> <span data-ttu-id="841a2-117">适配器使用此代码来创建并打开在 Oracle 服务器; 上的 REF CURSOR 变量然后，它将调用函数或存储过程使用此变量作为 IN 参数。</span><span class="sxs-lookup"><span data-stu-id="841a2-117">The adapter uses this code to create and OPEN a REF CURSOR variable on the Oracle server; it then calls the function or stored procedure using this variable as the IN parameter.</span></span>  
  
 <span data-ttu-id="841a2-118">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表示 IN REF CURSOR 参数为包含 PL/SQL 代码块的字符串。</span><span class="sxs-lookup"><span data-stu-id="841a2-118">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents IN REF CURSOR parameters as strings that contain the PL/SQL code block.</span></span> <span data-ttu-id="841a2-119">在此块中，用问号 （？） 指定 REF CURSOR 的位置。</span><span class="sxs-lookup"><span data-stu-id="841a2-119">Within this block, the location of the REF CURSOR is specified with a question mark (?).</span></span> <span data-ttu-id="841a2-120">PL/SQL 代码块可以包含包含 SQL 查询; 打开 FOR 语句也可以包含一个函数或过程调用中的 OUT 参数中返回打开的 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="841a2-120">The PL/SQL code block can contain an OPEN-FOR statement that contains a SQL query; or it can contain a function or procedure call in which an opened REF CURSOR is returned in an OUT parameter.</span></span>  
  
 <span data-ttu-id="841a2-121">下面演示如何通过调用存储的过程或函数，以打开 REF CURSOR 中指定 IN REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="841a2-121">The following shows how to specify an IN REF CURSOR by calling a stored procedure or function to open the REF CURSOR.</span></span>  
  
```  
<[IN_REF_CURSOR_PARAM_NAME]>begin [SP_NAME]([SP_PARAMS...], ?, [SP_PARAMS...]); end;</[IN_REF_CURSOR_PARAM_NAME]>  
  
Example:  
<EMP_RC>begin GETEMP(1, ?); end; </EMP_RC>  
```  
  
 <span data-ttu-id="841a2-122">下面演示如何通过使用 SELECT 查询以打开 REF CURSOR 中指定 IN REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="841a2-122">The following shows how to specify an IN REF CURSOR by using a SELECT query to open the REF CURSOR.</span></span>  
  
```  
<IN_REF_CURSOR_PARAM_NAME>begin open ? for select [FIELD_NAMES] from [TABLE_NAME]; end;</IN_REF_CURSOR_PARAM_NAME>  
  
Example:  
<EMP_RC>begin open ? for select * from EMP; end;</EMP_RC>  
```  
  
## <a name="out-ref-cursor-parameters"></a><span data-ttu-id="841a2-123">OUT REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="841a2-123">OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="841a2-124">出 REF CURSOR 参数将返回为强类型或弱类型化结果集。</span><span class="sxs-lookup"><span data-stu-id="841a2-124">OUT REF CURSOR parameters are returned as either strongly-typed or weakly-typed result sets.</span></span> <span data-ttu-id="841a2-125">返回的结果集的类型取决于是否 REF CURSOR 参数声明为存储过程或函数定义中的强类型或弱类型化的 REF CURSOR 在 Oracle 服务器上。</span><span class="sxs-lookup"><span data-stu-id="841a2-125">The type of the result set returned depends on whether the REF CURSOR parameter is declared as a strongly-typed or weakly-typed REF CURSOR in the stored procedure or function definition on the Oracle server.</span></span> <span data-ttu-id="841a2-126">强类型化结果集返回强类型化的 REF CURSOR 参数和弱类型化结果集返回弱类型 REF CURSOR 参数 （例如，参数与 SYS_REFCURSOR 类型声明）。</span><span class="sxs-lookup"><span data-stu-id="841a2-126">A strongly-typed result set is returned for strongly-typed REF CURSOR parameters and a weakly-typed result set is returned for weakly-typed REF CURSOR parameters (for example, parameters declared with a SYS_REFCURSOR type).</span></span>  
  
 <span data-ttu-id="841a2-127">下面显示了强类型出 REF CURSOR 参数的 XML。</span><span class="sxs-lookup"><span data-stu-id="841a2-127">The following shows the XML for a strongly-typed OUT REF CURSOR parameter.</span></span>  
  
```  
<[PARAM_NAME]>  
 <[PARAM_NAME]RECORD>  
  <[COL1_NAME]>value1</[COL1_NAME]>  
  <[COL2_NAME]>value2</[COL2_NAME]>  
  ...  
 </[PARAM_NAME]RECORD>  
</[PARAM_NAME]>  
  
[PARAM_NAME] = OUT REF CURSOR parameter name; for example, EMP_REFCURSOR  
[COL_NAME] = Name of a column in the REF CURSOR type; for example, Name.  
```  
  
 <span data-ttu-id="841a2-128">下图显示弱类型出 REF CURSOR 参数的 XML。</span><span class="sxs-lookup"><span data-stu-id="841a2-128">The following shows the XML for a weakly-typed OUT REF CURSOR parameter.</span></span>  
  
```  
<[PARAM_NAME]>  
 <GenRecordRow xmlns="oracledb">  
  <GenRecordColumn>  
   <ColumnName>COL_NAME</ColumnName>  
   <ColumnValue>COL_VALUE</ColumnValue>  
   <ColumnType>COL_TYPE</ColumnType>  
  </GenRecordColumn>  
  …  
 </GenRecordRow>  
 …  
</[PARAM_NAME]>  
  
[COL_NAME] = Name of column; for example, Name  
[COL_VALUE] = Column value; for example, Scott  
[COL_TYPE] = Column data type; for example, System.String  
```  
  
## <a name="in-out-ref-cursor-parameters"></a><span data-ttu-id="841a2-129">IN 出 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="841a2-129">IN OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="841a2-130">因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]模型在 REF CURSOR 参数作为字符串，并为复杂类型的出 REF CURSOR 参数，它不能在出 REF CURSOR 参数支持单一类型。</span><span class="sxs-lookup"><span data-stu-id="841a2-130">Because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] models IN REF CURSOR parameters as strings and OUT REF CURSOR parameters as complex types, it cannot support a single type for an IN OUT REF CURSOR parameter.</span></span> <span data-ttu-id="841a2-131">为此，它将在出 REF CURSOR 参数视为两个不同的参数： 请求消息和响应消息中的 OUT 参数中的 IN 参数。</span><span class="sxs-lookup"><span data-stu-id="841a2-131">For this reason, it treats IN OUT REF CURSOR parameters as two different parameters: an IN parameter in the request message and an OUT parameter in the response message.</span></span>  
  
 <span data-ttu-id="841a2-132">若要避免在服务模型编程中，名称冲突[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将字符串"_IN"附加到请求消息中的 IN 参数，这样，为给定的参数名为 [PARAM_NAME]，创建两个参数：</span><span class="sxs-lookup"><span data-stu-id="841a2-132">To avoid a name conflict in service model programming, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] appends the string "_IN" to the IN parameter in the request message so that for a given parameter named [PARAM_NAME], two parameters are created:</span></span>  
  
-   <span data-ttu-id="841a2-133">[PARAM_NAME] _IN 中的存储的过程或函数的请求消息是一个在 REF CURSOR 参数。</span><span class="sxs-lookup"><span data-stu-id="841a2-133">[PARAM_NAME]_IN is an IN REF CURSOR parameter in the stored procedure or function request message.</span></span> <span data-ttu-id="841a2-134">它包含返回 REF CURSOR 的 PL/SQL 语句 （select 查询或存储的过程或函数调用）。</span><span class="sxs-lookup"><span data-stu-id="841a2-134">It contains a PL/SQL statement (either a select query or a stored procedure or function call) that returns a REF CURSOR.</span></span>  
  
-   <span data-ttu-id="841a2-135">[PARAM_NAME] 中的存储的过程或函数响应消息是一个 OUT REF CURSOR 参数。</span><span class="sxs-lookup"><span data-stu-id="841a2-135">[PARAM_NAME] is an OUT REF CURSOR parameter in the stored procedure or function response message.</span></span> <span data-ttu-id="841a2-136">它包含出 REF CURSOR 作为强类型或弱类型化结果集。</span><span class="sxs-lookup"><span data-stu-id="841a2-136">It contains the OUT REF CURSOR as a strongly-typed or weakly-typed result set.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="841a2-137">适配器不能支持的过程或包含一个名为 [PARAM_NAME] _IN 和名为 [PARAM_NAME] IN 出 REF CURSOR 参数的 IN 参数的函数。</span><span class="sxs-lookup"><span data-stu-id="841a2-137">The adapter cannot support a procedure or function that contains an IN parameter named [PARAM_NAME]_IN and an IN OUT REF CURSOR parameter named [PARAM_NAME].</span></span> <span data-ttu-id="841a2-138">这是因为该适配器需要一个名为 [PARAM_NAME] _IN 来表示对 REF CURSOR 参数的输入参数并且不能在请求消息中指定这两个参数。</span><span class="sxs-lookup"><span data-stu-id="841a2-138">This is because the adapter expects a parameter named [PARAM_NAME]_IN to represent the input to the REF CURSOR parameter, and you cannot specify both parameters in the request message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="841a2-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="841a2-139">See Also</span></span>  
 [<span data-ttu-id="841a2-140">消息和用于 Oracle 数据库的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="841a2-140">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
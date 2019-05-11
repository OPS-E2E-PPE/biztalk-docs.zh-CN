---
title: REF CURSOR 的消息架构 |Microsoft Docs
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
ms.openlocfilehash: 23139cb3c335418af677e666359a5fcd862067a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376440"
---
# <a name="message-schemas-for-ref-cursors"></a><span data-ttu-id="e1696-102">REF CURSOR 的消息架构</span><span class="sxs-lookup"><span data-stu-id="e1696-102">Message Schemas for REF CURSORS</span></span>
<span data-ttu-id="e1696-103">REF CURSOR 是 Oracle PL/SQL 数据类型对结果集的 Oracle 数据库中表示的指针。</span><span class="sxs-lookup"><span data-stu-id="e1696-103">A REF CURSOR is an Oracle PL/SQL data type that represents a pointer to a result set in the Oracle database.</span></span> <span data-ttu-id="e1696-104">REF CURSOR 类型启用输入和输出流的数据非常适合用于传输大量数据传入和传出 PL/SQL 代码块。</span><span class="sxs-lookup"><span data-stu-id="e1696-104">REF CURSOR types enable input and output streaming of data and are ideal for transferring large amounts of data to and from a PL/SQL code block.</span></span> [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] <span data-ttu-id="e1696-105">为出将强类型化和弱类型化 REF CURSOR 参数传递给 PL/SQL 过程和函数中，并在 OUT 参数提供支持。</span><span class="sxs-lookup"><span data-stu-id="e1696-105">provides support for passing strongly-typed and weakly-typed REF CURSOR parameters to PL/SQL procedures and functions as IN, OUT and IN OUT parameters.</span></span>  
  
 <span data-ttu-id="e1696-106">在 Oracle 数据库中，REF CURSOR 类型可以是强类型化或弱类型：</span><span class="sxs-lookup"><span data-stu-id="e1696-106">In the Oracle database, a REF CURSOR type can be either strongly-typed or weakly-typed:</span></span>  
  
- <span data-ttu-id="e1696-107">使用作为中的 RETURN 子句声明强类型化 REF CURSOR `TYPE StrongCurType IS REF CURSOR RETURN emp%ROWTYPE;`。</span><span class="sxs-lookup"><span data-stu-id="e1696-107">A strongly-typed REF CURSOR is declared with a RETURN clause as in `TYPE StrongCurType IS REF CURSOR RETURN emp%ROWTYPE;`.</span></span> <span data-ttu-id="e1696-108">强类型化的 REF CURSOR 变量可以仅表示包含数据类型与其声明它的 REF CURSOR 类型相匹配的结果集。</span><span class="sxs-lookup"><span data-stu-id="e1696-108">A strongly-typed REF CURSOR variable can only represent a result set that contains data that matches the type with which its REF CURSOR type is declared.</span></span> <span data-ttu-id="e1696-109">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]返回强类型化结果集的强类型化 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="e1696-109">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] returns a strongly-typed result set for a strongly-typed REF CURSOR.</span></span>  
  
- <span data-ttu-id="e1696-110">弱类型化 REF 游标未声明为中的 RETURN 子句`TYPE WeakCurType IS REF CURSOR;`。</span><span class="sxs-lookup"><span data-stu-id="e1696-110">A weakly-typed REF CURSOR is declared without a RETURN clause as in `TYPE WeakCurType IS REF CURSOR;`.</span></span> <span data-ttu-id="e1696-111">Oracle 还提供了一种特殊的 REF CURSOR 类型称为可用于声明弱类型化的 REF CURSOR 变量的 SYS_REFCURSOR。</span><span class="sxs-lookup"><span data-stu-id="e1696-111">Oracle also provides a special REF CURSOR type called SYS_REFCURSOR that can be used to declare weakly-typed REF CURSOR variables.</span></span> <span data-ttu-id="e1696-112">弱类型化的 REF CURSOR 变量可以表示包含任何类型的行数据的结果集。</span><span class="sxs-lookup"><span data-stu-id="e1696-112">Weakly-typed REF CURSOR variables can represent a result set that contains any kind of row data.</span></span> <span data-ttu-id="e1696-113">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]为弱类型化 REF CURSOR 返回弱类型化结果集的通用记录。</span><span class="sxs-lookup"><span data-stu-id="e1696-113">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] returns a weakly-typed result set of generic records for a weakly-typed REF CURSOR.</span></span>  
  
## <a name="in-ref-cursor-parameters"></a><span data-ttu-id="e1696-114">中的 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="e1696-114">IN REF CURSOR Parameters</span></span>  
 <span data-ttu-id="e1696-115">没有 ODP.NET API 创建 REF CURSOR 的 Oracle 服务器上，因此[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不能提供的功能，可以创建和维护 REF CURSOR 变量的客户端程序。</span><span class="sxs-lookup"><span data-stu-id="e1696-115">There is no ODP.NET API to create a REF CURSOR on the Oracle server, so the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] cannot provide the capability for a client program to create and maintain REF CURSOR variables.</span></span>  
  
 <span data-ttu-id="e1696-116">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ，但是，启用客户端将在 REF CURSOR 参数传递给函数或存储的过程，通过指定返回 REF CURSOR 的 PL/SQL 代码块。</span><span class="sxs-lookup"><span data-stu-id="e1696-116">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does, however, enable a client to pass IN REF CURSOR parameters to functions or stored procedures by specifying a block of PL/SQL code that returns a REF CURSOR.</span></span> <span data-ttu-id="e1696-117">适配器使用此代码以创建并打开 Oracle 服务器; 上的 REF CURSOR 变量然后，它将调用该函数或存储过程中使用此变量作为 IN 参数。</span><span class="sxs-lookup"><span data-stu-id="e1696-117">The adapter uses this code to create and OPEN a REF CURSOR variable on the Oracle server; it then calls the function or stored procedure using this variable as the IN parameter.</span></span>  
  
 <span data-ttu-id="e1696-118">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] IN REF CURSOR 参数表示为包含 PL/SQL 代码块的字符串。</span><span class="sxs-lookup"><span data-stu-id="e1696-118">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] represents IN REF CURSOR parameters as strings that contain the PL/SQL code block.</span></span> <span data-ttu-id="e1696-119">在此块中，用问号 （？） 指定 REF CURSOR 的位置。</span><span class="sxs-lookup"><span data-stu-id="e1696-119">Within this block, the location of the REF CURSOR is specified with a question mark (?).</span></span> <span data-ttu-id="e1696-120">PL/SQL 代码块可以包含包含 SQL 查询; 打开 FOR 语句也可以包含函数或过程调用中的 OUT 参数中返回打开的 REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="e1696-120">The PL/SQL code block can contain an OPEN-FOR statement that contains a SQL query; or it can contain a function or procedure call in which an opened REF CURSOR is returned in an OUT parameter.</span></span>  
  
 <span data-ttu-id="e1696-121">下面演示了如何通过调用存储的过程或函数，以打开 REF CURSOR 指定 IN REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="e1696-121">The following shows how to specify an IN REF CURSOR by calling a stored procedure or function to open the REF CURSOR.</span></span>  
  
```  
<[IN_REF_CURSOR_PARAM_NAME]>begin [SP_NAME]([SP_PARAMS...], ?, [SP_PARAMS...]); end;</[IN_REF_CURSOR_PARAM_NAME]>  
  
Example:  
<EMP_RC>begin GETEMP(1, ?); end; </EMP_RC>  
```  
  
 <span data-ttu-id="e1696-122">下面演示了如何使用 SELECT 查询以打开 REF CURSOR 指定 IN REF CURSOR。</span><span class="sxs-lookup"><span data-stu-id="e1696-122">The following shows how to specify an IN REF CURSOR by using a SELECT query to open the REF CURSOR.</span></span>  
  
```  
<IN_REF_CURSOR_PARAM_NAME>begin open ? for select [FIELD_NAMES] from [TABLE_NAME]; end;</IN_REF_CURSOR_PARAM_NAME>  
  
Example:  
<EMP_RC>begin open ? for select * from EMP; end;</EMP_RC>  
```  
  
## <a name="out-ref-cursor-parameters"></a><span data-ttu-id="e1696-123">扩展的 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="e1696-123">OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="e1696-124">出 REF CURSOR 参数返回为强类型化或弱类型化结果集。</span><span class="sxs-lookup"><span data-stu-id="e1696-124">OUT REF CURSOR parameters are returned as either strongly-typed or weakly-typed result sets.</span></span> <span data-ttu-id="e1696-125">返回的结果集的类型取决于是否 REF CURSOR 参数被声明为存储过程或函数定义中的强类型化或弱类型化的 REF CURSOR 在 Oracle 服务器上。</span><span class="sxs-lookup"><span data-stu-id="e1696-125">The type of the result set returned depends on whether the REF CURSOR parameter is declared as a strongly-typed or weakly-typed REF CURSOR in the stored procedure or function definition on the Oracle server.</span></span> <span data-ttu-id="e1696-126">强类型化结果集返回强类型化 REF CURSOR 参数的和为弱类型化 REF CURSOR 参数返回弱类型化结果集 （例如，参数以 SYS_REFCURSOR 类型声明）。</span><span class="sxs-lookup"><span data-stu-id="e1696-126">A strongly-typed result set is returned for strongly-typed REF CURSOR parameters and a weakly-typed result set is returned for weakly-typed REF CURSOR parameters (for example, parameters declared with a SYS_REFCURSOR type).</span></span>  
  
 <span data-ttu-id="e1696-127">下面显示了强类型化 OUT REF CURSOR 参数的 XML。</span><span class="sxs-lookup"><span data-stu-id="e1696-127">The following shows the XML for a strongly-typed OUT REF CURSOR parameter.</span></span>  
  
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
  
 <span data-ttu-id="e1696-128">下面显示了弱类型化 OUT REF CURSOR 参数的 XML。</span><span class="sxs-lookup"><span data-stu-id="e1696-128">The following shows the XML for a weakly-typed OUT REF CURSOR parameter.</span></span>  
  
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
  
## <a name="in-out-ref-cursor-parameters"></a><span data-ttu-id="e1696-129">在扩展的 REF CURSOR 参数</span><span class="sxs-lookup"><span data-stu-id="e1696-129">IN OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="e1696-130">因为[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]模型在 REF CURSOR 参数作为字符串，并为复杂类型的 OUT REF CURSOR 参数，它不能在 OUT REF CURSOR 参数支持一种类型。</span><span class="sxs-lookup"><span data-stu-id="e1696-130">Because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] models IN REF CURSOR parameters as strings and OUT REF CURSOR parameters as complex types, it cannot support a single type for an IN OUT REF CURSOR parameter.</span></span> <span data-ttu-id="e1696-131">出于此原因，它将 IN 出 REF CURSOR 参数视为两个不同的参数： IN 参数在请求消息和响应消息中的一个输出参数。</span><span class="sxs-lookup"><span data-stu-id="e1696-131">For this reason, it treats IN OUT REF CURSOR parameters as two different parameters: an IN parameter in the request message and an OUT parameter in the response message.</span></span>  
  
 <span data-ttu-id="e1696-132">若要避免在服务模型编程中，名称冲突[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将字符串"_IN"追加到请求消息中的 IN 参数，因此，对于给定的参数名为 [PARAM_NAME]，创建两个参数：</span><span class="sxs-lookup"><span data-stu-id="e1696-132">To avoid a name conflict in service model programming, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] appends the string "_IN" to the IN parameter in the request message so that for a given parameter named [PARAM_NAME], two parameters are created:</span></span>  
  
-   <span data-ttu-id="e1696-133">[PARAM_NAME] _IN 存储的过程或函数请求消息中是一个在 REF CURSOR 参数。</span><span class="sxs-lookup"><span data-stu-id="e1696-133">[PARAM_NAME]_IN is an IN REF CURSOR parameter in the stored procedure or function request message.</span></span> <span data-ttu-id="e1696-134">它包含返回 REF CURSOR 的 PL/SQL 语句 （select 查询或存储的过程或函数调用）。</span><span class="sxs-lookup"><span data-stu-id="e1696-134">It contains a PL/SQL statement (either a select query or a stored procedure or function call) that returns a REF CURSOR.</span></span>  
  
-   <span data-ttu-id="e1696-135">[PARAM_NAME] 存储的过程或函数响应消息中是一个 OUT REF CURSOR 参数。</span><span class="sxs-lookup"><span data-stu-id="e1696-135">[PARAM_NAME] is an OUT REF CURSOR parameter in the stored procedure or function response message.</span></span> <span data-ttu-id="e1696-136">它包含出 REF CURSOR 作为强类型化或弱类型化结果集。</span><span class="sxs-lookup"><span data-stu-id="e1696-136">It contains the OUT REF CURSOR as a strongly-typed or weakly-typed result set.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e1696-137">该适配器不能支持的过程或包含 IN 参数名为 [PARAM_NAME] _IN 和名为 [PARAM_NAME] 的 IN 出 REF CURSOR 参数的函数。</span><span class="sxs-lookup"><span data-stu-id="e1696-137">The adapter cannot support a procedure or function that contains an IN parameter named [PARAM_NAME]_IN and an IN OUT REF CURSOR parameter named [PARAM_NAME].</span></span> <span data-ttu-id="e1696-138">这是因为该适配器需要一个名为 [PARAM_NAME] _IN 来表示 REF CURSOR 参数的输入参数并不能在请求消息中指定这两个参数。</span><span class="sxs-lookup"><span data-stu-id="e1696-138">This is because the adapter expects a parameter named [PARAM_NAME]_IN to represent the input to the REF CURSOR parameter, and you cannot specify both parameters in the request message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1696-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1696-139">See Also</span></span>  
 [<span data-ttu-id="e1696-140">Oracle 数据库的 BizTalk 适配器的消息和消息架构</span><span class="sxs-lookup"><span data-stu-id="e1696-140">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)
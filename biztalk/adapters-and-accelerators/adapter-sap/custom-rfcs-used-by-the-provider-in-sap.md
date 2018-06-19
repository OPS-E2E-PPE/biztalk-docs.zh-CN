---
title: SAP 中提供程序所使用的自定义 Rfc |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Z_EXTRACT_DATA_OO, limitations related to
- RFC, Z_EXTRACT_DATA_OO
- Z_EXTRACT_DATA_OO
- Z_EXTRACT_DATA_OO, best practice
- Z_EXTRACT_DATA_OO, security issue
ms.assetid: 95661f4c-0431-40ca-8a53-3fbe359b8afd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e55473dbcfeebecc504906d569c129989b054211
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216837"
---
# <a name="custom-rfcs-used-by-the-provider-in-sap"></a><span data-ttu-id="1dfcb-102">SAP 中提供程序所使用的自定义 Rfc</span><span class="sxs-lookup"><span data-stu-id="1dfcb-102">Custom RFCs Used by the Provider in SAP</span></span>
<span data-ttu-id="1dfcb-103">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]提供它在内部使用 SAP 系统上执行操作的以下自定义 Rfc。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-103">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] provides the following custom RFCs that it internally uses to perform operations on the SAP system.</span></span>  
  
-   <span data-ttu-id="1dfcb-104">**Z_EXTRACT_DATA_OO RFC**。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-104">**Z_EXTRACT_DATA_OO RFC**.</span></span> <span data-ttu-id="1dfcb-105">数据提取 RFC，Z_EXTRACT_DATA_OO，从表中提取数据或视图中 SAP / 3 系统、 将转换数据，并返回以同步方式中的 SQL Server 表的数据或转储的平面文件数据。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-105">The data extraction RFC, Z_EXTRACT_DATA_OO, extracts data from tables or views in the SAP R/3 system, converts the data, and either returns the data synchronously in a SQL Server table or dumps data to a flat file.</span></span> <span data-ttu-id="1dfcb-106">Z_EXTRACT_DATA_OO 用于执行与 WHERE 子句的选择操作。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-106">The Z_EXTRACT_DATA_OO is used to perform SELECT operation with WHERE clauses.</span></span> <span data-ttu-id="1dfcb-107">此 RFC 的性能是依赖于您的 SAP 系统硬件。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-107">The performance of this RFC is dependent on your SAP system hardware.</span></span>  
  
     <span data-ttu-id="1dfcb-108">有关如何为 Z_EXTRACT_DATA_OO RFC 映射的.NET 和 SAP 数据类型的信息，请参阅[Data Type Mapping for 自定义 Rfc](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-108">For information on how the .NET and SAP data types are mapped for Z_EXTRACT_DATA_OO RFC, see [Data Type Mapping for Custom RFCs](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md).</span></span>  
  
-   <span data-ttu-id="1dfcb-109">**Z_EXECUTE_SAP_QUERY RFC**。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-109">**Z_EXECUTE_SAP_QUERY RFC**.</span></span> <span data-ttu-id="1dfcb-110">使用此 RFC[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]执行已在 SAP 系统中定义的查询。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-110">This RFC is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] to execute queries that are already defined in the SAP system.</span></span> <span data-ttu-id="1dfcb-111">此 RFC 内部执行 SAP RFC，RSAQ_REMOTE_QUERY_CALL。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-111">This RFC internally executes the SAP RFC, RSAQ_REMOTE_QUERY_CALL.</span></span> <span data-ttu-id="1dfcb-112">SAP 查询都是通过选择表、 列、 输入的参数，结果集等的排序顺序中使用 SAP GUI 以图形方式创建的查询。使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]您现在可以从 ADO.NET 客户端执行此类 SAP 查询。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-112">SAP queries are queries that are graphically created using the SAP GUI by selecting the tables, columns, input parameters, sort order of the result set, etc. Using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] you can now execute such SAP queries from an ADO.NET client.</span></span>  
  
     <span data-ttu-id="1dfcb-113">EXECQUERY 操作返回的所有值都是字符串类型。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-113">All values returned by the EXECQUERY operation are of string type.</span></span>  
  
## <a name="limitations-related-to-the-zextractdataoo-rfc"></a><span data-ttu-id="1dfcb-114">与 Z_EXTRACT_DATA_OO RFC 相关的限制</span><span class="sxs-lookup"><span data-stu-id="1dfcb-114">Limitations Related to the Z_EXTRACT_DATA_OO RFC</span></span>  
  
-   <span data-ttu-id="1dfcb-115">Z_EXTRACT_DATA_OO RFC 支持满足以下条件的表中读取数据：</span><span class="sxs-lookup"><span data-stu-id="1dfcb-115">The Z_EXTRACT_DATA_OO RFC supports reading data from tables that satisfy the following conditions:</span></span>  
  
    -   <span data-ttu-id="1dfcb-116">为表的 TabClass 是 TRANSP、 群集或池。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-116">TabClass for the table is TRANSP, CUSTER, or POOL.</span></span>  
  
    -   <span data-ttu-id="1dfcb-117">TabClass 是视图且 ViewClass 是 D 或 P.</span><span class="sxs-lookup"><span data-stu-id="1dfcb-117">TabClass is VIEW and ViewClass is either D or P.</span></span>  
  
-   <span data-ttu-id="1dfcb-118">Z_EXTRACT_DATA_OO 不支持 HR 群集表，例如 PCL1、 PCL2、 PCL3、 PCL4、 PCL5。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-118">Z_EXTRACT_DATA_OO does not support HR cluster tables, for example PCL1, PCL2, PCL3, PCL4, PCL5.</span></span>  
  
-   <span data-ttu-id="1dfcb-119">可以通过 Z_EXTRACT_DATA_OO 提取的行数取决于 SAP 服务器上的硬件资源。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-119">The number of rows that can be extracted by Z_EXTRACT_DATA_OO depends on the hardware resources on the SAP server.</span></span>  
  
-   <span data-ttu-id="1dfcb-120">中的主键的顺序返回所有提取的数据。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-120">All extracted data is returned in order of the primary keys.</span></span>  
  
-   <span data-ttu-id="1dfcb-121">不支持表或视图包含字符串、 SSTRING 和 RAWSTRING 的可变长度数据类型。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-121">Tables or views containing the variable-length data types STRING, SSTRING and RAWSTRING are not supported.</span></span> <span data-ttu-id="1dfcb-122">无法提取表或视图包含这些数据类型。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-122">Tables or views containing these data types cannot be extracted.</span></span>  
  
-   <span data-ttu-id="1dfcb-123">Z_EXTRACT_DATA_OO 上已分配给他们的转换退出的所有字段运行转换退出。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-123">Z_EXTRACT_DATA_OO runs conversion exits on all fields that have conversion exits assigned to them.</span></span> <span data-ttu-id="1dfcb-124">SELECT 语句的 WHERE 子句中，必须输入生成转换后的值。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-124">The resulting converted values must be entered in the WHERE clause of a SELECT statement.</span></span> <span data-ttu-id="1dfcb-125">转换后的值也会返回。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-125">Converted values are also returned.</span></span> <span data-ttu-id="1dfcb-126">这可能会导致 Z_EXTRACT_DATA_OO 返回的结果和 SAP 数据浏览器 (SE16) 中返回的结果之间的不一致。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-126">This might cause inconsistencies between the results returned by Z_EXTRACT_DATA_OO and the results returned in the SAP data browser (SE16).</span></span>  
  
-   <span data-ttu-id="1dfcb-127">所选的表不能包含是 ABAP （例如，连接） 中的保留的名称的字段名称。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-127">Selected tables cannot contain field names that are reserved names in ABAP (for example, CONNECTION).</span></span>  
  
-   <span data-ttu-id="1dfcb-128">由于 SAP / 3，版本 4.6 C 中，为整数类型的字段的值中的查询处理器中存在的限制 INT4 必须大于或等于-999999999 WHERE 子句中。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-128">Due to a limitation in the query processor in SAP R/3 version 4.6C, values for integer fields of type INT4 must be greater than or equal to -999999999 in the WHERE clause.</span></span> <span data-ttu-id="1dfcb-129">无论是否选中了包含的值字段将不提取具有小于-999999999 INT4 值的行。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-129">Rows with INT4 values less than -999999999 will not be extracted regardless of whether the field containing the value is selected.</span></span>  
  
-   <span data-ttu-id="1dfcb-130">在 SAP 系统版本 4.7 或更高版本; 上执行时，WHERE 子句被限制为 256 个字符中的所有数据的值类型限制为版本 4.6 c 中的 70 个字符。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-130">Values for all data types in a WHERE clause are limited to 256 characters when executing on SAP system version 4.7 or greater; the limit is 70 characters in version 4.6c.</span></span> <span data-ttu-id="1dfcb-131">原始数据类型值，这些限制减半到 128 到 35 个字符，分别。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-131">For RAW data type values, these limits are halved to 128 and 35 characters, respectively.</span></span> <span data-ttu-id="1dfcb-132">没有任何限制在 RAW 和 LCHR 数据类型长度时它们作为结果返回。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-132">There is no limit on RAW and LCHR data type length when they are returned as a result.</span></span>  
  
-   <span data-ttu-id="1dfcb-133">在 SAP / 3，版本 4.6 C 字段在 WHERE 子句仅限于 70 个字符。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-133">In SAP R/3 version 4.6C, fields in the WHERE clause are limited to 70 characters.</span></span>  
  
-   <span data-ttu-id="1dfcb-134">在 SAP / 3 版本 4.6 C，无法提取任何表具有主键字段具有输出长度大于 70 个字符。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-134">In SAP R/3 version 4.6C, any table with a primary key field that has an output length greater than 70 characters cannot be extracted.</span></span>  
  
-   <span data-ttu-id="1dfcb-135">在 SAP / 3，版本 4.6 c，表和视图包含可变长度数据类型 (`VARC`) 不支持和表和视图包含不能从使用 Z_EXTRACT_DATA_OO 函数调用的数据源中提取这些数据类型。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-135">In SAP R/3, version 4.6c, tables and views that contain variable length data types (`VARC`) are not supported, and tables and views containing these data types cannot be extracted from the data source using the Z_EXTRACT_DATA_OO function call.</span></span>  
  
-   <span data-ttu-id="1dfcb-136">在文件模式下，Z_EXTRACT_DATA_OO 函数调用不会检查是否目标文件已打开，独自或其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-136">In file mode, the Z_EXTRACT_DATA_OO function call does not check whether a destination file is already opened, either by itself or by another application.</span></span> <span data-ttu-id="1dfcb-137">因此，函数可以不正确时将写到打开的文件同时将数据追加到相同的文件。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-137">Therefore, the function can incorrectly write to an open file while simultaneously appending data to the same file.</span></span> <span data-ttu-id="1dfcb-138">不会引发错误。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-138">No error is raised.</span></span>  
  
-   <span data-ttu-id="1dfcb-139">在文件模式下，Z_EXTRACT_DATA_OO 函数调用可以覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-139">In file mode, the Z_EXTRACT_DATA_OO function call can overwrite existing files.</span></span> <span data-ttu-id="1dfcb-140">确保使用 Z_EXTRACT_DATA_OO SAP 用户通过 S_DATASET 的文件系统访问受到限制。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-140">Ensure that SAP users who use Z_EXTRACT_DATA_OO have restricted file-system access by way of S_DATASET.</span></span>  
  
## <a name="security-considerations-with-the-custom-rfc"></a><span data-ttu-id="1dfcb-141">使用自定义的 RFC 的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="1dfcb-141">Security Considerations with the Custom RFC</span></span>  
  
-   <span data-ttu-id="1dfcb-142">`Security Issue`： 没有潜在来公开如果没有帮助保护这些文件写入平面文件的数据。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-142">`Security Issue`: There is potential to expose data that is written to flat files if you do not help protect those files.</span></span>  
  
     <span data-ttu-id="1dfcb-143">`Best practice`： 提高到任何数据由 Z_EXTRACT_DATA_OO 函数调用在平面文件模式下写入的文件共享的安全性。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-143">`Best practice`: Improve the security of the file share to which any data is written by the Z_EXTRACT_DATA_OO function call in flat file mode.</span></span>  
  
-   <span data-ttu-id="1dfcb-144">`Security Issue`： 没有可能会覆盖写入到在文件模式下使用 Z_EXTRACT_DATA_OO 函数调用任何共享上的文件。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-144">`Security Issue`: There is the potential to overwrite files on any share that is written to using the Z_EXTRACT_DATA_OO function call in file mode.</span></span> <span data-ttu-id="1dfcb-145">这可能发生到 SAP 域帐户有权访问任何共享上的任何文件。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-145">This can occur to any file on any share to which the SAP domain account has access.</span></span>  
  
     <span data-ttu-id="1dfcb-146">`Best practice`： 努力保护 SAP 域帐户有权访问的所有共享。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-146">`Best practice`: Strive to protect all shares to which the SAP domain account has access.</span></span>  
  
-   <span data-ttu-id="1dfcb-147">`Security Issue`： 用户在从 SAP 应用程序服务器传输到其目标文件共享，过程中具有检查 （或"探查"） 数据的能力，在目标为不同的物理计算机上时的情况下。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-147">`Security Issue`: Users have the ability to inspect (or "sniff") data during transmission from an SAP application server to its target file share, in cases when the target is on a different physical machine.</span></span>  
  
     <span data-ttu-id="1dfcb-148">`Best practice`： 使用 IPsec 或另一种适当的方法来帮助提高通信安全性 SAP 服务器和目标之间。</span><span class="sxs-lookup"><span data-stu-id="1dfcb-148">`Best practice`: Use IPsec or another appropriate method to help make communication more secure between the SAP server and its targets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dfcb-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1dfcb-149">See Also</span></span>  
 [<span data-ttu-id="1dfcb-150">有关.NET Framework 数据提供程序为 mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="1dfcb-150">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)
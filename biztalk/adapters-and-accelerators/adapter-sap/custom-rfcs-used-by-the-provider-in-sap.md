---
title: 在 SAP 中提供程序所使用的自定义 Rfc |Microsoft Docs
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
ms.openlocfilehash: 36b359fc893b8616fd4fb7339e9efbc42d7d3e13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992718"
---
# <a name="custom-rfcs-used-by-the-provider-in-sap"></a><span data-ttu-id="c6229-102">在 SAP 中提供程序所使用的自定义 Rfc</span><span class="sxs-lookup"><span data-stu-id="c6229-102">Custom RFCs Used by the Provider in SAP</span></span>
<span data-ttu-id="c6229-103">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]提供它在内部使用在 SAP 系统上执行操作的以下自定义 Rfc。</span><span class="sxs-lookup"><span data-stu-id="c6229-103">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] provides the following custom RFCs that it internally uses to perform operations on the SAP system.</span></span>  
  
- <span data-ttu-id="c6229-104">**Z_EXTRACT_DATA_OO RFC**。</span><span class="sxs-lookup"><span data-stu-id="c6229-104">**Z_EXTRACT_DATA_OO RFC**.</span></span> <span data-ttu-id="c6229-105">数据提取 RFC，Z_EXTRACT_DATA_OO，从表中提取数据或视图中的 SAP R/3 系统、 转换数据，并返回同步中的 SQL Server 表中的数据或转储到平面文件数据。</span><span class="sxs-lookup"><span data-stu-id="c6229-105">The data extraction RFC, Z_EXTRACT_DATA_OO, extracts data from tables or views in the SAP R/3 system, converts the data, and either returns the data synchronously in a SQL Server table or dumps data to a flat file.</span></span> <span data-ttu-id="c6229-106">Z_EXTRACT_DATA_OO 用于执行与 WHERE 子句的 SELECT 操作。</span><span class="sxs-lookup"><span data-stu-id="c6229-106">The Z_EXTRACT_DATA_OO is used to perform SELECT operation with WHERE clauses.</span></span> <span data-ttu-id="c6229-107">此 RFC 的性能是依赖于您的 SAP 系统硬件。</span><span class="sxs-lookup"><span data-stu-id="c6229-107">The performance of this RFC is dependent on your SAP system hardware.</span></span>  
  
   <span data-ttu-id="c6229-108">有关如何 Z_EXTRACT_DATA_OO rfc 映射的.NET 和 SAP 数据类型的信息，请参阅[数据类型映射为自定义 Rfc](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)。</span><span class="sxs-lookup"><span data-stu-id="c6229-108">For information on how the .NET and SAP data types are mapped for Z_EXTRACT_DATA_OO RFC, see [Data Type Mapping for Custom RFCs](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md).</span></span>  
  
- <span data-ttu-id="c6229-109">**Z_EXECUTE_SAP_QUERY RFC**。</span><span class="sxs-lookup"><span data-stu-id="c6229-109">**Z_EXECUTE_SAP_QUERY RFC**.</span></span> <span data-ttu-id="c6229-110">使用此 RFC[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]执行已在 SAP 系统中定义的查询。</span><span class="sxs-lookup"><span data-stu-id="c6229-110">This RFC is used by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] to execute queries that are already defined in the SAP system.</span></span> <span data-ttu-id="c6229-111">此 RFC 在内部执行 SAP RFC，RSAQ_REMOTE_QUERY_CALL。</span><span class="sxs-lookup"><span data-stu-id="c6229-111">This RFC internally executes the SAP RFC, RSAQ_REMOTE_QUERY_CALL.</span></span> <span data-ttu-id="c6229-112">SAP 查询是通过选择表、 列、 输入的参数，结果集，等等的排序顺序使用 SAP GUI 以图形方式创建的查询。使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]现在可以从 ADO.NET 客户端执行此类 SAP 查询。</span><span class="sxs-lookup"><span data-stu-id="c6229-112">SAP queries are queries that are graphically created using the SAP GUI by selecting the tables, columns, input parameters, sort order of the result set, etc. Using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] you can now execute such SAP queries from an ADO.NET client.</span></span>  
  
   <span data-ttu-id="c6229-113">EXECQUERY 操作返回的所有值都是字符串类型。</span><span class="sxs-lookup"><span data-stu-id="c6229-113">All values returned by the EXECQUERY operation are of string type.</span></span>  
  
## <a name="limitations-related-to-the-zextractdataoo-rfc"></a><span data-ttu-id="c6229-114">与 Z_EXTRACT_DATA_OO RFC 相关的限制</span><span class="sxs-lookup"><span data-stu-id="c6229-114">Limitations Related to the Z_EXTRACT_DATA_OO RFC</span></span>  
  
-   <span data-ttu-id="c6229-115">Z_EXTRACT_DATA_OO RFC 支持满足以下条件的表中读取数据：</span><span class="sxs-lookup"><span data-stu-id="c6229-115">The Z_EXTRACT_DATA_OO RFC supports reading data from tables that satisfy the following conditions:</span></span>  
  
    -   <span data-ttu-id="c6229-116">表 TabClass 是 TRANSP、 群集或池。</span><span class="sxs-lookup"><span data-stu-id="c6229-116">TabClass for the table is TRANSP, CUSTER, or POOL.</span></span>  
  
    -   <span data-ttu-id="c6229-117">TabClass 是视图且 ViewClass 是 D 或 p。</span><span class="sxs-lookup"><span data-stu-id="c6229-117">TabClass is VIEW and ViewClass is either D or P.</span></span>  
  
-   <span data-ttu-id="c6229-118">Z_EXTRACT_DATA_OO 不支持 HR 群集表，例如 PCL1、 PCL2、 PCL3、 PCL4、 PCL5。</span><span class="sxs-lookup"><span data-stu-id="c6229-118">Z_EXTRACT_DATA_OO does not support HR cluster tables, for example PCL1, PCL2, PCL3, PCL4, PCL5.</span></span>  
  
-   <span data-ttu-id="c6229-119">可以通过 Z_EXTRACT_DATA_OO 提取的行数取决于 SAP 服务器上的硬件资源。</span><span class="sxs-lookup"><span data-stu-id="c6229-119">The number of rows that can be extracted by Z_EXTRACT_DATA_OO depends on the hardware resources on the SAP server.</span></span>  
  
-   <span data-ttu-id="c6229-120">中的主键的顺序返回所有提取的数据。</span><span class="sxs-lookup"><span data-stu-id="c6229-120">All extracted data is returned in order of the primary keys.</span></span>  
  
-   <span data-ttu-id="c6229-121">不支持表或视图，其中包含字符串、 SSTRING 和 RAWSTRING 的可变长度数据类型。</span><span class="sxs-lookup"><span data-stu-id="c6229-121">Tables or views containing the variable-length data types STRING, SSTRING and RAWSTRING are not supported.</span></span> <span data-ttu-id="c6229-122">无法提取表或视图包含这些数据类型。</span><span class="sxs-lookup"><span data-stu-id="c6229-122">Tables or views containing these data types cannot be extracted.</span></span>  
  
-   <span data-ttu-id="c6229-123">Z_EXTRACT_DATA_OO 上所有已分配给他们的转换退出的字段运行转换退出。</span><span class="sxs-lookup"><span data-stu-id="c6229-123">Z_EXTRACT_DATA_OO runs conversion exits on all fields that have conversion exits assigned to them.</span></span> <span data-ttu-id="c6229-124">必须在 SELECT 语句的 WHERE 子句中输入生成转换后的值。</span><span class="sxs-lookup"><span data-stu-id="c6229-124">The resulting converted values must be entered in the WHERE clause of a SELECT statement.</span></span> <span data-ttu-id="c6229-125">转换后的值也会返回。</span><span class="sxs-lookup"><span data-stu-id="c6229-125">Converted values are also returned.</span></span> <span data-ttu-id="c6229-126">这可能会导致 Z_EXTRACT_DATA_OO 返回的结果中的 SAP 数据浏览器 (SE16) 返回的结果之间的不一致性。</span><span class="sxs-lookup"><span data-stu-id="c6229-126">This might cause inconsistencies between the results returned by Z_EXTRACT_DATA_OO and the results returned in the SAP data browser (SE16).</span></span>  
  
-   <span data-ttu-id="c6229-127">所选的表不能包含在 ABAP （例如，连接） 的保留名称的字段名称。</span><span class="sxs-lookup"><span data-stu-id="c6229-127">Selected tables cannot contain field names that are reserved names in ABAP (for example, CONNECTION).</span></span>  
  
-   <span data-ttu-id="c6229-128">由于 SAP R/3 版本 4.6c，整数类型的字段的值中的查询处理器中的限制 INT4 必须大于或等于-999999999 WHERE 子句中。</span><span class="sxs-lookup"><span data-stu-id="c6229-128">Due to a limitation in the query processor in SAP R/3 version 4.6C, values for integer fields of type INT4 must be greater than or equal to -999999999 in the WHERE clause.</span></span> <span data-ttu-id="c6229-129">无论是否选中包含的值字段将不提取具有小于-999999999 INT4 值的行。</span><span class="sxs-lookup"><span data-stu-id="c6229-129">Rows with INT4 values less than -999999999 will not be extracted regardless of whether the field containing the value is selected.</span></span>  
  
-   <span data-ttu-id="c6229-130">SAP 系统版本 4.7 或更高版本; 在执行时，WHERE 子句被限制为 256 个字符中的所有数据的值类型在版本 4.6 c 70 个字符的限制。</span><span class="sxs-lookup"><span data-stu-id="c6229-130">Values for all data types in a WHERE clause are limited to 256 characters when executing on SAP system version 4.7 or greater; the limit is 70 characters in version 4.6c.</span></span> <span data-ttu-id="c6229-131">原始数据类型值，这些限制是缩减了一半到 128 到 35 个字符，分别。</span><span class="sxs-lookup"><span data-stu-id="c6229-131">For RAW data type values, these limits are halved to 128 and 35 characters, respectively.</span></span> <span data-ttu-id="c6229-132">没有任何限制在 RAW 和 LCHR 数据类型长度时返回结果。</span><span class="sxs-lookup"><span data-stu-id="c6229-132">There is no limit on RAW and LCHR data type length when they are returned as a result.</span></span>  
  
-   <span data-ttu-id="c6229-133">在 SAP R/3 版本 4.6c，字段在 WHERE 子句仅限于 70 个字符。</span><span class="sxs-lookup"><span data-stu-id="c6229-133">In SAP R/3 version 4.6C, fields in the WHERE clause are limited to 70 characters.</span></span>  
  
-   <span data-ttu-id="c6229-134">在 SAP R/3 版本 4.6c，不能提取与具有输出长度大于 70 个字符的主键字段的任何表。</span><span class="sxs-lookup"><span data-stu-id="c6229-134">In SAP R/3 version 4.6C, any table with a primary key field that has an output length greater than 70 characters cannot be extracted.</span></span>  
  
-   <span data-ttu-id="c6229-135">在 SAP R/3，版本 4.6 c，包含可变长度数据类型的表和视图 (`VARC`) 不受支持，以及表和视图包含不能从使用 Z_EXTRACT_DATA_OO 函数调用的数据源中提取这些数据类型。</span><span class="sxs-lookup"><span data-stu-id="c6229-135">In SAP R/3, version 4.6c, tables and views that contain variable length data types (`VARC`) are not supported, and tables and views containing these data types cannot be extracted from the data source using the Z_EXTRACT_DATA_OO function call.</span></span>  
  
-   <span data-ttu-id="c6229-136">在文件模式下，Z_EXTRACT_DATA_OO 函数调用不会检查是否目标文件已打开，本身或其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="c6229-136">In file mode, the Z_EXTRACT_DATA_OO function call does not check whether a destination file is already opened, either by itself or by another application.</span></span> <span data-ttu-id="c6229-137">因此，该函数可以不正确时将写到打开的文件同时将数据追加到同一个文件。</span><span class="sxs-lookup"><span data-stu-id="c6229-137">Therefore, the function can incorrectly write to an open file while simultaneously appending data to the same file.</span></span> <span data-ttu-id="c6229-138">不会引发错误。</span><span class="sxs-lookup"><span data-stu-id="c6229-138">No error is raised.</span></span>  
  
-   <span data-ttu-id="c6229-139">在文件模式下，Z_EXTRACT_DATA_OO 函数调用可以覆盖现有文件。</span><span class="sxs-lookup"><span data-stu-id="c6229-139">In file mode, the Z_EXTRACT_DATA_OO function call can overwrite existing files.</span></span> <span data-ttu-id="c6229-140">请确保使用 Z_EXTRACT_DATA_OO SAP 用户通过 S_DATASET 的文件系统访问权限受到限制。</span><span class="sxs-lookup"><span data-stu-id="c6229-140">Ensure that SAP users who use Z_EXTRACT_DATA_OO have restricted file-system access by way of S_DATASET.</span></span>  
  
## <a name="security-considerations-with-the-custom-rfc"></a><span data-ttu-id="c6229-141">使用自定义 RFC 的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="c6229-141">Security Considerations with the Custom RFC</span></span>  
  
-   <span data-ttu-id="c6229-142">`Security Issue`： 可能会公开数据，如果您没有帮助保护这些文件写入到平面文件。</span><span class="sxs-lookup"><span data-stu-id="c6229-142">`Security Issue`: There is potential to expose data that is written to flat files if you do not help protect those files.</span></span>  
  
     <span data-ttu-id="c6229-143">`Best practice`： 提高 Z_EXTRACT_DATA_OO 函数调用在平面文件模式下的任何数据写入到文件共享的安全性。</span><span class="sxs-lookup"><span data-stu-id="c6229-143">`Best practice`: Improve the security of the file share to which any data is written by the Z_EXTRACT_DATA_OO function call in flat file mode.</span></span>  
  
-   <span data-ttu-id="c6229-144">`Security Issue`： 没有可能会覆盖上写入到在文件模式下使用 Z_EXTRACT_DATA_OO 函数调用的任何共享的文件。</span><span class="sxs-lookup"><span data-stu-id="c6229-144">`Security Issue`: There is the potential to overwrite files on any share that is written to using the Z_EXTRACT_DATA_OO function call in file mode.</span></span> <span data-ttu-id="c6229-145">这可能到 SAP 域帐户有权访问的任何共享上的任何文件。</span><span class="sxs-lookup"><span data-stu-id="c6229-145">This can occur to any file on any share to which the SAP domain account has access.</span></span>  
  
     <span data-ttu-id="c6229-146">`Best practice`： 致力于保护 SAP 域帐户有权访问的所有共享。</span><span class="sxs-lookup"><span data-stu-id="c6229-146">`Best practice`: Strive to protect all shares to which the SAP domain account has access.</span></span>  
  
-   <span data-ttu-id="c6229-147">`Security Issue`： 用户可以检查 （或"探查"） 数据从 SAP 应用程序服务器传输到其目标文件共享，期间在目标为不同的物理计算机上的情况下。</span><span class="sxs-lookup"><span data-stu-id="c6229-147">`Security Issue`: Users have the ability to inspect (or "sniff") data during transmission from an SAP application server to its target file share, in cases when the target is on a different physical machine.</span></span>  
  
     <span data-ttu-id="c6229-148">`Best practice`： 使用 IPsec 或另一个适当的方法来帮助提高通信安全性 SAP 服务器和目标之间。</span><span class="sxs-lookup"><span data-stu-id="c6229-148">`Best practice`: Use IPsec or another appropriate method to help make communication more secure between the SAP server and its targets.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6229-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6229-149">See Also</span></span>  
 [<span data-ttu-id="c6229-150">关于 mySAP Business Suite 的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="c6229-150">About the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)
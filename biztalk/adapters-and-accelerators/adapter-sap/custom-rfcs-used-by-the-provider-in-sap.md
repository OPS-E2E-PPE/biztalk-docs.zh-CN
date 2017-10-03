---
title: "SAP 中提供程序所使用的自定义 Rfc |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Z_EXTRACT_DATA_OO, limitations related to
- RFC, Z_EXTRACT_DATA_OO
- Z_EXTRACT_DATA_OO
- Z_EXTRACT_DATA_OO, best practice
- Z_EXTRACT_DATA_OO, security issue
ms.assetid: 95661f4c-0431-40ca-8a53-3fbe359b8afd
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e55473dbcfeebecc504906d569c129989b054211
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="custom-rfcs-used-by-the-provider-in-sap"></a>SAP 中提供程序所使用的自定义 Rfc
[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]提供它在内部使用 SAP 系统上执行操作的以下自定义 Rfc。  
  
-   **Z_EXTRACT_DATA_OO RFC**。 数据提取 RFC，Z_EXTRACT_DATA_OO，从表中提取数据或视图中 SAP / 3 系统、 将转换数据，并返回以同步方式中的 SQL Server 表的数据或转储的平面文件数据。 Z_EXTRACT_DATA_OO 用于执行与 WHERE 子句的选择操作。 此 RFC 的性能是依赖于您的 SAP 系统硬件。  
  
     有关如何为 Z_EXTRACT_DATA_OO RFC 映射的.NET 和 SAP 数据类型的信息，请参阅[Data Type Mapping for 自定义 Rfc](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)。  
  
-   **Z_EXECUTE_SAP_QUERY RFC**。 使用此 RFC[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]执行已在 SAP 系统中定义的查询。 此 RFC 内部执行 SAP RFC，RSAQ_REMOTE_QUERY_CALL。 SAP 查询都是通过选择表、 列、 输入的参数，结果集等的排序顺序中使用 SAP GUI 以图形方式创建的查询。使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]您现在可以从 ADO.NET 客户端执行此类 SAP 查询。  
  
     EXECQUERY 操作返回的所有值都是字符串类型。  
  
## <a name="limitations-related-to-the-zextractdataoo-rfc"></a>与 Z_EXTRACT_DATA_OO RFC 相关的限制  
  
-   Z_EXTRACT_DATA_OO RFC 支持满足以下条件的表中读取数据：  
  
    -   为表的 TabClass 是 TRANSP、 群集或池。  
  
    -   TabClass 是视图且 ViewClass 是 D 或 P.  
  
-   Z_EXTRACT_DATA_OO 不支持 HR 群集表，例如 PCL1、 PCL2、 PCL3、 PCL4、 PCL5。  
  
-   可以通过 Z_EXTRACT_DATA_OO 提取的行数取决于 SAP 服务器上的硬件资源。  
  
-   中的主键的顺序返回所有提取的数据。  
  
-   不支持表或视图包含字符串、 SSTRING 和 RAWSTRING 的可变长度数据类型。 无法提取表或视图包含这些数据类型。  
  
-   Z_EXTRACT_DATA_OO 上已分配给他们的转换退出的所有字段运行转换退出。 SELECT 语句的 WHERE 子句中，必须输入生成转换后的值。 转换后的值也会返回。 这可能会导致 Z_EXTRACT_DATA_OO 返回的结果和 SAP 数据浏览器 (SE16) 中返回的结果之间的不一致。  
  
-   所选的表不能包含是 ABAP （例如，连接） 中的保留的名称的字段名称。  
  
-   由于 SAP / 3，版本 4.6 C 中，为整数类型的字段的值中的查询处理器中存在的限制 INT4 必须大于或等于-999999999 WHERE 子句中。 无论是否选中了包含的值字段将不提取具有小于-999999999 INT4 值的行。  
  
-   在 SAP 系统版本 4.7 或更高版本; 上执行时，WHERE 子句被限制为 256 个字符中的所有数据的值类型限制为版本 4.6 c 中的 70 个字符。 原始数据类型值，这些限制减半到 128 到 35 个字符，分别。 没有任何限制在 RAW 和 LCHR 数据类型长度时它们作为结果返回。  
  
-   在 SAP / 3，版本 4.6 C 字段在 WHERE 子句仅限于 70 个字符。  
  
-   在 SAP / 3 版本 4.6 C，无法提取任何表具有主键字段具有输出长度大于 70 个字符。  
  
-   在 SAP / 3，版本 4.6 c，表和视图包含可变长度数据类型 (`VARC`) 不支持和表和视图包含不能从使用 Z_EXTRACT_DATA_OO 函数调用的数据源中提取这些数据类型。  
  
-   在文件模式下，Z_EXTRACT_DATA_OO 函数调用不会检查是否目标文件已打开，独自或其他应用程序。 因此，函数可以不正确时将写到打开的文件同时将数据追加到相同的文件。 不会引发错误。  
  
-   在文件模式下，Z_EXTRACT_DATA_OO 函数调用可以覆盖现有文件。 确保使用 Z_EXTRACT_DATA_OO SAP 用户通过 S_DATASET 的文件系统访问受到限制。  
  
## <a name="security-considerations-with-the-custom-rfc"></a>使用自定义的 RFC 的安全注意事项  
  
-   `Security Issue`： 没有潜在来公开如果没有帮助保护这些文件写入平面文件的数据。  
  
     `Best practice`： 提高到任何数据由 Z_EXTRACT_DATA_OO 函数调用在平面文件模式下写入的文件共享的安全性。  
  
-   `Security Issue`： 没有可能会覆盖写入到在文件模式下使用 Z_EXTRACT_DATA_OO 函数调用任何共享上的文件。 这可能发生到 SAP 域帐户有权访问任何共享上的任何文件。  
  
     `Best practice`： 努力保护 SAP 域帐户有权访问的所有共享。  
  
-   `Security Issue`： 用户在从 SAP 应用程序服务器传输到其目标文件共享，过程中具有检查 （或"探查"） 数据的能力，在目标为不同的物理计算机上时的情况下。  
  
     `Best practice`： 使用 IPsec 或另一种适当的方法来帮助提高通信安全性 SAP 服务器和目标之间。  
  
## <a name="see-also"></a>另请参阅  
 [有关.NET Framework 数据提供程序为 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)
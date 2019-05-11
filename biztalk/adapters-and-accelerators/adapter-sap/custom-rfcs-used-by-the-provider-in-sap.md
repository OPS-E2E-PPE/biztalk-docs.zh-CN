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
ms.openlocfilehash: 0e28ea61e09eb8098b98e7396deea0662090eb98
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373559"
---
# <a name="custom-rfcs-used-by-the-provider-in-sap"></a>在 SAP 中提供程序所使用的自定义 Rfc
[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]提供它在内部使用在 SAP 系统上执行操作的以下自定义 Rfc。  
  
- **Z_EXTRACT_DATA_OO RFC**. 数据提取 RFC，Z_EXTRACT_DATA_OO，从表中提取数据或视图中的 SAP R/3 系统、 转换数据，并返回同步中的 SQL Server 表中的数据或转储到平面文件数据。 Z_EXTRACT_DATA_OO 用于执行与 WHERE 子句的 SELECT 操作。 此 RFC 的性能是依赖于您的 SAP 系统硬件。  
  
   有关如何 Z_EXTRACT_DATA_OO rfc 映射的.NET 和 SAP 数据类型的信息，请参阅[数据类型映射为自定义 Rfc](../../adapters-and-accelerators/adapter-sap/data-type-mapping-for-custom-rfcs.md)。  
  
- **Z_EXECUTE_SAP_QUERY RFC**。 使用此 RFC[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]执行已在 SAP 系统中定义的查询。 此 RFC 在内部执行 SAP RFC，RSAQ_REMOTE_QUERY_CALL。 SAP 查询是通过选择表、 列、 输入的参数，结果集，等等的排序顺序使用 SAP GUI 以图形方式创建的查询。使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]现在可以从 ADO.NET 客户端执行此类 SAP 查询。  
  
   EXECQUERY 操作返回的所有值都是字符串类型。  
  
## <a name="limitations-related-to-the-zextractdataoo-rfc"></a>与 Z_EXTRACT_DATA_OO RFC 相关的限制  
  
-   Z_EXTRACT_DATA_OO RFC 支持满足以下条件的表中读取数据：  
  
    -   表 TabClass 是 TRANSP、 群集或池。  
  
    -   TabClass 是视图且 ViewClass 是 D 或 p。  
  
-   Z_EXTRACT_DATA_OO 不支持 HR 群集表，例如 PCL1、 PCL2、 PCL3、 PCL4、 PCL5。  
  
-   可以通过 Z_EXTRACT_DATA_OO 提取的行数取决于 SAP 服务器上的硬件资源。  
  
-   中的主键的顺序返回所有提取的数据。  
  
-   不支持表或视图，其中包含字符串、 SSTRING 和 RAWSTRING 的可变长度数据类型。 无法提取表或视图包含这些数据类型。  
  
-   Z_EXTRACT_DATA_OO 上所有已分配给他们的转换退出的字段运行转换退出。 必须在 SELECT 语句的 WHERE 子句中输入生成转换后的值。 转换后的值也会返回。 这可能会导致 Z_EXTRACT_DATA_OO 返回的结果中的 SAP 数据浏览器 (SE16) 返回的结果之间的不一致性。  
  
-   所选的表不能包含在 ABAP （例如，连接） 的保留名称的字段名称。  
  
-   由于 SAP R/3 版本 4.6c，整数类型的字段的值中的查询处理器中的限制 INT4 必须大于或等于-999999999 WHERE 子句中。 无论是否选中包含的值字段将不提取具有小于-999999999 INT4 值的行。  
  
-   SAP 系统版本 4.7 或更高版本; 在执行时，WHERE 子句被限制为 256 个字符中的所有数据的值类型在版本 4.6 c 70 个字符的限制。 原始数据类型值，这些限制是缩减了一半到 128 到 35 个字符，分别。 没有任何限制在 RAW 和 LCHR 数据类型长度时返回结果。  
  
-   在 SAP R/3 版本 4.6c，字段在 WHERE 子句仅限于 70 个字符。  
  
-   在 SAP R/3 版本 4.6c，不能提取与具有输出长度大于 70 个字符的主键字段的任何表。  
  
-   在 SAP R/3，版本 4.6 c，包含可变长度数据类型的表和视图 (`VARC`) 不受支持，以及表和视图包含不能从使用 Z_EXTRACT_DATA_OO 函数调用的数据源中提取这些数据类型。  
  
-   在文件模式下，Z_EXTRACT_DATA_OO 函数调用不会检查是否目标文件已打开，本身或其他应用程序。 因此，该函数可以不正确时将写到打开的文件同时将数据追加到同一个文件。 不会引发错误。  
  
-   在文件模式下，Z_EXTRACT_DATA_OO 函数调用可以覆盖现有文件。 请确保使用 Z_EXTRACT_DATA_OO SAP 用户通过 S_DATASET 的文件系统访问权限受到限制。  
  
## <a name="security-considerations-with-the-custom-rfc"></a>使用自定义 RFC 的安全注意事项  
  
-   `Security Issue`设置用户帐户 ：可能会公开数据，如果您没有帮助保护这些文件写入到平面文件。  
  
     `Best practice`设置用户帐户 ：提高 Z_EXTRACT_DATA_OO 函数调用在平面文件模式下的任何数据写入到文件共享的安全性。  
  
-   `Security Issue`设置用户帐户 ：还有可能会覆盖上写入到在文件模式下使用 Z_EXTRACT_DATA_OO 函数调用的任何共享的文件。 这可能到 SAP 域帐户有权访问的任何共享上的任何文件。  
  
     `Best practice`设置用户帐户 ：致力于保护 SAP 域帐户有权访问的所有共享。  
  
-   `Security Issue`设置用户帐户 ：用户可以检查 （或"探查"） 数据从 SAP 应用程序服务器传输到其目标文件共享，期间在目标为不同的物理计算机上的情况下。  
  
     `Best practice`设置用户帐户 ：使用 IPsec 或另一个适当的方法来帮助提高通信安全性 SAP 服务器和目标之间。  
  
## <a name="see-also"></a>请参阅  
 [关于 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)
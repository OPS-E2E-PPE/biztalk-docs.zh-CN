---
title: 有关 Siebel 的数据提供程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for Siebel, overview
ms.assetid: 461fe4d8-75f2-49d5-9fc2-3baab4ccf13f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81cac425bf1671166b4f40cecae3e1a3aca1c8e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217757"
---
# <a name="about-the-data-provider-for-siebel"></a>有关 Siebel 的数据提供程序
## <a name="overview"></a>概述
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]之上生成[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。 你可以使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]到：  
  
-   编写的 ADO.NET 客户端可以连接到 Siebel 系统。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]公开某些使您能够使用提供程序接口的类。  
  
-   Siebel 业务组件上运行 SELECT 查询
  
-   在 Siebel 业务服务上运行的 EXEC 查询
  
-   使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使用 SQL Server Integration Services (SSIS)
  
[.NET Framework 数据提供程序用于 Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)位于用于信息的重大资源：  
  
-   通过 ADO.NET 接口扩展[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]  
  
-   要连接到 Siebel 系统的连接字符串  
  
-   SELECT 和 EXEC 语句的语法  
  
-   使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使用 SSIS  
  
## <a name="limitations"></a>限制
以下已知的限制[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]:  
  
-   [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]别名支持为表的名称，在 SELECT 子句中，但不是在 WHERE 子句。  
  
-   [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]无法创建表，具有特殊字符，列名称的"]"。 可以通过包括另一个右方括号转义特殊字符。 因此，你应包括"]]"而不是"]"。  
  
-   由于出现超时处理由基础 Siebel 客户端 API，问题[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]不支持命令和连接超时。  
  
-   [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]不支持异步命令的行为。  
  
-   使用 SQL Server Integration Services (SSIS) 项目，使用时[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]无法检索包含与多个 8000 个字符的值的列的数据。 这是由于依据的 SSIS 限制：  
  
    -   不支持大于 4000 个字符在 SSIS 变量的值。  
  
    -   不支持大于 4000 宽字符的值。  
  
    -   不支持大于 8000 单字节字符的值。  
  
-   EXEC 操作将不起作用时使用[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]与 SQL Server Integration Services (SSIS)。 因此，例如，适配器客户端将不能在 Siebel 中执行业务服务 (使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) 时使用 SSIS 数据提供程序。 

## <a name="see-also"></a>另请参阅
[Siebel 适配器的限制](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
[解决在 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)
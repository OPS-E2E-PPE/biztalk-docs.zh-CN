---
title: 有关用于 Siebel 的数据提供程序 |Microsoft Docs
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
ms.openlocfilehash: 97d7366ba227c16a5910a8000e57e92f992d3e1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989574"
---
# <a name="about-the-data-provider-for-siebel"></a>有关用于 Siebel 的数据提供程序
## <a name="overview"></a>概述
[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]构建的[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。 可以使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]到：  
  
- 编写 ADO.NET 客户端连接到 Siebel 系统。 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]公开某些类，您可以使用提供程序接口。  
  
- Siebel 业务组件上运行 SELECT 查询
  
- Siebel 业务服务上运行的 EXEC 查询
  
- 使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使用 SQL Server Integration Services (SSIS)
  
[用于 Siebel eBusiness 应用程序使用.NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)上是一个不错的资源的信息：  
  
- 通过扩展 ADO.NET 接口 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]  
  
- 要连接到 Siebel 系统的连接字符串  
  
- SELECT 和 EXEC 语句的语法  
  
- 使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使用 SSIS  
  
## <a name="limitations"></a>限制
以下已知的限制[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]:  
  
- [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]支持别名的表的名称，在 SELECT 子句，但不是在 WHERE 子句。  
  
- [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]无法创建表，具有特殊字符的列名称的"]"。 可通过包含另一个右方括号转义特殊字符。 因此，应包含"]]"而不是"]"。  
  
- 由于超时由基础 Siebel 客户端 API，处理的问题[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]不支持命令，并连接超时。  
  
- [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]不支持异步命令的行为。  
  
- 当使用 SQL Server Integration Services (SSIS) 项目，使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]无法检索包含超过 8000 个字符的值的列的数据。 这是因为依据的 SSIS 限制：  
  
  -   不支持大于 4000 个字符中的 SSIS 变量的值。  
  
  -   不支持大于 4000 个宽字符的值。  
  
  -   不支持大于 8000 的单字节字符的值。  
  
- EXEC 操作将不能正常运行时使用[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]与 SQL Server Integration Services (SSIS)。 因此，例如，适配器客户端将不能在 Siebel 中执行业务服务 (使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) 时使用 SSIS 中使用的数据提供程序。 

## <a name="see-also"></a>另请参阅
[Siebel 适配器的限制](../../adapters-and-accelerators/adapter-siebel/limitations-of-biztalk-adapter-for-siebel-ebusiness-applications.md)  
[Siebel 适配器疑难解答](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)
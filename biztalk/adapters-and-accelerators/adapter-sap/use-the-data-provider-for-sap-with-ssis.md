---
title: "为 SAP 使用 SSIS 中使用的数据提供程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, using with SSIS
- SSIS, Data Provider for SAP
ms.assetid: e8c50cc1-ac25-4993-9aee-7fd88268d65d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8459453e153626b6a79a5dc5f57ce041ba67d1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-the-data-provider-for-sap-with-ssis"></a>为 SAP 使用 SSIS 中使用的数据提供程序
你可以使用[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]以及 SQL Server 的集成服务 (SSIS) 将从 SAP 系统的数据导入 SQL Server 数据库表，平面文件或其他兼容的目标类型。 你可以创建 SSIS 包可执行从某个 SAP 系统导入数据。  
  
 你必须使用 SQL Server 导入和导出向导将数据导入的 SQL Server 数据库。 必须提供查询以指定要导入数据。 你可以指定一个查询使用 SELECT 语句或 EXECQUERY 语句。 支持的语义查询必须遵循[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。 有关语法的详细信息，以进行 SELECT 查询[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[为 SAP 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。 有关的 EXECQUERY 语句的语法的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 中 EXECQUERY 语句语法](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md)。  
  
 从 SQL Server Management Studio 或 Visual Studio 中的集成服务项目，可以启动 SQL Server 导入导出向导。 此部分提供有关从 Management Studio 和 Visual Studio 接口运行向导的说明。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 SQL Server Management Studio 导入 SAP 数据](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-sql-server-management-studio.md)  
  
-   [使用 Visual Studio 的导入 SAP 数据](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-visual-studio.md)  
  
## <a name="see-also"></a>另请参阅  
 [使用.NET Framework 数据提供程序为 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)
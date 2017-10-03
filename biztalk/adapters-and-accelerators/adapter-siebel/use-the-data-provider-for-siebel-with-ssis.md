---
title: "使用用于 Siebel 使用 SSIS 数据提供程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSIS
- SQL Server Integration Services
- Data Provider for Siebel, using with SSIS
ms.assetid: e72cecf2-6c05-4df7-8e6e-aff3a9df8b79
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0c46c1437d7eeedd56ee37b054f9f6eb6b72ada
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-the-data-provider-for-siebel-with-ssis"></a>使用用于 Siebel 使用 SSIS 数据提供程序
你可以使用[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)]([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) 以及 SQL Server Integration Services (SSIS) 将数据从 Siebel 系统导入 SQL Server 数据库表，平面文件或其他兼容的目标类型。 具体而言，你可以创建 SSIS 包可执行此数据导入。  
  
 若要将数据导入的 SQL Server 数据库，使用 SQL Server 导入和导出向导中，并提供选择查询以指定要导入数据。 支持的语义查询必须遵循[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。 有关语法的详细信息，以进行 SELECT 查询[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，请参阅[为 Siebel 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)。  
  
> [!NOTE]
>  [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]不支持使用 SSIS EXEC 语句。  
  
 从 SQL Server Management Studio 或 Visual Studio 中的集成服务项目，你可以启动 SQL Server 导入和导出向导。 此部分提供有关 SQL Server Management Studio 和 Visual Studio 接口从运行向导的说明。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [导入 Siebel 数据使用 SQL Server Management Studio](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-sql-server-management-studio.md)  
  
-   [使用 Visual Studio 的 Siebel 数据导入](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-visual-studio.md)  
  
## <a name="see-also"></a>另请参阅  
 [.NET Framework 数据提供程序用于 Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
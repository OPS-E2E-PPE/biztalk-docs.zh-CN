---
title: 使用包含 SSIS 的 SAP 数据提供程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, using with SSIS
- SSIS, Data Provider for SAP
ms.assetid: e8c50cc1-ac25-4993-9aee-7fd88268d65d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d75ea62e0cb8edb39f655e1e763c1855e19f46a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372239"
---
# <a name="use-the-data-provider-for-sap-with-ssis"></a>使用包含 SSIS 的 SAP 数据提供程序
可以使用[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]以及 SQL Server 集成服务 (SSIS) 来将数据从 SAP 系统导入 SQL Server 数据库表，平面文件或其他兼容的目标类型。 可以创建可执行从 SAP 系统导入数据的 SSIS 包。  
  
 必须使用 SQL Server 导入和导出向导导入到 SQL Server 数据库的数据。 必须提供查询以指定要导入数据。 可以指定一个查询使用 SELECT 语句或 EXECQUERY 语句。 查询必须确认受语义[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。 有关语法的详细信息，为 SELECT 查询[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[为 SAP 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。 有关为 EXECQUERY 语句的语法详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 中的 EXECQUERY 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md)。  
  
 从 SQL Server Management Studio 或 Visual Studio 中的集成服务项目，可以启动 SQL Server 导入导出向导。 本部分说明了从 Management Studio 和 Visual Studio 接口运行向导。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 SQL Server Management Studio 导入 SAP 数据](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-sql-server-management-studio.md)  
  
-   [使用 Visual Studio 导入 SAP 数据](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-visual-studio.md)  
  
## <a name="see-also"></a>请参阅  
 [使用 mySAP Business Suite 的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)
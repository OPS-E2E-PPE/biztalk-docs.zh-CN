---
title: 使用用于 Siebel 使用 SSIS 数据提供程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSIS
- SQL Server Integration Services
- Data Provider for Siebel, using with SSIS
ms.assetid: e72cecf2-6c05-4df7-8e6e-aff3a9df8b79
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 999583cf09c663e847a6ae680736af9aea581726
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370249"
---
# <a name="use-the-data-provider-for-siebel-with-ssis"></a>使用用于 Siebel 使用 SSIS 数据提供程序
你可以使用[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) 以及 SQL Server Integration Services (SSIS) 将数据从 Siebel 系统导入 SQL Server 数据库表，平面文件或其他兼容的目标类型。 具体而言，可以创建一个 SSIS 包，可以执行此数据导入。  
  
 若要导入到 SQL Server 数据库的数据，使用 SQL Server 导入和导出向导中，并提供 SELECT 查询，以便指定要导入的数据。 查询必须确认受语义[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。 有关语法的详细信息，为 SELECT 查询[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，请参阅[Siebel 中的选择语句的语法](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)。  
  
> [!NOTE]
>  [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]不支持使用 SSIS 中使用 EXEC 语句。  
  
 从 SQL Server Management Studio 或 Visual Studio 中的集成服务项目，可以启动 SQL Server 导入和导出向导。 本部分说明了从 SQL Server Management Studio 和 Visual Studio 接口运行向导。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 SQL Server Management Studio 导入 Siebel 数据](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-sql-server-management-studio.md)  
  
-   [使用 Visual Studio 导入 Siebel 数据](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-visual-studio.md)  
  
## <a name="see-also"></a>请参阅  
 [使用用于 Siebel eBusiness 应用程序的 .NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
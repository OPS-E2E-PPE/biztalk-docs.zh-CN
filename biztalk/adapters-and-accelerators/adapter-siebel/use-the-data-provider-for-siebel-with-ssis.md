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
# <a name="use-the-data-provider-for-siebel-with-ssis"></a><span data-ttu-id="f60fa-102">使用用于 Siebel 使用 SSIS 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="f60fa-102">Use the Data Provider for Siebel with SSIS</span></span>
<span data-ttu-id="f60fa-103">你可以使用[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) 以及 SQL Server Integration Services (SSIS) 将数据从 Siebel 系统导入 SQL Server 数据库表，平面文件或其他兼容的目标类型。</span><span class="sxs-lookup"><span data-stu-id="f60fa-103">You can use the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) along with SQL Server Integration Services (SSIS) to import data from a Siebel system into SQL Server database tables, flat files, or other compatible destination types.</span></span> <span data-ttu-id="f60fa-104">具体而言，你可以创建 SSIS 包可执行此数据导入。</span><span class="sxs-lookup"><span data-stu-id="f60fa-104">Specifically, you can create an SSIS package that can be executed to import this data.</span></span>  
  
 <span data-ttu-id="f60fa-105">若要将数据导入的 SQL Server 数据库，使用 SQL Server 导入和导出向导中，并提供选择查询以指定要导入数据。</span><span class="sxs-lookup"><span data-stu-id="f60fa-105">To import data into the SQL Server database, use the SQL Server Import and Export Wizard, and provide a SELECT query to specify the data to be imported.</span></span> <span data-ttu-id="f60fa-106">支持的语义查询必须遵循[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f60fa-106">The query must confirm to the semantics supported by the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span> <span data-ttu-id="f60fa-107">有关语法的详细信息，以进行 SELECT 查询[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，请参阅[为 Siebel 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="f60fa-107">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f60fa-108">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]不支持使用 SSIS EXEC 语句。</span><span class="sxs-lookup"><span data-stu-id="f60fa-108">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] does not support using an EXEC statement with SSIS.</span></span>  
  
 <span data-ttu-id="f60fa-109">从 SQL Server Management Studio 或 Visual Studio 中的集成服务项目，你可以启动 SQL Server 导入和导出向导。</span><span class="sxs-lookup"><span data-stu-id="f60fa-109">You can start the SQL Server Import and Export wizard either from the SQL Server Management Studio or from an Integration Service project in Visual Studio.</span></span> <span data-ttu-id="f60fa-110">此部分提供有关 SQL Server Management Studio 和 Visual Studio 接口从运行向导的说明。</span><span class="sxs-lookup"><span data-stu-id="f60fa-110">This section provides instructions on running the wizard from both the SQL Server Management Studio and Visual Studio interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f60fa-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="f60fa-111">In This Section</span></span>  
  
-   [<span data-ttu-id="f60fa-112">导入 Siebel 数据使用 SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f60fa-112">Import Siebel Data Using SQL Server Management Studio</span></span>](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="f60fa-113">使用 Visual Studio 的 Siebel 数据导入</span><span class="sxs-lookup"><span data-stu-id="f60fa-113">Import Siebel Data Using Visual Studio</span></span>](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-visual-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="f60fa-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f60fa-114">See Also</span></span>  
 [<span data-ttu-id="f60fa-115">.NET Framework 数据提供程序用于 Siebel eBusiness Applications</span><span class="sxs-lookup"><span data-stu-id="f60fa-115">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
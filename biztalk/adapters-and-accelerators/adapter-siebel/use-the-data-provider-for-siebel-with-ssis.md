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
# <a name="use-the-data-provider-for-siebel-with-ssis"></a><span data-ttu-id="975ef-102">使用用于 Siebel 使用 SSIS 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="975ef-102">Use the Data Provider for Siebel with SSIS</span></span>
<span data-ttu-id="975ef-103">你可以使用[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) 以及 SQL Server Integration Services (SSIS) 将数据从 Siebel 系统导入 SQL Server 数据库表，平面文件或其他兼容的目标类型。</span><span class="sxs-lookup"><span data-stu-id="975ef-103">You can use the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]) along with SQL Server Integration Services (SSIS) to import data from a Siebel system into SQL Server database tables, flat files, or other compatible destination types.</span></span> <span data-ttu-id="975ef-104">具体而言，可以创建一个 SSIS 包，可以执行此数据导入。</span><span class="sxs-lookup"><span data-stu-id="975ef-104">Specifically, you can create an SSIS package that can be executed to import this data.</span></span>  
  
 <span data-ttu-id="975ef-105">若要导入到 SQL Server 数据库的数据，使用 SQL Server 导入和导出向导中，并提供 SELECT 查询，以便指定要导入的数据。</span><span class="sxs-lookup"><span data-stu-id="975ef-105">To import data into the SQL Server database, use the SQL Server Import and Export Wizard, and provide a SELECT query to specify the data to be imported.</span></span> <span data-ttu-id="975ef-106">查询必须确认受语义[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="975ef-106">The query must confirm to the semantics supported by the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span> <span data-ttu-id="975ef-107">有关语法的详细信息，为 SELECT 查询[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，请参阅[Siebel 中的选择语句的语法](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="975ef-107">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="975ef-108">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]不支持使用 SSIS 中使用 EXEC 语句。</span><span class="sxs-lookup"><span data-stu-id="975ef-108">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] does not support using an EXEC statement with SSIS.</span></span>  
  
 <span data-ttu-id="975ef-109">从 SQL Server Management Studio 或 Visual Studio 中的集成服务项目，可以启动 SQL Server 导入和导出向导。</span><span class="sxs-lookup"><span data-stu-id="975ef-109">You can start the SQL Server Import and Export wizard either from the SQL Server Management Studio or from an Integration Service project in Visual Studio.</span></span> <span data-ttu-id="975ef-110">本部分说明了从 SQL Server Management Studio 和 Visual Studio 接口运行向导。</span><span class="sxs-lookup"><span data-stu-id="975ef-110">This section provides instructions on running the wizard from both the SQL Server Management Studio and Visual Studio interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="975ef-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="975ef-111">In This Section</span></span>  
  
-   [<span data-ttu-id="975ef-112">使用 SQL Server Management Studio 导入 Siebel 数据</span><span class="sxs-lookup"><span data-stu-id="975ef-112">Import Siebel Data Using SQL Server Management Studio</span></span>](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="975ef-113">使用 Visual Studio 导入 Siebel 数据</span><span class="sxs-lookup"><span data-stu-id="975ef-113">Import Siebel Data Using Visual Studio</span></span>](../../adapters-and-accelerators/adapter-siebel/import-siebel-data-using-visual-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="975ef-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="975ef-114">See Also</span></span>  
 [<span data-ttu-id="975ef-115">使用用于 Siebel eBusiness 应用程序的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="975ef-115">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-net-framework-data-provider-for-siebel-ebusiness-applications.md)
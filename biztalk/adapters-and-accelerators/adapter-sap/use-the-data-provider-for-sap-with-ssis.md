---
title: 为 SAP 使用 SSIS 中使用的数据提供程序 |Microsoft 文档
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
ms.openlocfilehash: a8459453e153626b6a79a5dc5f57ce041ba67d1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217341"
---
# <a name="use-the-data-provider-for-sap-with-ssis"></a><span data-ttu-id="c84a3-102">为 SAP 使用 SSIS 中使用的数据提供程序</span><span class="sxs-lookup"><span data-stu-id="c84a3-102">Use the Data Provider for SAP with SSIS</span></span>
<span data-ttu-id="c84a3-103">你可以使用[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]以及 SQL Server 的集成服务 (SSIS) 将从 SAP 系统的数据导入 SQL Server 数据库表，平面文件或其他兼容的目标类型。</span><span class="sxs-lookup"><span data-stu-id="c84a3-103">You can use the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] along with SQL Server Integration Service (SSIS) to import data from an SAP system into SQL Server database tables, flat files, or other compatible destination types.</span></span> <span data-ttu-id="c84a3-104">你可以创建 SSIS 包可执行从某个 SAP 系统导入数据。</span><span class="sxs-lookup"><span data-stu-id="c84a3-104">You can create an SSIS package that can be executed to import data from an SAP system.</span></span>  
  
 <span data-ttu-id="c84a3-105">你必须使用 SQL Server 导入和导出向导将数据导入的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="c84a3-105">You must use the SQL Server Import and Export wizard to import data into the SQL Server database.</span></span> <span data-ttu-id="c84a3-106">必须提供查询以指定要导入数据。</span><span class="sxs-lookup"><span data-stu-id="c84a3-106">You must provide a query to specify data to be imported.</span></span> <span data-ttu-id="c84a3-107">你可以指定一个查询使用 SELECT 语句或 EXECQUERY 语句。</span><span class="sxs-lookup"><span data-stu-id="c84a3-107">You can specify a query using the SELECT statement or the EXECQUERY statement.</span></span> <span data-ttu-id="c84a3-108">支持的语义查询必须遵循[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c84a3-108">The query must confirm to the semantics supported by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="c84a3-109">有关语法的详细信息，以进行 SELECT 查询[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[为 SAP 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="c84a3-109">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span> <span data-ttu-id="c84a3-110">有关的 EXECQUERY 语句的语法的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 中 EXECQUERY 语句语法](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="c84a3-110">For more information about the grammar for an EXECQUERY statement for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for an EXECQUERY Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md).</span></span>  
  
 <span data-ttu-id="c84a3-111">从 SQL Server Management Studio 或 Visual Studio 中的集成服务项目，可以启动 SQL Server 导入导出向导。</span><span class="sxs-lookup"><span data-stu-id="c84a3-111">You can start the SQL Server Import Export wizard either from the SQL Server Management Studio or from an Integration Service project in Visual Studio.</span></span> <span data-ttu-id="c84a3-112">此部分提供有关从 Management Studio 和 Visual Studio 接口运行向导的说明。</span><span class="sxs-lookup"><span data-stu-id="c84a3-112">This section provides instructions on running the wizard from both the Management Studio and Visual Studio interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c84a3-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="c84a3-113">In This Section</span></span>  
  
-   [<span data-ttu-id="c84a3-114">使用 SQL Server Management Studio 导入 SAP 数据</span><span class="sxs-lookup"><span data-stu-id="c84a3-114">Import SAP Data Using SQL Server Management Studio</span></span>](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="c84a3-115">使用 Visual Studio 的导入 SAP 数据</span><span class="sxs-lookup"><span data-stu-id="c84a3-115">Import SAP Data Using Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-visual-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="c84a3-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c84a3-116">See Also</span></span>  
 [<span data-ttu-id="c84a3-117">使用.NET Framework 数据提供程序为 mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="c84a3-117">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)
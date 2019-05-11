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
# <a name="use-the-data-provider-for-sap-with-ssis"></a><span data-ttu-id="efa96-102">使用包含 SSIS 的 SAP 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="efa96-102">Use the Data Provider for SAP with SSIS</span></span>
<span data-ttu-id="efa96-103">可以使用[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]以及 SQL Server 集成服务 (SSIS) 来将数据从 SAP 系统导入 SQL Server 数据库表，平面文件或其他兼容的目标类型。</span><span class="sxs-lookup"><span data-stu-id="efa96-103">You can use the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] along with SQL Server Integration Service (SSIS) to import data from an SAP system into SQL Server database tables, flat files, or other compatible destination types.</span></span> <span data-ttu-id="efa96-104">可以创建可执行从 SAP 系统导入数据的 SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="efa96-104">You can create an SSIS package that can be executed to import data from an SAP system.</span></span>  
  
 <span data-ttu-id="efa96-105">必须使用 SQL Server 导入和导出向导导入到 SQL Server 数据库的数据。</span><span class="sxs-lookup"><span data-stu-id="efa96-105">You must use the SQL Server Import and Export wizard to import data into the SQL Server database.</span></span> <span data-ttu-id="efa96-106">必须提供查询以指定要导入数据。</span><span class="sxs-lookup"><span data-stu-id="efa96-106">You must provide a query to specify data to be imported.</span></span> <span data-ttu-id="efa96-107">可以指定一个查询使用 SELECT 语句或 EXECQUERY 语句。</span><span class="sxs-lookup"><span data-stu-id="efa96-107">You can specify a query using the SELECT statement or the EXECQUERY statement.</span></span> <span data-ttu-id="efa96-108">查询必须确认受语义[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="efa96-108">The query must confirm to the semantics supported by the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="efa96-109">有关语法的详细信息，为 SELECT 查询[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[为 SAP 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="efa96-109">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span> <span data-ttu-id="efa96-110">有关为 EXECQUERY 语句的语法详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 中的 EXECQUERY 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="efa96-110">For more information about the grammar for an EXECQUERY statement for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for an EXECQUERY Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-an-execquery-statement-in-sap.md).</span></span>  
  
 <span data-ttu-id="efa96-111">从 SQL Server Management Studio 或 Visual Studio 中的集成服务项目，可以启动 SQL Server 导入导出向导。</span><span class="sxs-lookup"><span data-stu-id="efa96-111">You can start the SQL Server Import Export wizard either from the SQL Server Management Studio or from an Integration Service project in Visual Studio.</span></span> <span data-ttu-id="efa96-112">本部分说明了从 Management Studio 和 Visual Studio 接口运行向导。</span><span class="sxs-lookup"><span data-stu-id="efa96-112">This section provides instructions on running the wizard from both the Management Studio and Visual Studio interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="efa96-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="efa96-113">In This Section</span></span>  
  
-   [<span data-ttu-id="efa96-114">使用 SQL Server Management Studio 导入 SAP 数据</span><span class="sxs-lookup"><span data-stu-id="efa96-114">Import SAP Data Using SQL Server Management Studio</span></span>](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="efa96-115">使用 Visual Studio 导入 SAP 数据</span><span class="sxs-lookup"><span data-stu-id="efa96-115">Import SAP Data Using Visual Studio</span></span>](../../adapters-and-accelerators/adapter-sap/import-sap-data-using-visual-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="efa96-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="efa96-116">See Also</span></span>  
 [<span data-ttu-id="efa96-117">使用 mySAP Business Suite 的 .NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="efa96-117">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)
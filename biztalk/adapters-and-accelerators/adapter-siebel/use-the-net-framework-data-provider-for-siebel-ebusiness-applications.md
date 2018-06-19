---
title: .NET Framework 数据提供程序用于 Siebel eBusiness Applications |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ADO.NET programming, performing operations
- Data Provider for Siebel, overview
ms.assetid: 97fe4f95-c9ae-42f1-a159-1b0e98607b31
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5acb8f96add3dcde48456751d82dc2a8e00ffe43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222237"
---
# <a name="use-the-net-framework-data-provider-for-siebel-ebusiness-applications"></a><span data-ttu-id="7a87c-102">.NET Framework 数据提供程序用于 Siebel eBusiness Applications</span><span class="sxs-lookup"><span data-stu-id="7a87c-102">Use the .NET Framework Data Provider for Siebel eBusiness Applications</span></span>
<span data-ttu-id="7a87c-103">此部分提供有关使用说明[!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="7a87c-103">This section provides instructions on using the [!INCLUDE[adoprovidersiebellong](../../includes/adoprovidersiebellong-md.md)] ([!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]).</span></span> <span data-ttu-id="7a87c-104">本部分提供有关的信息：</span><span class="sxs-lookup"><span data-stu-id="7a87c-104">This section provides information about:</span></span>  
  
-   <span data-ttu-id="7a87c-105">要连接到 Siebel 系统使用的 ADO.NET 客户端的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="7a87c-105">The connection string to connect to a Siebel system using an ADO.NET client.</span></span>  
  
-   <span data-ttu-id="7a87c-106">SELECT 和 EXEC 语句的语法。</span><span class="sxs-lookup"><span data-stu-id="7a87c-106">The syntax for SELECT and EXEC statements.</span></span>  
  
-   <span data-ttu-id="7a87c-107">使用[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使用 SSIS。</span><span class="sxs-lookup"><span data-stu-id="7a87c-107">Using the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] with SSIS.</span></span>  
  
-   <span data-ttu-id="7a87c-108">ADO.NET 接口[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]扩展。</span><span class="sxs-lookup"><span data-stu-id="7a87c-108">The ADO.NET interfaces that the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] extends.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a87c-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="7a87c-109">In This Section</span></span>  
  
-   [<span data-ttu-id="7a87c-110">扩展 Siebel 适配器 ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="7a87c-110">Extend ADO.NET Interfaces with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/extend-ado-net-interfaces-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="7a87c-111">Siebel 连接字符串的数据提供程序属性</span><span class="sxs-lookup"><span data-stu-id="7a87c-111">Data Provider properties for the Siebel Connection String</span></span>](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)  
  
-   [<span data-ttu-id="7a87c-112">Siebel 中的 SELECT 语句的语法</span><span class="sxs-lookup"><span data-stu-id="7a87c-112">Syntax for a SELECT Statement in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)  
  
-   [<span data-ttu-id="7a87c-113">Siebel 中 EXEC 语句的的语法</span><span class="sxs-lookup"><span data-stu-id="7a87c-113">Syntax for an EXEC Statement in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/syntax-for-an-exec-statement-in-siebel.md)  
  
-   [<span data-ttu-id="7a87c-114">在带有 Siebel 业务组件上运行 SELECT 查询</span><span class="sxs-lookup"><span data-stu-id="7a87c-114">Run a SELECT Query on Business Components with Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/run-a-select-query-on-business-components-with-siebel.md)  
  
-   [<span data-ttu-id="7a87c-115">使用 Siebel 运行业务服务上的执行操作</span><span class="sxs-lookup"><span data-stu-id="7a87c-115">Run an EXECUTE Operation on Business Services with Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/run-an-execute-operation-on-business-services-with-siebel.md)  
  
-   [<span data-ttu-id="7a87c-116">使用用于 Siebel 使用 SSIS 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="7a87c-116">Use the Data Provider for Siebel with SSIS</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)
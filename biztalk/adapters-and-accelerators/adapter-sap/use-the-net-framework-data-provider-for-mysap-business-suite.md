---
title: ".NET Framework 数据提供程序用于 mySAP Business Suite |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DDEX plug-in
- NET Framework Data Provider for mySAP Business Suite
- function module
- SSIS
- installation
- EXEC query
- SELECT query
- SAPDiscoveredObjects.xml
- SQL Server Integration Services
- Data Provider for SAP
- custom RFC
- installing
- configuration file
ms.assetid: 3abe9c34-b81b-4c0a-9bfd-bf05f89f29b8
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa813fa6218d5afcb470406097d745ddf93522b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="7d52a-102">使用.NET Framework 数据提供程序为 mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="7d52a-102">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="7d52a-103">此部分提供有关使用说明[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7d52a-103">This section provides instructions on using the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> <span data-ttu-id="7d52a-104">有关使用的自定义 RFC[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]和提供程序的限制，请参阅[有关.NET Framework 数据提供程序为 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="7d52a-104">For information about the custom RFC used by [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] and the limitations of the provider see [About the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d52a-105">即使您选择要安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，你必须安装在 SAP 系统某些自定义的 Rfc 使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7d52a-105">Even if you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, you must install some custom RFCs at the SAP system to use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="7d52a-106">有关如何安装自定义的 Rfc 的说明，请参阅[安装适用于 SAP 的数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="7d52a-106">For instructions on how to install the custom RFCs, see [Installing Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7d52a-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="7d52a-107">In This Section</span></span>  
  
-   [<span data-ttu-id="7d52a-108">使用 SAP 适配器扩展 ADO.NET 接口</span><span class="sxs-lookup"><span data-stu-id="7d52a-108">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="7d52a-109">有关数据提供程序类型读取 SAP 连接字符串</span><span class="sxs-lookup"><span data-stu-id="7d52a-109">Read about Data Provider types for the SAP Connection String</span></span>](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)  
  
-   [<span data-ttu-id="7d52a-110">SAP 中的 SELECT 语句的语法</span><span class="sxs-lookup"><span data-stu-id="7d52a-110">Syntax for a SELECT Statement in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)  
  
-   [<span data-ttu-id="7d52a-111">SAP 中的 EXEC 语句的语法</span><span class="sxs-lookup"><span data-stu-id="7d52a-111">Syntax for an EXEC Statement in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)  
  
-   [<span data-ttu-id="7d52a-112">对执行 SAP 查询的支持</span><span class="sxs-lookup"><span data-stu-id="7d52a-112">Support for Executing SAP Queries</span></span>](https://msdn.microsoft.com/library/dd788118.aspx)  
  
-   [<span data-ttu-id="7d52a-113">通过在 SAP 中使用 EXEC 命令调用 Rfc 和 BAPIs</span><span class="sxs-lookup"><span data-stu-id="7d52a-113">Invoking RFCs and BAPIs by using the EXEC Command in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-and-bapis-using-the-exec-command-in-sap.md)  
  
-   [<span data-ttu-id="7d52a-114">通过在 SAP 中使用 SELECT 命令执行查询</span><span class="sxs-lookup"><span data-stu-id="7d52a-114">Performing a Query by using the SELECT Command in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/run-a-query-using-the-select-command-in-sap.md)  
  
-   [<span data-ttu-id="7d52a-115">执行使用 EXECQUERY 命令 SAP 查询</span><span class="sxs-lookup"><span data-stu-id="7d52a-115">Executing an SAP Query Using the EXECQUERY Command</span></span>](../../adapters-and-accelerators/adapter-sap/execute-an-sap-query-using-the-execquery-command.md)  
  
-   [<span data-ttu-id="7d52a-116">使用的数据提供程序插件 DDEX 与 SAP</span><span class="sxs-lookup"><span data-stu-id="7d52a-116">Using the Data Provider for SAP with the DDEX Plug-in</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md)  
  
-   [<span data-ttu-id="7d52a-117">使用 Data Provider for SSIS 与 SAP</span><span class="sxs-lookup"><span data-stu-id="7d52a-117">Using the Data Provider for SAP with SSIS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)  
  
-   [<span data-ttu-id="7d52a-118">为 SAP 使用 SSRS 使用的数据提供程序</span><span class="sxs-lookup"><span data-stu-id="7d52a-118">Using the Data Provider for SAP with SSRS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)
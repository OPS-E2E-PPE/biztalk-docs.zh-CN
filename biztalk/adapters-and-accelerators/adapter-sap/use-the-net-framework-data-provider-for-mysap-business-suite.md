---
title: 使用用于 mySAP Business Suite 的.NET Framework 数据提供程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c743be7e38186c0435c91ba22fd61ad4353d1b84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372085"
---
# <a name="use-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="8df6b-102">使用用于 mySAP Business Suite 的.NET Framework 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="8df6b-102">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="8df6b-103">本部分说明了使用[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8df6b-103">This section provides instructions on using the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].</span></span> <span data-ttu-id="8df6b-104">有关使用自定义 RFC[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]和提供程序的限制，请参阅[关于.NET Framework 数据提供程序用于 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="8df6b-104">For information about the custom RFC used by [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] and the limitations of the provider see [About the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8df6b-105">即使您选择安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，必须安装一些自定义 rfc 均在 SAP 系统使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8df6b-105">Even if you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, you must install some custom RFCs at the SAP system to use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="8df6b-106">有关如何安装自定义 Rfc 的说明，请参阅[安装适用于 SAP 数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="8df6b-106">For instructions on how to install the custom RFCs, see [Installing Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8df6b-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="8df6b-107">In This Section</span></span>  
  
-   [<span data-ttu-id="8df6b-108">扩展 ADO.NET 接口，与 SAP 适配器</span><span class="sxs-lookup"><span data-stu-id="8df6b-108">Extend ADO.NET Interfaces with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/extend-ado-net-interfaces-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="8df6b-109">了解数据提供程序类型适用于 SAP 连接字符串</span><span class="sxs-lookup"><span data-stu-id="8df6b-109">Read about Data Provider types for the SAP Connection String</span></span>](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)  
  
-   [<span data-ttu-id="8df6b-110">在 SAP 中的 SELECT 语句的语法</span><span class="sxs-lookup"><span data-stu-id="8df6b-110">Syntax for a SELECT Statement in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)  
  
-   [<span data-ttu-id="8df6b-111">在 SAP 中的 EXEC 语句的语法</span><span class="sxs-lookup"><span data-stu-id="8df6b-111">Syntax for an EXEC Statement in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/syntax-for-an-exec-statement-in-sap.md)  
  
-   [<span data-ttu-id="8df6b-112">在执行 SAP 查询的支持</span><span class="sxs-lookup"><span data-stu-id="8df6b-112">Support for Executing SAP Queries</span></span>](https://msdn.microsoft.com/library/dd788118.aspx)  
  
-   [<span data-ttu-id="8df6b-113">在 SAP 中使用 EXEC 命令调用 Rfc 和 Bapi</span><span class="sxs-lookup"><span data-stu-id="8df6b-113">Invoking RFCs and BAPIs by using the EXEC Command in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-and-bapis-using-the-exec-command-in-sap.md)  
  
-   [<span data-ttu-id="8df6b-114">在 SAP 中使用 SELECT 命令执行的查询</span><span class="sxs-lookup"><span data-stu-id="8df6b-114">Performing a Query by using the SELECT Command in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/run-a-query-using-the-select-command-in-sap.md)  
  
-   [<span data-ttu-id="8df6b-115">执行 SAP 查询使用 EXECQUERY 命令</span><span class="sxs-lookup"><span data-stu-id="8df6b-115">Executing an SAP Query Using the EXECQUERY Command</span></span>](../../adapters-and-accelerators/adapter-sap/execute-an-sap-query-using-the-execquery-command.md)  
  
-   [<span data-ttu-id="8df6b-116">使用包含 DDEX 插件的 SAP 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="8df6b-116">Using the Data Provider for SAP with the DDEX Plug-in</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-the-ddex-plug-in.md)  
  
-   [<span data-ttu-id="8df6b-117">使用包含 SSIS 的 SAP 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="8df6b-117">Using the Data Provider for SAP with SSIS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)  
  
-   [<span data-ttu-id="8df6b-118">使用包含 SSRS 的 SAP 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="8df6b-118">Using the Data Provider for SAP with SSRS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)
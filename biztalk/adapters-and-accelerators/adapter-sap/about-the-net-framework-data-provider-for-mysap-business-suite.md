---
title: 有关.NET Framework Data Provider for mySAP Business Suite |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSIS
- EXEC query
- SELECT query
- SAPDiscoveredObjects.xml
- SQL Server Integration Services
- .NET Framework Data Provider for mySAP Business Suite
- Data Provider for SAP
- custom RFC
- Visual Studio DDEX plug-in
ms.assetid: 4832f789-c1d8-4c5d-a49d-b1da6b7d4bd4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ee712f6b818b94ca731d94165cd345a3249a61d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978910"
---
# <a name="about-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="45df5-102">有关.NET Framework Data Provider for mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="45df5-102">About the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="45df5-103">本部分提供有关信息[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) 及其功能。</span><span class="sxs-lookup"><span data-stu-id="45df5-103">This section provides information about the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) and its features.</span></span> <span data-ttu-id="45df5-104">有关如何使用的说明[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[使用用于 mySAP Business Suite 的.NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="45df5-104">For instructions about how to use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45df5-105">即使您选择安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，你[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]SAP 系统中安装自定义 RFC 才仍不完整。</span><span class="sxs-lookup"><span data-stu-id="45df5-105">Even if you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, your [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] is still incomplete until you install a custom RFC in the SAP system.</span></span> <span data-ttu-id="45df5-106">有关如何安装自定义 RFC 的说明，请参阅[安装适用于 SAP 数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="45df5-106">For instructions on how to install the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
 <span data-ttu-id="45df5-107">可以使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]以下方面：</span><span class="sxs-lookup"><span data-stu-id="45df5-107">You can use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] in the following ways:</span></span>  
  
- <span data-ttu-id="45df5-108">若要编写的 ADO.NET 客户端连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="45df5-108">To write an ADO.NET client to connect to the SAP system.</span></span> <span data-ttu-id="45df5-109">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]公开某些类，您可以使用提供程序接口。</span><span class="sxs-lookup"><span data-stu-id="45df5-109">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] exposes certain classes that enable you to interface with the provider.</span></span>  
  
- <span data-ttu-id="45df5-110">若要在 SAP 系统上执行的 SELECT 查询。</span><span class="sxs-lookup"><span data-stu-id="45df5-110">To execute a SELECT query on the SAP system.</span></span> <span data-ttu-id="45df5-111">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]用于此功能的自定义 RFC。</span><span class="sxs-lookup"><span data-stu-id="45df5-111">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses the custom RFC for this feature.</span></span>  
  
- <span data-ttu-id="45df5-112">若要执行 SAP 系统上的执行操作。</span><span class="sxs-lookup"><span data-stu-id="45df5-112">To execute an EXEC operation on the SAP system.</span></span> <span data-ttu-id="45df5-113">此操作可用于在 SAP 系统上执行查询。</span><span class="sxs-lookup"><span data-stu-id="45df5-113">You can use this operation to perform queries on the SAP system.</span></span>  
  
- <span data-ttu-id="45df5-114">若要执行对 SAP 系统的 EXECQUERY 操作。</span><span class="sxs-lookup"><span data-stu-id="45df5-114">To execute an EXECQUERY operation on the SAP system.</span></span> <span data-ttu-id="45df5-115">此操作可用于执行已在 SAP 系统中定义的查询。</span><span class="sxs-lookup"><span data-stu-id="45df5-115">You can use this operation to execute queries that are already defined in the SAP system.</span></span>  
  
- <span data-ttu-id="45df5-116">以，进而使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]DDEX 插件到图面上的表和函数模块从 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="45df5-116">To, in turn, use the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX plug-in to surface tables and function modules from the SAP system.</span></span> <span data-ttu-id="45df5-117">从 SAP 系统中发现的对象的名称写入配置文件，SAPDiscoveredObjects.xml。</span><span class="sxs-lookup"><span data-stu-id="45df5-117">The names of the objects discovered from the SAP system are written to a configuration file, SAPDiscoveredObjects.xml.</span></span>  
  
- <span data-ttu-id="45df5-118">若要使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]与 SQL Server Integration Services (SSIS)。</span><span class="sxs-lookup"><span data-stu-id="45df5-118">To use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] with SQL Server Integration Services (SSIS).</span></span>  
  
- <span data-ttu-id="45df5-119">若要使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]与 SQL Server Reporting Services (SSRS)。</span><span class="sxs-lookup"><span data-stu-id="45df5-119">To use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] with SQL Server Reporting Services (SSRS).</span></span>  
  
  <span data-ttu-id="45df5-120">有关执行这些任务的详细信息，请参阅[使用用于 mySAP Business Suite 的.NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="45df5-120">For more information about performing these tasks, see [Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span> <span data-ttu-id="45df5-121">有关自定义 RFC、 在 SAPDiscoveredObjects.xml 配置文件和相关的限制的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅以下链接。</span><span class="sxs-lookup"><span data-stu-id="45df5-121">For more information about the custom RFC, the SAPDiscoveredObjects.xml configuration file, and the limitations associated with the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see the following links.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="45df5-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="45df5-122">In This Section</span></span>  
  
-   [<span data-ttu-id="45df5-123">在 SAP 中提供程序所使用的自定义 Rfc</span><span class="sxs-lookup"><span data-stu-id="45df5-123">Custom RFCs Used by the Provider in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/custom-rfcs-used-by-the-provider-in-sap.md)  
  
-   [<span data-ttu-id="45df5-124">有关 SAP 在 SAPDiscoveredObjects.xml 文件</span><span class="sxs-lookup"><span data-stu-id="45df5-124">About the SAPDiscoveredObjects.xml File in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)  
  
-   [<span data-ttu-id="45df5-125">.NET Framework Data Provider for mySAP Business Suite 的限制</span><span class="sxs-lookup"><span data-stu-id="45df5-125">Limitations of the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/limitations-of-the-net-framework-data-provider-for-mysap-business-suite.md)
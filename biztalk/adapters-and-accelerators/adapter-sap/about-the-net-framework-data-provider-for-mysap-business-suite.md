---
title: 有关.NET Framework 数据提供程序为 mySAP Business Suite |Microsoft 文档
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
ms.openlocfilehash: cf6b8a1657f0731fc09c4ebc1ef1fa99e0e6ae4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217405"
---
# <a name="about-the-net-framework-data-provider-for-mysap-business-suite"></a><span data-ttu-id="c8cad-102">有关.NET Framework 数据提供程序为 mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="c8cad-102">About the .NET Framework Data Provider for mySAP Business Suite</span></span>
<span data-ttu-id="c8cad-103">本部分提供有关信息[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) 及其功能。</span><span class="sxs-lookup"><span data-stu-id="c8cad-103">This section provides information about the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) and its features.</span></span> <span data-ttu-id="c8cad-104">有关如何使用说明[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[.NET Framework 数据提供程序用于 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="c8cad-104">For instructions about how to use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8cad-105">即使您选择要安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，你[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]SAP 系统中安装自定义的 RFC 才仍不完整。</span><span class="sxs-lookup"><span data-stu-id="c8cad-105">Even if you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, your [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] is still incomplete until you install a custom RFC in the SAP system.</span></span> <span data-ttu-id="c8cad-106">有关如何安装自定义的 RFC 的说明，请参阅[安装适用于 SAP 的数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="c8cad-106">For instructions on how to install the custom RFC, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
 <span data-ttu-id="c8cad-107">你可以使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]通过以下方式：</span><span class="sxs-lookup"><span data-stu-id="c8cad-107">You can use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] in the following ways:</span></span>  
  
-   <span data-ttu-id="c8cad-108">要写入的 ADO.NET 客户端可以连接到 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="c8cad-108">To write an ADO.NET client to connect to the SAP system.</span></span> <span data-ttu-id="c8cad-109">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]公开某些使您能够使用提供程序接口的类。</span><span class="sxs-lookup"><span data-stu-id="c8cad-109">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] exposes certain classes that enable you to interface with the provider.</span></span>  
  
-   <span data-ttu-id="c8cad-110">若要在 SAP 系统上执行 SELECT 查询。</span><span class="sxs-lookup"><span data-stu-id="c8cad-110">To execute a SELECT query on the SAP system.</span></span> <span data-ttu-id="c8cad-111">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]获取此功能使用的自定义的 RFC。</span><span class="sxs-lookup"><span data-stu-id="c8cad-111">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] uses the custom RFC for this feature.</span></span>  
  
-   <span data-ttu-id="c8cad-112">若要执行对 SAP 系统的 EXEC 操作。</span><span class="sxs-lookup"><span data-stu-id="c8cad-112">To execute an EXEC operation on the SAP system.</span></span> <span data-ttu-id="c8cad-113">此操作可用于 SAP 系统上执行查询。</span><span class="sxs-lookup"><span data-stu-id="c8cad-113">You can use this operation to perform queries on the SAP system.</span></span>  
  
-   <span data-ttu-id="c8cad-114">若要执行对 SAP 系统的 EXECQUERY 操作。</span><span class="sxs-lookup"><span data-stu-id="c8cad-114">To execute an EXECQUERY operation on the SAP system.</span></span> <span data-ttu-id="c8cad-115">此操作可用于执行已在 SAP 系统中定义的查询。</span><span class="sxs-lookup"><span data-stu-id="c8cad-115">You can use this operation to execute queries that are already defined in the SAP system.</span></span>  
  
-   <span data-ttu-id="c8cad-116">用于，反过来， [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX 插件到图面表和函数模块从 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="c8cad-116">To, in turn, use the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX plug-in to surface tables and function modules from the SAP system.</span></span> <span data-ttu-id="c8cad-117">从 SAP 系统发现的对象的名称写入到配置文件，SAPDiscoveredObjects.xml。</span><span class="sxs-lookup"><span data-stu-id="c8cad-117">The names of the objects discovered from the SAP system are written to a configuration file, SAPDiscoveredObjects.xml.</span></span>  
  
-   <span data-ttu-id="c8cad-118">若要使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]与 SQL Server Integration Services (SSIS)。</span><span class="sxs-lookup"><span data-stu-id="c8cad-118">To use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] with SQL Server Integration Services (SSIS).</span></span>  
  
-   <span data-ttu-id="c8cad-119">若要使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]与 SQL Server Reporting Services (SSRS)。</span><span class="sxs-lookup"><span data-stu-id="c8cad-119">To use the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] with SQL Server Reporting Services (SSRS).</span></span>  
  
 <span data-ttu-id="c8cad-120">有关执行这些任务的详细信息，请参阅[.NET Framework 数据提供程序用于 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="c8cad-120">For more information about performing these tasks, see [Use the .NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md).</span></span> <span data-ttu-id="c8cad-121">有关自定义的 RFC、 SAPDiscoveredObjects.xml 配置文件和与关联的限制的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅以下链接。</span><span class="sxs-lookup"><span data-stu-id="c8cad-121">For more information about the custom RFC, the SAPDiscoveredObjects.xml configuration file, and the limitations associated with the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see the following links.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c8cad-122">本节内容</span><span class="sxs-lookup"><span data-stu-id="c8cad-122">In This Section</span></span>  
  
-   [<span data-ttu-id="c8cad-123">SAP 中提供程序所使用的自定义 Rfc</span><span class="sxs-lookup"><span data-stu-id="c8cad-123">Custom RFCs Used by the Provider in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/custom-rfcs-used-by-the-provider-in-sap.md)  
  
-   [<span data-ttu-id="c8cad-124">有关 SAP 中 SAPDiscoveredObjects.xml 文件</span><span class="sxs-lookup"><span data-stu-id="c8cad-124">About the SAPDiscoveredObjects.xml File in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)  
  
-   [<span data-ttu-id="c8cad-125">为 mySAP Business Suite.NET Framework 数据提供程序的限制</span><span class="sxs-lookup"><span data-stu-id="c8cad-125">Limitations of the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/limitations-of-the-net-framework-data-provider-for-mysap-business-suite.md)
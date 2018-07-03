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
# <a name="about-the-net-framework-data-provider-for-mysap-business-suite"></a>有关.NET Framework Data Provider for mySAP Business Suite
本部分提供有关信息[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) 及其功能。 有关如何使用的说明[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[使用用于 mySAP Business Suite 的.NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)。  
  
> [!NOTE]
>  即使您选择安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，你[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]SAP 系统中安装自定义 RFC 才仍不完整。 有关如何安装自定义 RFC 的说明，请参阅[安装适用于 SAP 数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。  
  
 可以使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]以下方面：  
  
- 若要编写的 ADO.NET 客户端连接到 SAP 系统。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]公开某些类，您可以使用提供程序接口。  
  
- 若要在 SAP 系统上执行的 SELECT 查询。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]用于此功能的自定义 RFC。  
  
- 若要执行 SAP 系统上的执行操作。 此操作可用于在 SAP 系统上执行查询。  
  
- 若要执行对 SAP 系统的 EXECQUERY 操作。 此操作可用于执行已在 SAP 系统中定义的查询。  
  
- 以，进而使用[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]DDEX 插件到图面上的表和函数模块从 SAP 系统。 从 SAP 系统中发现的对象的名称写入配置文件，SAPDiscoveredObjects.xml。  
  
- 若要使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]与 SQL Server Integration Services (SSIS)。  
  
- 若要使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]与 SQL Server Reporting Services (SSRS)。  
  
  有关执行这些任务的详细信息，请参阅[使用用于 mySAP Business Suite 的.NET Framework 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)。 有关自定义 RFC、 在 SAPDiscoveredObjects.xml 配置文件和相关的限制的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅以下链接。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在 SAP 中提供程序所使用的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/custom-rfcs-used-by-the-provider-in-sap.md)  
  
-   [有关 SAP 在 SAPDiscoveredObjects.xml 文件](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)  
  
-   [.NET Framework Data Provider for mySAP Business Suite 的限制](../../adapters-and-accelerators/adapter-sap/limitations-of-the-net-framework-data-provider-for-mysap-business-suite.md)
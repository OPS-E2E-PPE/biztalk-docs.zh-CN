---
title: "有关.NET Framework 数据提供程序为 mySAP Business Suite |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf6b8a1657f0731fc09c4ebc1ef1fa99e0e6ae4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="about-the-net-framework-data-provider-for-mysap-business-suite"></a>有关.NET Framework 数据提供程序为 mySAP Business Suite
本部分提供有关信息[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]) 及其功能。 有关如何使用说明[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[.NET Framework 数据提供程序用于 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)。  
  
> [!NOTE]
>  即使您选择要安装[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]作为的一部分[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]安装，你[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]SAP 系统中安装自定义的 RFC 才仍不完整。 有关如何安装自定义的 RFC 的说明，请参阅[安装适用于 SAP 的数据提供程序的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)。  
  
 你可以使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]通过以下方式：  
  
-   要写入的 ADO.NET 客户端可以连接到 SAP 系统。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]公开某些使您能够使用提供程序接口的类。  
  
-   若要在 SAP 系统上执行 SELECT 查询。 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]获取此功能使用的自定义的 RFC。  
  
-   若要执行对 SAP 系统的 EXEC 操作。 此操作可用于 SAP 系统上执行查询。  
  
-   若要执行对 SAP 系统的 EXECQUERY 操作。 此操作可用于执行已在 SAP 系统中定义的查询。  
  
-   用于，反过来， [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX 插件到图面表和函数模块从 SAP 系统。 从 SAP 系统发现的对象的名称写入到配置文件，SAPDiscoveredObjects.xml。  
  
-   若要使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]与 SQL Server Integration Services (SSIS)。  
  
-   若要使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]与 SQL Server Reporting Services (SSRS)。  
  
 有关执行这些任务的详细信息，请参阅[.NET Framework 数据提供程序用于 mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)。 有关自定义的 RFC、 SAPDiscoveredObjects.xml 配置文件和与关联的限制的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅以下链接。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [SAP 中提供程序所使用的自定义 Rfc](../../adapters-and-accelerators/adapter-sap/custom-rfcs-used-by-the-provider-in-sap.md)  
  
-   [有关 SAP 中 SAPDiscoveredObjects.xml 文件](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md)  
  
-   [为 mySAP Business Suite.NET Framework 数据提供程序的限制](../../adapters-and-accelerators/adapter-sap/limitations-of-the-net-framework-data-provider-for-mysap-business-suite.md)
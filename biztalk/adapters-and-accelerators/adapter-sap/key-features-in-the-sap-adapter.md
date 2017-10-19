---
title: "关键 SAP 适配器中的功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, deprecated features
- features, technology-related
- adapters, new features
- features, deprecated
- features, metadata-related
- librfc32u.dll
- tRFC server
- features, new
- adapters, new and deprecated features
- queued tRFC client calls
- features, operations-related
- RFC server
ms.assetid: 30e3140c-447f-42ba-a3b0-13ae66e78b0c
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b34a695e34f617f6444b728e92cb544f91448c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="key-features-in-the-sap-adapter"></a>SAP 适配器中的主要功能
本部分列出中的新的和已弃用功能[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。  
  
> [!NOTE]
>  已从早期版本使用本主题[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]帮助。  
  
## <a name="features-in-the-sap-adapter"></a>SAP 适配器中的功能  
 以下是早期版本中引入的功能[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
### <a name="technology-related-features"></a>技术相关功能  
  
|功能|注释|  
|-------------|-------------|  
|使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]与 SQL Server Reporting Services (SSRS)。|现在可以使用客户端程序[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]从 SAP 后端的数据导入 SSRS 项目并生成带数据的报表。 有关详细信息如何使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]与 SSRS，请参阅[数据提供程序用于与 SSRS SAP](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)。 有关 SSRS 的详细信息，请参阅[SQL Server Reporting Services](https://msdn.microsoft.com/library/ms159106.aspx)。|  
|用于调用查询在 SAP 系统中定义的支持|[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]公开某一操作，EXECQUERY，可用来执行在 SAP 系统中定义的查询。 有关如何使用 EXECQUERY 功能的详细信息，请参阅 [执行 SAP 查询支持

](https://msdn.microsoft.com/library/dd788118.aspx).|  
|支持使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 Microsoft Office SharePoint Server (MOSS) |适配器可用于显示从 SAP 系统到 MOSS 门户上的数据。 有关详细信息，请参阅[SAP 适配器将用于 SharePoint](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)。 |  
  
### <a name="metadata-related-features"></a>元数据相关的功能  
  
|功能|注释|  
|-------------|-------------|  
|**DataTypesBehavior**绑定属性|[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]提供复杂绑定属性， **DataTypesBehavior**，，允许适配器中 SAP 系统遇到特殊值时控制的适配器行为的客户端。 有关此绑定属性的详细讨论，请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。|  
  
### <a name="operations-related-features"></a>与操作相关的功能  
  
|功能|注释|  
|-------------|-------------|  
|调用由 RFC 所需的外部程序的支持|[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]提供的绑定属性， **RfcAllowStartProgram**可以设置以启用 RFC 客户端库，以调用外部程序，如果任何，所需的特定 RFC。 有关此绑定属性的详细信息，请参阅[阅读有关 BizTalk 适配器用于 mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。|  
|支持在单个调用中发送多个 Idoc|SAP 适配器现在支持将多个相同类型的 Idoc 发送单个适配器调用中。|  
  
### <a name="other-features"></a>其他功能  
  
|功能|注释|  
|-------------|-------------|  
|使用中的适配器的新方法[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]|[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以在 BizTalk 中作为 WCF 自定义端口或 WCF SAP 端口使用。 如果你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过 WCF 自定义端口，你不需要添加到的 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]默认情况下的管理控制台。 但是，如果你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过 WCF SAP 端口，您必须首先添加到 WCF SAP 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关详细信息，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。|  
  
## <a name="deprecated-features-in-the-sap-adapter"></a>SAP 适配器中已弃用的功能  
 下列各节列出的受支持在以前版本的适配器，但这不受支持的当前版本中的功能[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
### <a name="enablebusinessobjects-binding-property-deprecated"></a>弃用的 EnableBusinessObjects 绑定属性  
 此绑定属性中已弃用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 此绑定属性用于确定是否在使用时生成元数据时，会显示 BAPI 节点[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。  
  
## <a name="see-also"></a>另请参阅  
 [为 mySAP Business Suite 了解 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)
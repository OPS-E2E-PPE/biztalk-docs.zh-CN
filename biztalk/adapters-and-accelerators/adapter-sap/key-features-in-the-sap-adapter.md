---
title: 关键 SAP 适配器中的功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c227fa80a7152ade8bcc6f745d6c5fb2f760715
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373280"
---
# <a name="key-features-in-the-sap-adapter"></a>SAP 适配器的主要功能
本部分列出了中的新的和已弃用功能[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。  
  
> [!NOTE]
>  本主题已被使用从以前版本的[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]帮助。  
  
## <a name="features-in-the-sap-adapter"></a>SAP 适配器的功能  
 以下是早期版本中引入的功能[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
### <a name="technology-related-features"></a>与技术相关的功能  
  
|                                                            功能                                                             |                                                                                                                                                                                                                                                                                              注释                                                                                                                                                                                                                                                                                               |
|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]用于 SQL Server Reporting Services (SSRS)。 | 现在可以使用客户端程序[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]数据从 SAP 后端导入到 SSRS 项目和生成带数据的报表。 有关如何使用的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]与 SSRS，请参阅[使用包含 SSRS 的 SAP 数据提供程序](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)。 有关 SSRS 的详细信息，请参阅[SQL Server Reporting Services](https://msdn.microsoft.com/library/ms159106.aspx)。 |
|                                     调用在 SAP 系统中定义的查询支持                                      |                                                                                                                                                           [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]公开的操作，EXECQUERY，可用于执行 SAP 系统中定义的查询。 有关如何使用 EXECQUERY 功能的详细信息，请参阅 [对执行 SAP 查询的支持                                                                                                                                                            |

](https://msdn.microsoft.com/library/dd788118.aspx).|  
|支持使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与 Microsoft Office SharePoint Server (MOSS) |适配器可用于提供到 MOSS 门户上的 SAP 系统中的数据。 有关详细信息，请参阅[使用包含 SharePoint 的 SAP 适配器](../../adapters-and-accelerators/adapter-sap/use-the-sap-adapter-with-sharepoint.md)。 |  
  
### <a name="metadata-related-features"></a>与元数据相关的功能  
  
|                功能                 |                                                                                                                                                                                                                                                                                                   注释                                                                                                                                                                                                                                                                                                    |
|----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **DataTypesBehavior**绑定属性 | [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]附带[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]提供了复杂的绑定属性**DataTypesBehavior**，它使适配器客户端来控制在 SAP 系统遇到特殊值时，适配器的行为。 有关此绑定属性的详细讨论，请参阅[了解用于 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。 |
  
### <a name="operations-related-features"></a>与操作相关的功能  
  
|                          功能                          |                                                                                                                                                                                                                                                 注释                                                                                                                                                                                                                                                  |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 调用外部程序所需的 RFC 支持 | [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]提供的绑定属性， **RfcAllowStartProgram** ，可以设置以启用 RFC 客户端库来调用外部程序，如果任何，所需的特定 RFC。 有关此绑定属性的详细信息，请参阅[了解用于 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。 |
|    支持在单个调用中发送多个 Idoc    |                                                                                                                                                                                                      SAP 适配器现支持将多个相同类型的 Idoc 发送适配器的单一调用中。                                                                                                                                                                                                      |
  
### <a name="other-features"></a>其他功能  
  
|                                                        功能                                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                注释                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
|-----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 使用中的适配器的新方法 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] | [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以在 BizTalk 中可作为 WCF 自定义端口或 WCF SAP 端口使用。 如果你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过 WCF 自定义端口，您不需要添加到 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的默认情况下。 但是，如果你想要使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过 WCF SAP 端口，必须首先添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关详细信息，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。 |
  
## <a name="deprecated-features-in-the-sap-adapter"></a>SAP 适配器中弃用的功能  
 以下各节列出了的功能，支持在以前版本的适配器，但这不受支持的当前版本中[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
### <a name="enablebusinessobjects-binding-property-deprecated"></a>不推荐使用 EnableBusinessObjects 绑定属性  
 此绑定属性中已弃用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]随[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 此绑定属性用于确定是否使用时生成元数据时，会显示 BAPI 节点[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。  
  
## <a name="see-also"></a>请参阅  
 [了解用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)
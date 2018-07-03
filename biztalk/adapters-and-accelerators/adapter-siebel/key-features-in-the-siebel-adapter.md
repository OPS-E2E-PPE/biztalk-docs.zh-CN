---
title: 主要在 Siebel 适配器的功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- features, performance-related
- adapter features, new
- features, technology-related
- features, metadata-related
- adapter features, operations-related
- adapter features, performance-related
- features, new
- features, operations-related
- adapter features, metadata-related
ms.assetid: 4612c9ab-810e-4c69-9168-a25c58682e71
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4896256555ea6b721d917c992c9c41fd3737f101
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018322"
---
# <a name="key-features-in-the-siebel-adapter"></a>Siebel 适配器的主要功能
本部分列出了中的新增功能[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。  
  
> [!NOTE]
>  本主题已被使用从以前版本的[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]帮助。  
  
## <a name="new-features-in-the-siebel-adapter"></a>Siebel 适配器中的新增功能  
 以下是此版本中引入的新功能[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
### <a name="technology-related-features"></a>与技术相关的功能  
  
|                                                                    功能                                                                     |                                                                                                               注释                                                                                                               |
|------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 支持使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Microsoft Office SharePoint Server (MOSS) | 适配器可用于提供从 Siebel 系统到 MOSS 门户上的数据。 有关详细信息，请参阅[与 Microsoft Office SharePoint Server 使用 Siebel 适配器](https://msdn.microsoft.com/library/dd788017.aspx)。 |
  
### <a name="operations-related-features"></a>与操作相关的功能  
  
|功能|注释|  
|-------------|-------------|  
|对关联操作业务组件上的支持|通过指定搜索表达式的父记录和子记录，则可以将关联适配器客户端。 这是仅适用于多值属性的组 (包含 MVG) 字段的业务组件。 请注意，搜索表达式应筛选的父和子业务组件的一个记录。|  
|取消关联操作业务组件上的支持|通过指定搜索表达式的父记录和子记录，则可以取消关联适配器客户端。 这是仅适用于多值属性的组 (包含 MVG) 字段的业务组件。 请注意，搜索表达式必须筛选的父和子业务组件的一个记录。|  
|对多值链接查询的支持|适配器客户端可以查询通过指定的父记录和多值的字段名称与父记录关联的子记录。 这是仅适用于多值属性的组 (包含 MVG) 字段的业务组件。|  
  
### <a name="other-features"></a>其他功能  
  
|                                                        功能                                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  注释                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|-----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 使用中的适配器的新方法 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] | [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可以在 BizTalk 中可作为 WCF 自定义端口或 Wcf-siebel 端口使用。 如果你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过 WCF 自定义端口，您不需要添加到 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的默认情况下。 但是，如果你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过 WCF Siebel 端口，必须首先添加 Wcf-siebel 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关详细信息，请参阅[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。 |
  
## <a name="see-also"></a>请参阅  
 [了解用于 Siebel eBusiness 应用程序的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)
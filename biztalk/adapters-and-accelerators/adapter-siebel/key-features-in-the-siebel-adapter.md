---
title: "关键 Siebel 适配器中的功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 295ff8b13358109a5d4737fb5f9325b3c9caa0f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="key-features-in-the-siebel-adapter"></a>Siebel 适配器中的主要功能
本部分列出中的新功能[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。  
  
> [!NOTE]
>  已从早期版本使用本主题[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]帮助。  
  
## <a name="new-features-in-the-siebel-adapter"></a>Siebel 适配器中的新增功能  
 以下是此版本中引入的新功能[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
### <a name="technology-related-features"></a>技术相关功能  
  
|功能|注释|  
|-------------|-------------|  
|支持使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与 Microsoft Office SharePoint Server (MOSS)|适配器可用于显示从 MOSS 门户到 Siebel 系统的数据。 有关详细信息，请参阅[Siebel 适配器使用 Microsoft Office SharePoint Server](https://msdn.microsoft.com/library/dd788017.aspx)。|  
  
### <a name="operations-related-features"></a>与操作相关的功能  
  
|功能|注释|  
|-------------|-------------|  
|在业务组件上的关联操作的支持|适配器客户端可以将记录通过指定搜索表达式父和子记录相关联。 这是仅适用于多值的组 (MVG) 字段的业务组件。 请注意，搜索表达式应筛选恰好一个记录的父和子业务组件。|  
|在业务组件上的取消操作的支持|通过指定父搜索表达式的记录和子记录，则可以取消关联适配器客户端。 这是仅适用于多值的组 (MVG) 字段的业务组件。 请注意，搜索表达式必须筛选恰好一个记录的父和子业务组件。|  
|支持的多值链接查询|适配器客户端可以查询通过指定的父记录和多值的字段名称与父记录关联的子记录。 这是仅适用于多值的组 (MVG) 字段的业务组件。|  
  
### <a name="other-features"></a>其他功能  
  
|功能|注释|  
|-------------|-------------|  
|使用中的适配器的新方法[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]|[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]可以在 BizTalk 中作为 WCF 自定义端口或 WCF Siebel 端口使用。 如果你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过 WCF 自定义端口，你不需要添加到的 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]默认情况下的管理控制台。 但是，如果你想要使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过 WCF Siebel 端口，您必须首先添加到在 WCF Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 有关详细信息，请参阅[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。|  
  
## <a name="see-also"></a>另请参阅  
 [为 Siebel eBusiness 应用程序了解的 BizTalk Adapter](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)
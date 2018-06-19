---
title: 为 Siebel 适配器客户端的功能 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter features
- features, of the adapter
ms.assetid: 11792629-a692-4378-b522-d33484ee8acb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f929b14415265c4ad9894a16b87294dccd4e906f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222069"
---
# <a name="features-for-siebel-adapter-clients"></a>Siebel 适配器客户端的的功能
除了对在的主题中讨论的功能[概述的 BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]提供以下功能，可用于适配器客户端：  
  
-   **配置使用绑定属性的适配器的支持**。 适配器客户端可以配置[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过生成元数据时指定某些绑定属性。 有关详细信息，请参阅[了解针对 Siebel 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。  
  
-   **有关操作参数的 null 值的支持**。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使适配器客户端能够为业务对象操作参数使用 XSD"nillable"属性提供 null 值。 适配器不将具有 null 值的字段传递给 Siebel 系统。  
  
-   **对 XML 数据进行流式处理支持**。 适配器客户端可以流式传输的数据或从[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使用**XMLReader**或**XMLWriter**接口。  
  
-   **BizTalk Server 中的动态端口支持**。 通过 BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持动态端口，使动态路由的消息从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]基于消息上下文属性。 有关详细信息，请参阅[Siebel 适配器使用配置动态端口](../../adapters-and-accelerators/adapter-siebel/configure-dynamic-ports-with-the-siebel-adapter.md)。  
  
-   **对消息版本管理的支持**。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持将消息版本控制。 有关不同的消息架构在将来的版本，这会使支持[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[消息版本控制支持](../../adapters-and-accelerators/adapter-siebel/message-versioning-support2.md)。  
  
-   **对性能计数器支持**。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持适配器客户端可以使用的基于 WCF 的性能计数器。 有关性能计数器的详细信息，请参阅[使用性能计数器与 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/use-performance-counters-with-the-siebel-adapter.md)。  
  
    > [!NOTE]
    >  此功能不提供与早期版本的适配器的向后兼容性。  
  
-   **支持编码的 XML 元素名称**。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]显示从企业应用程序的实体，并且在 XML 中的元素名称。 下划线是可以包含在元素名称的唯一特殊字符。 因此，下划线用于编码带有特殊字符的元素名称。 例如，`emp$name`编码为`emp_x0024_name`。  
  
## <a name="see-also"></a>另请参阅  
 [为 Siebel eBusiness 应用程序的 BizTalk Adapter 概述](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)
---
title: Siebel 适配器客户端的功能 |Microsoft Docs
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
ms.openlocfilehash: 8b168fcab312f53e38556b1e60a81f97538608fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371684"
---
# <a name="features-for-siebel-adapter-clients"></a>Siebel 适配器客户端的功能
除了讨论的主题的功能[概述的 BizTalk 适配器用于 Siebel eBusiness 应用程序](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)，则[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]提供可用于适配器客户端的以下功能：  
  
- **配置使用绑定属性的适配器的支持**。 适配器客户端可以配置[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过生成元数据时指定绑定的某些属性。 有关详细信息，请参阅[了解关于 BizTalk Adapter for Siebel 绑定属性](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)。  
  
- **操作参数的 null 值的支持**。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]使适配器客户端能够为业务对象操作参数使用 XSD"nillable"属性提供 null 值。 适配器不将具有 null 值的字段传递到 Siebel 系统。  
  
- **对 XML 数据进行流式处理支持**。 适配器客户端可以流式传输数据来自或发往[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]通过使用**XMLReader**或**XMLWriter**接口。  
  
- **支持在 BizTalk Server 中的动态端口**。 通过 BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，则[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持动态端口，使动态路由的消息从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]基于消息上下文属性。 有关详细信息，请参阅[使用 Siebel 适配器配置动态端口](../../adapters-and-accelerators/adapter-siebel/configure-dynamic-ports-with-the-siebel-adapter.md)。  
  
- **对消息版本控制的**。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持消息版本控制。 这支持不同的消息架构在将来的版本的[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[消息版本控制支持](../../adapters-and-accelerators/adapter-siebel/message-versioning-support2.md)。  
  
- **对性能计数器支持**。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]支持适配器客户端可以使用的基于 WCF 的性能计数器。 有关性能计数器的详细信息，请参阅[使用 Siebel 适配器的使用性能计数器](../../adapters-and-accelerators/adapter-siebel/use-performance-counters-with-the-siebel-adapter.md)。  
  
  > [!NOTE]
  >  此功能不提供向后兼容早期版本的适配器。  
  
- **支持编码的 XML 元素名称**。 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将企业应用程序中的实体表示为 XML 中的元素名称。 下划线是可以包含的元素名称中的唯一特殊字符。 因此，下划线用于对元素名称包含特殊字符进行编码。 例如，`emp$name`编码为`emp_x0024_name`。  
  
## <a name="see-also"></a>请参阅  
 [用于 Siebel eBusiness 应用程序的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)
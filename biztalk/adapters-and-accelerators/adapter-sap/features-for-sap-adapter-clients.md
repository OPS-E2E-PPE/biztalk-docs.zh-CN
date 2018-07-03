---
title: SAP 适配器客户端的功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic ports
- adapters, features
- XML data streaming
- performance counters
- adapters, support for dynamic ports in BizTalk Server
- adapters, support for message versioning
- adapters, support for XML data streaming
- adapters, support for performance counters
- adapters, support for configuring adapters using binding properties
ms.assetid: 9003c2c1-931d-405e-9a58-660032195af7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 411ae3a1b044b89a0ef5390a0f0ad26430909bcb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984630"
---
# <a name="features-for-sap-adapter-clients"></a>SAP 适配器客户端的功能
除了讨论的主题的功能[用于 mySAP Business Suite 的 BizTalk 适配器的体系结构概述](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)，则[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还提供了以下功能，可用于适配器客户端。  
  
- **配置使用绑定属性的适配器的支持**。 适配器客户端可以配置[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]通过指定特定绑定属性。 例如，客户端可以配置适配器后，若要通过指定的值指定适配器的连接池中的最大连接数**MaxConnectionsPerSystem**属性绑定。 有关详细信息，请参阅[了解用于 mySAP Business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  
  
- **支持在 BizTalk Server 中的动态端口**。 通过 BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，则[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持动态端口，使动态路由的消息从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]基于消息上下文属性。 有关详细信息，请参阅[配置动态端口](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md)。
  
- **对消息版本控制的**。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]支持消息版本控制以启用对不同的消息架构的将来版本中支持[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[消息版本控制支持](../../adapters-and-accelerators/adapter-sap/message-versioning-support1.md)。  
  
  > [!NOTE]
  >  此功能不提供向后兼容早期版本的适配器。  
  
- **对性能计数器支持**。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]以供适配器客户端支持的基于 WCF 的性能计数器。 有关性能计数器的详细信息，请参阅[使用与 SAP 适配器的性能计数器](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
 [用于 mySAP Business Suite 的 BizTalk 适配器的体系结构概述](../../adapters-and-accelerators/adapter-sap/architecture-overview-of-the-biztalk-adapter-for-mysap-business-suite.md)
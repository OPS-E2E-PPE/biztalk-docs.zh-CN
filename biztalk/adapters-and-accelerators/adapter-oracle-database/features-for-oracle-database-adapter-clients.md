---
title: Oracle 数据库适配器客户端的功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- data streaming, support for
- binding properties
- adapter, features
- adapters, configuring
- message versioning, support for
- XML data streaming
- performance counters, support for
- dynamic ports in BizTalk, support for
- data streaming
ms.assetid: 63b52573-80a5-4206-95c3-478b86718fee
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f369c3a0689898bafb5383e333b980398054d0ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376725"
---
# <a name="features-for-oracle-database-adapter-clients"></a>Oracle 数据库适配器客户端的功能
除了讨论的主题的功能[概述的 BizTalk 适配器用于 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)，则[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]还提供了可用于适配器客户端的以下功能：  
  
- **配置使用绑定属性的适配器的支持**。 适配器客户端可以配置[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]通过指定特定绑定属性。 例如，客户端可以配置适配器后，通过设置使用 ODP.NET 连接池**UseOracleConnectionPool**属性绑定。 有关详细信息，请参阅[用于 Oracle 数据库配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)。  
  
- **操作参数的 null 值的支持**。 适配器客户端可以为输入 XML 中使用"nil"属性的操作参数提供 null 值。  
  
- **支持在 BizTalk 中的动态端口**。 通过 BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，则[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持动态端口，使动态路由的消息从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]基于消息上下文属性。 有关详细信息，请参阅[配置动态端口](../../adapters-and-accelerators/adapter-oracle-database/configure-dynamic-ports-in-the-oracle-database-adapter.md)。  
  
- **对性能计数器支持**。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]以供适配器客户端支持的基于 WCF 的性能计数器。 有关性能计数器的详细信息，请参阅[性能计数器](../../core/performance-counters.md)。  
  
## <a name="see-also"></a>请参阅  
 [用于 Oracle 数据库的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)
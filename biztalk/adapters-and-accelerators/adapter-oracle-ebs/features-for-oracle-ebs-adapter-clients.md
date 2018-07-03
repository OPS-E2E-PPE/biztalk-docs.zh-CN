---
title: Oracle EBS 适配器客户端的功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50256fb7-5f0c-4b32-87e6-98f49da0b360
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 974f75eaa2416ae11572a1b29eb682d6bc7c0172
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968878"
---
# <a name="features-for-oracle-ebs-adapter-clients"></a>Oracle EBS 适配器客户端的功能
除了讨论的主题的功能[概述的 BizTalk 适配器用于 Oracle E-business Suite](http://msdn.microsoft.com/library/4f18fa2e-4e97-4c28-b38d-fc39ac53789e)，则[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]还提供了可用于适配器客户端的以下功能：  
  
- **配置使用绑定属性的适配器的支持**。 适配器客户端可以配置[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过指定特定绑定属性。 例如，客户端可以配置适配器后，通过设置使用 ODP.NET 连接池**UseOracleConnectionPool**属性绑定。 有关详细信息，请参阅[了解关于 BizTalk Adapter for Oracle E-business Suite 绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。  
  
- **操作参数的 null 值的支持**。 适配器客户端可以为输入 XML 中使用"nil"属性的操作参数提供 null 值。  
  
- **支持在 BizTalk 中的动态端口**。 通过 BizTalk [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]，则[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持动态端口，使动态路由的消息从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]基于消息上下文属性。 有关详细信息，请参阅[中的 SQL 适配器配置动态端口](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md)。  
  
## <a name="see-also"></a>请参阅  
[了解用于 Oracle E-Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)
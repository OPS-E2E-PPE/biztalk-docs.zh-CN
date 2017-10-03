---
title: "优化通过限制的主机的资源使用情况 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host throttling
- performance, host throttling
ms.assetid: 823b431d-707d-4201-9a6e-4a879e767b66
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fa30cb66371ef519741658dec47e08f6f92e871
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="optimizing-resource-usage-through-host-throttling"></a>通过主机阻止优化资源使用率
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用多种不同的 Microsoft 技术，其中每个可以使用的内存、 磁盘和 CPU 资源在 BizTalk server 和包含 BizTalk Server 数据库的 SQL 服务器上可用的重要部分。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用限制的机制，来帮助管理可用资源，以最大程度减少资源使用争用的使用。 本主题讨论此机制的设计。 有关如何调整的限制值的信息，请参阅[BizTalk Server 性能优化使用设置仪表板](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [主机限制？](../core/what-is-host-throttling.md)  
  
-   [BizTalk Server 如何实施限制的主机](../core/how-biztalk-server-implements-host-throttling.md)  
  
-   [主机限制性能计数器](../core/host-throttling-performance-counters.md)  
  
-   [限制的设计建议](../core/throttling-design-recommendations.md)
---
title: 优化资源使用情况通过主机阻止 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host throttling
- performance, host throttling
ms.assetid: 823b431d-707d-4201-9a6e-4a879e767b66
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ada7b36453945b676db8aa897d7e0e862d3907
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262947"
---
# <a name="optimizing-resource-usage-through-host-throttling"></a>通过主机阻止优化资源使用情况
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用多个不同的 Microsoft 技术，其中每个可使用内存、 磁盘和 BizTalk server 和包含 BizTalk Server 数据库的 SQL 服务器上的可用 CPU 资源的重要部分。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 利用阻止机制来帮助管理可用资源，以最大程度减少使用的资源争用的使用。 本主题讨论此机制的设计。 有关如何调整阻止值的信息，请参阅[使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [主机限制概述](../core/what-is-host-throttling.md)  
  
-   [BizTalk Server 如何实现主机限制](../core/how-biztalk-server-implements-host-throttling.md)  
  
-   [主机限制性能计数器](../core/host-throttling-performance-counters.md)  
  
-   [限制设计建议](../core/throttling-design-recommendations.md)
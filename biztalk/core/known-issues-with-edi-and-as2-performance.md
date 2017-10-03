---
title: "已知问题 EDI 和 AS2 性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c47294f9-f728-4b6b-abe1-578434eb54df
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e034cf228ee92157c4b29c36660111bb1856c358
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-and-as2-performance"></a>EDI 和 AS2 性能的已知问题
本主题介绍有关 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的性能和 AS2 解决方案的已知问题。  
  
## <a name="performance-considerations-for-edi-and-as2-status-reporting"></a>EDI 和 AS2 状态报告在性能方面的注意事项  
 激活 EDI 或 AS2 状态报告后，为多少消息执行状态报告可能会影响系统的性能。 为 EDI 或 AS2 处理选择了“存储事务集/负载以用于报告”属性后，为多大的消息执行状态报告可能会影响系统的性能。  
  
 BAMPrimaryImport 数据库中用于 EDI 或 AS2 状态报告的表已进行了优化。 不需要进行进一步的优化。 但可以增大 BAM 主导入数据库中数据的存档速率，方法是更改 BAMPrimaryImport 数据库中活动实例数据的存档时段。 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的“存档主导入数据库数据”。  
  
 事务集/负载数据存储在 BizTalkDTADb 数据库中。 有关此数据库性能的详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的“了解 DTA 跟踪性能行为”。  
  
 系统的性能还可能受在系统配置中启用的状态报告的程度影响。 通过禁用特定类型的状态报告，或许能够提高性能。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 和 AS2 解决方案疑难解答](../core/troubleshooting-edi-and-as2-solutions.md)
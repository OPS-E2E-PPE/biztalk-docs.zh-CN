---
title: 使用 EDI 和 AS2 性能的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c47294f9-f728-4b6b-abe1-578434eb54df
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cf091226c91660568d56b53618f04cbe4364318
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330539"
---
# <a name="known-issues-with-edi-and-as2-performance"></a>EDI 和 AS2 性能的已知的问题
本主题介绍有关 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的性能和 AS2 解决方案的已知问题。  
  
## <a name="performance-considerations-for-edi-and-as2-status-reporting"></a>EDI 和 AS2 状态报告在性能方面的注意事项  
 激活 EDI 或 AS2 状态报告后，为多少消息执行状态报告可能会影响系统的性能。 为 EDI 或 AS2 处理选择了“存储事务集/负载以用于报告”属性后，为多大的消息执行状态报告可能会影响系统的性能。  
  
 BAMPrimaryImport 数据库中用于 EDI 或 AS2 状态报告的表已进行了优化。 不需要进行进一步的优化。 但可以增大 BAM 主导入数据库中数据的存档速率，方法是更改 BAMPrimaryImport 数据库中活动实例数据的存档时段。 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的“存档主导入数据库数据”。  
  
 事务集/负载数据存储在 BizTalkDTADb 数据库中。 有关此数据库性能的详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的“了解 DTA 跟踪性能行为”。  
  
 系统的性能还可能受在系统配置中启用的状态报告的程度影响。 通过禁用特定类型的状态报告，或许能够提高性能。  
  
## <a name="see-also"></a>请参阅  
 [EDI 和 AS2 解决方案的疑难解答](../core/troubleshooting-edi-and-as2-solutions.md)
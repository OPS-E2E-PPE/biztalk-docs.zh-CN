---
title: 发行阶段的建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5ac72aa-decd-4b3e-be34-e585e54568b3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a186306a951b249c7bcadb243549c8761f6408fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397967"
---
# <a name="release-phase-recommendations"></a>发行阶段的建议
发布阶段涉及到将传播到生产硬件上现在已验证的系统。  
  
## <a name="propagate-test-bed-optimizations-to-production-systems"></a>传播到生产系统的测试平台优化  
 传播系统项目和配置到生产硬件上的，然后启动它最多进程是一个相对较简单的过程。 但是，在实践中，有需要就可以轻松地错过了此阶段期间的性能考虑事项：  
  
-   **验证的传播平台优化**。 在实现和验证，它很常见实现任意数量的平台级别的性能优化。  
  
     例如时使用隔离的适配器 HTTP 等 Internet 信息服务器 (IIS) 上，有大量的常见性能优化，可以使用如增加适配器将在其中运行的 IIS 中的进程数。 所有此类的性能优化之前必须跟踪和传播到生产环境也发行，找到。  
  
-   **设置和自动执行数据的备份，日志传送，数据保留期配置和清除任务**。 作为用于生产的一部分，备份和清除 （适用于示例中，BizTalk 跟踪数据库和 BAM 数据库） 数据库的频率是认证的可持续性的关键，因此这些设置必须迁移到它们尚未存在的生产环境。  
  
## <a name="see-also"></a>请参阅  
 [分阶段描述的项目规划建议](../core/project-planning-recommendations-by-phase.md)   
 [需求阶段的建议](../core/requirements-phase-recommendations.md)   
 [设计阶段的建议](../core/design-phase-recommendations.md)   
 [实现阶段的建议](../core/implementation-phase-recommendations.md)   
 [验证阶段的建议](../core/verification-phase-recommendations.md)
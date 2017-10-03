---
title: "发布阶段建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5ac72aa-decd-4b3e-be34-e585e54568b3
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46a38a8a06fac8dc35fed4d965ea9b7952c5fdfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="release-phase-recommendations"></a>发行阶段的建议
发布阶段涉及传播到生产硬件上的现在已验证的系统。  
  
## <a name="propagate-test-bed-optimizations-to-production-systems"></a>传播到生产系统的测试平台优化  
 传播的系统项目和到生产硬件上的配置和达启动过程是一个相对较简单的过程。 但是，在实践中，有要考虑在此阶段可以轻松地丢失性能有关的事项：  
  
-   **验证平台优化会传播**。 在实现和验证中，很容易实现任意数量的平台级别的性能优化。  
  
     例如，在 Internet 信息服务 (IIS) 上使用诸如 HTTP 这样的独立适配器时，有许多常见的可以使用的性能优化，如在 IIS 中增加适配器将在其中运行的进程数。 任何这种性能优化之前必须跟踪版本，且将其传播到生产环境也，找到。  
  
-   **设置和自动执行数据备份，日志传送，数据保持期配置和清除任务**。 作为用于生产环境的认证的一部分，备份和清除数据库的频率（例如，BizTalk 跟踪数据库和 BAM 数据库）是可持续性的关键，因此那些设置必须迁移到它们尚未存在的生产环境。  
  
## <a name="see-also"></a>另请参阅  
 [项目规划阶段的建议](../core/project-planning-recommendations-by-phase.md)   
 [要求阶段建议](../core/requirements-phase-recommendations.md)   
 [设计阶段建议](../core/design-phase-recommendations.md)   
 [实现阶段建议](../core/implementation-phase-recommendations.md)   
 [验证阶段建议](../core/verification-phase-recommendations.md)
---
title: 验证阶段的建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00663354-ce5d-4391-b835-89940c92c1ce
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48f7c28edd87ff0f1c9f780a5999be542eaaa398
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292591"
---
# <a name="verification-phase-recommendations"></a>验证阶段的建议
系统代码编写完成后，它已准备好进行稳定和可验证的发布条件。 此阶段通常称为稳定阶段。 此阶段的最终目标是识别并修复 bug，并证明系统准备好进行生产。 此阶段中，因此，涉及到系统的候选发布版本上测试最后一的轮。  
  
 候选发布版本是版本 （通常是最新） 被视为完整的系统，稳定，足以成为发布的版本验证测试全部通过。 这经验证的方法是成功完成一系列功能、 性能和压力测试，以验证它确实已准备。  
  
## <a name="test-to-verify-sustainable-throughput-and-latency"></a>测试以验证可持续吞吐量和延迟  
 验证测试的性能与实施阶段并行启动，但需要最终确定已被证实将成功地承受发布标准测试的完整集的候选发布版本。 理想情况下，到候选发布版的任何更改不会在最终测试阶段，以便置信度较高尚未引入回归。 在实践中，这是非常困难并更改已签入生成，因为必须返工回归的风险进行评估。  
  
 例如，如果引入管道或业务流程等系统项目的基础更改，性能测试可能需要按顺序重新运行验证新的候选。  
  
 若要确保系统准备好进行生产，必须验证以可持续的方式端到端上已经过测试。 这意味着所有操作活动，如都数据库维护、 操作查询和计划内和计划外的停机必须进行测试，如本主题中所定义[可承受性能？](../core/what-is-sustainable-performance.md) 这是最后一次机会来验证对系统的准备情况，所以务必要合并的最终测试过程中可持续性能测试的完整套件。  
  
## <a name="identify-bottlenecks-and-adjust-hardware-or-solution-to-remove-goal-blockers"></a>识别瓶颈并调整硬件或解决方案以排除障碍  
 在实践中，是常见的最终测试传递测试平台是更接近于生产硬件方面比测试平台的开发。  它是重要的是，因此，在最终测试阶段利用此机会可以标识系统中的任何新的或现有的瓶颈，并确定它们是否足够大以进行调整。 即使硬件无需立即进行调整，发现最普遍的系统瓶颈，将提供宝贵的计划和操作信息。  
  
 例如，如果系统通过生产负载状况，但它观察到 MessageBox 服务器上的物理磁盘空闲时间太少 （例如，小于 20%)，然后在生产期间监视此磁盘可以将标识为一个关键的运行状况指示符。 此外，增加系统的负载功能的计划现在可以包括磁盘子系统需要改进的知识。  
  
## <a name="see-also"></a>请参阅  
 [分阶段描述的项目规划建议](../core/project-planning-recommendations-by-phase.md)   
 [需求阶段的建议](../core/requirements-phase-recommendations.md)   
 [设计阶段的建议](../core/design-phase-recommendations.md)   
 [实现阶段的建议](../core/implementation-phase-recommendations.md)   
 [发行阶段的建议](../core/release-phase-recommendations.md)
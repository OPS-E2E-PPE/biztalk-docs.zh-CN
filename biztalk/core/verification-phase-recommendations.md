---
title: "验证阶段建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00663354-ce5d-4391-b835-89940c92c1ce
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25344eafc37f492474b3f0bb36318afaf566829a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="verification-phase-recommendations"></a>验证阶段的建议
系统代码编写完成后，即准备好进行稳定工作并验证发布标准。 此阶段通常称为稳定阶段。 此阶段的最终目的是发现并修复错误，以及验证系统是否已准备就绪可以投入生产。 因此，此阶段涉及系统候选版本的最终测试步骤。  
  
 候选版本是一种系统版本（通常是最新的）；如果所有验证测试全部通过，则它将被认为是足够完整和稳定的并可以成为发行版本。 为此，需要成功完成一系列功能、性能和压力测试，以验证它是否确实已准备完毕。  
  
## <a name="test-to-verify-sustainable-throughput-and-latency"></a>测试以验证可持续吞吐量和延迟  
 性能的验证测试与实施阶段并行启动，但是需要最终确定一个已成功通过一整套发布标准测试的候选版本。 理想情况下，在最终测试期间对候选版本没有进行任何更改，这样就会有信心不会出现返工。 实际上这是非常困难的，随着对内部版本进行不断更改，必须对返工的风险进行评估。  
  
 例如，如果对系统项目（如管道或业务流程）进行了重大的更改，则很可能需要重新运行性能测试以验证新的候选版本。  
  
 为了确保系统已准备就绪可以投入生产，必须验证是否已经以可持续的方式对它进行了端对端测试。 这意味着所有的操作活动，如数据库维护、 查询和计划的操作和计划外的停机必须进行测试，在主题中定义[什么是可持续的性能？](../core/what-is-sustainable-performance.md) 这是最后一次的机会，若要验证对系统的准备情况，所以务必要组合可持续的性能测试中的最终测试传递的完整套件。  
  
## <a name="identify-bottlenecks-and-adjust-hardware-or-solution-to-remove-goal-blockers"></a>确认瓶颈并调整硬件或解决方案以排除障碍  
 在实践中，很普遍最终测试通过的测试平台上为更接近于生产与硬件测试台的开发比。  很重要，因此，若要使用的最终测试传递过程的机会来标识系统中的任何新的或现有的瓶颈，并确定它们是否足够大，需要调整硬件中。 即使不需要立即对硬件进行调整，找出最普遍的系统瓶颈也将提供宝贵的计划和操作信息。  
  
 例如，如果系统通过生产负载测试，但是观测到 MessageBox 服务器物理磁盘的空闲时间很低（例如，低于 20%），则在生产期间监视此磁盘将被视为一项关键的运行状况指标。 另外，在此阶段制定增加系统负载能力的所有计划时，应认识到需要对磁盘子系统进行改善。  
  
## <a name="see-also"></a>另请参阅  
 [项目规划阶段的建议](../core/project-planning-recommendations-by-phase.md)   
 [要求阶段建议](../core/requirements-phase-recommendations.md)   
 [设计阶段建议](../core/design-phase-recommendations.md)   
 [实现阶段建议](../core/implementation-phase-recommendations.md)   
 [发布阶段建议](../core/release-phase-recommendations.md)
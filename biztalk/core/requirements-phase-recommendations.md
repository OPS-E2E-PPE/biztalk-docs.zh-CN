---
title: 需求阶段的建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b510313-c3a7-42bc-9c9b-336c927a5d4a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b0f78179d57085dd1a9dc97aedb2b424d306638
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322130"
---
# <a name="requirements-phase-recommendations"></a>需求阶段的建议
与需求阶段相关联主要可交付成果是需求规范或包括要求包括性能目标的功能规范。 它是非常重要，以确定这些目标，以确保性能的准确配置文件派生时涉及的最终用户和系统的业务所有者。  
  
## <a name="establish-performance-criteria"></a>建立性能标准  
 从性能角度看，在此阶段中创建功能规范的最重要部分是项目的详细的性能目标的定义和建立性能发布标准。 有三个关键组件定义性能标准：  
  
- 将性能定义的函数的时间为一条曲线。  
  
- 性能要求，与性能函数相关联。  
  
- 文件大小和类型的分布。  
  
  这些条件中讨论了[可承受性能？](../core/what-is-sustainable-performance.md)  
  
  中的性能目标的应用程序的性能发布标准，则派生。 这些标准包含可实现的、 可衡量的行为，您可以通过测试来证明。 应用程序不会移动到版本中，除非之前所有的发布条件已满足或，如果不可实现标识为发布标准的例外情况。  
  
  它是产品周期的早期阶段设置发布标准非常重要。 所涉及的每个人都这么做意味着知道的目标是，并且没有达到之前设计和实现已注销的后果。  
  
  此外，性能测试用例将基于如何发布条件的评估，因此条件必须为详细，不足以避免混淆。 例如，当声明的特定吞吐量来实现时，它应包括：  
  
- 在其它必须运行硬件，例如的数量和类型的服务器、 磁盘速度/类型等。  
  
- 哪些方案是进行测试，例如，路径消息将引导完成应用程序  
  
- 方式进行度量，例如，自定义代码的性能计数器测量消息到达共享等的时间。  
  
  若要判断如何正确发布条件是，任何人都应能够查看发布标准所述并了解如何生成测试用例来证明该标准。  
  
## <a name="identify-performance-risks"></a>确定性能风险  
 性能发布目标和条件在充分地介绍具有后，可以执行性能风险区域的初始评估。 此分析的目的是确定应用程序可能需要特殊的设计关注，解决替代方案或消除以达到所需的条件的部分。  
  
 例如，每个传输适配器类型都有其自己的性能和缩放特征。 如果所需的吞吐量超出一个或多个适配器类型的功能 （接收或发送），然后替代扩展适配器方案可能需要进行调查。  
  
## <a name="estimate-sizing"></a>估算大小  
 根据已建立的目标和条件，它将永远不会过早地开始估计将需要达到的目标的硬件大小的过程。 与使用任何调整大小估算，其中一个必须基于这些估计值实际的测试结果。 在项目早期阶段，这些结果必定来自外部源。 您可以光临在 BizTalk Server 开发人员中心，案例研究[ http://go.microsoft.com/fwlink/?LinkId=49339 ](http://go.microsoft.com/fwlink/?LinkId=49339)。 案例研究提供有关方案的详细信息进行测试，在其执行测试的硬件和测试的配置。 您可以从这些测试用例，若要获得您的系统的初始大小估计值实现的性能进行推断。  
  
 请记住，没有任何预测模型或模拟准确预测系统大小上运行的任意应用程序的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 是一个平台在其可以部署多种应用程序解决方案，每个都有其自己的性能行为。 因此，尽管使用现有的案例研究结果派生估计值将为进行规划提供很好的起点，系统的最终大小极有可能需要调整对于所有的最简单的应用程序体系结构。  
  
## <a name="plan-for-sufficient-testing"></a>充分的测试计划  
 如上所述，目前尚没有模型或模拟能够准确预测为满足性能目标所需的硬件。 这意味着，才能真正证明该系统可以到达目标的唯一方法是测试生产级硬件上。 也就是说，执行测试用例的硬件，尽可能接近生产设置尽可能。  
  
 这一部分的规划至关重要，整合在一起的原则可承受性能、 详细信息，了解吞吐量状况以及性能发布标准。 使用配置文件从现有数据，测试用例推出必须派生，一致地评估发布标准的吞吐量。 必须记住可持续运行测试用例。 有关可持续测试的示例，请参阅以下主题：  
  
-   [测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)  
  
-   [测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)  
  
## <a name="see-also"></a>请参阅  
 [分阶段描述的项目规划建议](../core/project-planning-recommendations-by-phase.md)   
 [设计阶段的建议](../core/design-phase-recommendations.md)   
 [实现阶段的建议](../core/implementation-phase-recommendations.md)   
 [验证阶段的建议](../core/verification-phase-recommendations.md)   
 [发行阶段的建议](../core/release-phase-recommendations.md)
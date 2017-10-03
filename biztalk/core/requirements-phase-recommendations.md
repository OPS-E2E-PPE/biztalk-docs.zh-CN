---
title: "要求阶段建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b510313-c3a7-42bc-9c9b-336c927a5d4a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d945e50d9c7b8f0a9feae5e0f93a4766d108c695
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="requirements-phase-recommendations"></a>需求阶段的建议
与需求阶段相关的主要可交付成果是需求规范，即包括诸如性能目标等要求的功能规范。 务必让使用该系统的最终用户和业务所有者参与确定这些目标，以确保了解准确的性能状况。  
  
## <a name="establish-performance-criteria"></a>建立性能标准  
 从性能角度看，在此阶段创建的功能要求的最重要部分是项目的详细的性能目标的定义并建立性能释放条件。 定义性能标准有以下三个关键部分：  
  
-   将性能定义为时间的函数的曲线。  
  
-   与性能函数相关联的性能要求。  
  
-   文件大小和类型的分布。  
  
 这些条件中讨论了[什么是可持续的性能？](../core/what-is-sustainable-performance.md)  
  
 您可以从性能目标派生出应用程序的性能发布标准。 这些标准包含可实现和可评估的行为，这些行为可以通过测试来证明。 应用程序将不会发布，除非它已经满足所有的发布标准或被标识为发布标准的例外情况（如果不可实现）。  
  
 务必在产品周期的早期阶段设置发布标准。 这意味着在设计和实现结束之前涉及到的每个人都知道目标是什么以及没有达到目标的后果。  
  
 另外，性能测试用例将会基于发布标准的评估方式，因此必须详细介绍标准以避免混淆。 例如，当说明要达到的特定吞吐量时，应包括以下内容：  
  
-   所需的硬件，例如服务器的数量和类型，磁盘速度/类型等  
  
-   要测试的方案，例如消息通过应用程序的路径  
  
-   评估的方式，例如性能计数器、自定义代码、测量消息到达共享的次数等  
  
 若要判断发布标准是否合适，所有人都应能够查看发布标准文档，并了解如何生成测试用例来证明该标准。  
  
## <a name="identify-performance-risks"></a>确定性能风险  
 在充分地介绍了性能发布目标和标准后，就可以执行性能风险区域的初始评估了。 此分析的目的是为了确定在设计应用程序时需要特别关注的部分、需要备选解决方案的部分或需要去除的部分，以便达到所需标准。  
  
 例如，每个传输适配器类型都有自己的性能和扩展特性。 如果所需的吞吐量超出了一个或多个适配器类型（即接收或发送）的能力，则需要调查适配器的替代扩展方案。  
  
## <a name="estimate-sizing"></a>估算大小  
 根据已建立的目标和标准，应尽早开始估算为达到目标所需的硬件大小。 与估算任何大小的情形一样，必须根据实际的测试结果进行估算。 在项目的早期阶段，这些结果必定来自外部源。 你可以在阅读案例研究在 BizTalk Server 开发人员中心， [http://go.microsoft.com/fwlink/?LinkId=49339](http://go.microsoft.com/fwlink/?LinkId=49339)。 这些案例研究提供有关测试的方案、执行测试的硬件以及测试的配置的详细信息。 您可以从这些测试用例已实现的性能来推算出您的系统的初始大小估计值。  
  
 请记住没有预测模型或准确地预测系统大小上运行任何任意应用程序的模拟[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是一个平台可以部署大量不同的应用程序解决方案，每个都有其自己的性能行为。 因此，尽管使用现有的案例研究结果可以为规划目的提供良好的开端，不过，即使对于最简单的应用程序结构，其系统的最终大小也很可能需要进行调整。  
  
## <a name="plan-for-sufficient-testing"></a>计划充分的测试  
 如上所述，目前没有模型或模拟能够准确预测为满足性能目标所需的硬件。 这表示只有在生产级别的硬件中对系统进行测试才能真正证明该系统是否可以满足目标。 即，在与生产设置尽可能接近的硬件中执行测试用例。  
  
 这部分规划是很关键的，它将可持续性能的原则、详细了解吞吐量状况以及性能发布标准组合在一起。 使用从现有数据推出的吞吐量状况，必须派生能够一致地评估发布标准的测试用例。 请注意，测试用例必须以可持续的方式运行。 有关可持续测试的示例，请参阅以下主题：  
  
-   [测量的最大可持续引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)  
  
-   [测量的最大可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)  
  
## <a name="see-also"></a>另请参阅  
 [项目规划阶段的建议](../core/project-planning-recommendations-by-phase.md)   
 [设计阶段建议](../core/design-phase-recommendations.md)   
 [实现阶段建议](../core/implementation-phase-recommendations.md)   
 [验证阶段建议](../core/verification-phase-recommendations.md)   
 [发布阶段建议](../core/release-phase-recommendations.md)
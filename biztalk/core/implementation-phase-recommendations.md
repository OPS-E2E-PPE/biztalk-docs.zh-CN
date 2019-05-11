---
title: 实现阶段的建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04877156-cc32-480b-8410-d26eb073c327
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a95cca535bce9fd85665b69bcde19692ce93c53
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382749"
---
# <a name="implementation-phase-recommendations"></a>实现阶段的建议
实现阶段采用要求和设计阶段产品，并实现它们使用适当的技术。 对于验证测试，它是在此阶段已完成并在准备用于验证测试中自动测试用例。 通常情况下，大量的测试系统前期版本上也执行在此阶段，不仅要验证系统，但若要验证测试用例本身没有问题。  
  
## <a name="implement-performance-test-cases"></a>实现性能测试用例  
 在需求阶段和设计阶段，有代表性的测试用例是定义和设计，以证明系统的性能满足或超过了性能发布标准。 在实现阶段，这些测试用例是实现、 自动化，并最初执行验证，系统的各个组成部分达到代码完成，测试准备好验证性能。  
  
 它必须自动执行设置、 运行和结果分析的在实现阶段，尽可能多地测试。 可能很大的性能测试的数量和各个测试可能需要很长时间才能运行，因此实现测试自动化会增加运行它们，减少所需的人力资源部门的效率。 此外，预计运行验证测试多次测试通过期间的性能瓶颈确定并修复提供。 具有测试自动化更容易，更快，并更一致，若要重新运行性能验证生成。  
  
## <a name="build-the-performance-test-bed"></a>生成性能测试平台  
 它是非常重要，一致且可重现的方式执行所有的性能测试。 使用同一个硬件来设立基准并运行测试所依据是密钥 （如果这些测试的结果，则为可比较。 根据您的解决方案的体系结构，有各种硬件变量可能会显著影响结果。  
  
 例如，我们发现可用，即使在完全相同的服务器上的内存缓存显著影响结果，即使它可能不会通过查看服务器配置的两个服务器都具有不同级别的缓存很明显。 确保测试运行之间未更改的测试平台上运行可以消除任何问题可比性。 如果必须更改硬件配置，例如调整新的系统规模评估，则基线应重新建立，以便可以进行比较。  
  
## <a name="begin-performance-validation-testing"></a>开始性能验证测试  
 性能测试几乎总是开始与测试实现并行。  它是几乎不会过早地开始以来尽早开始，更快地做出反应如果发现的问题发布标准的验证。  
  
 开始正式测试的主要考虑因素是系统或被测系统的一部分的准备情况。 系统准备是非常主观判断，但应考虑以下因素：  
  
 是要测试代码完成的系统的路径？ 如果还有重要代码需要添加到路径，您可以考虑将工作重点放在其他地方直到"临界"准备就绪。  
  
 功能测试已成功在系统上运行？ 它可以是非常耗时且效率低下，若要设置和开始性能测试系统或子系统仅找出有一些功能上问题的进一步执行性能测试。 请确保路径必要的功能测试开始性能测试之前。  
  
 系统或子系统进行测试的风险级别是什么？ 若要进行调查的第一个系统路径应是最高的风险方面满足性能发布标准。 项目生命周期，可用于将时间更改过程中尽早发现系统瓶颈的重要性不能通过表示。  
  
## <a name="see-also"></a>请参阅  
 [分阶段描述的项目规划建议](../core/project-planning-recommendations-by-phase.md)   
 [需求阶段的建议](../core/requirements-phase-recommendations.md)   
 [设计阶段的建议](../core/design-phase-recommendations.md)   
 [验证阶段的建议](../core/verification-phase-recommendations.md)   
 [发行阶段的建议](../core/release-phase-recommendations.md)
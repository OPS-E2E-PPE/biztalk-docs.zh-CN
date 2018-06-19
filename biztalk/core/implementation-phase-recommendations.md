---
title: 实现阶段建议 |Microsoft 文档
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
ms.openlocfilehash: fce6d7df21f15b40e0312438394859f4b94b7fc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257397"
---
# <a name="implementation-phase-recommendations"></a>实现阶段的建议
实现阶段要实现需求和设计阶段产品，并使用相应的技术来完成这些任务。 对于验证测试，要在此阶段完成测试用例，并自动做好验证测试的准备工作。 系统前期版本的许多测试通常也是在这个阶段完成的，不仅要验证系统，还要检验测试用例自身是否存在问题。  
  
## <a name="implement-performance-test-cases"></a>实现性能测试用例  
 在需求阶段和设计阶段，需要定义和设计一些具有代表性的测试用例，来证实系统的性能满足或超过了性能发布标准。 在实现阶段，在完成系统各个部分的代码编写工作后，还需要实现、自动化并试运行这些测试用例，以检验验证性能的测试是否准备就绪。  
  
 在实现阶段，尽可能实现测试工作的设置、运行和结果分析的自动化是非常重要的。 由于性能测试的工作量会很大，单个测试花费的时间也会很长，因此实现测试工作的自动化将有助于提高运行效率，减少对人力资源的需求。 此外，在测试中如果出现了性能瓶颈，需要进行修补时，可能需要多次运行验证测试。 测试自动化会使每次生成后的重新运行性能验证更加简单、快捷和一致。  
  
## <a name="build-the-performance-test-bed"></a>建立性能测试平台  
 确保所有的性能测试以一致、可重现的方式进行是极其重要的。 要使测试结果可比较，使用同一个硬件来设立基准并运行测试将是很关键的。 针对解决方案的体系结构，有众多硬件可供选择，这会对测试结果产生重大影响。  
  
 例如，我们发现，除了缓存大小不同以外完全相同的两台服务器，其测试结果显著不同，尽管在服务器配置中可用内存缓存的差异并不那么明显。 确保运行测试的测试平台不在测试期间发生变化，这样就不会产生可比性的问题。 如果必须更改硬件配置，例如调整新系统规模评估的情况，则应重新设立基准，以便于比较。  
  
## <a name="begin-performance-validation-testing"></a>开始性能验证测试  
 性能测试几乎总是与测试实现同时开始的。  达到发布标准的验证工作开始得越早越好，因为如果出现问题，可以尽早做出反应。  
  
 开始正式测试所面临的主要问题是被测系统（或部分系统）是否就绪。 虽然系统是否就绪需要很多判断，但至少应考虑以下因素：  
  
 要进行代码测试的系统的路径是否完整？ 如果还有重要代码需要添加到该路径，则在达到“临界点”前，您可能需要将精力用在其他工作上。  
  
 功能测试是否已在系统上成功完成？ 如果发现系统或子系统存在功能故障，导致性能测试不能进一步执行，则设置和开始性能测试将是一件既费时又低效的事情。 在性能测试开始前，请确保先对该路径进行必要的功能测试。  
  
 待测试系统或子系统的风险有多大？ 考虑到需要满足性能发布标准，第一个待测试的系统路径应是风险最高的路径。 尽早发现系统瓶颈，可在项目的生命周期中争取到更正时间，其重要性不容低估。  
  
## <a name="see-also"></a>另请参阅  
 [项目规划阶段的建议](../core/project-planning-recommendations-by-phase.md)   
 [要求阶段建议](../core/requirements-phase-recommendations.md)   
 [设计阶段建议](../core/design-phase-recommendations.md)   
 [验证阶段建议](../core/verification-phase-recommendations.md)   
 [发布阶段建议](../core/release-phase-recommendations.md)
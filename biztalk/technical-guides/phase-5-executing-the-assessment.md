---
title: "阶段 5： 执行评估 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d40fc64-b6cb-448b-8ea1-a6ad7302ab8b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fba6d49d8d69276af4282ad0a941ee1fc4d8068
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="phase-5-executing-the-assessment"></a>阶段 5： 执行评估
执行阶段是通过自动的负载测试和其中性能瓶颈将发现并解决其中生成的性能数据。 此阶段都有一个迭代过程性能瓶颈，减少或消除通过测试，评估性能、 优化和重新测试。  
  
 本主题介绍在 BizTalk Server 性能评估的执行阶段通常遵循的步骤：  
  
## <a name="step-1-run-automated-tests"></a>步骤 1： 运行自动的测试  
 运行自动的测试来开始执行之后阶段。 BizTalk Server 性能评估通常侧重于吞吐量和/或延迟测试，但可能包含生成验证和功能的测试。 有关运行自动测试的全面信息，请参阅[实现自动化测试](../technical-guides/implementing-automated-testing.md)。  
  
## <a name="step-2-document-and-evaluate-test-results"></a>步骤 2： 记录和评估测试结果  
 在每个测试结束时，全面记录的测试结果和评估是否均已满足规定的性能目标。  
  
## <a name="step-3-modify-the-configuration-of-biztalk-server-third-party-systems-or-solution-artifacts-to-tune-for-performance-based-on-the-test-results"></a>步骤 3： 修改的配置 BizTalk Server、 第三方系统或解决方案项目关联，以优化性能基于测试结果  
 使用测试结果来做出有关如何优化环境的决定，以达到规定的吞吐量或延迟目标。  
  
## <a name="step-4-record-all-changes-made-to-the-environment"></a>步骤 4： 记录对环境所做的所有更改  
 确保完整地记录对环境进行任何更改。 所做的更改的 a 记录将允许你轻松地将应用生产环境中的更改，将容纳更改的撤消，如果需要。  
  
## <a name="step-5-repeat-this-cycle-until-goals-are-achieved"></a>步骤 5： 重复此循环直至实现目标  
 继续测试、 评估和记录结果、 优化环境，和记录对环境的更改，直至达到预期的性能目标的周期。  
  
## <a name="step-6-summarize-test-results-at-the-end-of-each-day"></a>步骤 6： 汇总每一天的末尾测试结果  
 完成"执行摘要"的测试结果和末尾的每一天的进度。 编译包含摘要，链接的电子邮件并发送给所有利益干系人在性能评估以使所有人的正在进行的进度通知。  
  
## <a name="step-7-update-the-project-plan-as-timeline-goals-are-met"></a>步骤 7： 更新项目计划作为目标都通过时间线  
 在计划阶段中开发的时间线是对于性能评估的整个过程参考资料。 更新此时间线为了向所有利益干系人传达进度。  
  
## <a name="see-also"></a>另请参阅  
 [性能评估阶段](../technical-guides/phases-of-a-performance-assessment.md)
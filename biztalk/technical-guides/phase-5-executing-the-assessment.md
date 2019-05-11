---
title: 阶段 5:执行评估 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d40fc64-b6cb-448b-8ea1-a6ad7302ab8b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 332073502c1b2cc358e09ce7f50338321eb42bdf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393467"
---
# <a name="phase-5-executing-the-assessment"></a>阶段 5:执行评估
执行阶段是通过自动的负载测试和其中性能瓶颈将发现并解决其中生成性能数据。 此阶段都有一个迭代过程性能瓶颈，减少或消除通过测试，评估性能、 优化和重新测试。  
  
 本主题介绍在 BizTalk Server 性能评估的执行阶段期间通常遵循的步骤：  
  
## <a name="step-1-run-automated-tests"></a>第 1 步：运行自动的测试  
 运行自动的测试来开始执行阶段。 通常，BizTalk Server 性能评估侧重于吞吐量和/或延迟测试，但可能包括生成验证和功能测试。 运行自动测试的全面信息，请参阅[实现自动化测试](../technical-guides/implementing-automated-testing.md)。  
  
## <a name="step-2-document-and-evaluate-test-results"></a>第 2 步：记录和评估测试结果  
 在每个测试结束时，全面记录测试结果和评估是否满足了规定的性能目标。  
  
## <a name="step-3-modify-the-configuration-of-biztalk-server-third-party-systems-or-solution-artifacts-to-tune-for-performance-based-on-the-test-results"></a>步骤 3：修改 BizTalk Server、 第三方系统或解决方案项目要优化的性能基于测试结果的配置  
 使用测试结果来做出有关如何优化环境来访问所述的吞吐量或延迟目标。  
  
## <a name="step-4-record-all-changes-made-to-the-environment"></a>步骤 4：记录所有对环境所做的更改  
 请确保完整地记录对环境进行任何更改。 所做的更改的记录将允许您轻松地将应用在生产环境中的更改并将容纳操作撤消更改，如果需要。  
  
## <a name="step-5-repeat-this-cycle-until-goals-are-achieved"></a>步骤 5：重复此过程，直到实现目标  
 继续测试、 评估和记录结果、 优化的环境和记录对环境的更改，直至达到所需的性能目标的循环。  
  
## <a name="step-6-summarize-test-results-at-the-end-of-each-day"></a>步骤 6：每一天结束时汇总测试结果  
 完成"执行摘要"的测试结果和每一天结束时的进度。 编译包含摘要的电子邮件并发送到性能评估中的所有利益干系人以保证所有人知情的正在进行的进度。  
  
## <a name="step-7-update-the-project-plan-as-timeline-goals-are-met"></a>步骤 7：根据时间线目标更新项目计划  
 在计划阶段中开发的时间线是很好的参考，对于性能评估的整个过程。 更新此时间线，根据需要向所有利益干系人传达进度。  
  
## <a name="see-also"></a>请参阅  
 [性能评估阶段](../technical-guides/phases-of-a-performance-assessment.md)
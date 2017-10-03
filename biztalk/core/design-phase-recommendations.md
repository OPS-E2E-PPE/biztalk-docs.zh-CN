---
title: "设计阶段建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee3d183e-a6f3-47d0-90ac-99b12c064607
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0f361734aa7539f12940212a339b582bb4f2641
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="design-phase-recommendations"></a>设计阶段建议
设计阶段的主要可交付成果是针对系统和测试用例（用于验证系统功能和性能）的设计规范。 调查功能和测试的可行性是设计过程的主要组成部分，这涉及到初始开发以及在验证设计情况下对所实现概念验证的一些早期测试，如以下部分所讨论的。  
  
## <a name="acquire-detailed-throughput-and-latency-profiles"></a>获取详细的吞吐量和延迟状况  
 根据以前项目阶段的性能发布标准所基于的初始负载状况，在设计阶段期间确定详细的吞吐量和延迟状况。 如果可以，从生产系统获取性能数据。 在此阶段中使用生产数据可以让您针对真实的性能状况设计测试用例。 如果生产数据不可用，则必须根据预期负载推断出实际状况。  
  
 在设计阶段创建性能测试用例（包括性能状况）是很重要的，以便更准确地模拟系统在生产环境中的性能表现。 有关创建现实和可持续性能配置文件的详细信息，请参阅[什么是可持续的性能？](../core/what-is-sustainable-performance.md)  
  
## <a name="investigate-performance-risk-mitigations"></a>研究性能风险缓解措施  
 在需求阶段，已经确定了实现所需性能目标的风险，并且确定了可能的缓解措施。  在设计阶段应尽可能早地研究风险和缓解措施，以便在需要时能够有时间更改设计。 首先应使用概念验证 (POC) 测试证明所确定的每个风险的确是一个问题，然后应测试缓解措施以评估其功效。  
  
 例如，假定旧有系统使用 FTP 与其他系统进行通信。 但是，根据旧有 FTP 服务器与 BizTalk Server FTP 适配器配合使用时可达到的吞吐量水平，显然无法达到所需的吞吐量（在需求阶段确定的发布标准）。 为减轻对项目所带来的风险，在需求阶段确定了以下备选方法：  
  
-   向上或向外扩展 FTP 服务器，并创建多个专门用于特定消息类型的逻辑 FTP 地址，以分散负载  
  
-   将旧有系统修改为将单个文件中的多个消息作为批传送，从而减少每条消息的传输开销  
  
-   将旧有系统修改为使用已知速度快于 FTP 的其他协议，例如 MSMQ。  
  
 在本例中首先需要完成的研究是通过测试当前的 FTP 系统的性能来证明存在风险。 将构建和部署仅从 FTP 服务器接收消息的一个简单的概念验证解决方案，并且将 FTP 途径将要面对的生产负载状况应用于此概念验证解决方案。 如果服务器能够承受所需负载，则就不会出现风险也不需要进行进一步的研究。 如果无法承受所需负载，则应通过概念验证研究来找出最有可能以最少成本和最低项目风险来解决此问题的其他方法。  
  
## <a name="refine-system-size-estimate"></a>提升系统规模评估  
 在设计阶段进行的研究可提供有关系统性能的宝贵经验性信息。  
  
 例如，继续上述示例，假如我们发现 FTP 的性能过低。 由于环境已包括将 MSMQ 用作消息传输手段的系统，因此决定将旧有系统也修改为使用 MSMQ。 但是，在对使用 MSMQ 的新 POC 进行性能测试期间，观察到 MessageBox 数据库所位于的 SQL 服务器的 CPU 利用率几乎固定在 100%，并且无法通过 MSMQ 途径实现预期的吞吐量。  
  
 假定 SQL Server 配置对应用程序来说已经是最佳的，那么显然对于所需吞吐量而言 SQL Server 硬件的能力不足并且需要提升系统规模。 在这种情况下，SQL Server 硬件需要更多的 CPU 或速度更快的 CPU，或同时需要二者。  
  
## <a name="see-also"></a>另请参阅  
 [项目规划阶段的建议](../core/project-planning-recommendations-by-phase.md)   
 [要求阶段建议](../core/requirements-phase-recommendations.md)   
 [实现阶段建议](../core/implementation-phase-recommendations.md)   
 [验证阶段建议](../core/verification-phase-recommendations.md)   
 [发布阶段建议](../core/release-phase-recommendations.md)
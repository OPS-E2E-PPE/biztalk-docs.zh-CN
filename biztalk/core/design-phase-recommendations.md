---
title: 设计阶段的建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ee3d183e-a6f3-47d0-90ac-99b12c064607
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54d65cdefbba019d7643d701cea8e41e815fe1c2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351674"
---
# <a name="design-phase-recommendations"></a>设计阶段的建议
在设计阶段的主要可交付成果是针对系统的设计规范和以验证系统功能和性能测试用例。 调查功能和测试的可行性是设计过程，涉及到初始开发的典型部分，并在验证设计的情况下作为概念证明实现一些早期测试此部分中讨论下面。  
  
## <a name="acquire-detailed-throughput-and-latency-profiles"></a>获取详细的吞吐量和延迟状况  
 基础上建立从以前项目阶段的性能发布标准的初始加载配置文件，在设计阶段建立详细的吞吐量和延迟状况。 如果可用，获取从生产系统的性能数据。 使用生产数据将提供真实的性能状况在此阶段可以在其设计测试用例。 如果生产数据不可用，必须从预期的负载推测真实的配置文件。  
  
 在设计阶段创建性能测试用例包括预期需要更准确地模拟系统的配置文件以支持在生产环境中的性能至关重要。 有关创建实际和可持续性能配置文件的详细信息，请参阅[可承受性能？](../core/what-is-sustainable-performance.md)  
  
## <a name="investigate-performance-risk-mitigations"></a>调查性能风险缓解措施  
 在需求阶段，实现所需的性能目标的风险已标识的标识和可能缓解措施。  风险和缓解措施应进行调查设计阶段尽可能早地以便留出时间来根据需要更改设计。 首先应证明每个标识的风险是使用概念证明 (POC) 测试问题，然后应测试缓解措施以评估其功效。  
  
 例如，假定旧有系统使用 FTP 与其他系统进行通信。 但是，查看的旧有 FTP 服务器可以在 BizTalk Server FTP 适配器的组合来实现的吞吐量级别，很明显，所需的吞吐量 （已建立的发布标准在需求阶段） 将不会得以实现。 若要缓解使项目遭受危险，以下备选方案标识在需求阶段：  
  
- 扩展或横向扩展 FTP 服务器并创建多个逻辑 FTP 地址专用于特定消息类型以分散负载  
  
- 旧有系统修改为将单个文件中的许多消息传递作为批处理以减少每个消息传输开销  
  
- 旧有系统修改为使用已知速度快于 FTP 如 MSMQ 的其他协议  
  
  第一个需要在此示例中完成的调查是为了证明通过测试当前的 FTP 系统性能存在风险。 简单的概念将构建和部署解决方案，只需从 FTP 服务器接收消息并对其应用的 FTP 途径的不同的预期的生产负载配置文件的概念验证。 如果服务器能够承受所需的负载，然后未实现风险并不需要进一步调查。 如果不能够承受所需的负载，应通过概念验证研究调查最有可能解决此问题最少的成本和项目风险的备选方法。  
  
## <a name="refine-system-size-estimate"></a>提升系统规模评估  
 在设计阶段进行的研究提供您的系统性能功能有关的宝贵经验性信息。  
  
 例如，让我们继续在其中找到 FTP 的性能过低上面的示例。 由于环境已包括将 MSMQ 用作消息传输的系统，因此决定修改旧有系统也使用 MSMQ。 但是，在使用 MSMQ 的新 poc 性能测试期间观察到的 MessageBox 数据库所位于几乎固定在 100%利用率，并且在 SQL server 上的 CPU 不能实现预期的吞吐量 MSMQ 途径.  
  
 假设 SQL Server 配置最适合应用程序，SQL Server 硬件是显然对于所需的吞吐量和需要明确定义的系统的大小。 在这种情况下，SQL Server 硬件需要更多的 Cpu、 更快的 Cpu，或这两者。  
  
## <a name="see-also"></a>请参阅  
 [分阶段描述的项目规划建议](../core/project-planning-recommendations-by-phase.md)   
 [需求阶段的建议](../core/requirements-phase-recommendations.md)   
 [实现阶段的建议](../core/implementation-phase-recommendations.md)   
 [验证阶段的建议](../core/verification-phase-recommendations.md)   
 [发行阶段的建议](../core/release-phase-recommendations.md)
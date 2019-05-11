---
title: 阶段 4:构建评估环境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b90d7c5-60ca-4a81-b3d9-6d4e9d91e684
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1b9829591af749f5e253cc7873af4ab114af542
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249647"
---
# <a name="phase-4-building-the-assessment-environment"></a>阶段 4:构建评估环境
性能评估的生成实验室阶段用于安装的硬件和软件环境中符合在前几个阶段中所做的设计决策。 生成实验室阶段可能会非常耗时，因为它不是异常这一阶段重叠较早阶段。 在许多情况下，硬件和操作系统可能会安装之前的最终决策进行有关应用程序体系结构。 性能评估的生成实验室阶段通常包括本主题中讨论的任务。  
  
## <a name="obtain-all-build-lab-infrastructure-at-least-a-week-in-advance-of-the-lab-start-date"></a>获取实验室开始日期之前至少一周的所有生成实验室基础结构  
 实验室开始日期之前一周至少具有可用的所需的硬件和软件的所有计划。 这将确保不浪费宝贵的实验室时间而进行的所需基础结构。  
  
## <a name="configure-third-party-software-systems"></a>配置第三方软件系统  
 可能需要进行构建和配置实验室可以开始之前的第三方系统。 如果主题事项专家 (Sme) 所需的这些系统，请确保计划生成扩展和实验室执行阶段。 请确保它们详尽地记录其生成扩展过程。  
  
## <a name="install-and-configure-the-biztalk-server-environment"></a>安装和配置 BizTalk Server 环境  
 中的详细的说明安装 BizTalk Server 和必需的依赖关系软件[安装和升级指南](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)。 后已成功安装和配置 BizTalk Server 环境，需要完成以下任务：  
  
-   请按照中列出的建议[操作准备就绪清单](operational-readiness-checklists.md)
  
-   请按照中的建议[优化性能](../technical-guides/optimizing-performance.md)。  
  
-   请确保正确同步所有计算机的时间。  
  
-   验证在环境中的所有计算机之间的 MSDTC 功能。  
  
-   请确保任何自定义跟踪/日志记录已禁用，除非绝对必要。  
  
-   安装 Visual Studio 旗舰版中的负载测试。  有关如何执行自动测试使用 Visual Studio 的详细信息，请参阅[促进自动测试使用 Visual Studio](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)。  
  
-   根据需要设置性能监视器计数器和日志。  
  
-   安装程序的调试的计算机，如果性能评估作用域内的代码更改调试解决方案。  
  
-   对所有硬盘进行碎片都整理。  
  
-   禁用防病毒实时扫描。  
  
-   备份企业单一登录主密钥。  
  
## <a name="install-the-biztalk-server-application-to-be-tested"></a>安装 BizTalk Server 应用程序进行测试  
 要进行测试的应用程序的安装通常包括以下步骤：  
  
1.  使用 BizTalk Server 管理控制台来执行以下操作：  
  
    -   创建主机  
  
    -   创建发送/接收处理程序。  
  
    -   创建主机实例。  
  
    -   创建 BizTalk Server 应用程序。  
  
2.  应用程序安装：  
  
    1.  将 BizTalk Server 二进制文件部署到 BizTalk Server 组。  
  
    2.  绑定导入到 BizTalk Server 组。  
  
    3.  所有框上的 gac 中 BizTalk Server 和 BizTalk Server 二进制文件。  
  
    4.  请确保在所有框上存在依存关系组件。  
  
3.  安装依赖应用程序。  
  
4.  在 BizTalk Server 管理控制台中配置的传输和物理终结点。  
  
5.  启动服务。  
  
6.  执行基本冒烟测试-测试你的解决方案的基本功能的端到端功能测试执行冒烟测试。  
  
## <a name="implement-automated-build-and-load-testing"></a>实施自动生成和负载测试  
 自动的生成和负载测试过程的实现可以说是 BizTalk Server 性能评估的基础。 如果性能评估作用域内的代码更改，则应实现自动的生成过程。 应为所有负载测试方案实现自动化的负载测试。 若要实现自动的生成和负载测试所需的初始时间投资快速得到了补偿，自动化可容纳的受到人为错误的常见生成/测试任务的快速而精确地重复。 有关实现自动化的生成和测试过程的详细信息，请参阅[实现自动化测试](../technical-guides/implementing-automated-testing.md)本指南中。  
  
## <a name="configure-performance-monitoring"></a>配置性能监视  
 准确的性能监视对性能评估的成功至关重要。 确定应计算哪些性能度量值根据在审视阶段中定义的吞吐量和延迟目标。 在 BizTalk Server 环境中的每台计算机上，应执行性能监视。 请参阅[性能计数器](../core/performance-counters.md)。 使用日志的性能分析工具 (PAL) 来生成 HTML 报告，以图形方式图表重要的性能计数器和超出这些计数器的阈值时生成警报。 S[性能分析的日志 (PAL) 工具](https://github.com/clinthuffman/PAL)。  
  
## <a name="establish-and-document-the-solutions-baseline-performance"></a>建立和记录解决方案的基线性能  
 应计算基准性能，以便可以测量性能评估过程中应用的性能优化的效果。  
  
## <a name="see-also"></a>请参阅  
 [性能评估阶段](../technical-guides/phases-of-a-performance-assessment.md)
---
title: "BizTalk Server 2010 性能优化指南 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a56b27f-3e57-47db-a776-520f2d67d65e
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c83e610a96343dfc32917f898f69645c13e5fa79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-2010-performance-optimization-guide"></a>BizTalk Server 2010 性能优化指南
欢迎使用 Microsoft® BizTalk® Server 2010年性能优化指南。 我们创建了本指南提供有关优化 BizTalk Server 解决方案的性能的深入信息。 在企业应用程序部署过程经常忽略完整的端到端性能测试。 了解 Microsoft 已生成可伸缩的消息传递基础结构后，使用 BizTalk Server 中的许多组织花在执行性能测试的自己的应用程序的很少或没有时间。 BizTalk Server 应用程序包含的许多部分，其中可能包括定制的组件，以及由 Microsoft 提供。 它不是不可能对性能的 Microsoft 测试每种可能组合的这些组件。 因此，完全正确并执行你的应用程序的性能测试是任何部署的一个关键步骤。  
  
 本指南的目的是合并安全性并提供最佳的实践和以优化 BizTalk 服务器性能，应遵循的技术的说明性指导。  
  
 若要下载本指南中 chm、 pdf、 或 docx 窗体的副本，请转到[Microsoft BizTalk Server 2010 性能优化指南](http://go.microsoft.com/fwlink/?LinkId=210870)(http://go.microsoft.com/fwlink/?LinkId=210870)。  
  
## <a name="whats-in-it"></a>什么是它？  
 通常情况下，服务器的性能由具有最低的性能的组件 — 系统中的瓶颈。 提高性能的关键能够找出瓶颈，请确定其原因，并应用相应的纠正措施。  
  
 在你规划你[!INCLUDE[prague](../includes/prague-md.md)]部署，使用本指南可帮助设计并优化你的环境。 性能的概念与可伸缩性的概念紧密相关。 如果必须清楚地了解影响系统组件的性能的因素，你可以部署组件可以进行扩展以支持高需求的时段的方式。  
  
 此指南提供了有关优化性能，基于实践经验的 IT 专业人员在进行了广泛使用 BizTalk Server 的指南。 具体而言，本指南包含四个主要部分：  
  
-   **查找并消除瓶颈**:[查找和消除瓶颈](../technical-guides/finding-and-eliminating-bottlenecks.md)部分将介绍各种类型的性能瓶颈，它们与 BizTalk Server 解决方案和有关如何对信息解决瓶颈。  
  
-   **优化性能**:[优化性能](../technical-guides/optimizing-performance.md)部分提供了有关优化性能的指南[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与在其平台的性能密切相关性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。 本部分提供有关优化性能的建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]平台。  
  
-   **缩放生产 BizTalk Server 环境**:[缩放生产 BizTalk Server 环境](../technical-guides/scaling-a-production-biztalk-server-environment.md)部分提供的详细的结果[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]完成 BizTalk 产品的性能测试团队。 这些测试侧重于可伸缩性和测量的添加影响[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]计算机、 添加的影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库，以及的影响的同时添加[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]计算机和[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]MessageBox 数据库移到解决方案同时。  
  
    -   增加的数量时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组，这些测试只有一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库配置为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这些测试侧重于添加的影响仅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机连接到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  
  
    -   增加的数量时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]所用的 MessageBox 数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这些测试侧重于添加的影响仅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库移到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  
  
    -   当同时数目增加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]所用的 MessageBox 数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这些测试测量添加这两个添加的影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库移到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  
  
-   **BizTalk Server 性能测试方法**: [BizTalk Server 性能测试方法](../technical-guides/biztalk-server-performance-testing-methodology.md)部分提供有关如何测试和优化的详细的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能。 它包括性能条件重点介绍有关信息，并评估时应该应用的基本阶段[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能。  
  
## <a name="additions-to-this-version-of-the-guide"></a>添加到此版本的指南  
 [使用 Visual Studio 连接到促进自动测试](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)– 介绍使用 Visual Studio 负载测试以评估 BizTalk 服务器应用程序的性能。  
  
## <a name="acknowledgments"></a>鸣谢  
 我们在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用户培训团队 gratefully 提供技术反馈以及大量的内容的确认以下个人的未完成的贡献[!INCLUDE[prague](../includes/prague-md.md)]性能优化指南：  
  
 **作者**  
  
-   Tim Wieman Microsoft  
  
-   Paolo Salvatori、 Microsoft  
  
-   Trace Young，Microsoft  
  
 **审阅者**  
  
-   Tim Wieman Microsoft  
  
-   Paolo Salvatori、 Microsoft
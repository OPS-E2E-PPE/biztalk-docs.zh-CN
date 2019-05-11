---
title: BizTalk Server 2010 性能优化指南 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a56b27f-3e57-47db-a776-520f2d67d65e
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ae884f413d258042b224b53fef983e477062850
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400508"
---
# <a name="biztalk-server-2010-performance-optimization-guide"></a>BizTalk Server 2010 性能优化指南
欢迎使用 Microsoft® BizTalk® Server 2010年性能优化指南。 我们创建了本指南，以提供有关优化 BizTalk Server 解决方案的性能的详细信息。 完整的端到端性能测试是经常被忽视企业应用程序部署过程。 了解 Microsoft 具有构建可缩放的消息传送基础结构后，使用 BizTalk Server 的许多组织花费很少或没有时间来执行性能测试的自己的应用程序。 BizTalk Server 应用程序包含许多部分，其中可能包括自定义构建的组件，以及它们由 Microsoft 提供。 对于 Microsoft 性能测试这些组件的每种可能组合，它是不可能。 因此，完整而恰当执行你的应用程序的性能测试是任何部署的一个关键步骤。  

 本指南的目的是合并和最佳做法和优化 BizTalk Server 性能应遵循的技术提供规范性指南。  

 若要下载本指南中 chm、 pdf 或 docx 窗体的副本，请转到[Microsoft BizTalk Server 2010 性能优化指南](http://go.microsoft.com/fwlink/?LinkId=210870)(http://go.microsoft.com/fwlink/?LinkId=210870)。  

## <a name="whats-in-it"></a>什么是它？  
 通常情况下，服务器的性能由具有最低性能组件 — 系统中的瓶颈。 提高性能的关键能够识别瓶颈，确定其原因，并应用适当的纠正措施。  

 在规划 BizTalk Server 部署，请使用本指南以帮助设计和优化您的环境。 与可伸缩性的概念密切相关的性能概念。 深入了解影响的系统组件的性能因素后，你可以部署组件可以进行扩展以支持高需求的时间段的方式。  

 本指南提供有关优化性能，基于实践经验的 IT 专业人员已广泛使用 BizTalk Server 的指导。 具体而言，本指南包括四个主要部分：  

- **查找并消除瓶颈**:[查找并消除瓶颈](../technical-guides/finding-and-eliminating-bottlenecks.md)部分介绍各种类型的性能瓶颈，因为它们与 BizTalk Server 解决方案和有关如何解决瓶颈问题的信息。  

- **优化性能**:[优化性能](../technical-guides/optimizing-performance.md)部分提供了用于优化性能的指导[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与在其平台的性能密切相关性能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装。 本部分提供了有关优化这两者的性能建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]平台。  

- **缩放生产 BizTalk Server 环境**:[缩放生产 BizTalk Server 环境](../technical-guides/scaling-a-production-biztalk-server-environment.md)部分提供了详细的由 BizTalk 产品团队完成 BizTalk Server 性能测试结果。 这些测试侧重于可伸缩性和度量添加 BizTalk Server 计算机，添加的影响的影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库，并向解决方案添加 BizTalk Server 计算机和 BizTalk Server MessageBox 数据库的影响同时。  

  - 增加的数量时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组中，针对这些测试只有一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库中配置的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这些测试只侧重于添加的影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机连接到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  

  - 当增加的数量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用的 MessageBox 数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这些测试只侧重于添加的影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库移到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  

  - 增加的数目时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用的 MessageBox 数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。 这些测试度量添加这两个添加的影响[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库移到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组。  

- **BizTalk Server 性能测试方法**:[BizTalk Server 性能测试方法](../technical-guides/biztalk-server-performance-testing-methodology.md)部分提供有关如何测试和优化的详细的信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能。 它包括有关专注于哪些性能条件的信息，并评估时应该应用的基本阶段[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]性能。  

## <a name="additions-to-this-version-of-the-guide"></a>添加到此版本的指南  
 [使用 Visual Studio 来促进自动测试](../technical-guides/using-visual-studio-to-facilitate-automated-testing.md)– 介绍如何使用 Visual Studio 负载测试来评估 BizTalk Server 应用程序的性能。  

## <a name="acknowledgments"></a>确认  
 我们在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用户培训团队有幸确认提供技术反馈以及大量的内容的 BizTalk Server 性能优化指南的以下个人的杰出贡献：  

 **作者**  

- Tim Wieman Microsoft  

- Paolo Salvatori、 Microsoft  

- Microsoft trace Young  

  **审阅者**  

- Tim Wieman Microsoft  

- Paolo Salvatori、 Microsoft

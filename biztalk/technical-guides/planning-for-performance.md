---
title: 为性能规划 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 267a8bc6-a0ab-4335-bc04-c22d5a56792f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fac21f0b483ac3cbaec64c48b524a17422cb146
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302997"
---
# <a name="planning-for-performance"></a>规划性能
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是一个应用程序平台。 它不是只是一种服务器产品或只是开发人员产品。 它是一个用于构建业务流程管理系统，将企业应用程序，以自动执行工作流，集成的应用程序平台和启用服务的面向体系结构。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是依赖于许多其他软件组件。 BizTalk 应用程序平台通常提供多个以下的软件组件： Windows Server 操作系统的 SQL Server， [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，IIS （可选），外部系统的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与，进行交互，以及非 Microsoft 适配器和组件。  
  
 本质上是复杂的性质，因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，有许多注意事项为性能规划时进行。 有几种默认设置适用于所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境和一些其他注意事项和有关优化方法特定的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构。  
  
 本主题提供的默认设置优化的所有性能时应该应用概述[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 它还提供用于测试和优化建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]旨在用于特定方案的环境。  
  
## <a name="settings-that-you-should-apply-to-all-biztalk-server-environments"></a>应适用于所有的 BizTalk Server 环境的设置  
 [操作的准备情况清单](../technical-guides/operational-readiness-checklists.md)部分本指南包含使用任何 BizTalk 解决方案前应查看的项的列表。 此清单包含会对性能有显著的影响的操作项你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]而不考虑特定性质的 BizTalk 解决方案采用的环境。  
  
## <a name="considerations-for-testing-and-optimizing-a-biztalk-solution"></a>测试和优化 BizTalk 解决方案注意事项  
 不同的 BizTalk 解决方案可能有差别很大的性能条件。 例如，围绕运行业务流程构建一个 BizTalk 解决方案将具有比侧重于接收、 转换和映射平面文件文档 BizTalk 解决方案的不同的性能配置文件。 业务流程已设定焦点的解决方案可能是 CPU 密集型，也可以调用受益优化，而平面文件转换和映射已设定焦点的解决方案可能更占用大量内存的自定义组件。  
  
 适配器和用于接收和发送中和扩展的文档的管道[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]也可能对 BizTalk 解决方案的性能产生深远的影响。 解决方案所需的文档跟踪的级别将也会显著影响性能。 由于的多个同名的不同性能配置文件在不同的 BizTalk 解决方案可能会出现，它是非常关键，测试 BizTalk 解决方案以度量最大可持续的性能和最大可持续跟踪性能。  
  
 确定后的最大可持续的性能和最大可持续跟踪性能 BizTalk 解决方案，有一些可以用于瓶颈移除 BizTalk 解决方案中的特定步骤。 有关详细信息，请参阅[BizTalk Server 2009 性能指南](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID=150492)。  
  
## <a name="see-also"></a>另请参阅  
 [规划 BizTalk 服务器层](../technical-guides/planning-the-biztalk-server-tier.md)
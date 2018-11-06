---
title: 规划性能 |Microsoft Docs
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
ms.openlocfilehash: 452dd1a8a038ab151b98aac8ce6c4f93641f7361
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752709"
---
# <a name="planning-for-performance"></a>规划性能
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 是一个应用程序平台。 它不是只是一种服务器产品或只是开发人员产品。 它是一个应用程序平台，用于生成业务流程管理系统，以集成企业应用程序，以自动执行工作流，并启用服务面向体系结构。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 是依赖于许多其他软件组件。 BizTalk 应用程序平台通常包含多个以下的软件组件： Windows Server 操作系统的 SQL Server [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，IIS （可选），外部系统的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行交互，以及非 Microsoft 适配器和组件。  
  
 本质上较复杂的性质[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，有许多注意事项规划性能时进行。 有几种默认设置适用于所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境和一些其他注意事项和方法来优化特定的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构。  
  
 本主题提供优化的所有性能时应该应用的默认设置的概述[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。 它还提供用于测试和优化建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]专为特定方案的环境。  
  
## <a name="settings-that-you-should-apply-to-all-biztalk-server-environments"></a>应该应用于所有 BizTalk Server 环境的设置  
 [操作准备就绪清单](../technical-guides/operational-readiness-checklists.md)本指南的部分包含使用任何 BizTalk 解决方案之前应该查看的项的列表。 此清单包含会对的性能产生重大影响的操作项您[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]所用的 BizTalk 解决方案的环境而不考虑特定的性质。  
  
## <a name="considerations-for-testing-and-optimizing-a-biztalk-solution"></a>测试和优化 BizTalk 解决方案的注意事项  
 不同的 BizTalk 解决方案可能差别很大的性能条件。 例如，专为运行业务流程的 BizTalk 解决方案将具有一个比侧重于接收、 转换和映射的平面文件文档的 BizTalk 解决方案的不同的性能配置文件。 专注于业务流程的解决方案可能是 CPU 密集型，也可以调用受益于优化，而平面文件转换和映射为中心的解决方案可能会耗费更多内存的自定义组件。  
  
 适配器和管道用于接收和发送文档中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]还可以在 BizTalk 解决方案的性能产生深远的影响。 解决方案所需的文档跟踪的级别将也会显著影响性能。 由于多个同名的不同性能的配置文件可以在不同的 BizTalk 解决方案中，绝对重要的是测试 BizTalk 解决方案以度量最大可承受性能和最大可承受跟踪性能。  
  
 确定后的最大可承受性能和最大可承受跟踪性能 BizTalk 解决方案，有一些您可使用 BizTalk 解决方案中消除瓶颈的特定步骤。 有关详细信息，请参阅[BizTalk Server 2009 性能指南](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID=150492)。  
  
## <a name="see-also"></a>请参阅  
 [规划 BizTalk Server 层](../technical-guides/planning-the-biztalk-server-tier.md)
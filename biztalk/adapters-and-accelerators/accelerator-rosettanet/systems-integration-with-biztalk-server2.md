---
title: "与 BizTalk Server2 系统集成 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system integration
- tools, BizTalk Server
- BizTalk Server, tools
- BizTalk Server, about BizTalk Server
- BizTalk Server, business processes
- messages, BizTalk Server
- BizTalk Server, messages
- BizTalk Server, system integration
- business processes, BizTalk Server
ms.assetid: 5ba3dda1-efdb-4a2b-bb3a-825d76696f15
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b93f0f810259708d301ed683af8c10d364e1cca7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="systems-integration-with-biztalk-server"></a>与 BizTalk Server 的系统集成
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] 是为 eBusiness 应用程序设计的集成服务器。 构建的[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]系统平台，包括[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]® 2008， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 2008 R2/2008 SP1 和[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] SharePoint® Services，并利用功能[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 这种多层次的技术为开发、实现、操作和维护你的解决方案提供了丰富的功能。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]提供以下你可以结合使用的集成服务[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。 有关详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]集成服务，请参阅[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]帮助。  
  
## <a name="message-integration"></a>消息集成  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 通过自动交换消息集成了不同的实体（部门、业务合作伙伴和供应商）。 它使用 XML 作为公用通信协议。 它使用 XML 架构定义 (XSD) 架构来描述和验证消息，同时使用 XSL 转换 (XSLT) 在一条消息与另一条消息间转换数据。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]集成引擎将从一个位置消息路由到另一个。 采用发布方/订阅方模型（某一部门发布文档，另一部门订阅此文档）是它的一大特色。 订阅部门可以在发布部门不知情的情况下订阅消息。 这就启用了高效的合作伙伴组织处理功能，使用灵活的中心-分支方式替代了点对点的通信。  
  
## <a name="business-process-automation"></a>业务流程自动化  
 通过使用作为业务流程来引用的流程映射以链接单一流程内一组不同但相关的操作，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 自动处理并集成了业务流程。 通过创建业务流程，你可以将基于数据交换和分析的步骤（如消息接收、消息发送、决策、循环和其他操作）连接起来。 有了业务流程，你可以创建在事件发生时自动运行的业务流程。  
  
 使用 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你可以动态地更改基于业务规则的流程。 这就可以让你根据业务需要灵活地更改业务流程中采取的操作。 限制只对超过特定阈值以上的订单进行订单开票审批流程就是一个例子。  
  
 通过使用 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你可以将人工操作包括在工作流服务范围内的自动业务流程之中。 有关详细信息，请参阅 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 帮助中的“工作流服务 (HWS)”。  
  
## <a name="integration-of-heterogeneous-systems"></a>异构系统的集成  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以将集成在其系统传输不同通信协议中的数据对异类环境中的 IT 系统。 这是通过使用适配器连接使用不同协议的系统而实现的。 它支持使用 File、FTP、HTTP、SMTP、SOAP 和 SQL 适配器。 你可以使用 BizTalk 适配器框架来创建自定义的适配器。 有关详细信息，请参阅 [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] 帮助中的“使用适配器框架开发适配器”。  
  
## <a name="role-based-tools"></a>基于角色的工具  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]是在其中开发人员、 IT 专业人员和业务专业人员协作创建、 实现、 操作、 维护和自定义系统开发和执行环境。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]其中每个角色提供自定义其使用的工具。  
  
 有关详细信息，请参阅[A Role-Based 产品和 #91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/a-role-based-product2.md)，和[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]帮助。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 如何解决的业务需要](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [BizTalk Accelerator for RosettaNet 将添加到 BizTalk Server](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)
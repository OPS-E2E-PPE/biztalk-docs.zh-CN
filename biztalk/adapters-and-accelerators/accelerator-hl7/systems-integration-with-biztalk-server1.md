---
title: "与 BizTalk Server1 系统集成 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system integration
- BizTalk Server, tools
- business processes, automating
- BTAHL7, BizTalk Server
- BizTalk Server
- BizTalk Server, business process automation
- BizTalk Server, messages
- BizTalk Server, system integration
ms.assetid: 8f66a4fc-186c-415f-a7ed-31f620f0495f
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13eba7a4a799803340d2757bd39c3e5e9844603e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="systems-integration-with-biztalk-server"></a>与 BizTalk Server 的系统集成
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] 是为 eBusiness 应用程序设计的集成服务器。 构建的[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]系统平台，包括[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Windows Server 2008， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]，和[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSharePointSvcsNoVersion](../../includes/btswinsharepointsvcsnoversion-md.md)]，并可利用的功能[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[vs2012](../../includes/vs2012-md.md)]. 这种多层次的技术为开发、实现、操作和维护你的解决方案提供了丰富的功能。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]提供以下你可以结合使用的集成服务[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。 有关详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]集成服务，请参阅[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。  
  
## <a name="message-integration"></a>消息集成  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将不同实体 （部门、 业务合作伙伴、 供应商，等） 集成通过自动执行消息交换。 它使用可扩展标记语言 (XML) 作为一种常见通信协议。 它使用 XML 架构定义 (XSD) 架构来描述和验证消息，同时使用 XSL 转换 (XSLT) 在一条消息与另一条消息间转换数据。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]集成引擎将从一个位置消息路由到另一个。 采用发布方/订阅方模型（某一部门发布文档，另一部门订阅此文档）是它的一大特色。 订阅部门可以在发布部门不知情的情况下订阅消息。 这就启用了高效的合作伙伴组织处理功能，使用灵活的中心-分支方式替代了点对点的通信。  
  
## <a name="business-process-automation"></a>业务流程自动化  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]自动执行，并通过使用调用业务流程的流程图链接在单个进程的不同，相关操作的一组集成业务流程。 通过创建业务流程，你可以将基于数据交换和分析的步骤（如消息接收、消息发送、决策、循环和其他操作）连接起来。 业务流程可用于创建将在事件发生时自动运行的业务流程。  
  
 使用 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你可以动态地更改基于业务规则的流程。 这就可以让你根据业务需要灵活地更改业务流程中采取的操作。 限制只对超过特定阈值以上的订单进行订单开票审批流程就是一个例子。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]另外，可以包括自动业务流程，通过工作流服务内的人工操作。  
  
## <a name="integration-of-heterogeneous-systems"></a>异构系统的集成  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以将集成在其系统传输不同通信协议中的数据对异类环境中的 IT 系统。 这是通过使用适配器连接使用不同协议的系统而实现的。 它支持使用的文件、 FTP、 HTTP、 SMTP、 SOAP 和 SQL 适配器。 你可以使用 BizTalk 适配器框架来创建自定义的适配器。  
  
## <a name="role-based-tools"></a>基于角色的工具  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]是在其中开发人员、 IT 专业人员和业务专业人员协作创建、 实现、 操作、 维护和自定义系统开发和执行环境。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]其中每个角色提供专门针对于其使用的工具。  
  
 有关详细信息，请参阅[基于角色的产品](../../adapters-and-accelerators/accelerator-hl7/a-role-based-product1.md)，和[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Accelerator for HL7 将添加到 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/what-biztalk-accelerator-for-hl7-adds-to-biztalk-server.md)
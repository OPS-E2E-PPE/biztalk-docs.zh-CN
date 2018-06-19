---
title: HL7 系统集成 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f66a4fc-186c-415f-a7ed-31f620f0495f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c7189802ea981bd26b717f09bb3de0e445c9314
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005030"
---
# <a name="systems-integration-with-biztalk-server"></a>与 BizTalk Server 的系统集成
Microsoft BizTalk Server 是为电子商务应用程序设计的集成服务器。 它基于 Windows Server、 SQL Server 和 SharePoint，并可利用 Visual Studio 的功能。 这种多层次的技术为开发、实现、操作和维护你的解决方案提供了丰富的功能。  
  
 BizTalk Server 提供以下可用于结合使用 BizTalk Accelerator HL7 的集成服务 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。  
  
## <a name="message-integration"></a>消息集成  
 BizTalk Server 集成通过自动执行消息交换的不同实体 （部门、 业务合作伙伴、 供应商，等）。 它使用可扩展标记语言 (XML) 作为一种常见通信协议。 它使用 XML 架构定义 (XSD) 架构来描述和验证消息，同时使用 XSL 转换 (XSLT) 在一条消息与另一条消息间转换数据。  
  
 BizTalk Server 集成引擎将从一个位置的消息路由到另一个。 采用发布方/订阅方模型（某一部门发布文档，另一部门订阅此文档）是它的一大特色。 订阅部门可以在发布部门不知情的情况下订阅消息。 这就启用了高效的合作伙伴组织处理功能，使用灵活的中心-分支方式替代了点对点的通信。  
  
## <a name="business-process-automation"></a>业务流程自动化  
 BizTalk Server 自动执行，并通过使用调用业务流程的流程图链接在单个进程的不同，相关操作的一组集成业务流程。 通过创建业务流程，你可以将基于数据交换和分析的步骤（如消息接收、消息发送、决策、循环和其他操作）连接起来。 业务流程可用于创建将在事件发生时自动运行的业务流程。  
  
 使用 BizTalk Server，您可以动态更改业务规则所基于的进程。 这就可以让你根据业务需要灵活地更改业务流程中采取的操作。 限制只对超过特定阈值以上的订单进行订单开票审批流程就是一个例子。  
  
 BizTalk Server 还可包括自动业务流程，通过工作流服务内的人工操作。  
  
## <a name="integration-of-heterogeneous-systems"></a>异构系统的集成  
 BizTalk Server 可以将在其中系统传输不同通信协议中的数据对异类环境中的 IT 系统集成。 这是通过使用适配器连接使用不同协议的系统而实现的。 它支持使用的文件、 FTP、 HTTP、 SMTP、 SOAP 和 SQL 适配器。 你可以使用 BizTalk 适配器框架来创建自定义的适配器。  
  
## <a name="role-based-tools"></a>基于角色的工具  
 BizTalk Server 是在其中开发人员、 IT 专业人员和业务专业人员协作创建、 实现、 操作、 维护和自定义系统开发和执行环境。 BizTalk Server 提供的每个这些角色定制其使用的工具。  
  
 有关详细信息，请参阅[基于角色的产品](../../adapters-and-accelerators/accelerator-hl7/a-role-based-product1.md)。
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Accelerator for HL7 向 BizTalk Server 添加的功能](../../adapters-and-accelerators/accelerator-hl7/what-biztalk-accelerator-for-hl7-adds-to-biztalk-server.md)
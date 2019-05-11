---
title: HL7 系统集成 |Microsoft Docs
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
ms.openlocfilehash: 9b44f31b20785effb88728e63255c23245fe7051
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286546"
---
# <a name="systems-integration-with-biztalk-server"></a>与 BizTalk Server 的系统集成
Microsoft BizTalk Server 是为 eBusiness 应用程序设计的集成服务器。 它基于 Windows Server、 SQL Server 和 SharePoint，并使用 Visual Studio 的功能。 此技术堆栈提供了一系列功能和用于开发、 实现、 操作和维护您的解决方案的功能。  
  
 BizTalk Server 提供以下集成服务，可结合使用 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。  
  
## <a name="message-integration"></a>消息集成  
 BizTalk Server 通过自动交换消息集成不同的实体 （部门、 业务合作伙伴、 供应商等）。 它使用可扩展标记语言 (XML) 作为一种常见通信协议。 它使用 XML 架构定义 (XSD) 架构来描述和验证消息和 XSL 转换 (XSLT) 转换到另一个消息中的数据。  
  
 BizTalk Server 集成引擎将从一个位置的消息路由到另一个。 其特点允许一个部门发布文档，和另一个订阅的发布服务器/订阅模型。 不发布部门不知情的情况下，订阅部门可以订阅该消息。 这样合作伙伴组织，替换为灵活的中心辐射型排列为点到点通信的高效的处理。  
  
## <a name="business-process-automation"></a>业务流程的自动化  
 BizTalk Server 自动执行，并通过使用调用业务流程的流程映射以链接的一组不同但相关操作在单个进程中集成的业务流程。 通过创建业务流程，你可以链接基于数据交换和分析，如消息接收、 消息发送、 决策、 循环、 步骤和其他操作。 业务流程，可创建将在事件发生时自动运行的业务流程。  
  
 使用 BizTalk Server，你可以动态更改基于业务规则的过程。 这使你灵活地更改业务流程根据业务需要而执行的操作。 示例会超过特定阈值以上的订单限制订单开票审批流程。  
  
 BizTalk Server 还可以包含在自动化业务流程，通过工作流服务中的人工操作。  
  
## <a name="integration-of-heterogeneous-systems"></a>异构系统的集成  
 BizTalk Server 可以集成异构环境中不同的通信协议的数据传输中的系统中的 IT 系统。 它会通过使用适配器连接到使用不同协议的系统。 它支持使用的文件、 FTP、 HTTP、 SMTP、 SOAP 和 SQL 适配器。 可以使用 BizTalk 适配器框架来创建自定义适配器。  
  
## <a name="role-based-tools"></a>基于角色的工具  
 BizTalk Server 是在其中开发人员、 IT 专业人员和业务专业人员协作来创建、 实现、 操作、 维护和自定义系统的开发和执行环境。 BizTalk Server 为每个角色提供适用于其使用的工具。  
  
 有关详细信息，请参阅[基于角色的产品](../../adapters-and-accelerators/accelerator-hl7/a-role-based-product1.md)。
  
## <a name="see-also"></a>请参阅  
 [BizTalk Accelerator for HL7 向 BizTalk Server 添加的功能](../../adapters-and-accelerators/accelerator-hl7/what-biztalk-accelerator-for-hl7-adds-to-biztalk-server.md)
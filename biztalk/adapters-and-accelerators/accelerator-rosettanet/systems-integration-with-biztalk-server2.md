---
title: 与 BizTalk Server 的系统集成 |Microsoft 文档
description: BizTalk Server 包括集成消息使用 XML、 自动执行业务流程使用地图和业务流程，并使用系统使用不同的协议，例如 FTP、 HTTP、 SMTP、 SOAP 和 SQL 的功能。
ms.custom: ''
ms.date: 06/08/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5ba3dda1-efdb-4a2b-bb3a-825d76696f15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24d2251bf51e59aea919e20b93ff0f7864f3bf31
ms.sourcegitcommit: 7deb2b5a17d740b777a17566d557b25bdd505302
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "35290377"
---
# <a name="systems-integration-with-biztalk-server"></a>与 BizTalk Server 的系统集成
BizTalk Server 是使用集成服务器[发布和订阅体系结构](../../core/publish-and-subscribe-architecture.md)。 它专为电子商务应用程序，[使用适配器](../../core/using-adapters.md)若要接收和发送消息，实现[通过业务流程的业务流程](../../core/defining-business-processes.md)，并且包括[管理和跟踪](../../core/management-and-tracking-architecture.md)这些不同的部分。 BizTalk Server 还包括[贸易合作伙伴管理](../../core/trading-partner-management-using-biztalk-server.md)以执行企业到企业消息传递，[高可用性](../../core/planning-for-high-availability3.md)以最大化运行时间，一个开发平台，到[创建你自己的组件](../../core/developing-custom-components.md)，到管理控制台[管理你的项目](../../core/operational-and-administrative-tasks-in-your-biztalk-environment.md)，和业务活动监视管理[聚合、 警报和配置文件](../../core/using-business-activity-monitoring.md)。 这种多层次的技术为开发、实现、操作和维护你的解决方案提供了丰富的功能。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 提供以下集成服务，你可以将这些集成服务与 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 结合起来使用。 有关详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]集成服务，请参阅[BizTalk Accelerator for RosettaNet ](microsoft-biztalk-accelerator-for-rosettanet-documentation.md)。
  
## <a name="message-integration"></a>消息集成  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 通过自动交换消息集成了不同的实体（部门、业务合作伙伴和供应商）。 它使用 XML 作为公用通信协议。 它使用 XML 架构定义 (XSD) 架构来描述和验证消息，同时使用 XSL 转换 (XSLT) 在一条消息与另一条消息间转换数据。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]集成引擎将从一个位置消息路由到另一个。 采用发布方/订阅方模型（某一部门发布文档，另一部门订阅此文档）是它的一大特色。 订阅部门可以在发布部门不知情的情况下订阅消息。 这就启用了高效的合作伙伴组织处理功能，使用灵活的中心-分支方式替代了点对点的通信。  
  
## <a name="business-process-automation"></a>业务流程自动化  
 通过使用作为业务流程来引用的流程映射以链接单一流程内一组不同但相关的操作，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 自动处理并集成了业务流程。 通过创建业务流程，你可以将基于数据交换和分析的步骤（如消息接收、消息发送、决策、循环和其他操作）连接起来。 有了业务流程，你可以创建在事件发生时自动运行的业务流程。  
  
 使用 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你可以动态地更改基于业务规则的流程。 这就可以让你根据业务需要灵活地更改业务流程中采取的操作。 限制只对超过特定阈值以上的订单进行订单开票审批流程就是一个例子。  
  
  
## <a name="integration-of-heterogeneous-systems"></a>异构系统的集成  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 可以将集成在其系统传输不同通信协议中的数据对异类环境中的 IT 系统。 这是通过使用适配器连接使用不同协议的系统而实现的。 它支持使用 File、FTP、HTTP、SMTP、SOAP 和 SQL 适配器。 你可以使用 BizTalk 适配器框架来创建自定义的适配器。 有关详细信息，请参阅[创建自定义适配器](../../core/developing-custom-adapters.md)。
  
## <a name="role-based-tools"></a>基于角色的工具  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 是在其中开发人员、 IT 专业人员和业务专业人员协作创建、 实现、 操作、 维护和自定义系统开发和执行环境。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 其中每个角色提供自定义其使用的工具。  
  
 有关详细信息，请参阅[A Role-Based 产品](../../adapters-and-accelerators/accelerator-rosettanet/a-role-based-product2.md)，和[有关 RosettaNet 快捷键](../../adapters-and-accelerators/accelerator-rosettanet/learn-the-rosettanet-accelerator-and-the-biztalk-tools-available.md)。
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何解决的业务需要](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [BizTalk Accelerator for RosettaNet 向 BizTalk Server 添加的功能](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)

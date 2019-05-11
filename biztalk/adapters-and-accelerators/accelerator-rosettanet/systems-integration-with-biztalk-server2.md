---
title: 与 BizTalk Server 的系统集成 |Microsoft Docs
description: BizTalk Server 包括集成使用 XML 的消息、 自动执行业务流程使用映射和业务流程，并使用系统使用不同的协议，例如 FTP、 HTTP、 SMTP、 SOAP 和 SQL 的功能。
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
ms.openlocfilehash: 27b29ccb1c4e249200bc409b36d1ee383b664a68
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314618"
---
# <a name="systems-integration-with-biztalk-server"></a>与 BizTalk Server 的系统集成
BizTalk Server 是一个集成服务器，使用[发布和订阅体系结构](../../core/publish-and-subscribe-architecture.md)。 目的是为 eBusiness 应用程序的[使用适配器](../../core/using-adapters.md)若要接收和发送消息，实现[业务流程通过业务流程](../../core/defining-business-processes.md)，并包括[管理和跟踪](../../core/management-and-tracking-architecture.md)的这些不同的部分。 BizTalk Server 还包括[贸易合作伙伴管理](../../core/trading-partner-management-using-biztalk-server.md)用于企业到企业消息传送，[高可用性](../../core/planning-for-high-availability3.md)若要最大化运行时间，一个开发平台[创建您自己组件](../../core/developing-custom-components.md)，向一个管理控制台[管理项目](../../core/operational-and-administrative-tasks-in-your-biztalk-environment.md)，和业务活动监视管理[聚合、 警报和配置文件](../../core/using-business-activity-monitoring.md)。 此技术堆栈提供了一系列功能和用于开发、 实现、 操作和维护您的解决方案的功能。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 提供以下集成服务，可以使用与 Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]。 有关详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]集成服务，请参阅[BizTalk Accelerator for RosettaNet ](microsoft-biztalk-accelerator-for-rosettanet-documentation.md)。
  
## <a name="message-integration"></a>消息集成  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 通过自动交换消息集成不同的实体 （部门、 业务合作伙伴、 供应商）。 它使用 XML 作为公用通信协议。 它使用 XML 架构定义 (XSD) 架构来描述和验证消息和 XSL 转换 (XSLT) 转换到另一个消息中的数据。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]集成引擎将消息从一个位置路由到另一个。 其特点允许一个部门发布文档，和另一个订阅的发布服务器/订阅模型。 不发布部门不知情的情况下，订阅部门可以订阅该消息。 这样合作伙伴组织，替换为灵活的中心辐射型排列为点到点通信的高效的处理。  
  
## <a name="business-process-automation"></a>业务流程的自动化  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 自动执行，并通过使用称为业务流程的流程映射以链接的一组不同但相关操作在单个进程中集成的业务流程。 通过创建业务流程，你可以链接基于数据交换和分析，如消息接收、 消息发送、 决策、 循环、 步骤和其他操作。 与业务流程，可以创建将在事件发生时自动运行的业务流程。  
  
 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，可以动态更改基于业务规则的过程。 这使你灵活地更改业务流程根据业务需要而执行的操作。 示例会超过特定阈值以上的订单限制订单开票审批流程。  
  
  
## <a name="integration-of-heterogeneous-systems"></a>异构系统的集成  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 可以将集成系统将在不同的通信协议中的数据传输在其中对异类环境中的 IT 系统。 它会通过使用适配器连接到使用不同协议的系统。 它支持使用文件、 FTP、 HTTP、 SMTP、 SOAP 和 SQL 适配器。 可以使用 BizTalk 适配器框架来创建自定义适配器。 有关详细信息，请参阅[创建自定义适配器](../../core/developing-custom-adapters.md)。
  
## <a name="role-based-tools"></a>基于角色的工具  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 是在其中开发人员、 IT 专业人员和业务专业人员协作来创建、 实现、 操作、 维护和自定义系统的开发和执行环境。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 为每个角色提供为其自定义工具。  
  
 有关详细信息，请参阅[基于角色的产品](../../adapters-and-accelerators/accelerator-rosettanet/a-role-based-product2.md)，并[有关 RosettaNet 加速器](../../adapters-and-accelerators/accelerator-rosettanet/learn-the-rosettanet-accelerator-and-the-biztalk-tools-available.md)。
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何解决的业务需要](../../adapters-and-accelerators/accelerator-rosettanet/how-biztalk-server-solves-the-business-need1.md)   
 [BizTalk Accelerator for RosettaNet 向 BizTalk Server 添加的功能](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)

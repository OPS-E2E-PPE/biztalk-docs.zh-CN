---
title: "在业务流程中使用角色链接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- role links
- roles, links
- roles
- roles, about roles
- role links, about role links
- role links, properties
- role links, initializing
ms.assetid: 0cf85544-12c9-4541-8925-61a6e946cce0
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e3c4e4a4c3a99fb6e1962299d440717eaa8d51b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-role-links-in-orchestrations"></a>在业务流程中使用角色链接
角色链接将业务流程与贸易合作伙伴之间的交互活动以抽象的形式表现出来。 借助角色链接，您就可以在不改变整体业务流程的前提下，依据贸易合作伙伴解析、消息内容或数据库查询结果，动态地选择要交互的贸易合作伙伴。  
  
 例如在企业对企业方案中，有多个买方，一个供应商，同时该供应商还有多个发货机构。 如果一个买方向供应商发送采购订单，供应商通过参与方解析，就可以知道该采购订单是哪个买方发送的，从而采用相应的折扣。 而且，供应商还可依据所订购的商品，在运行时确定由哪个发货机构负责送货。 尽管每个发货机构都可能有自己的传输协议，但供应商仍可在运行时使用同一业务流程来应对所有发货机构，并确定要联系哪个发货机构。 在后面的阶段，如果传送代理更新其传输协议 — 例如，从 FTP 改为 HTTP-供应商仅需要使用 BizTalk 资源管理器或 BizTalk Server 管理控制台来更新与该特定传送代理关联的发送端口。 供应商不需要更改业务流程中的业务程序。  
  
## <a name="roles"></a>角色  
 业务流程中有两个角色：  
  
-   一个是“实现”角色，负责接收和处理消息。 该角色也称为提供者。  
  
-   一个是“使用”角色，负责发送消息。 该角色也称为使用者。  
  
## <a name="role-links"></a>角色链接  
 一个角色链接可包含一个使用者角色或一个提供者角色，也可各含一个。 使用者角色享受提供者角色提供的服务。 如果您所定义的角色链接具有一种或两种这样的角色，则将假定与您链接的合作伙伴充当了互补角色。  
  
 角色链接具有**SourceParty**属性， **DestinationParty**属性，且启动角色。 启动角色是在首次通信发生，并且这将因此启动角色链接通过设置的值的角色**DestinationParty**属性。  
  
 如果启动的角色仅适用于发送消息的使用者，则显式设置**DestinationParty**业务流程中的属性 （一次，并且一次）。 若要执行此操作，你设置的值**DestinationParty**中**表达式**形状，如以下示例，其中 ConfirmOrder 是相应角色的名称，使用省略号和单位名称是所示方的参数：  
  
```  
ConfirmOrder(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party("PartnerName", "OrganizationName");  
```  
  
 如果启动角色是提供用于接收消息， **DestinationParty**接收方自动初始化属性。 **DestinationParty**设置为提供程序本身。 **SourceParty**属性是只读的并且要为基于或与方相关联的证书上的安全标识符 (SID) 发件人的方名称解析的受信任的管道组件通过提供。 运行管道组件的主机必须标记为**受信任的身份验证**。 你可以获取的值**SourceParty**中**表达式**通过使用下面的示例代码的形状：  
  
 `PartyName = Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty);`  
  
## <a name="role-link-types"></a>角色链接类型  
 角色链接是由一个或两个角色组成的角色链接类型的实例。 使用角色链接类型时，请注意以下事项：  
  
-   对于任何给定的端口类型，只能在单个角色链接类型中对其引用一次。  
  
-   由于角色链接类型定义中包括端口类型，因此端口类型的作用域必须包含使用它的所有角色链接类型的作用域。  
  
-   使用业务活动服务 (BAS) 时，必须在同一 BizTalk 程序集中定义结构化的参数架构和与其相关联的角色链接类型。 由于与架构相关联的是角色链接类型，而不是组成该角色链接类型的各个角色，因此如果扮演不同角色的参与方共享包含该角色类型的程序集，则双方会看到相同的结构化参数架构。 如果双方使用相同的角色链接类型，但必须拥有不同的参数架构，则应创建不同的程序集。 各自程序集中的角色链接类型应完全相同。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何在业务流程中创建角色链接](../core/how-to-create-role-links-in-orchestrations.md)  
  
-   [如何使用角色链接形状](../core/how-to-use-the-role-link-shape.md)  
  
-   [如何使用角色链接向导](../core/how-to-use-the-role-link-wizard.md)  
  
## <a name="see-also"></a>另请参阅  
 [如何配置参与方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md)   
 [使用在业务流程中的端口](../core/using-ports-in-orchestrations.md)
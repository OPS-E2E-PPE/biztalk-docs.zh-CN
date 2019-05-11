---
title: 在业务流程中使用角色链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3508252cd77f002d635958f0f2bdc0202ace2d56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396558"
---
# <a name="using-role-links-in-orchestrations"></a>在业务流程中使用角色链接
角色链接是抽象的一种形式以用于在您的业务流程与贸易合作伙伴之间的交互。 角色链接，可以动态地选择要与之交互的贸易合作伙伴基于贸易合作伙伴解析、 消息内容或数据库查询结果，同时保持整体业务流程保持不变。  
  
 例如，在企业到企业方案中，有多个买方，一个供应商和供应商的多个发货机构。 当购买者向供应商发送采购订单时，供应商知道通过参与方解析哪个买方发送采购订单，并且可以采用相应的折扣。 供应商基于订购的商品，此外，确定在运行时的发货机构将负责交付。 尽管每个发货机构可能有其自己的传输协议，但供应商可以使用同一个业务流程在运行时来处理所有发货机构并确定哪个机构与进行交互。 在后面的阶段，如果发货机构更新其传输协议 — 例如，从 HTTP 到 FTP-供应商只需使用 BizTalk 浏览器或 BizTalk Server 管理控制台来更新与该特定发货机构相关联的发送端口。 供应商不需要更改其业务流程中，将驻留在业务流程中。  
  
## <a name="roles"></a>角色  
 在业务流程中有两个角色：  
  
-   "实现"角色来接收和处理消息。 此角色也称为是提供程序。  
  
-   若要将消息发送"使用"角色。 此角色是也称为使用者。  
  
## <a name="role-links"></a>角色链接  
 角色链接可以包含使用者或提供者角色或每个的一个。 使用者角色享受提供者角色提供的服务。 在定义的角色链接具有一个或两个这些角色时，假定要与之链接的合作伙伴，要满足了互补角色。  
  
 角色链接具有**SourceParty**属性， **DestinationParty**属性，以及初始化角色。 初始化角色是在首次通信出现，这种情况，和用于因此启动角色链接的值设置角色**DestinationParty**属性。  
  
 如果初始化角色是一个使用者发送消息，则显式设置**DestinationParty**属性 （仅一次） 在业务流程中的。 若要执行此操作，你设置的值**DestinationParty**中**表达式**形状，如下面的示例，其中，ConfirmOrder 是角色链接的名称，PartnerName 和 OrganizationName 是中所示参与方的参数：  
  
```  
ConfirmOrder(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party("PartnerName", "OrganizationName");  
```  
  
 如果初始化角色是用于接收消息，提供商**DestinationParty**接收方会自动初始化属性。 **DestinationParty**设置为提供程序本身。 **SourceParty**属性是只读的并且提供通过受信任的管道组件以解析参与方名称基于安全标识符 (SID) 发件人或与该参与方相关联的证书。 运行该管道组件的主机必须标记为**受信任验证**。 你可以获取的值**SourceParty**中**表达式**形状使用下面的示例代码：  
  
 `PartyName = Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty);`  
  
## <a name="role-link-types"></a>角色链接类型  
 角色链接是角色链接类型，其中包括一个或两个角色的实例。 当使用角色链接类型时，考虑以下方面：  
  
-   可以为任何给定的端口类型的单个角色链接类型中只有一次引用。  
  
-   角色链接类型定义包括端口类型，因为端口类型的作用域必须包含的所有使用它的角色链接类型。  
  
-   使用业务活动服务 (BAS) 时，必须中与之关联的角色链接类型相同的 BizTalk 程序集中定义结构化的参数架构。 因为架构关联角色链接类型而不是各个角色，组成该角色链接类型，如果扮演不同角色的参与方共享包含角色链接类型的程序集时，会看到相同的结构化的参数架构。 如果两个参与方使用相同的角色链接类型，但必须具有不同的参数架构，应为每个参与方创建不同的程序集。 应在每个程序集中重复的角色链接类型。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何在业务流程中创建角色链接](../core/how-to-create-role-links-in-orchestrations.md)  
  
-   [如何使用角色链接形状](../core/how-to-use-the-role-link-shape.md)  
  
-   [如何使用角色链接向导](../core/how-to-use-the-role-link-wizard.md)  
  
## <a name="see-also"></a>请参阅  
 [如何配置参与方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md)   
 [在业务流程中使用端口](../core/using-ports-in-orchestrations.md)
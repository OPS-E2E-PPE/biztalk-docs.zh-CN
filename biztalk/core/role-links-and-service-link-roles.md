---
title: 角色链接和服务链接角色 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, orchestrations
- service link roles
- role links
- roles, orchestrations
- roles
- roles, about roles
- service link roles, about service link roles
- orchestrations, roles
- role links, about role links
- orchestrations, deleting
ms.assetid: 23b4ca34-a1a5-44d4-a50d-661277681c72
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6630b1ad22ba86f3efe8a19409f3b731880c8a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268677"
---
# <a name="role-links-and-service-link-roles"></a>角色链接和服务器链接角色
A*角色*是使用服务或实现服务的端口类型集合。 角色表示参与方可以具有的与一个或多个业务流程之间的交互类型。 随着参与方数量的增加，使用角色可更便捷地进行管理。 例如，业务流程可能使用发运方角色。 该发运方将有一两个关联的参与方。 当业务流程确定使用哪家发运公司来发运货物时，它会比较发运方角色中各个参与方的价格。  
  
 A*角色链接类型*是一个属性，描述两个服务或业务流程之间的关系。 它定义了关系中双方服务的角色并指定了双方角色所提供的端口类型。  
  
 参与方（或组织单位）表示位于 BizTalk Server 之外与业务流程进行交互的实体。 在 BizTalk Server 中，您与之交换消息的每个组织都以参与方表示。 您可通过在角色中登记参与方来定义该参与方的交互方式。  
  
 如果角色链接类型与某个业务流程相关联，则可以部署或删除该类型。  
  
## <a name="orchestrations-and-roles"></a>业务流程和角色  
 在部署使用某个角色链接类型的业务流程时，配置数据库将保存该角色。 由于一个角色可以由多个业务流程使用，因此管理数据库将只保存该角色链接类型的一个副本。  
  
 如果 BizTalk 项目在不同的业务流程 (.odx) 文件中包含两个具有相同名称和命名空间的角色链接类型，则该 BizTalk 项目将不会进行编译。  
  
### <a name="orchestration-removals-that-use-roles"></a>使用角色的业务流程删除  
 由于一个角色链接类型可以由多个业务流程使用，因此在取消部署包含使用角色的业务流程的程序集时，只有在没有其他任何业务流程使用该角色时，管理数据库才会删除该角色。  
  
 此外，只有当角色中没有登记任何参与方时，管理数据库才会删除该角色。 就像不能覆盖具有已登记参与方的角色一样，您不能删除具有已登记参与方的角色。  
  
## <a name="see-also"></a>另请参阅  
 [在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)   
 [项目](../core/artifacts.md)
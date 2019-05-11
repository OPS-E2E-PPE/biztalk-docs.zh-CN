---
title: 角色链接和服务链接角色 |Microsoft Docs
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
ms.openlocfilehash: f7b52a13878363e79b9b2ffa3e600de16aeacd3c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254712"
---
# <a name="role-links-and-service-link-roles"></a>角色链接和服务链接角色
一个*角色*是使用一项服务或实现服务的端口类型集合。 角色表示参与方可以与一个或多个业务流程的交互的类型。 角色提供灵活性和易于管理的参与方增加数。 例如，业务流程可能使用发运方角色。 发运方具有与其关联的一个或两个参与方。 当业务流程确定哪家送货公司来发运货物的使用时，它会比较发运方角色中各个参与方的价格。  
  
 一个*角色链接类型*是两个服务或业务流程之间的关系的属性。 它定义每个关系中服务的作用，并指定每个角色提供的端口类型。  
  
 参与方或组织单位，表示位于与业务流程交互的 BizTalk Server 之外的实体。 在 BizTalk Server 中，与之交换消息每个组织都以参与方表示。 您可以定义通过在角色中登记参与方的交互方式。  
  
 你可以部署或与业务流程关联后删除角色链接类型。  
  
## <a name="orchestrations-and-roles"></a>业务流程和角色  
 在部署使用角色链接类型的业务流程时，配置数据库将保存该角色。 由于一个角色可以由多个业务流程，管理数据库将保存角色链接类型只有一个的副本。  
  
 如果您的 BizTalk 项目包含两个单独的业务流程 (.odx) 文件中具有相同名称和命名空间中的角色链接类型，不会进行编译您的 BizTalk 项目。  
  
### <a name="orchestration-removals-that-use-roles"></a>使用角色的业务流程删除  
 由于角色链接类型可以使用多个业务流程，取消部署包含使用角色的业务流程的程序集时，管理数据库中删除角色，仅当没有其他业务流程使用该角色。  
  
 此外，管理数据库中删除角色仅在没有任何与其已登记的参与方。 正如您无法覆盖具有已登记的参与方的角色，则无法删除具有与其已登记参与方的角色。  
  
## <a name="see-also"></a>请参阅  
 [在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)   
 [项目](../core/artifacts.md)
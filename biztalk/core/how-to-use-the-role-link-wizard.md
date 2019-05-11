---
title: 如何使用角色链接向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- links [roles]
- Role Link Wizard [Orchestration Designer]
- roles, links
- Orchestration Designer, Role Link Wizard
- role links, Role Link Wizard [Orchestration Designer]
- links [roles], about links
ms.assetid: ddc33d87-c08d-4193-9483-4644ef302853
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5336dcbb129b01be8fc03c43756bb1fc1ac53063
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333202"
---
# <a name="how-to-use-the-role-link-wizard"></a>如何使用角色链接向导
角色链接向导，可创建新的角色链接或修改一个现有。 可以使用它来设置或查看名称、 类型和角色链接，以及实现角色和撰写的角色链接类型使用角色的访问限制。 若要了解如何角色链接的工作，请参阅[业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。  
  
 **角色链接名称**:角色链接名称为您填充，并为要配置的现有角色链接的当前名称或自动生成的名称，如果要创建新的角色链接。 在任一情况下可以修改名称。  
  
 **角色链接类型**:可以选择现有角色链接类型，也可以创建一个新。 是否要配置新的或现有角色链接类型，您可以指定您的业务流程参与服务的方式。  
  
> [!NOTE]
>  我们建议你创建的角色链接类型和关联的端口类型之前，若要创建角色链接，以便您可以使用现有角色链接类型用于定义角色链接。 有关详细信息，请参阅[如何在业务流程中创建角色链接](../core/how-to-create-role-links-in-orchestrations.md)。  
  
 **角色链接用法**:如果创建新的角色链接类型，会自动为您创建实现和使用角色。 可以选择反映了您的业务流程参与服务的方式的角色。 完成向导中的步骤后，可以重命名角色标识符或删除角色以更好地匹配您的实现。 角色链接类型必须包含一个是角色类型或每个角色类型之一。 当您单击**确定**，未配置的角色创建与每个名称相对应。 此外可以在类型窗口中选择端口类型的角色。  
  
> [!NOTE]
>  如果您调用端口配置向导以创建端口类型为角色链接类型，并且想要选择以前定义的端口类型，请确保端口类型的访问限制与角色链接类型的访问限制不冲突。  
  
## <a name="see-also"></a>请参阅  
 [在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)
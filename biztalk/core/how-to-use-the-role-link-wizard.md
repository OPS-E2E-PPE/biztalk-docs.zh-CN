---
title: "如何使用角色链接向导 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- links [roles]
- Role Link Wizard [Orchestration Designer]
- roles, links
- Orchestration Designer, Role Link Wizard
- role links, Role Link Wizard [Orchestration Designer]
- links [roles], about links
ms.assetid: ddc33d87-c08d-4193-9483-4644ef302853
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d31abcc8fcc2bfaf1ebd641e1e52ad08d1c9c9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-role-link-wizard"></a>如何使用角色链接向导
使用角色链接向导，您可以创建新的角色链接或修改现有的角色链接。 您可以使用该向导设置或查看角色链接的名称、类型和访问限制，以及组成该角色链接类型的实现角色和使用角色。 若要了解如何角色链接工作，请参阅[在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)。  
  
 **角色链接名称**： 角色链接名称为您填写和为你进行配置，现有角色链接的当前名称或自动生成的名称，如果要创建新的角色链接。 在上述两种情况下，您都可以修改名称。  
  
 **角色链接类型**： 你可以选择现有角色链接类型，或创建一个新。 无论您是配置新的角色链接类型还是选择现有角色链接类型，都可以指定业务流程参与服务的方式。  
  
> [!NOTE]
>  建议您在创建角色链接前，先创建角色链接类型和相关端口类型，以便可以使用现有角色链接类型来定义角色链接。 有关详细信息，请参阅[如何创建用户角色在业务流程中的链接](../core/how-to-create-role-links-in-orchestrations.md)。  
  
 **角色链接用法**： 如果你创建新的角色链接类型，这两个实现和使用角色会自动为您创建。 您可以选择反映您的业务流程参与服务的方式的角色。 在您完成向导中的各步骤之后，可以重命名角色标识符或删除角色以更好地匹配您的实现。 角色链接类型必须包含两个角色类型之一，或者每个角色类型各包含一个。 当你单击**确定**，未配置的角色创建与每个名称对应。 您还可以在“类型”窗口中为角色选择端口类型。  
  
> [!NOTE]
>  如果您调用端口配置向导来为您的角色链接类型创建端口类型，并且要选择以前定义的端口类型，则请确保该端口类型的访问限制与角色链接类型的访问限制不冲突。  
  
## <a name="see-also"></a>另请参阅  
 [在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)
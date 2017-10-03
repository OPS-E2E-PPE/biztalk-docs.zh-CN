---
title: "如何配置相关类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deleting, correlation types
- correlation types, configuring
- correlation types, deleting
- configuring, correlation types
ms.assetid: cfae4d2e-ec79-45c8-93b3-799dc5e0576e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 646ac7dafd5207a2558e45252077efe2d9616a70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-correlation-types"></a>如何配置相关类型
你使用**相关性属性**对话框中添加或删除相关类型的属性。 相关类型列出相关集中的属性，发送活动和接收活动使用这些属性来确保在运行时将传入消息与业务流程的正确实例相关联。  
  
 该对话框中有两个窗格，每个窗格都包含一个属性列表。 左侧窗格的是“可用属性”，包含您项目中定义或引用的所有属性的树视图。 默认情况下显示的属性为系统属性，是 BizTalk Server 定义的，但您也可以在属性架构中定义您自己的属性。 有关创建属性架构的详细信息，请参阅[属性架构](../core/property-schemas.md)。  
  
> [!NOTE]
>  架构属性必须升级，才能在相关类型中使用。 有关详细信息，请参阅[提升属性](../core/promoting-properties.md)。  
  
### <a name="to-add-and-configure-a-correlation-type"></a>添加和配置相关类型  
  
-   在业务流程视图窗口中，右键单击**相关性类型**，然后单击**新相关类型**。  
  
     **相关性属性**弹出对话框。 添加要包含在相关类型中的属性。  
  
    > [!NOTE]
    >  如果你访问**相关性属性**对话框直接从相关设置，如果尚不存在创建关联集的相关类型。 您的更改将被保存到新相关类型中，且相关集将被配置为使用该新相关类型。 如果该相关集已有相关类型，则您的更改将会修改该相关类型。  
  
### <a name="to-remove-a-correlation-type"></a>删除相关类型  
  
-   在业务流程视图窗口中，右键单击你想要删除，然后单击相关类型**删除**。
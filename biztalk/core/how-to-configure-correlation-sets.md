---
title: "如何配置相关设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- correlation sets, send activities
- correlation sets, assigning correlation types
- correlation types, correlation sets
- correlation sets, receive activities
- configuring, correlation sets
- correlation sets, configuring
- correlation types, assigning
ms.assetid: 060bf2ba-c173-4dca-a8c4-4c5341e5ceaa
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52bcb0216fc24e14107c7632df97671b64f2ac1d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-correlation-sets"></a>如何配置相关设置
若要配置相关集，您可以选择现有相关类型、创建新的相关类型或修改现有相关类型。  
  
### <a name="to-assign-a-correlation-type-to-a-correlation-set"></a>向相关集分配相关类型  
  
-   选择现有相关类型。  
  
     \-或者-  
  
     右键单击新的相关类型并选择**配置相关性属性**。  
  
     \-或者-  
  
     单击省略号 (**...**) 上的按钮**相关**中的属性**属性**窗口。  
  
     **相关性属性**弹出对话框。 添加要包含在相关集中的属性。 如果尚未将相关类型分配给相关集，则将创建一个新相关类型。  
  
 如果你的关联集，已存在的相关类型和添加或删除具有属性**相关性属性**对话框中，现有相关性类型将进行相应修改。  
  
#### <a name="to-associate-send-and-receive-activities-with-a-correlation-set"></a>将发送和接收活动与相关集相关联  
  
1.  展开**相关设置**节点。  
  
2.  从下拉列表中选择发送或接收活动。  
  
     \-或者-  
  
     选择设置中的相关**初始化关联集**属性或**以下相关集**中的属性**属性**每个窗口**发送**或**接收**你想要将与相关集相关联的形状。  
  
#### <a name="to-disassociate-send-and-receive-activities-from-a-correlation-set"></a>取消发送和接收活动与相关集的关联  
  
-   在**业务流程视图**窗口中，根据需要展开相关集节点，右键单击你想要删除，，然后单击的活动**删除**。  
  
     \-或者-  
  
     清除关联集在**初始化关联集**属性或**以下相关集**中的属性**属性**每个窗口**发送**或**接收**你想要解除与相关集关联的形状。  
  
## <a name="see-also"></a>另请参阅  
 [使用接收消息形状使用筛选器](../core/using-filters-with-the-receive-message-shape.md)   
 [在业务流程中使用相关性](../core/using-correlations-in-orchestrations.md)
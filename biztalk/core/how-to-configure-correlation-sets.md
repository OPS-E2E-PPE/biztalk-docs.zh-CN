---
title: 如何配置相关集 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51c56d7f319023bb0379050452253c65634929c0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968854"
---
# <a name="how-to-configure-correlation-sets"></a>如何配置相关集
若要配置相关集，您可以选择现有相关类型、创建新的相关类型或修改现有相关类型。  
  
### <a name="to-assign-a-correlation-type-to-a-correlation-set"></a>向相关集分配相关类型  
  
- 选择现有相关类型。  
  
   \- 或 -  
  
   右键单击新相关类型并选择**配置相关性属性**。  
  
   \- 或 -  
  
   单击省略号 (**...**) 按钮**相关**中的属性**属性**窗口。  
  
   **相关性属性**弹出对话框。 添加要包含在相关集中的属性。 如果尚未将相关类型分配给相关集，则将创建一个新相关类型。  
  
  如果某一相关类型已存在的相关集，并且添加或删除具有的属性**相关性属性**对话框中，现有相关类型将进行相应修改。  
  
#### <a name="to-associate-send-and-receive-activities-with-a-correlation-set"></a>将发送和接收活动与相关集相关联  
  
1.  展开**相关集**节点。  
  
2.  从下拉列表中选择发送或接收活动。  
  
     \- 或 -  
  
     选择相关集中任意一种**初始化相关集**属性或**沿用相关集**中的属性**属性**为每个窗口**发送**或**接收**你想要将与相关集相关联的形状。  
  
#### <a name="to-disassociate-send-and-receive-activities-from-a-correlation-set"></a>取消发送和接收活动与相关集的关联  
  
-   在中**业务流程视图**窗口中，如有必要展开相关集节点，右键单击你想要删除，然后单击的活动**删除**。  
  
     \- 或 -  
  
     清除相关集中任意一种**初始化相关集**属性或**沿用相关集**中的属性**属性**窗口中的每个**发送**或**接收**你想要从该相关集取消关联的形状。  
  
## <a name="see-also"></a>请参阅  
 [接收消息形状中使用筛选器](../core/using-filters-with-the-receive-message-shape.md)   
 [在业务流程中使用关联](../core/using-correlations-in-orchestrations.md)
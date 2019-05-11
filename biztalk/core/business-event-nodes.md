---
title: 业务事件节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events, Tracking Profile Editor
- events, date specific
- events, time specific
- Tracking Profile Editor, node descriptions
- Business Event nodes [Tracking Profile Editor]
- Tracking Profile Editor, events
ms.assetid: 177bc3c4-e762-42fe-80bc-edede5cd4fcd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 213f97f2a0e4276cfc3e49d52ff69c222b6b7959
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357687"
---
# <a name="business-event-nodes"></a>业务事件节点
业务事件或里程碑节点定义特定于日期或时间的事件。 从业务最终用户导入活动定义中的预定义的业务事件和里程碑文件夹存在并且不能删除它们而无需重新导入活动定义文件。  
  
## <a name="working-with-business-event-nodes"></a>使用业务事件节点  
 您可以将形状从业务流程拖到业务事件文件夹，以执行形状完成时跟踪这些事件。  
  
 TPE 将形状的名称用于事件文件夹的名称和此文件夹将具有一个唯一的图标。 例如，在示例贷款流程方案中，tpe 根据事件，如 Approved 或 Denied。 该业务流程涉及多个跟踪配置文件时，应只跟踪一次每个业务流程的业务事件。 如果在业务流程中有一个条件路径，可以选择这两个路径中的业务事件，因为只有一个会执行。 不应选择一个循环内的形状。  
  
> [!NOTE]
>  虽然您无法删除文件夹，而无需重新导入活动定义，可以删除形状 （事件）。  
  
## <a name="see-also"></a>请参阅  
 [“TPE 活动视图”节点](../core/tpe-activity-view-nodes.md)
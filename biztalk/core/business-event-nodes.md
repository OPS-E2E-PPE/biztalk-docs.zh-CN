---
title: 业务事件节点 |Microsoft 文档
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
ms.openlocfilehash: 44c3d06e553f129abb36eb53c4dde9c5ab9c25f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230901"
---
# <a name="business-event-nodes"></a>业务事件节点
业务事件节点或里程碑节点定义特定于日期或时间的事件。 预定义的业务事件文件夹和里程碑文件夹包含在从业务最终用户导入的活动定义中，您在没有重新导入活动定义文件时不能删除这些文件夹。  
  
## <a name="working-with-business-event-nodes"></a>使用业务事件节点  
 可以将业务流程中的形状拖动到业务事件文件夹，以在执行形状完成时跟踪这些事件。  
  
 TPE 将形状的名称用作事件文件夹的名称，并且此文件夹将具有一个唯一的图标。 例如，在贷款流程方案示例中，TPE 根据事件命名文件夹（如 Approved 或 Denied）。 当业务流程涉及多个跟踪配置文件时，对每个业务流程应只跟踪一次业务事件。 如果业务流程中有一个条件路径，则可以从条件的两个路径中选择业务事件，而只会执行一个路径中的业务事件。 不要选择循环内的形状。  
  
> [!NOTE]
>  不重新导入活动定义就不能删除文件夹，但可以删除形状（事件）。  
  
## <a name="see-also"></a>另请参阅  
 [键入活动视图节点](../core/tpe-activity-view-nodes.md)
---
title: 数据项节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definition files [BAM], data items
- Data Item nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- Tracking Profile Editor, definition files [BAM]
ms.assetid: 95856bfa-90e3-49d9-b55b-5f1b35a23f78
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a968bf7533697922938eeb8953f17813c77147c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238021"
---
# <a name="data-item-nodes"></a>数据项节点
数据项节点存在于开发人员从业务分析员创建的观察模型所导入的活动定义文件中。 跟踪配置文件编辑器 (TPE) 将为所跟踪的数据项命名相应的节点（如“客户姓名”）。 然后，您可以将一个或多个数据项从消息架构视图拖到对应于“客户姓名”的节点。  
  
## <a name="working-with-data-item-nodes"></a>使用数据项节点  
 映射数据项节点时，如果业务流程涉及多个跟踪配置文件，则只应在每个业务流程中跟踪数据项一次。 如果业务流程中有一个条件路径，则可以同时从这两个路径中选择数据项，因为只运行其中一个。 但是，除非每一迭代数据项的值都不同，否则请不要选择循环中的形状。  
  
## <a name="see-also"></a>另请参阅  
 [如何将映射项数据](../core/how-to-map-item-data.md)   
 [键入活动视图节点](../core/tpe-activity-view-nodes.md)
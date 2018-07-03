---
title: 活动和 ActivityID 节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ActivityID nodes [Tracking Profile Editor]
- Activity nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- activities [BAM], definitions
ms.assetid: 94d4130a-53c5-4cd5-916a-4a6bd9acbf23
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbe92c28a3ca84cdd94236c1069c9d340cc4630f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983558"
---
# <a name="activity-and-activityid-nodes"></a>活动和 ActivityID 节点
活动节点 和 ActivityID 节点用于包含和标识活动定义。 活动节点是活动定义中项的父文件夹。 所有数据项和业务事件节点都属于或包含于相关的活动节点中。 活动节点的名称应该反映活动本身的名称。  
  
 ActivityID 节点是活动定义中自动生成的项，用于保存活动的唯一标识符。 ActivityID 节点可用于跟踪用户提供的标识符或系统生成的标识符。 例如，如果将采购订单的编号作为系统中所有采购订单的唯一标识符，则可以将此标识符用作 ActivityID，此时将从某些事件源（如采购订单架构中的采购订单编号字段）映射 ActivityID 的值。 反之，如果采购订单值不是唯一的，则可以不映射节点，BAM 将在运行时将自动生成唯一标识符。  
  
 活动可关联至其他活动。 在某些方案中，这些关系明确地作为观察模型的一部分。  具体而言，当用户视图中包含两个或多个活动时，这些活动之间将自动产生关系。  存在这种关系后，在活动树的活动节点下将自动为每个已知的同级活动创建关系节点。 如果存在数据关系而不存在延伸视图，则您可以手动向活动树中添加关系节点。  
  
 无论哪种情况，关系节点的用途都是为相关的活动提供标识符。 例如，采购订单和发货可以有多对多关系（一个 PO 需要多次发货，一次发货可以运送多个 PO 的产品)。  每个采购订单的活动记录可以有多个指向相关发货的指针，而每个发货活动记录可以指向一个或多个采购订单。  如果用数据库术语来描述，关系节点的值就是指向其他活动的表的外键。  
  
## <a name="working-with-activity-id-nodes"></a>使用 ActivityID 节点  
 例如，考虑以下方案： EquityLoan 业务流程包含活动文件夹 LoanProcess。 它引用如下所示的业务事件：  
  
- LoanApplicationReceived  
  
- CHRequest  
  
- CHResponse  
  
- AppraisalRequest  
  
- AppraisalResponse  
  
- 已同意  
  
- 拒绝  
  
  解决方案开发人员使用 ActivityID 节点可以提取唯一标识活动的数据，如采购订单编号；而对于实例情形而言，应该提取的是消息的 SSN 字段。 如果没有向 ActivityID 节点拖放任何数据，则自动生成的 GUID 将标识业务活动。  
  
  若要在不同业务流程中的业务事件或里程碑之间定义关系，则目标业务流程必须引用 ActivityID。 有关如何使用 TPE 实现关系的详细信息，请参阅[关系节点](../core/relationship-nodes.md)。  
  
## <a name="see-also"></a>请参阅  
 [“TPE 活动视图”节点](../core/tpe-activity-view-nodes.md)
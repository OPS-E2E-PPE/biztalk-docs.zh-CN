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
ms.openlocfilehash: e0ad89c82f7eac4aca14ca3d424a5bda6056f95f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361821"
---
# <a name="activity-and-activityid-nodes"></a>活动和 ActivityID 节点
活动和 ActivityID 节点用于包含和标识活动定义。 活动节点是活动定义中的项的父文件夹。 所有数据项和业务事件节点都都属于或包含在相关的活动节点。 活动节点的名称应反映活动本身的名称。  
  
 ActivityID 节点是活动定义中自动生成的项，旨在用于保存活动的唯一标识符。 ActivityID 节点可用于跟踪用户提供的标识符或系统生成的标识符。 例如，在其中有采购订单号的唯一标识符作为所有采购订单的系统中的情况下，您可以使用它作为 ActivityID，在这种情况下将映射从某些事件源，例如采购订单编号字段中的 ActivityID 的值 采购订单架构。 但是，如果采购订单值不是唯一的则可以将映射节点，并且 BAM 将自动生成在运行时的唯一标识符。  
  
 可以与其他活动相关的活动。 在某些情况下这些关系是显式的观察模型的一部分。  具体而言，当用户视图中包含两个或多个活动，自动产生关系之间没有这些活动。  存在此类关系时，将自动在活动树中，每个已知的同级活动的活动节点下创建关系节点。 在方案中，为数据关系，不存在延伸视图，可以手动添加关系节点到活动树。  
  
 在任一情况下，关系节点的目的是为相关的活动提供标识符。 例如，采购订单和发货可以有多对多关系 （一个 PO 需要多次发货情况; 一次发货可以满足许多 POs 产品）。  每个采购订单的活动记录可以有多个指向相关发货和每个发货活动记录可以指向一个或多个采购订单。  在数据库术语中，关系节点的值是其他活动到表的外键。  
  
## <a name="working-with-activity-id-nodes"></a>使用活动 ID 节点  
 例如，考虑以下方案： EquityLoan 业务流程包含活动文件夹 LoanProcess。 它引用了业务事件包括以下：  
  
- LoanApplicationReceived  
  
- CHRequest  
  
- CHResponse  
  
- AppraisalRequest  
  
- AppraisalResponse  
  
- 已批准  
  
- 拒绝  
  
  解决方案开发人员，以提取数据，唯一标识活动，例如采购订单编号，或者，在示例方案中，该消息的 SSN 字段的情况下使用 ActivityID 节点可以。 如果向 ActivityID 节点不拖放任何数据，自动生成的 GUID 标识的业务活动。  
  
  若要在不同的业务流程中定义业务事件或里程碑之间的关系，则目标业务流程必须引用 ActivityID。 有关如何使用 TPE 实现关系的详细信息，请参阅[关系节点](../core/relationship-nodes.md)。  
  
## <a name="see-also"></a>请参阅  
 [“TPE 活动视图”节点](../core/tpe-activity-view-nodes.md)
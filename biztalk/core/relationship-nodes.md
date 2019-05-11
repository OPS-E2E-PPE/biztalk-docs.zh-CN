---
title: 关系节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definition files [BAM], relationships
- definition files [BAM], Tracking Profile Editor
- Relationship nodes [Tracking Profile Editor]
- activities [BAM], relationships
- activities [BAM], Tracking Profile Editor
- Tracking Profile Editor, node descriptions
- Tracking Profile Editor, definition files [BAM]
ms.assetid: 74090133-24d1-4aba-a4fc-f12d19c881fb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce7acbed8914fa7af8c80e739c9d29279df1054d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397985"
---
# <a name="relationship-nodes"></a>关系节点
当活动定义文件中包含多个活动时使用关系文件夹。 文件夹的名称匹配关联的活动的名称。 通过向相关活动的活动 ID 的关系文件夹的名称匹配的和匹配的值的数据项目，可以形成链接。 定义使用单独的节点的每个关系。  
  
## <a name="working-with-relationship-nodes"></a>使用关系节点  
 指示链接的活动之间的数据项目的唯一实例标识符：  
  
- 将一个数据项映射到主业务流程的 ActivityId 节点。  
  
- 拖放相关活动中具有相同的名称上面的关系节点到的数据项。 关系节点具有与主活动的活动节点相同的名称。  
  
  例如，在示例方案中，可能有相关但不同的业务流程表示在调用 RefinanceOrchestration 业务流程中。 该业务流程可以包含 LoanRefinance 活动节点、 Refinance ActivityID 和业务流程形状，如接收评价请求。 关系节点和关系 ID，但是，可以是 LoanID，指示链接到原始 LoanProcess 活动。  
  
## <a name="see-also"></a>请参阅  
 [“TPE 活动视图”节点](../core/tpe-activity-view-nodes.md)
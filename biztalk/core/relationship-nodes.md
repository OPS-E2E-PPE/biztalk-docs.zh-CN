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
ms.openlocfilehash: 866a2e1367279c6a53eeb738f4800a647a0cd468
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001750"
---
# <a name="relationship-nodes"></a>关系节点
只要活动定义文件包含多个活动，就要使用关系文件夹。 这些文件夹的名称与相关活动的名称匹配。 通过将关系文件夹的名称与相关活动的活动 ID 进行匹配并匹配数据项的值，可以形成链接。 您需要使用单独的节点定义每个关系。  
  
## <a name="working-with-relationship-nodes"></a>使用关系节点  
 指示在活动之间链接数据项的唯一实例标识符：  
  
- 将一个数据项映射到主业务流程的 ActivityId 节点。  
  
- 将与上述数据项同名的数据项拖放到相关活动的关系节点中。 该关系节点具有与主活动的活动节点相同的名称。  
  
  例如，在示例方案中，名为“RefinanceOrchestration”的业务流程中可以有一个相关但独立的业务程序。 该业务流程可以包含 LoanRefinance 活动节点、Refinance ActivityID 和业务流程形状（如接收评价请求）。 但是，关系节点和关系 ID 可以是 LoanID，指示链接到原始 LoanProcess 活动。  
  
## <a name="see-also"></a>请参阅  
 [“TPE 活动视图”节点](../core/tpe-activity-view-nodes.md)
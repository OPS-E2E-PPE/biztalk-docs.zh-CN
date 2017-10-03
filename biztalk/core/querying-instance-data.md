---
title: "查询实例数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BAM, instance data
- queries [BAM], instance data
ms.assetid: ae4a8854-d5c2-4b36-a0ef-3f74e138306e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 762ad9dd241f65db700e452a2ac181442c863607
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="querying-instance-data"></a>查询实例数据
关于各个活动实例的数据可在 BAM 主导入数据库中动态创建的 SQL 视图内进行查询。  
  
 此视图的名称是  
  
 **bam_\<**  *ViewName* **> _\<**  *ActivityName* **> 查看 （_v)**  
  
 位置  
  
 **\<***ViewName*  **>** 为在 BAM 定义 XML 中，视图元素的名称属性即相同在相关的 Microsoft Excel 向导中输入视图名称。  
  
 **\<***ActivityName*  **>** 为在 BAM 定义 XML 中，活动元素的名称属性即相同当在 Excel 向导中输入的活动名称。  
  
 在查询实例数据时，请一定要注意下列情况：  
  
-   如果您通过 DirectEventStream 向 BAM 发送活动数据，则实例数据没有延迟时间，这意味着调用应用程序中的事务提交后，实例数据会立刻显示。  
  
-   如果活动数据通过 BufferedEventStream 发送到 BAM，则实例数据将在查询执行几秒钟后显示，具体情况取决于 BAM 事件总线服务的负载以及 BAM 主导入数据库的宿主 SQL 服务器。  
  
-   此视图背后的表的实际结构较复杂，这是为了确保当前或最新活动的数据可供查询，而活动查询不再需要的已完成活动的数据则被存档或清除，同时又不使系统脱机。 有关详细信息，请参阅[活动数据存储](../core/activity-data-storage.md)。  
  
## <a name="see-also"></a>另请参阅  
 [活动数据存储](../core/activity-data-storage.md)   
 [查询 BAM 数据](../core/querying-bam-data.md)
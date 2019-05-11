---
title: 查询实例数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, instance data
- queries [BAM], instance data
ms.assetid: ae4a8854-d5c2-4b36-a0ef-3f74e138306e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 083bbe25734f5305c2c7e49837955f648a65a52d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398299"
---
# <a name="querying-instance-data"></a>查询实例数据
有关各个活动实例的数据是可在 BAM 主导入数据库中动态创建的 SQL 视图中进行查询。  
  
 此视图的名称是  
  
 **bam_\<** *ViewName* **\>_\<** *ActivityName* **\>_View**  
  
 位置  
  
 **\<** *ViewName* **\>** 是 BAM 定义 XML 中 View 元素的名称属性即相同相关的 Microsoft Excel 向导中输入视图名称。  
  
 **\<** *ActivityName* **\>** 是 BAM 定义 XML 中的 Activity 元素的名称属性即相同在 Excel 向导中输入的活动名称。  
  
 请务必查询实例数据时，请注意以下条件：  
  
-   如果活动数据发送到通过 DirectEventStream BAM 时，实例数据有没有延迟时间，这意味着，会立刻显示调用应用程序中的事务提交后。  
  
-   如果活动数据发送到 BAM 通过 BufferedEventStream，数据会显示注册实例查询几秒钟后，具体取决于 BAM 事件总线服务和承载 BAM 主导入数据库的 SQL 服务器的负载。  
  
-   此视图背后的表的实际结构是更复杂，以确保当前或最近活动的数据可用于查询，而存档或清除活动的已完成并且不再需要使活动查询数据无需使系统脱机。 有关详细信息，请参阅[活动数据存储](../core/activity-data-storage.md)。  
  
## <a name="see-also"></a>请参阅  
 [活动数据存储](../core/activity-data-storage.md)   
 [查询 BAM 数据](../core/querying-bam-data.md)
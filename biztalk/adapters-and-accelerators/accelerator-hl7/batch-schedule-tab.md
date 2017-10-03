---
title: "批处理计划选项卡 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: btahl7.configurationexplorer.tab.batchschedule
helpviewer_keywords:
- batching, scheduling
- Batch Schedule tab [Configuration Explorer]
- scheduling batching
ms.assetid: 3792388b-6af2-41c2-8f41-bdfda7e17b2b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d870abad399dcca76c32a3a8d0e8c6637fc93284
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="batch-schedule-tab"></a>批处理计划选项卡
你使用**批处理计划**选项卡以激活、 请求或终止出站批处理。 激活的出站批处理包括两个步骤： 配置基于时间的或消息计数条件，然后启动出站批处理业务流程。  
  
 你可以配置[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]创建基于时间的使用的出站批处理或消息计数条件或两者的组合。 设置批处理激活条件是可选的。 如果未指定，则可以手动激活一批。 如果你想要激活使用基于时间的一批或消息计数条件，则必须在激活批处理之前指定这些条件。  
  
 在**BTAHL7 配置资源管理器**对话框中，在**批处理计划**选项卡上，执行以下操作：  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**第一次批处理前的小时数**|键入前启动第一批的小时数。<br /><br /> 当你选择作为批处理控件的消息计数时，此选项不可用。|  
|**重复后的批处理**|选择以下选项之一：<br /><br /> -                   **小时**。 键入要重复批处理过程前等待小时的数。<br /><br /> -                   **消息**。 键入你想要在启动下一批之前处理的消息数。|  
|**批处理控件**|使用以下选项：<br /><br /> -                   **启动计划**： 选择此选项以开始你批处理的计划。<br /><br /> -                   **立即发送**： 选择此选项以立即开始批处理。 此设置将替代**小时以后再开始第一批**和**重复批处理后**设置。<br /><br /> -                   **停止计划**： 选择此选项以停止当前的批处理计划。 这完成当前批次，然后停止批处理业务流程。|
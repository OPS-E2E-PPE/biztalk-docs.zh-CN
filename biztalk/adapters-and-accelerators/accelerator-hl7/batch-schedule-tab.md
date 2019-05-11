---
title: 批处理计划选项卡 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.batchschedule
helpviewer_keywords:
- batching, scheduling
- Batch Schedule tab [Configuration Explorer]
- scheduling batching
ms.assetid: 3792388b-6af2-41c2-8f41-bdfda7e17b2b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bf479425a6a0e80b75791d9b43ee0880e6ada63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251805"
---
# <a name="batch-schedule-tab"></a>批处理计划选项卡
您使用**批处理计划**选项卡以激活、 请求或终止出站批。 激活的出站批包括两个步骤： 配置基于时间的或消息计数条件，然后启动出站批处理业务流程。  
  
 你可以配置[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]创建基于时间的使用出站批或消息计数条件或这两者的组合。 设置批处理激活条件是可选的。 如果未指定，则可以手动激活批处理。 如果你想要激活使用基于时间的批处理或消息计数条件，则必须在激活批处理之前指定这些条件。  
  
 在中**BTAHL7 配置资源管理器**对话框中，在**批处理计划**选项卡上，执行以下操作：  
  
|使用此选项|执行的操作|  
|--------------|----------------|  
|**第一次批处理之前的小时数**|键入前启动第一批的小时数。<br /><br /> 选择消息计数作为批处理控件时，此选项不可用。|  
|**重复执行批处理后**|选择以下选项之一：<br /><br /> -                   **小时**。 键入要重复批处理过程之前等待小时的数。<br /><br /> -                   **消息**。 键入你想要启动下一批之前处理的消息数。|  
|**批处理控件**|使用以下选项：<br /><br /> -                   **启动计划**:选择此选项以启动批处理计划。<br /><br /> -                   **立即发送**:选择此选项以立即启动批处理过程。 此设置将替代**小时之后第一批,** 并**重复执行批处理后**设置。<br /><br /> -                   **停止计划**:选择此选项可停止当前批处理计划。 这完成当前批次，然后停止批处理业务流程。|
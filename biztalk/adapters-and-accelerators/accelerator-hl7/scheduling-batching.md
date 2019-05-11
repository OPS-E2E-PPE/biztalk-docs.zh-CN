---
title: 计划批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, scheduling
- scheduling batching
ms.assetid: 037626f1-1b3b-43e6-80eb-5fb900cdbd46
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1522a050fc6cc1b690cdd59adb26ddde5d7449f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289900"
---
# <a name="scheduling-batching"></a>计划批处理
您使用[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]配置资源管理器来激活、 请求，或终止出站批。 激活的出站批包括两个步骤： 配置基于时间的或消息计数条件，然后启动出站批处理业务流程。  
  
 下图显示[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**批处理计划**选项卡。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")  
  
 使用以下过程来打开[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器和计划批处理。  
  
### <a name="to-open-btahl7-configuration-explorer"></a>若要打开 BTAHL7 配置资源管理器  
  
-   单击**启动**，依次指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  
  
### <a name="to-schedule-message-batching"></a>若要计划消息批处理  
  
1.  打开 BTAHL7 配置资源管理器。  
  
2.  在 BTAHL7 配置资源管理器中**BTAHL7 配置资源管理器**对话框中，在**方**选项卡上，选择你想要配置，该参与的方，然后在**批处理计划**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**第一次批处理之前的小时数**|键入第一批是启动前的小时数。|  
    |**重复执行批处理后**|选择下列选项之一：<br /><br /> -   **小时**。 键入要重复批处理过程的小时数。<br />-   **消息**。 开始键入你想要在下一步的批处理过程之前处理的消息数。|  
    |**批处理控件**|选择下列选项之一：<br /><br /> -   **启动计划**:选择此项可启动批处理计划。<br />-   **立即发送**:选择此选项可以立即启动批处理过程。<br />-   **停止计划**:选择此项可停止当前批处理计划。|  
  
## <a name="see-also"></a>请参阅  
 [配置批处理确认](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)
---
title: 计划批处理 |Microsoft 文档
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
ms.openlocfilehash: 790cf5cb853da211d5e8928f398ecc1a2b3fe0ba
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961531"
---
# <a name="scheduling-batching"></a>计划批处理
你使用[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]配置资源管理器，若要激活、 请求，或终止出站批处理。 激活的出站批处理包括两个步骤： 配置基于时间的或消息计数条件，然后启动出站批处理业务流程。  
  
 下图显示[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器**批处理计划**选项卡。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")  
  
 使用以下过程来打开[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器和计划批处理。  
  
### <a name="to-open-btahl7-configuration-explorer"></a>若要打开 BTAHL7 配置资源管理器  
  
-   单击**启动**，指向**程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  
  
### <a name="to-schedule-message-batching"></a>若要计划消息批处理  
  
1.  打开 BTAHL7 配置资源管理器。  
  
2.  在 BTAHL7 配置资源管理器，在**BTAHL7 配置资源管理器**对话框中，在**方**选项卡上，选择你想要配置，的方，然后在**批处理计划**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**第一次批处理前的小时数**|键入第一个批处理是从开始前的小时数。|  
    |**重复后的批处理**|选择下列选项之一：<br /><br /> -   **小时**。 键入要重复的批处理的小时数。<br />-   **消息**。 开始键入你想要在下一步批处理之前处理的消息数。|  
    |**批处理控件**|选择下列选项之一：<br /><br /> -   **启动计划**： 选择用于启动批处理计划。<br />-   **立即发送**： 选择要启动批处理立即处理。<br />-   **停止计划**： 选择此项可停止当前的批处理计划。|  
  
## <a name="see-also"></a>另请参阅  
 [配置批处理确认](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)
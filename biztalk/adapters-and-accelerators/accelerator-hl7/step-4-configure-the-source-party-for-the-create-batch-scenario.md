---
title: 步骤 4：配置源参与方创建批处理方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b06b6545-4c2e-4a56-9feb-bd3f9574d4d1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1923e1527b619bd934056ae380e88a0fcb343b4b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288275"
---
# <a name="step-4-configure-the-source-party-for-the-create-batch-scenario"></a>步骤 4：配置源参与方创建批处理方案
在此步骤中，可以配置创建 Batch 方案的源参与方。 您还选择确认该 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将进行批处理，为此参与方定义的一样。 设置为确认批处理计划以便[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]后的消息计数达到 2 将创建批。  
  
> [!NOTE]
>  在此方案中，你可以使用你在中创建的同一个源参与方[步骤 7:创建并配置源参与方](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)的 （零碎的入站批处理方案） 本教程的第 1 部分。  
  
### <a name="to-configure-the-source-party-for-the-create-batch-scenario"></a>若要配置源参与方创建批处理方案  
  
1. BTAHL7 配置资源管理器中上**参与方**选项卡上的控制台树中，单击**Tutorial_BatchSource**。  
  
2. 单击**确认**详细信息窗格中的选项卡。 确认**确认类型**是**OriginalMode**。  
  
3. 单击**批定义**选项卡。下**可用的消息确认**，单击**BTAHL7Schemas.ADT_A03_231_GLO_DEF**，单击向右箭头 (**>>**) 若要将此架构添加到**选择消息的 Ack**，然后单击**保存**。  
  
4. 单击**批处理计划**选项卡。在中**重复执行批处理后**部分中，选择**消息**，然后键入**2**中**消息**框。  
  
5. 单击**启动计划**。  
  
   请继续执行[步骤 5:为消息批处理创建发送端口](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)。
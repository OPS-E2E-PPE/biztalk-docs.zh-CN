---
title: "步骤 4： 配置创建批处理方案的源方 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b06b6545-4c2e-4a56-9feb-bd3f9574d4d1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12f7ca9eebb28bb97ae925aec4fc34cefd5a2dcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-configure-the-source-party-for-the-create-batch-scenario"></a>步骤 4： 配置创建批处理方案的源方
在此步骤中，你可以配置创建批次方案的源方。 你还选择确认该 BizTalk 快捷键的 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将批处理，此参与方的定义。 设置确认批次的计划以便[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将创建批次之后，消息计数达到 2。  
  
> [!NOTE]
>  在此方案中，你可以使用你在中创建的相同源方[步骤 7： 创建和配置源方](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)的 （分片入站批处理方案） 本教程的第 1 部分。  
  
### <a name="to-configure-the-source-party-for-the-create-batch-scenario"></a>若要配置的源方为创建批次方案  
  
1.  在 BTAHL7 配置资源管理器，在**方**在控制台树中的选项卡上，单击**Tutorial_BatchSource**。  
  
2.  单击**确认**详细信息窗格中的选项卡。 验证**确认类型**是**OriginalMode**。  
  
3.  单击**批定义**选项卡。下**可用消息确认**，单击**BTAHL7Schemas.ADT_A03_231_GLO_DEF**，单击右箭头转向 (**>>**) 将此架构添加到**选择消息确认**，然后单击**保存**。  
  
4.  单击**批处理计划**选项卡。在**重复批处理后**部分中，选择**消息**，然后键入**2**中**消息**框。  
  
5.  单击**启动计划**。  
  
 继续执行[步骤 5： 为消息批创建发送端口](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)。
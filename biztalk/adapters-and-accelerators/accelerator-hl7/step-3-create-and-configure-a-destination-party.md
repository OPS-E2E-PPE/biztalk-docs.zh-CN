---
title: 步骤 3： 创建并配置目标参与方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8746f115-9f69-4593-9943-9ccda45cd900
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 086f2ff18db68651187e1b7392d5995f231234c4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997862"
---
# <a name="step-3-create-and-configure-a-destination-party"></a>步骤 3： 创建并配置目标参与方
此步骤中，创建并配置创建 Batch 方案的目标参与方。 你还选择的消息的[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]批处理和批处理计划，为该参与方定义的一样。 您计划为一小时后将文件复制到文件夹中的批发送时间。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 频率为一小时之后收到任何消息进行批处理。  
  
### <a name="to-create-and-configure-a-destination-party"></a>若要创建和配置目标参与方  
  
1. 在 BizTalk Server 管理控制台中，右键单击**参与方**，依次指向**新建**，然后单击**参与方**。  
  
2. 在参与方属性对话框中，在**名称**框中，键入**Tutorial_BatchDest**，然后单击**确定**。  
  
3. 单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  
  
4. BTAHL7 配置资源管理器中上**参与方**选项卡上的控制台树中，单击**Tutorial_BatchDest**。  
  
5. 单击**确认**详细信息窗格中的选项卡。 确认**确认类型**是**None**。  
  
6. 单击**批定义**选项卡。在中**可用消息**窗格中，选择**BTAHL7Schemas.ADT_A03_231_GLO_DEF**。 单击向右箭头 (**>>**) 添加到此架构**选择消息**，然后单击**保存**。  
  
7. 单击**批处理计划**选项卡。在中**重复执行批处理后**部分中，验证**小时**已选中，然后键入**1**中**小时**框。 在中**小时之后第一批,** 框中，键入**1**，然后单击**开始计划**。  
  
   请继续执行[步骤 4： 配置源参与方创建批处理方案](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)。
---
title: 步骤 3： 创建并配置目标方 |Microsoft 文档
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
ms.openlocfilehash: 66d955aeaabe4d7207a07827de04c1c21e4c2c7a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961339"
---
# <a name="step-3-create-and-configure-a-destination-party"></a>步骤 3： 创建并配置目标方
在此步骤中，你可以创建和配置创建批次方案的目标方。 你还选择的消息，[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]批处理和批处理计划，该方的定义。 计划批发送时间为 1 小时后将文件复制到的文件夹。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]为频率为一小时之后接收任何消息进行批处理。  
  
### <a name="to-create-and-configure-a-destination-party"></a>若要创建和配置目标方  
  
1.  在 BizTalk Server 管理控制台中，右键单击**方**，指向**新建**，然后单击**方**。  
  
2.  在参与方属性对话框中，在**名称**框中，键入**Tutorial_BatchDest**，然后单击**确定**。  
  
3.  单击**启动**，指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  
  
4.  在 BTAHL7 配置资源管理器，在**方**在控制台树中的选项卡上，单击**Tutorial_BatchDest**。  
  
5.  单击**确认**详细信息窗格中的选项卡。 验证**确认类型**是**无**。  
  
6.  单击**批定义**选项卡。在**可用消息**窗格中，选择**BTAHL7Schemas.ADT_A03_231_GLO_DEF**。 单击右箭头转向 (**>>**) 添加到此架构**选择消息**，然后单击**保存**。  
  
7.  单击**批处理计划**选项卡。中**重复批处理后**部分中，验证**小时**选择时，，然后键入**1**中**小时**框。 在**小时以后再开始第一批**框中，键入**1**，然后单击**启动计划**。  
  
 继续执行[步骤 4： 配置创建批处理方案的源方](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)。
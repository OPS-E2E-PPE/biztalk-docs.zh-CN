---
title: "步骤 7： 创建并配置源方 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8788a9c-ae6f-461b-82e5-f4276d1d5e0c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32539b1c352ac1fd2b60d2acd4c5ee975e2c3d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-create-and-configure-a-source-party"></a>步骤 7： 创建并配置源方
在此步骤中，你将创建并配置源方，并分配发送端口以便允许传出消息的消息标头转换。  
  
### <a name="to-create-and-configure-a-source-party"></a>若要创建和配置源方  
  
1.  在 BizTalk 管理控制台中，右键单击**方**，指向**新建**，然后单击**方**。  
  
2.  在**参与方属性**对话框中，在名称字段中，类型**Tutorial_BatchSource**。  
  
    > [!NOTE]
    >  在此框中键入的值是从原始 FHS3.1[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]消息的批处理，FragmentedInboundBatch.txt。  
  
3.  在控制台树中，单击**发送端口**。  
  
4.  在发送端口窗格中的名称字段中，选择**Tutorial_2wayAck**。  
  
5.  单击 **“确定”**。  
  
6.  单击**启动**，指向**所有程序**，指向**Microsoft BizTalk\<版本 > Accelerator for HL7**，然后单击**BTAHL7配置资源管理器**。  
  
7.  在 BTAHL7 配置资源管理器，在**方**选项卡上，单击**Tutorial_BatchSource**。  
  
8.  选择**批定义**BTAHL7 配置浏览器选项卡。 选择**是**为**所需的碎片**，然后单击**保存**。  
  
9. 选择**确认**选项卡。有关**确认类型**，选择**OriginalMode**，然后单击**保存**。  
  
 继续执行[步骤 8： 重新启动 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)。
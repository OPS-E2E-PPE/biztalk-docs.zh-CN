---
title: 步骤 7： 创建和配置源参与方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d8788a9c-ae6f-461b-82e5-f4276d1d5e0c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4708a682047ced4fa33ae34781fd88d379c5e70b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968926"
---
# <a name="step-7-create-and-configure-a-source-party"></a>步骤 7： 创建和配置源参与方
在此步骤中，创建并配置源参与方，并分配要启用消息标头转换为传出消息的发送端口。  
  
### <a name="to-create-and-configure-a-source-party"></a>若要创建和配置源参与方  
  
1. 在 BizTalk 管理控制台中，右键单击**参与方**，依次指向**新建**，然后单击**参与方**。  
  
2. 在中**参与方属性**对话框中，在名称字段中，类型**Tutorial_BatchSource**。  
  
   > [!NOTE]
   >  在此框中键入的值是从原始 FHS3.1[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]批处理的消息，FragmentedInboundBatch.txt。  
  
3. 在控制台树中，单击**发送端口**。  
  
4. 在发送端口窗格的名称字段中，选择**Tutorial_2wayAck**。  
  
5. 单击“确定” 。  
  
6. 单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for HL7**，然后单击**BTAHL7 配置资源管理器**。  
  
7. BTAHL7 配置资源管理器中上**参与方**选项卡上，单击**Tutorial_BatchSource**。  
  
8. 选择**批定义**BTAHL7 配置资源管理器选项卡。 选择**是**有关**所需的碎片**，然后单击**保存**。  
  
9. 选择**确认**选项卡。有关**确认类型**，选择**OriginalMode**，然后单击**保存**。  
  
   请继续执行[步骤 8： 重启 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)。
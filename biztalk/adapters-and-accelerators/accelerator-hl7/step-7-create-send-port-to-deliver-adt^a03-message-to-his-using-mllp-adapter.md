---
title: 步骤 7：创建发送端口以将 ^ A03 消息到他使用 MLLP 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- creating, send ports
- send ports, creating
ms.assetid: d9e7f281-3d25-4675-a13e-0e2057f5e69a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49d75da284ecbf0852d62e614cae2a787bc6dc52
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65287916"
---
# <a name="step-7-create-a-send-port-to-deliver-the-adta03-message-to-his-using-the-mllp-adapter"></a>步骤 7：创建发送端口以将 ^ A03 消息到他使用 MLLP 适配器
在此步骤中，你创建发送端口将消息发送到医院信息系统 (HIS) 使用 MLLP 适配器。  

### <a name="to-create-the-tutorialmllpsend-send-port"></a>若要创建 Tutorial_MllpSend 发送端口  

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  

2. 在发送端口属性对话框中，执行以下操作：  


   |      使用此选项      |                                执行的操作                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      **名称**      |                        类型**Tutorial_MllpSend**。                        |
   | **传输类型** |                 选择**MLLP**从下拉列表。                  |
   |   **配置**    | 单击**配置**以打开**MLLP 传输属性**对话框。 |


3. 在处的 MLLP 传输属性对话框中，执行以下操作，然后单击**确定**。  


   |      使用此选项       |     执行的操作      |
   |---------------------|---------------------|
   | **连接名称** | 类型**1WaySend**。  |
   |      **主机**       | 类型**localhost**。 |
   |      **端口**       |   类型**14000**。   |


4. 在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。  

5. 在左窗格中，选择**筛选器**，然后执行以下操作：  

   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**属性**|选择**BTS。ReceivePortName**从下拉列表。|  
   |**“运算符”**|选择**==** 从下拉列表。|  
   |**ReplTest1**|类型**Tutorial_1WayReceive**。|  

   > [!NOTE]
   >  该端口将侦听 1WayReceive 的任何消息中指定的端口。  

6. 单击**Apply**，然后单击**确定。**  

7. 在管理控制台中，单击**发送端口**，右键单击**Tutorial_MllpSend**，然后单击**启动**。  

   请继续执行[步骤 8:配置参与方信息](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)。
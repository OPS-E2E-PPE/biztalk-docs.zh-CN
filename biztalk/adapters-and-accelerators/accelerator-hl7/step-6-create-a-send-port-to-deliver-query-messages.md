---
title: 步骤 6： 创建用于传递查询消息的发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, send ports
ms.assetid: a3cfa2aa-888d-4a82-9eb3-2e9cc29ee582
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24e65ec7bc4e04850907609fc6d1d63e6f166593
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004046"
---
# <a name="step-6-create-a-send-port-to-deliver-query-messages"></a>步骤 6： 创建用于传递查询消息的发送端口
在此步骤中，创建发送端口以将传入的查询 (QRY ^ Q01 消息) 到医院信息系统 (HIS)。  

### <a name="to-create-the-hissend-send-port"></a>若要创建 HIS_Send 发送端口  

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后选择**静态单向发送端口**。  

2. 在“发送端口属性”对话框中，执行以下操作：  


   |      使用此选项      |                        执行的操作                        |
   |--------------------|----------------------------------------------------------|
   |      **名称**      |                    类型**HIS_Send**。                    |
   | **传输类型** |                     选择**MLLP**。                     |
   |   **配置**    | 单击**配置**右侧的按钮**类型**。 |


3. 在处的 MLLP 传输属性对话框中，输入以下信息，然后单击**确定**。  


   |      使用此选项       |       执行的操作       |
   |---------------------|------------------------|
   | **连接名称** | 类型**HIS_SendMLLP**。 |
   |      **主机**       |  类型**localhost**。   |
   |      **端口**       |    类型**24000**。     |


4. 在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。  

5. 在控制台树中，单击**筛选器**，然后执行以下操作：  


   |   使用此选项   |                              执行的操作                               |
   |--------------|-----------------------------------------------------------------------|
   | **属性** |             有关**属性**，选择**BTS。MessageType**。             |
   | **“运算符”** |                选择**==** 从下拉列表。                 |
   |  **ReplTest1**   | 类型**<http://microsoft.com/HealthCare/HL7/2X#QRY_Q01_24_GLO_DEF>**。 |
   | **分组依据** |                选择**AND**从下拉列表。                |
   | **属性** | 有关**属性**在第二行中，选择**BTAHL7Schemas.MSH5_1**。 |
   | **“运算符”** |                选择**==** 从下拉列表。                 |
   |  **ReplTest1**   |                             类型**HIS**。                             |

   > [!NOTE]
   >  第一个筛选器指定发送端口只选择消息符合 QRY ^ Q01 架构在步骤 3A 中创建。 第二个筛选器指定到的目标[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎将发送这些消息。  

6. 单击“确定” 。  

7. 在管理控制台中，选择**发送端口**，右键单击**HIS_Send**，然后单击**启动**。  

   请继续执行[步骤 7： 创建用于传递响应消息的发送端口](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)。
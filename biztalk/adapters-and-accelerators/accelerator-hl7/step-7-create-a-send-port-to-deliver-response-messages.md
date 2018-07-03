---
title: 步骤 7： 创建用于传递响应消息的发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, send ports
ms.assetid: 5edaefb6-72f2-4317-9477-f3a0d0027e0c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4139e07c5ca503a8cb58b1aa88fe8e602a92ee07
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987822"
---
# <a name="step-7-create-a-send-port-to-deliver-response-messages"></a>步骤 7： 创建用于传递响应消息的发送端口
在此步骤中，创建发送端口以将查询响应返回到病人入院、 放电装置和传输 (ADT) 系统。  

### <a name="to-create-the-adtsend-send-port"></a>若要创建 ADT_Send 发送端口  

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后选择**静态单向发送端口**。  

2. 在“发送端口属性”对话框中，执行以下操作：  


   |      使用此选项      |                        执行的操作                        |
   |--------------------|----------------------------------------------------------|
   |      **名称**      |                    类型**ADT_Send**。                    |
   | **传输类型** |                     选择**MLLP**。                     |
   |   **配置**    | 单击**配置**右侧的按钮**类型**。 |


3. 在处的 MLLP 传输属性对话框中，输入以下信息，然后依次**确定**。  


   |      使用此选项       |       执行的操作       |
   |---------------------|------------------------|
   | **连接名称** | 类型**ADT_SendMLLP**。 |
   |      **主机**       |  类型**localhost**。   |
   |      **端口**       |    类型**25000**。     |


4. 在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。  

5. 在控制台树中，单击**筛选器**，然后执行以下操作：  


   |   使用此选项   |                                        执行的操作                                        |
   |--------------|------------------------------------------------------------------------------------------|
   | **属性** |                               选择**BTS。MessageType**。                                |
   | **“运算符”** |                          选择**==** 从下拉列表。                          |
   |  **ReplTest1**   |          类型**<http://microsoft.com/HealthCare/HL7/2X#DSR_Q01_24_GLO_DEF>**。           |
   | **分组依据** |                         选择**AND**从下拉列表。                          |
   | **属性** | 在第一个属性，单击空白框中，然后选择**BTAHL7Schemas.MSH5_1**。 |
   | **“运算符”** |                          选择**==** 从下拉列表。                          |
   |  **ReplTest1**   |                                      类型**ADT**。                                       |

   > [!NOTE]
   >  第一个筛选器指定发送端口只选择消息符合 DSR ^ Q01 架构在步骤 3A 中创建。 第二个筛选器指定到的目标[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎将发送这些消息。  

6. 单击“确定” 。  

7. 在管理控制台中，单击**发送端口**，右键单击**ADT_Send**，然后单击**启动**。  

   请继续执行[步骤 8： 配置参与方信息](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)。
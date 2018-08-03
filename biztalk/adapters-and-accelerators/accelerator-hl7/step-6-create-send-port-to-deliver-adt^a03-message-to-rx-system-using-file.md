---
title: 步骤 6： 创建发送端口以将 ^ A03 至 RX 系统使用文件适配器的消息 |Microsoft Docs
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
ms.assetid: 66c4b524-c8ff-43b5-9c44-6d7bc759ae2c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95a9200d4c03f11f2feca89042bfb57ba36de345
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004374"
---
# <a name="step-6-create-a-send-port-to-deliver-the-adta03-message-to-the-rx-system-using-the-file-adapter"></a>步骤 6： 创建发送端口以将 ^ A03 至 RX 系统使用文件适配器的消息
在此步骤中，您创建的发送端口文件适配器时的药房系统 (RX)。  

### <a name="to-create-the-tutorialsendmsgrx-send-port"></a>若要创建 Tutorial_sendMsg_RX 发送端口  

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  

2. 在中**发送端口属性**对话框中，执行以下操作，然后单击**确定**。  


   |      使用此选项      |                                执行的操作                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      **名称**      |                       类型**Tutorial_sendMsg_RX**。                       |
   | **传输类型** |                 选择**文件**从下拉列表。                  |
   |   **配置**    | 单击**配置**以打开**File 传输属性**对话框。 |


3. 在 FILE 传输属性对话框中，执行以下操作，然后单击**确定**。  


   |        使用此选项        |                                                                     执行的操作                                                                     |
   |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
   | **目标文件夹** | 浏览到**\<**<em>驱动器</em>**:\>\Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_sendMsg_RX**。 |
   |     **文件名**      |                                   类型 **%MessageID%.txt** （替换带.txt 扩展名的.xml 扩展名）。                                   |


4. 在中**发送端口属性**对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。  

5. 在左窗格中，选择**筛选器**，然后执行以下操作。 单击 **“确定”** 继续。  


   |          使用此选项          |                                            执行的操作                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   | **属性**（第一次行）  |                       选择**BTS。MessageType**从下拉列表。                        |
   |        **“运算符”**        |                              选择 **！ =** 从下拉列表。                              |
   |         **ReplTest1**          |                类型**<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**。                 |
   |        **分组依据**        |                              选择**或**从下拉列表。                              |
   | **属性**（第二行） | 单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。 |
   |        **“运算符”**        |                              选择 **！ =** 从下拉列表。                              |
   |         **ReplTest1**          |                类型 **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>。**                 |
   |        **分组依据**        |                             选择**AND**从下拉列表。                              |
   | **属性**（第三个行）  |                                 选择**BTAHL7Schemas.MSH3_1**。                                 |
   |        **“运算符”**        |                              选择**==** 从下拉列表。                              |
   |         **ReplTest1**          |                                   类型**Tutorial_ADTSystem**。                                   |

   > [!NOTE]
   >  第一个筛选器意味着医院信息系统 (HIS) 一条消息，确认不到订阅。 第二个筛选器意味着他订阅其源是病人入院出院事项和传输 (ADT) 系统的消息。  

   > [!NOTE]
   >  BTAHL7 会将消息放在文件存放位置\<*驱动器*\>： 程序 FilesMicrosoft BizTalk <version> HL7SDKEnd 端到端 TutorialTutorial_sendMsg_RX 的加速器。  

6. 单击**Apply**，然后单击**确定。**  

7. 在管理控制台中，单击**发送端口**，右键单击**Tutorial_sendMsg_RX**，然后单击**启动**。  

   请继续执行[步骤 7： 创建一个发送端口以将 ^ A03 消息到他使用 MLLP 适配器](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)。
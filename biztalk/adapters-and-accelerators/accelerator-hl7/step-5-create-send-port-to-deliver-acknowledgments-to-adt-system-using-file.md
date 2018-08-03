---
title: 步骤 5： 创建用于将确认传递至 ADT 系统使用文件适配器的发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, send ports
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: 565a2adf-fd86-46e3-8035-7e4748aefffc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1421b39ed4bbd15fb82cb16ed55b23e5781eead6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002094"
---
# <a name="step-5-create-a-send-port-to-deliver-acknowledgments-to-the-adt-system-using-the-file-adapter"></a>步骤 5： 创建用于将确认传递至 ADT 系统使用文件适配器的发送端口
在此步骤中，创建要生成确认使用文件适配器的发送端口。  

### <a name="to-create-the-tutorialsendackadt-send-port"></a>若要创建 Tutorial_sendAck_ADT 发送端口  

1. 使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器中，创建\<*驱动器*:\>\Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_ 的快捷键sendAck_ADT 文件夹。  

2. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  

3. 在“发送端口属性”对话框中，执行以下操作：  


   |      使用此选项      |                                执行的操作                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      **名称**      |                      类型**Tutorial_sendAck_ADT**。                       |
   | **传输类型** |                 选择**文件**从下拉列表。                  |
   |   **配置**    | 单击**配置**以打开**File 传输属性**对话框。 |


4. 在 FILE 传输属性对话框中，执行以下操作，然后单击**确定**。  


   |        使用此选项        |                                                                     执行的操作                                                                      |
   |------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
   | **目标文件夹** | 浏览到**\<**<em>驱动器</em>**:\>\Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_sendAck_ADT**。 |
   |     **文件名**      |                                   类型 **%MessageID%.txt** （替换带.txt 扩展名的.xml 扩展名）。                                    |


5. 在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。  

6. 在左窗格中，单击**筛选器**，然后执行以下操作：  

   > [!NOTE]
   >  第一个筛选器意味着您要订阅的确认消息。 第二个筛选器意味着您要订阅确认发送到发布服务器 Tutorial_ADTSystem。  

    单击**确定**您何时准备好继续。  


   |          使用此选项          |                                            执行的操作                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   |        **属性**        | 单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。 |
   |        **“运算符”**        |                              选择**==** 从下拉列表。                              |
   |         **ReplTest1**          |                类型**<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**。                 |
   |        **分组依据**        |                              选择**或**从下拉列表。                              |
   | **属性 （第二行）** | 单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。 |
   |        **“运算符”**        |                              选择**==** 从下拉列表。                              |
   |         **ReplTest1**          |                类型 **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>。**                 |
   |        **分组依据**        |                             选择**AND**从下拉列表。                              |
   |        **属性**        |     在第一个属性，单击空白框中，然后选择**BTAHL7Schemas.MSH5_1**。     |
   |        **“运算符”**        |                              选择**==** 从下拉列表。                              |
   |         **ReplTest1**          |                                   类型**Tutorial_ADTSystem**。                                   |

   > [!NOTE]
   >  为发送端口 Tutorial_sendAck_ADT，BTAHL7 将删除对确认在文件存放位置\<*驱动器*\>： 程序 FilesMicrosoft BizTalk <version> HL7SDKEnd 端到端的快捷键TutorialTutorial_sendAck_ADT。  

7. 单击**Apply**，然后单击**确定。**  

8. 在管理控制台中，单击**发送端口**，右键单击**Tutorial_sendAck_ADT**，然后单击**启动**。  

   请继续执行[第 6 步： 创建一个发送端口以将 ^ A03 消息至 RX 系统使用文件适配器](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)。
---
title: 步骤 2： 修改或创建发送和接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d96d02c-b75d-4d18-a127-37002c5ff138
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42c40652d334fd2c7dec2475edca81b9fc9b1b14
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996518"
---
# <a name="step-2-modify-or-create-the-send-and-receive-ports"></a>步骤 2： 修改或创建发送和接收端口
所需文件发送和接收端口的批处理中 / 出站教程批处理。 如果单击了**启动教程**安装的 Enterprise Edition 的末尾按钮[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]为你创建这些端口： 名为 Tutorial_BTAHL7Drop，一个发送端口和一个名为 Tutorial_BTAHL7PickUp 的接收端口。 如果您有这些端口，仍需要修改发送端口 Tutorial_BTAHL7Drop。  

 如果[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]安装程序不未创建发送和接收端口，请参阅本主题中的"创建 BIBOTutorialPickup 接收端口"过程，然后请参阅"创建 BIBOTutorialDrop 发送端口"还在本主题中的过程。  

### <a name="to-modify-the-tutorialbtahl7drop-send-port"></a>若要修改 Tutorial_BTAHL7Drop 发送端口  

1. 单击**启动**，依次指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。  

3. 单击**发送端口**，右键单击**Tutorial_BTAHL7Drop**，然后单击**属性**。  

4. 在控制台树中，单击**筛选器**。  

5. 在中**筛选器**窗格中的，在第二个行中，选择**BTAHL7Schemas.MessageClass**有关**属性**，选择**==** 为**运算符**，然后键入**MessageClass2X**有关**值**。 单击 **“输入”**。  

6. 设置**分组依据**上**BTS。ReceivePortName**到行**或者**，然后单击**确定**。  

7. 在 microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理窗口中，展开**平台设置**，然后展开**主机实例**。 右键单击**BizTalkServerApplication**，然后单击**重新启动**。  

   > [!NOTE]
   >  仅使用以下过程，如果安装 Standard Edition [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]，或如果未单击**启动教程**按钮设置时[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。  

### <a name="to-create-the-tutorialbtahl7pickup-receive-port-and-location"></a>若要创建 Tutorial_BTAHL7Pickup 接收端口和位置  

1. 单击**启动**，依次指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  

2. 在管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。  

3. 右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。  

4. 在接收端口属性对话框中，在**名称**框中，键入**Tutorial_BTAHL7PickUp**。  

5. 单击**Apply**以绑定端口，然后单击**确定**。  

6. 右键单击**接收位置**，依次指向**新建**，然后单击**单向接收位置**。  

7. 在选择接收端口对话框中，单击**Tutorial_BTAHL7PickUp**，然后单击**确定**。  

8. 在接收位置属性对话框中，在**名称**框中，键入**Tutorial_FileReceiveLoc**。  

9. 在中**传输**部分中，对于**类型**文本框中，单击下拉列表，然后选择**文件**。  

10. 单击**配置**类型下拉列表右侧的按钮。  

11. 在 FILE 传输属性对话框中，请执行以下操作：  


    |      使用此选项      |                                                                                                                                                                         执行的操作                                                                                                                                                                          |
    |--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | **接收文件夹** | 浏览到**\<**<em>驱动器</em>**\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BTAHL7PickUp**。 **注意：** 这是到公共共享的文件系统上的位置中的位置的路径[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]会选取该文件。 |
    |   **文件掩码**    |                                                                                                                                                                      类型 **\*.txt**。                                                                                                                                                                       |


12. 单击“确定” 。  

13. 在接收位置属性对话框中，请执行以下操作：  


    |       使用此选项       |                      执行的操作                       |
    |----------------------|-------------------------------------------------------|
    | **接收处理程序**  |    保持**BizTalkServerApplication**为选中状态。     |
    | **接收管道** | 选择**BTAHL72XPipelines.BTAHL72XReceivePipeline**。 |


14. 单击“确定” 。  

15. 在 BizTalk 浏览器中右键单击**Tutorial_FileReceiveLoc**，然后单击**启用**。  

### <a name="to-create-the-tutorialbtahl7drop-send-port"></a>若要创建 Tutorial_BTAHL7Drop 发送端口  

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  

2. 在“发送端口属性”对话框中，执行以下操作：  


   |   使用此选项    |                                执行的操作                                 |
   |---------------|---------------------------------------------------------------------------|
   |   **名称**    |                       类型**Tutorial_BTAHL7Drop**。                       |
   |   **类型**    |                 选择**文件**从下拉列表。                  |
   | **配置** | 单击**配置**以打开**FILE 传输属性**对话框。 |


3. 在 FILE 传输属性对话框中，请执行以下操作：  


   |        使用此选项        |                                                                                                                                                                      执行的操作                                                                                                                                                                       |
   |------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **目标文件夹** | 浏览到**\<**<em>驱动器</em>**:\>\Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BTAHL7Drop**。 **注意：** 这是到公共共享的文件系统上的位置的路径[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将写入文件。 |
   |     **文件名**      |                                                                                                                                          类型 **%MessageID%.txt** （请注意该扩展名是 txt、 非 xml）。                                                                                                                                          |


4. 单击“确定” 。  

5. 在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**从下拉列表。  

6. 在控制台树中，单击**筛选器**，然后执行以下操作：  


   |   使用此选项   |                       执行的操作                        |
   |--------------|---------------------------------------------------------|
   | **属性** | 选择**BTS。ReceivePortName**从下拉列表。 |
   | **“运算符”** |              将保留**==** 与运算符。              |
   |  **ReplTest1**   |             类型**Tutorial_BTAHL7PickUp**。             |
   | **分组依据** |         选择**或**从下拉列表。          |
   | **属性** |         选择**BTAHL7Schemas.MessageClass**。          |
   | **“运算符”** |              将保留**==** 与运算符。              |
   |  **ReplTest1**   |                类型**MessageClass2X**。                 |


7. 单击 **“输入”**。 在对话框中底部窗格中验证筛选器表达式正确。  

8. 单击“确定” 。  

9. 在管理控制台中，单击**发送端口**，右键单击**Tutorial_BTAHL7Drop**，然后单击**启动**。  

10. 展开**平台设置**，然后单击**主机实例**。 右键单击**BizTalkServerApplication**，然后单击**重新启动**。  

    请继续执行[步骤 3： 测试在入站批处理 / 出站批处理方案](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)。
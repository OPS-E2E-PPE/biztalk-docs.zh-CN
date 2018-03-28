---
title: 步骤 2： 修改或创建发送方和接收端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d96d02c-b75d-4d18-a127-37002c5ff138
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fa94183f0eb83dc51fc0add22ba50484f7282fb
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="step-2-modify-or-create-the-send-and-receive-ports"></a>步骤 2： 修改或创建发送方和接收端口
你需要文件发送和接收端口批中 / 批处理出教程。 如果你单击**启动教程**末尾的安装 Enterprise Edition 的按钮[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]为你创建这些端口： 名为 Tutorial_BTAHL7Drop，发送端口和一个名为 Tutorial_BTAHL7PickUp 的接收端口。 如果你有这些端口，你仍需要修改发送端口 Tutorial_BTAHL7Drop。  
  
 如果[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]安装程序不未创建发送和接收端口，请参阅本主题中的"创建 BIBOTutorialPickup 接收端口"过程，然后请参阅"创建 BIBOTutorialDrop 发送端口"还在本主题中的过程。  
  
### <a name="to-modify-the-tutorialbtahl7drop-send-port"></a>若要修改 Tutorial_BTAHL7Drop 发送端口  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。  
  
3.  单击**发送端口**，右键单击**Tutorial_BTAHL7Drop**，然后单击**属性**。  
  
4.  在控制台树中，单击**筛选器**。  
  
5.  在**筛选器**窗格中，在第二个行中，选择**BTAHL7Schemas.MessageClass**为**属性**，选择**==**为**运算符**，和类型**MessageClass2X**为**值**。 单击 **“输入”**。  
  
6.  设置**分组依据**上**BTS。ReceivePortName**行**或者**，然后单击**确定**。  
  
7.  在[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理窗口中，展开**平台设置**，然后展开**主机实例**。 右键单击 **BizTalkServerApplication**, ，然后单击 **重新启动**。  
  
    > [!NOTE]
    >  仅使用以下过程，如果你安装 Standard Edition 的[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]，或如果您没有单击**启动教程**按钮设置完成[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。  
  
### <a name="to-create-the-tutorialbtahl7pickup-receive-port-and-location"></a>若要创建 Tutorial_BTAHL7Pickup 接收端口和位置  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。  
  
3.  右键单击 **接收端口**, ，指向 **新建**, ，然后单击 **单向接收端口**。  
  
4.  在接收端口属性对话框中，在**名称**框中，键入**Tutorial_BTAHL7PickUp**。  
  
5.  单击**应用**以绑定端口，然后单击**确定**。  
  
6.  右键单击**接收位置**，指向**新建**，然后单击**单向接收位置**。  
  
7.  在选择接收端口对话框中，单击**Tutorial_BTAHL7PickUp**，然后单击**确定**。  
  
8.  在接收位置属性对话框中，在**名称**框中，键入**Tutorial_FileReceiveLoc**。  
  
9. 在**传输**部分中，为**类型**文本框中，单击下拉列表中，，然后选择**文件**。  
  
10. 单击**配置**类型下拉列表右侧的按钮。  
  
11. 在文件传输属性对话框中，请执行以下操作：  
  
    |使用此选项|動作|  
    |--------------|----------------|  
    |**接收文件夹**|浏览到 **\<***驱动器***\>: files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\End 端到端 Tutorial\Tutorial_BTAHL7PickUp**. **注意：**这是指向文件系统或公共共享上的位置从何处路径[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将选取此文件。|  
    |**文件掩码**|类型 **\*.txt**。|  
  
12. 单击 **“确定”**。  
  
13. 在接收位置属性对话框中，请执行以下操作：  
  
    |使用此选项|動作|  
    |--------------|----------------|  
    |**接收处理程序**|保留**BizTalkServerApplication**为选中状态。|  
    |**接收管道**|选择**BTAHL72XPipelines.BTAHL72XReceivePipeline**。|  
  
14. 单击 **“确定”**。  
  
15. 在 BizTalk 资源管理器中，右键单击**Tutorial_FileReceiveLoc**，然后单击**启用**。  
  
### <a name="to-create-the-tutorialbtahl7drop-send-port"></a>若要创建 Tutorial_BTAHL7Drop 发送端口  
  
1.  在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在“发送端口属性”对话框中，执行以下操作：  
  
    |使用此选项|動作|  
    |--------------|----------------|  
    |**名称**|类型**Tutorial_BTAHL7Drop**。|  
    |**类型**|选择**文件**从下拉列表。|  
    |**配置**|单击**配置**以打开**文件传输属性**对话框。|  
  
3.  在文件传输属性对话框中，请执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**目标文件夹**|浏览到 **\<***驱动器***:\>files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\End 端到端 Tutorial\Tutorial_BTAHL7Drop**. **注意：**这是文件系统或到公共共享上的位置的路径[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将写入文件。|  
    |**File name**|类型**%MessageID%.txt** （请注意，扩展名为 txt、 不是 xml）。|  
  
4.  单击 **“确定”**。  
  
5.  在发送端口属性对话框中，为**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**从下拉列表。  
  
6.  在控制台树中，单击 **筛选器**, ，然后执行以下︰  
  
    |使用此选项|動作|  
    |--------------|----------------|  
    |**属性**|选择**BTS。ReceivePortName**从下拉列表。|  
    |**运算符**|保留**==**为运算符。|  
    |**Value**|类型**Tutorial_BTAHL7PickUp**。|  
    |**分组依据**|选择**或**从下拉列表。|  
    |**属性**|选择**BTAHL7Schemas.MessageClass**。|  
    |**运算符**|保留**==**为运算符。|  
    |**Value**|类型**MessageClass2X**。|  
  
7.  单击 **“输入”**。 在对话框中底部窗格中验证筛选器表达式正确。  
  
8.  单击 **“确定”**。  
  
9. 在管理控制台中，单击**发送端口**，右键单击**Tutorial_BTAHL7Drop**，然后单击**启动**。  
  
10. 展开**平台设置**，然后单击**主机实例**。 右键单击 **BizTalkServerApplication**, ，然后单击 **重新启动**。  
  
 继续执行[步骤 3： 测试中的批处理 / 批处理出方案](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)。
---
title: 步骤 5： 创建用于传递消息的发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f56ad7a7-5c77-4191-a001-691e5e0652a1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ec45b98cf1ef5152f52e6d11c9d3f6d150c6b55
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001678"
---
# <a name="step-5-create-a-send-port-to-deliver-messages"></a>步骤 5： 创建用于传递消息的发送端口
此步骤中，创建并配置用于发送包含接收的批中的单个消息的端口。 稍后在本教程中，将在中启用发起方 (Tutorial_BatchSource) 的碎片[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。 因此，BizTalk 集成引擎将拆分批处理为单个消息和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将通过在此步骤中创建的发送端口发送这些消息。  

 创建此端口是静态的以便仅将 MLLP 适配器，与相关联，而只会发送到特定目标 （目标业务线应用程序）。 在本教程中，该目标是 MESA_IS，MSH5 单条消息中。 用于限制通过过滤掉符合 ACK_024_GLO_DEF 架构或任何静态确认 (ACK) 消息发送消息，而不是确认，对该端口的筛选器创建端口。  

 配置此发送端口接收确认到从目标，通过将发送端口与名为的接收端口相关联**TwoWayAckReceivePort**。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 安装程序会创建此端口，并随附的接收位置的**TwoWayAckReceiveLocation**。 设置发送端口以通过设置与此端口来**要求响应启用**到**是**并设置**提交接收位置 URI**到**127.0.0.1:65535** （接受确认所需的设置）。 有关详细信息，请参阅[设置启动发送端口的接收 Ack](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)。  

### <a name="to-create-a-send-port-to-deliver-messages"></a>若要创建用于传递消息的发送端口  

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  

2. 在“发送端口属性”对话框中，执行以下操作：  


   |      使用此选项      |                              执行的操作                               |
   |--------------------|-----------------------------------------------------------------------|
   |      **名称**      |                      类型**Tutorial_2wayMsg**。                       |
   | **传输类型** |               选择**MLLP**从下拉列表。                |
   |   **配置**    | 单击**配置**以打开处的 MLLP 传输属性对话框。 |


3. 在处的 MLLP 传输属性对话框中，执行以下操作：  


   |                 使用此选项                  |                                                   执行的操作                                                   |
   |-------------------------------------------|----------------------------------------------------------------------------------------------------------------|
   |            **连接名称**            |                                               类型**2wayMsg**。                                                |
   |                 **主机**                  |                                              类型**localhost**。                                               |
   |                 **端口**                  |                                                类型**41000**。                                                 |
   |       **要求响应已启用**        | 单击右侧的字段**要求响应启用**，然后选择**是**从下拉列表。 |
   | **提交接收位置 (URI)，用于确认** |                                            类型**127.0.0.1:65535**                                             |


4. 单击“确定” 。  

5. 在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。  

6. 在控制台树中，单击**筛选器**，然后执行以下操作：  


   |          使用此选项          |                                                     执行的操作                                                      |
   |----------------------------|---------------------------------------------------------------------------------------------------------------------|
   | **属性**（第一次行）  |          单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。           |
   |        **“运算符”**        |                                       选择 **！ =** 从下拉列表。                                        |
   |         **ReplTest1**          |                          类型**<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**。                          |
   |        **分组依据**        |                                       选择**AND**从下拉列表。                                       |
   | **属性**（第二行） |          单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。           |
   |        **“运算符”**        |                                       选择 **！ =** 从下拉列表。                                        |
   |         **ReplTest1**          |                          类型 **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>。**                          |
   |        **分组依据**        |                                       选择**和**从下拉列表。                                       |
   | **属性**（第三个行）  | 单击下的第二个行上的字段**属性**，然后选择**BTS。MessageType**从下拉列表。 |
   |        **“运算符”**        |                                       选择 **！ =** 从下拉列表。                                        |
   |         **ReplTest1**          |                                                 类型**StaticAck**。                                                 |


7. 单击 **“输入”**。 在对话框中底部窗格中，验证是否正确，输入筛选器表达式，然后单击**确定**。  

8. 在管理控制台中，单击**发送端口**，右键单击**Tutorial_2wayMsg**，然后单击**启动**。  

   请继续执行[第 6 步： 创建用于传递确认消息的发送端口](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)。
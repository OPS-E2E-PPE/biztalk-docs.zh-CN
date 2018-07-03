---
title: 步骤 6： 创建用于传递确认消息的发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 739b3e60-db56-46e9-a6b1-0acbe0c08f55
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47e30db70d67cb70ba87cf661e46ca325de1f3cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003614"
---
# <a name="step-6-create-a-send-port-to-deliver-acknowledgments"></a>步骤 6： 创建用于传递确认消息的发送端口
在此步骤中，您将创建一个端口来发送确认回批处理的源。  

 创建此端口是静态的以便仅将 MLLP 适配器，与相关联，而只会发送到特定目标 （批处理的源）。 在本教程中，源是与该参与方 Tutorial_BatchSource 相关联。 此源参与方都包含在单个消息和 FHS3 MSH3 和 BHS3 原始批处理。  

 用于将端口限制为发送确认，不数据消息的筛选器创建端口。 这些筛选器指定 ACK_024_GLO_DEF 和 Tutorial_BatchSource 的目标的消息类型。  

 配置此发送端口接收确认从目标，通过将发送端口与名为的接收端口相关联**TwoWayAckReceivePort**。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 安装程序会创建此端口，并随附的接收位置的**TwoWayAckReceiveLocation**。 设置发送端口以通过设置与此端口来**要求响应启用**到**否**并设置**提交接收位置 URI**到**127.0.0.1:65535** （接受确认所需的设置）。 有关详细信息，请参阅[设置启动发送端口的接收 Ack](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)。  

### <a name="to-create-a-send-port-to-deliver-acknowledgments"></a>若要创建用于传递确认消息的发送端口  

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  

2. 在“发送端口属性”对话框中，执行以下操作：  


   |      使用此选项      |                                执行的操作                                 |
   |--------------------|---------------------------------------------------------------------------|
   |      **名称**      |                        类型**Tutorial_2wayAck**。                         |
   | **传输类型** |                 选择**MLLP**从下拉列表。                  |
   |   **配置**    | 单击**配置**以打开**MLLP 传输属性**对话框。 |


3. 在处的 MLLP 传输属性对话框中，执行以下操作：  


   |                 使用此选项                  |        执行的操作         |
   |-------------------------------------------|---------------------------|
   |            **连接名称**            |     类型**2wayAck**。     |
   |                 **主机**                  |    类型**localhost**。    |
   |                 **端口**                  |      类型**41002**。      |
   |       **要求响应已启用**        | 保留该字段作为**否**。 |
   | **提交接收位置 (URI)，用于确认** | 类型**127.0.0.1:65535**  |


4. 单击“确定” 。  

5. 在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。  

6. 在控制台树中，单击**筛选器**，然后执行以下操作：  

   > [!NOTE]
   >  请确保严格按照所示输入以下数据。 此数据是区分大小写。  

   |          使用此选项          |                                            执行的操作                                            |
   |----------------------------|--------------------------------------------------------------------------------------------------|
   | **属性**（第一次行）  |   单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。   |
   |        **“运算符”**        |                              选择**==** 从下拉列表。                              |
   |         **ReplTest1**          |                类型**<http://microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF>**。                 |
   |        **分组依据**        |                              选择**或**从下拉列表。                              |
   | **属性**（第二行） | 单击下的字段**属性**，然后选择**BTS。MessageType**从下拉列表。 |
   |        **“运算符”**        |                              选择**==** 从下拉列表。                              |
   |         **ReplTest1**          |                类型 **<http://microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF>。**                 |
   |        **分组依据**        |                             选择**和**从下拉列表。                              |
   | **属性**（第三个行）  |   单击下的第二个行上的字段**属性**，然后选择**BTAHL7Schemas.MSH5_1**。   |
   |        **“运算符”**        |                              选择**==** 从下拉列表。                              |
   |         **ReplTest1**          |                                  类型**Tutorial_BatchSource**。                                  |

   > [!NOTE]
   >  第一个筛选器意味着您要订阅的确认消息。 第二个筛选器表示你希望具有目标发布服务器上，确认**Tutorial_BatchSource**。  

7. 单击 **“输入”**。 在对话框中底部窗格中，验证是否正确，输入筛选器表达式，然后单击**确定**。  

8. 在管理控制台中，单击**发送端口**，右键单击**Tutorial_2wayAck**，然后选择**启动**。  

   > [!NOTE]
   >  为 Tutorial_2wayAck 发送端口才能正常工作，必须启用 TwoWayAckReceivePort 接收位置。  

9. 单击**接收位置**。 验证已启用 TwoWayAckReceiveLocation 的状态。 如果没有，请右键单击**TwoWayAckReceiveLocation**，然后单击**启用**。  

   请继续执行[步骤 7： 创建和配置源参与方](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)。
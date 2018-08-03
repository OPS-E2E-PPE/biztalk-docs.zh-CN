---
title: 步骤 5： 为消息批处理创建发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5db815df-5b76-4ba4-99ab-c7766b0c301a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24a71d788d0b12a3ffaef8f14ccd145ef61d673e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002838"
---
# <a name="step-5-create-the-send-port-for-the-message-batch"></a>步骤 5： 为消息批处理创建发送端口
在此步骤中，您创建用于将您创建的消息批传送到目标参与方的发送端口。 这是一个静态单向端口与文件适配器类型。 指定用于目标 (\Tutorial_BatchMsgDrop) 的文件文件夹位置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]会丢弃消息批处理文件。 定义用于指示哪种类型的消息批将发送端口的端口的筛选器。 筛选器指定的 Tutorial_BatchDest 和 OutboundBatch 的消息类型的目标。  

> [!NOTE]
>  当运行本教程的此部分，可以通过停止使用本教程的第 2 部分中的发送端口来简化结果： **Tutorial_BTAHL7Drop**发送端口。  

### <a name="to-create-the-send-port-for-the-message-batch"></a>若要创建消息批的发送端口  

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  

2. 在“发送端口属性”对话框中，执行以下操作：  


   |   使用此选项    |                              执行的操作                               |
   |---------------|-----------------------------------------------------------------------|
   |   **名称**    |                     类型**Tutorial_BatchDest**。                      |
   |   **类型**    |               选择**文件**从下拉列表。                |
   | **配置** | 单击**配置**打开 FILE 传输属性对话框。 |


3. 在中**FILE 传输属性**对话框框中，执行以下操作：  


   |        使用此选项        |                                                                                                                                                                           执行的操作                                                                                                                                                                            |
   |------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **目标文件夹** | 浏览到 **\<*驱动器*:\>\Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_BatchMsgDrop的快捷键**. 这是到公共共享的文件系统上的位置的路径[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将编写包含消息批的文件。 |
   |     **文件名**      |                                                                                                                                         类型 **%MessageID%.txt** （替换带.txt 扩展名的.xml 扩展名）。                                                                                                                                          |
   |     **副本模式**      |                                                                                                                                                                     选择**创建新的**。                                                                                                                                                                      |


4. 单击“确定” 。  

5. 在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。  

6. 在控制台树中，单击**筛选器**，然后执行以下操作：  


   |   使用此选项   |                                                              执行的操作                                                              |
   |--------------|--------------------------------------------------------------------------------------------------------------------------------------|
   | **属性** | 单击下的字段**属性**，然后选择**Microsoft.Solutions.BTAHL7.BatchOrchestration.Party**从下拉列表。 |
   | **“运算符”** |                                                    将保留**==** 与运算符。                                                     |
   |  **ReplTest1**   |                                                     类型**Tutorial_BatchDest**。                                                     |
   | **分组依据** |                                               选择**和**从下拉列表。                                                |
   | **属性** |                                             选择**BTAHL7Schemas.BTAHL7MessageType**。                                              |
   | **“运算符”** |                                                    将保留**==** 与运算符。                                                     |
   |  **ReplTest1**   |                                                       类型**OutboundBatch**。                                                        |


7. 按 **Enter**。 在对话框中底部窗格中，验证是否正确，输入筛选器表达式，然后单击**确定**。  

8. 在 BizTalk 管理控制台中，选择**发送端口**，右键单击**Tutorial_BatchDest**，然后单击**启动**。  

### <a name="to-associate-the-send-port-with-the-destination-party"></a>若要使用的目标参与方关联的发送端口  

1. 在 BizTalk Server 管理控制台中，展开**参与方**，单击**Tutorial_BatchDest**，然后右键单击**属性**。  

2. 在参与方属性对话框中，单击**发送端口**在控制台树中。  选择**Tutorial_BatchDest**从下拉列表中，然后单击**确定**。  

   > [!NOTE]
   >  如果并发冲突发生时**Tutorial_DestBatch**更新参与方，单击**确定**并关闭对话框。 在管理控制台中，右键单击**BizTalk 组**，单击**刷新**，然后重复步骤 1 和 2。  

   请继续执行[步骤 6： 为确认批处理创建发送端口](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)。
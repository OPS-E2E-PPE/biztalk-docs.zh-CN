---
title: 步骤 6： 为确认批处理创建发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2a0f1ee-e060-4fb9-923e-ebe8168777d9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f38b8c7f8e2f486e4de6feca12bf69551221428
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004998"
---
# <a name="step-6-create-the-send-port-for-the-acknowledgment-batch"></a>步骤 6： 为确认批处理创建发送端口
在此步骤中，您创建用于传递确认批处理创建的源参与方的发送端口。 这是一个静态单向端口与文件适配器类型。 指定用于源 (\Tutorial_BatchACKDrop) 的文件文件夹位置[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将删除确认批处理文件。 定义用于指示哪种类型的确认批将发送端口的端口的筛选器。 筛选器指定 Tutorial_BatchSource 和 OutboundBatch 的消息类型的源。  

### <a name="to-create-the-send-port-for-the-acknowledgment-batch"></a>若要创建确认批处理的发送端口  

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  

2. 在“发送端口属性”对话框中，执行以下操作：  


   |   使用此选项    |                              执行的操作                               |
   |---------------|-----------------------------------------------------------------------|
   |   **名称**    |                    类型**Tutorial_BatchSource**。                     |
   |   **类型**    |               选择**文件**从下拉列表。                |
   | **配置** | 单击**配置**打开 FILE 传输属性对话框。 |


3. 在 FILE 传输属性对话框中，请执行以下操作：  


   |        使用此选项        |                                                                                                                                                                              执行的操作                                                                                                                                                                               |
   |------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **目标文件夹** | 浏览到 **\<*驱动器*:\>\Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端 Tutorial\Tutorial_BatchACKDrop的快捷键**. 这是到公共共享的文件系统上的位置的路径[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将编写包含确认批处理文件。 |
   |     **文件名**      |                                                                                                                                            类型 **%MessageID%.txt** （替换带.txt 扩展名的.xml 扩展名）。                                                                                                                                             |
   |     **副本模式**      |                                                                                                                                                                        选择**创建新的**。                                                                                                                                                                         |


4. 单击“确定” 。  

5. 在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**。  

6. 在控制台树中，单击**筛选器**，然后执行以下操作：  


   |   使用此选项   |                                                              执行的操作                                                              |
   |--------------|--------------------------------------------------------------------------------------------------------------------------------------|
   | **属性** | 单击下的字段**属性**，然后选择**Microsoft.Solutions.BTAHL7.BatchOrchestration.Party**从下拉列表。 |
   | **“运算符”** |                                                    将保留**==** 与运算符。                                                     |
   |  **ReplTest1**   |                                                    类型**Tutorial_BatchSource**。                                                    |
   | **分组依据** |                                               选择**和**从下拉列表。                                                |
   | **属性** |                                             选择**BTAHL7Schemas.BTAHL7MessageType**。                                              |
   | **“运算符”** |                                                    将保留**==** 与运算符。                                                     |
   |  **ReplTest1**   |                                                       类型**OutboundBatch**。                                                        |


7. 按 **Enter**。 在对话框中底部窗格中，验证是否正确，输入筛选器表达式，然后单击**确定**。  

8. 在 BizTalk 管理控制台中，选择**发送端口**，右键单击**Tutorial_BatchSource**，然后单击**启动**。  

### <a name="to-associate-the-send-port-with-the-source-party"></a>若要使用的源参与方关联的发送端口  

1. 在 BizTalk 管理控制台中，单击**参与方**。 右键单击**Tutorial_BatchSource**，然后单击**属性**。  

2. 在参与方属性对话框中，单击**发送端口**在控制台树中。 有关**发送端口**，选择**Tutorial_BatchSource**从下拉列表中，然后单击**确定**。  

   请继续执行[第 7 步： 启动业务流程和重新启动 BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)。
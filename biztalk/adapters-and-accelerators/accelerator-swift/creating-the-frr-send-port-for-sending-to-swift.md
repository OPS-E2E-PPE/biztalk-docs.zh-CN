---
title: 创建用于发送到 SWIFT 的 FRR 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 1ad766db-d1da-437a-a520-a3b04f0695c4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1583072986eba20b5a0202e6973a5c08095aab01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972318"
---
# <a name="creating-the-frr-send-port-for-sending-to-swift"></a>创建用于发送到 SWIFT 的 FRR 发送端口
若要执行 FIN 响应对帐，需要创建一个发送端口将消息从发送[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到 SWIFT 网络。  

 **摘要**  

 创建具有以下属性和组件的发送端口：  


|     属性 / 组件      |                                                               设置                                                                |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
|          发送端口          |                                                         静态单向端口                                                          |
|       传输类型        |                                                               MQSeries                                                               |
| 队列定义 (MQSeries) |                                                 MQSeries server 队列管理器队列                                                  |
|        发送管道        | [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]您创建了的 FRR 发送管道 |
|           筛选器           |                                                     下表中所示                                                      |

### <a name="to-add-a-custom-send-port-for-sending-to-swift"></a>若要添加自定义发送端口发送到 SWIFT  

1. 在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态一个 waySend 端口**。  

2. 在发送端口属性对话框中，在**名称**框中，键入发送端口，例如 FRRSWIFTSendPort 的名称。  

3. 有关**类型**，选择**MQSeries**。  

4. 单击**配置**。  

5. 在 MQSeries 传输属性对话框中，单击**队列定义**，然后单击省略号 （...） 按钮。  

6. 在队列定义对话框中，输入 MQSeries 服务器、 队列管理器和队列。 单击“确定” 。  

7. 在 MQSeries 传输属性对话框中，验证对属性进行了所需。 单击“确定” 。  

   > [!NOTE]
   >  MQSeries 传输属性的详细信息，请参阅 MQSeries 文档。  

8. 在发送端口属性对话框中，对于**发送处理程序**，验证是否选择 BizTalkServerApplication。  

9. 有关**发送管道**，选择[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]您创建了的 FRR 发送管道。  

10. 单击**筛选器**中左窗格中，然后执行以下操作：  


    |   使用此选项   |                            执行的操作                             |
    |--------------|-------------------------------------------------------------------|
    | **属性** |  选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_Failed**。  |
    | **“运算符”** |                          选择**==**。                           |
    |  **ReplTest1**   |                          类型**False**。                          |
    |  **分组**   |                          选择**和**。                          |
    | **属性** | 类型**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SwiftBound**。 |
    | **“运算符”** |                          选择**==**。                           |
    |  **ReplTest1**   |                          类型 **，则返回 True**。                           |


11. 单击**Apply**，然后单击**确定**。  

12. 右键单击该发送端口，然后依次**启动**。

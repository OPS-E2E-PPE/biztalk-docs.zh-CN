---
title: 步骤 7： 配置用于向贸易合作伙伴发送确认的发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a082870-894c-4f64-a575-3681d8a5c4ea
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb00e99fc28c857e85d88733baced60299f58ef8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971494"
---
# <a name="step-7-configure-a-send-port-to-send-the-acknowledgment-to-your-trading-partner"></a>步骤 7： 配置用于向贸易合作伙伴发送确认的发送端口
![步骤 7 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-7of9.gif "Step_7of9")  

 在此步骤中配置发送端口以发送由生成的 997 确认消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 Fabrikam **toTHEM_997**文件夹。  

## <a name="prerequisites"></a>必要條件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  

### <a name="to-configure-a-send-port-that-subscribes-to-the-997-acknowledgment"></a>配置订阅 997 确认的发送端口  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  

2. 在中**发送端口属性**对话框框中，执行以下操作：  

   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**名称**|输入`toTHEM_997`。|  
   |**类型**|选择**文件**。|  
   |**配置**|单击**配置**。|  

   > [!NOTE]
   >  由于 997 是要传送到文件夹中的平面文件，因而发送端口的传输类型为 FILE。  

3. 在中**FILE 传输属性**对话框中，执行以下操作，然后单击**确定**:  


   |        使用此选项        |                                                                                                              执行的操作                                                                                                              |
   |------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **目标文件夹** | 单击**浏览**，然后在**浏览文件夹**对话框中，转到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\ Scenario A\toTHEM_997。 |
   |     **文件名**      |                                                                                           输入`%MessageID%.txt`，然后单击**确定**。                                                                                            |

   > [!NOTE]
   >  值设置为**文件名**属性可确保输出文件将具有.txt 扩展名。  

4. 在中**发送端口属性**对话框中，对于**发送管道**，选择**EdiSend**。  

   > [!NOTE]
   >  用于发送 EDI 交换的发送管道除通过 AS2 传输传递的之外其他均为 EdiSend 管道。 （AS2EdiSend 发送管道用于通过 AS2 传输发送 EDI 交换。）  

5. 在控制台树中，单击**筛选器**，然后执行以下操作：  


   |   使用此选项   |                           执行的操作                           |
   |--------------|----------------------------------------------------------------|
   | **属性** |                  选择**BTS。MessageType**。                   |
   | **“运算符”** |                         选择**==**。                         |
   |  **ReplTest1**   | 输入**<http://schemas.microsoft.com/Edi/X12#X12_997_Root>**。 |

   > [!NOTE]
   >  本筛选器可确保发送端口将提取 997 消息类型的消息。  

6. 单击“确定” 。  

7. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**发送端口**。 右键单击**toTHEM_997**，然后单击**启动**以登记并启动该端口。  

8. 在 BizTalk Server 管理控制台，在控制台树中，单击**平台设置**，然后单击**主机实例**。 在主机实例窗格中，单击**BizTalkServerApplication**，然后单击**重新启动**。  

## <a name="next-steps"></a>后续步骤  
 创建两个贸易合作伙伴之间的协议，如中所述[步骤 8： 配置参与方之间的贸易合作伙伴协议](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md)。  

## <a name="see-also"></a>请参阅  
 [配置静态发送端口以发送 EDI 交换和确认](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)
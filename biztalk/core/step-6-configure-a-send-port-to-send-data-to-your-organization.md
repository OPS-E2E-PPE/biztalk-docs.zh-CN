---
title: 步骤 6：配置发送端口以将数据发送到你的组织 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 796570ca-8178-4679-9213-d67a2a189bf9
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bdf1e798db4ef6da8b32194a781e8d56076ceab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244370"
---
# <a name="step-6-configure-a-send-port-to-send-data-to-your-organization"></a>步骤 6：配置发送端口以将数据发送到你的组织
![步骤 6 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")  

 在此步骤中配置发送端口以发送 850 消息从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到代表您所在组织的 OrderSystem 参与方。 此发送端口会应用**Inbound4010850_to_OrderFile**映射，将转换为在映射中指定的格式输出消息从输入消息的格式。  

## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  

### <a name="to-configure-a-send-port-for-the-850-message"></a>若要配置的 850 消息的发送端口  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**管道**，然后单击**刷新**。  

   > [!NOTE]
   >  正在刷新管道列表可能有必要将无法选择 SendOrderFilePipeline，你将创建的发送端口。  

2. 右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  

3. 在中**发送端口属性**对话框框中，执行以下操作：  

   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**名称**|输入`toOrderSystem`。|  
   |**类型**|选择**文件**。|  
   |**配置**|单击**配置**。|  

   > [!NOTE]
   >  由于测试消息是传送到文件夹的平面文件，发送端口的传输类型为 FILE。  

4. 在中**FILE 传输属性**对话框中，执行以下操作，然后单击**确定**:  


   |        使用此选项        |                                                                                                               执行的操作                                                                                                               |
   |------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **目标文件夹** | 单击**浏览**，然后在**查找文件夹**对话框中，转到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 界面开发人员 Tutorial\ProcessEDI_TestLocations\ Scenario A\toOrderSystem |
   |     **文件名**      |                                                                                            输入`%MessageID%.txt`，然后单击**确定**。                                                                                             |

   > [!NOTE]
   >  值设置为**文件名**属性可确保输出文件将具有.txt 扩展名。  

5. 在中**发送端口属性**对话框中，对于**发送管道**，选择**SendOrderFilePipeline**。  

   > [!NOTE]
   >  **SendOrderFilePipeline**发送管道包括平面文件组装器组合将.txt 输出文件，使用从输入 850 消息映射的数据。 由于输出文件是.txt 文件，它不会出现在交换 /ACK 状态报告中。  

6. 在控制台树中，单击**筛选器**，然后执行以下操作：  

   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**属性**|选择**BTS。ReceivePortName**。|  
   |**“运算符”**|选择 ==。|  
   |**ReplTest1**|输入`ReceiveEDI_fromTHEM_A`。|  
   |**分组依据**|选择**和**。|  
   |**属性**|在下一行中，选择**BTS。MessageType**。|  
   |**“运算符”**|选择 **！ =**。|  
   |**ReplTest1**|输入`http://schemas.microsoft.com/Edi/X12#X12_997_Root`。|  

   > [!NOTE]
   >  筛选器可确保发送端口将提取由 Receive_EDI_fromTHEM_A 接收到的消息接收位置和发送端口将不提取 997 确认，但将只提取 850 消息。  

7. 在控制台树中，单击**OutboundMaps**。 在中**出站映射**窗格中，在**地图**列，请在第一行中，选择**Inbound4010850_to_OrderFile**。 (中的条目**源文档**列将为 X12_00401_850。)  

   > [!NOTE]
   >  此步骤可确保输出消息将包含从输入消息映射的数据的仅**Inbound4010850_to_OrderFile**映射。  

8. 单击“确定” 。  

9. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**发送端口**。 右键单击**toOrderSystem**，然后单击**启动**以登记并启动该端口。  

## <a name="next-steps"></a>后续步骤  
 配置发送端口 (**toTHEM_997**) 以发送 997 确认回 Fabrikam，如中所述[步骤 7:配置用于向贸易合作伙伴发送确认的发送端口](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)。  

## <a name="see-also"></a>请参阅  
 [配置静态发送端口以发送 EDI 交换和确认](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)
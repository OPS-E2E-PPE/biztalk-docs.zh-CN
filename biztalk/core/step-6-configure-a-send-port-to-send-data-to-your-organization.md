---
title: 步骤 6： 配置发送端口将数据发送到你的组织 |Microsoft 文档
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
ms.openlocfilehash: 3b513725024aec755515ccac998745220ee5dfa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277005"
---
# <a name="step-6-configure-a-send-port-to-send-data-to-your-organization"></a>步骤 6： 配置发送端口将数据发送到你的组织
![步骤 6 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-6of9.gif "Step_6of9")  
  
 在该步骤中，会对发送端口进行配置，以将 850 消息从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送到代表您的组织的 OrderSystem 参与方。 此发送端口将应用**Inbound4010850_to_OrderFile**映射，转换到映射中指定的格式输入消息的格式输出消息。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-configure-a-send-port-for-the-850-message"></a>为 850 消息配置发送端口  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**管道**，然后单击**刷新**。  
  
    > [!NOTE]
    >  为了能够针对将要创建的发送端口选择 SendOrderFilePipeline，可能有必要刷新管道列表。  
  
2.  右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
3.  在**发送端口属性**对话框框中，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|输入`toOrderSystem`。|  
    |**类型**|选择**文件**。|  
    |**配置**|单击**配置**。|  
  
    > [!NOTE]
    >  由于测试消息是要传送到文件夹中的平面文件，因此发送端口的传输类型为 FILE。  
  
4.  在**文件传输属性**对话框框中，执行以下操作，然后单击**确定**:  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**目标文件夹**|单击**浏览**，然后在**浏览文件夹**对话框中，移动到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI 接口开发人员 Tutorial\ProcessEDI_TestLocations\ 方案 A\toOrderSystem|  
    |**文件名**|输入`%MessageID%.txt`，然后单击**确定**。|  
  
    > [!NOTE]
    >  值设置为**文件名**属性可确保输出文件将具有.txt 扩展名。  
  
5.  在**发送端口属性**对话框中，为**发送管道**，选择**SendOrderFilePipeline**。  
  
    > [!NOTE]
    >  **SendOrderFilePipeline**发送管道包括平面文件汇编组合.txt 输出文件中，使用从输入 850 消息映射的数据。 由于输出文件是 .txt 文件，因此它将不显示在交换/ACK 状态报告中。  
  
6.  在控制台树中，单击**筛选器**，然后执行以下：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**属性**|选择**BTS。ReceivePortName**。|  
    |**运算符**|选择 **==** 。|  
    |**值**|输入`ReceiveEDI_fromTHEM_A`。|  
    |**分组依据**|选择**和**。|  
    |**属性**|在下一行中，选择**BTS。MessageType**。|  
    |**运算符**|选择 **！ =**。|  
    |**值**|输入`http://schemas.microsoft.com/Edi/X12#X12_997_Root`。|  
  
    > [!NOTE]
    >  此筛选器可确保发送端口将提取由 Receive_EDI_fromTHEM_A 接收位置接收的消息，而且发送端口将不提取 997 确认，而只提取 850 消息。  
  
7.  在控制台树中，单击**OutboundMaps**。 在**出站映射**窗格中，请在**映射**列，请在第一行中，选择**Inbound4010850_to_OrderFile**。 (中的条目**源文档**列将为 X12_00401_850。)  
  
    > [!NOTE]
    >  此步骤可确保对输出消息将包含仅的数据从输入消息根据映射**Inbound4010850_to_OrderFile**映射。  
  
8.  单击 **“确定”**。  
  
9. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**发送端口**。 右键单击**toOrderSystem**，然后单击**启动**登记和启动端口。  
  
## <a name="next-steps"></a>后续步骤  
 配置发送端口 (**toTHEM_997**) 发送 997 确认重新为 Fabrikam 中, 所述[步骤 7： 配置发送端口将确认发送到你的贸易合作伙伴](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)。  
  
## <a name="see-also"></a>另请参阅  
 [配置静态发送端口发送 EDI 交换和确认](../core/configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments.md)
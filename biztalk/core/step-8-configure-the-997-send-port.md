---
title: 步骤 8：配置 997 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4780c491-9f1a-4f13-b346-6a2e1801ec09
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c31b67f99bf73e08d02500923125fa4b1fd278e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244236"
---
# <a name="step-8-configure-the-997-send-port"></a>步骤 8：配置 997 发送端口
![步骤 8 11](../core/media/tut-step8-of-11.gif "Tut_Step8_of_11")  
  
 在此步骤中，您还将设置发送端口将 997 消息发送到合作伙伴。 该发送端口使用 AS2EdiSend 发送管道将传输 EDIINT/AS2-编码的 997 确认到 _997ToFabrikam 文件夹。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-create-the-sendasync997-send-port"></a>创建 Send_Async_997 发送端口  
  
1. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在 BizTalk Application 1 节点中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**.  
  
   > [!NOTE]
   >  您将使用静态单向发送端口，因为作为 AS2 消息接收方的 Fabrikam 参与方不设置任何 MDN。  
  
2. 在中**发送端口属性**对话框框中，发送端口的名称**Send_Async_997**。 选择**HTTP**有关**类型**，然后单击**配置**。  
  
3. 在中**HTTP 传输属性**对话框中，对于**目标 URL**，输入`http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam`。 清除**启用 chunked 编码**，然后单击**确定**。  
  
   > [!NOTE]
   >  **目标 URL**设置可确保的发送端口将 997 消息发送到 Fabrikam 虚拟目录。 与该虚拟目录关联的 Default.aspx.cs 文件生成具有.msg 扩展名，997，并将其发送到目标文件夹。  
  
4. 在中**发送端口属性**对话框中，选择**AS2EdiSend**有关**发送管道**。  
  
5. 单击**筛选器**在控制台树中。 有关**属性**，选择**BTS。MessageType**。 有关**运算符**，选择 **==** 。 有关**值**，输入`http://schemas.microsoft.com/Edi/X12#X12_997_Root`。  
  
   > [!NOTE]
   >  此筛选器可确保发送端口仅将从 MessageBox 提取 997 确认。  
  
6. 单击“确定”  。  
  
7. 在中**发送端口**窗格[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**Send_Async_997**发送端口，然后依次**启动**。  
  
## <a name="next-steps"></a>后续步骤  
 配置发送端口 (**Send_Payload_EdiXml**) 中所述向 Contoso 发送 EDI 负载[步骤 9:配置 EDI 有效负载发送端口](../core/step-9-configure-the-edi-payload-send-port.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)   
 [配置 AS2 消息的静态发送端口](../core/configuring-a-static-send-port-for-messages-over-as2.md)
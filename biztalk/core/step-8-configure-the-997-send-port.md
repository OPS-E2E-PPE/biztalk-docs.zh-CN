---
title: 步骤 8： 配置 997 发送端口 |Microsoft 文档
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
ms.openlocfilehash: ec3c022ec1236d760c69250a2faecc7cacdb543c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277213"
---
# <a name="step-8-configure-the-997-send-port"></a>步骤 8： 配置 997 发送端口
![步骤 8 11](../core/media/tut-step8-of-11.gif "Tut_Step8_of_11")  
  
 在此步骤中，您将设置发送端口以将 997 消息发送给合作伙伴。 该发送端口使用 AS2EdiSend 发送管道将 EDIINT/AS2 编码的 997 确认传输到 _997ToFabrikam 文件夹。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-create-the-sendasync997-send-port"></a>创建 Send_Async_997 发送端口  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，BizTalk 应用程序 1 节点下右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**.  
  
    > [!NOTE]
    >  您将使用静态单向发送端口，这是因为没有为作为 AS2 消息接收方的 Fabrikam 参与方设置任何 MDN。  
  
2.  在**发送端口属性**对话框框中，将发送端口**Send_Async_997**。 选择**HTTP**为**类型**，然后单击**配置**。  
  
3.  在**HTTP 传输属性**对话框中，为**目标 URL**，输入`http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam`。 清除**启用 chunked 编码**，然后单击**确定**。  
  
    > [!NOTE]
    >  **目标 URL**设置可以确保发送端口将将 997 消息发送到 Fabrikam 虚拟目录。 与该虚拟目录关联的 Default.aspx.cs 文件可生成具有 .msg 扩展名的 997，并将其发送到目标文件夹。  
  
4.  在**发送端口属性**对话框中，选择**AS2EdiSend**为**发送管道**。  
  
5.  单击**筛选器**在控制台树中。 有关**属性**，选择**BTS。MessageType**。 有关**运算符**，选择 **==** 。 有关**值**，输入`http://schemas.microsoft.com/Edi/X12#X12_997_Root`。  
  
    > [!NOTE]
    >  该筛选器可确保发送端口只从 MessageBox 中提取 997 确认。  
  
6.  单击 **“确定”**。  
  
7.  在**发送端口**窗格[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**Send_Async_997**发送端口，并依次**启动**。  
  
## <a name="next-steps"></a>后续步骤  
 配置发送端口 (**Send_Payload_EdiXml**) 向 Contoso 发送 EDI 负载，如中所述[步骤 9： 配置 EDI 负载发送端口](../core/step-9-configure-the-edi-payload-send-port.md)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 将 AS2 消息的发送](../core/how-biztalk-server-sends-as2-messages.md)   
 [通过 AS2 消息配置静态发送端口](../core/configuring-a-static-send-port-for-messages-over-as2.md)
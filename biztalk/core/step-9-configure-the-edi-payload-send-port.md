---
title: 步骤 9： 配置 EDI 负载发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71a8a4a7-7c3e-4e33-a9c0-a6445a3cc236
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11f12d57a0aee016055412b9221ff2b2de442c17
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005550"
---
# <a name="step-9-configure-the-edi-payload-send-port"></a>步骤 9： 配置 EDI 负载发送端口
![步骤 9 11](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")  
  
 在此步骤中，您将设置发送端口发送到后端 Contoso 应用程序，从 EDI 负载生成的 XML 表示\\_EDIXMLToContoso 文件夹。 此发送端口使用 PassThruTransmit 发送管道。  
  
## <a name="prerequisites"></a>必要條件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-create-the-sendpayloadedixml-send-port"></a>创建 Send_Payload_EdiXml 发送端口  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态单向发送端口**。  
  
2. 在中**发送端口属性**对话框，为发送端口的名称**Send_Payload_EdiXml**。 选择**文件**有关**类型**，然后单击**配置**。  
  
   > [!NOTE]
   >  之所以指定 FILE 类型是因为该发送管道将不对负载文件执行 AS2 处理。 它只是将负载文件路由到某个本地文件夹，以便您可以看到 EDI 事务集。  
  
3. 在中**FILE 传输属性**对话框中，对于**目标文件夹**，浏览到并选择[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\\_EDIXMLToContoso。 将保留**文件名**作为 **%MessageID%.xml**。 单击“确定” 。  
  
4. 接受默认值为**PassThruTransmit**有关**发送管道**。  
  
   > [!NOTE]
   >  由于使用 PassThruTransmit 发送管道，该管道将不对负载消息执行任何 EDI 处理，而是将消息以 AS2EdiReceive 接收管道生成的 XML 格式发送到本地文件夹。  
  
5. 单击**筛选器**在控制台树中。 有关**属性**，输入**BTS。MessageType**。 有关**运算符**，输入**==**。 有关**值**，输入`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`。  
  
   > [!NOTE]
   >  该筛选器可确保此发送端口只从 MessageBox 中提取 X12 864 负载消息。  
  
6. 单击“确定” 。  
  
7. 在中**发送端口**窗格[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**Send_Payload_EdiXml**发送端口，然后依次**启动**。  
  
## <a name="next-steps"></a>后续步骤  
 创建一个 AS2 和 X12 协议之间的两个贸易合作伙伴，如中所述[步骤 10： 配置 X12 和 AS2 贸易合作伙伴协议](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)  
  
## <a name="see-also"></a>请参阅  
 [教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md)
---
title: "步骤 9： 配置 EDI 负载发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71a8a4a7-7c3e-4e33-a9c0-a6445a3cc236
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9de1dff24af11cd03cda2550dcab921aec25d585
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-9-configure-the-edi-payload-send-port"></a>步骤 9： 配置 EDI 负载发送端口
![步骤 9 11](../core/media/tut-step9-of-11.gif "Tut_Step9_of_11")  
  
 在此步骤中，你将发送端口设置为发送到后端 Contoso 应用程序，从 EDI 负载生成的 XML 表示\\_EDIXMLToContoso 文件夹。 此发送端口使用 PassThruTransmit 发送管道。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-create-the-sendpayloadedixml-send-port"></a>创建 Send_Payload_EdiXml 发送端口  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。  
  
2.  在**发送端口属性**对话框中，你发送端口作为名称**Send_Payload_EdiXml**。 选择**文件**为**类型**，然后单击**配置**。  
  
    > [!NOTE]
    >  之所以指定 FILE 类型是因为该发送管道将不对负载文件执行 AS2 处理。 它只是将负载文件路由到某个本地文件夹，以便您可以看到 EDI 事务集。  
  
3.  在**文件传输属性**对话框中，为**目标文件夹**，浏览到并选择[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 教程\\_EDIXMLToContoso。 保留**文件名**作为**%MessageID%.xml**。 单击 **“确定”**。  
  
4.  接受默认的**PassThruTransmit**为**发送管道**。  
  
    > [!NOTE]
    >  由于使用 PassThruTransmit 发送管道，该管道将不对负载消息执行任何 EDI 处理，而是将消息以 AS2EdiReceive 接收管道生成的 XML 格式发送到本地文件夹。  
  
5.  单击**筛选器**在控制台树中。 有关**属性**，输入**BTS。MessageType**。 有关**运算符**，输入 **==** 。 有关**值**，输入`http://schemas.microsoft.com/BizTalk/Edi/X12/2006#X12_00401_864`。  
  
    > [!NOTE]
    >  该筛选器可确保此发送端口只从 MessageBox 中提取 X12 864 负载消息。  
  
6.  单击 **“确定”**。  
  
7.  在**发送端口**窗格[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**Send_Payload_EdiXml**发送端口，并依次**启动**。  
  
## <a name="next-steps"></a>后续步骤  
 创建 X12 和 AS2 协议之间的两个贸易合作伙伴中, 所述[步骤 10： 配置 X12 和 AS2 贸易合作伙伴协议](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)  
  
## <a name="see-also"></a>另请参阅  
 [教程 3: AS2 教程](../core/tutorial-3-as2-tutorial.md)
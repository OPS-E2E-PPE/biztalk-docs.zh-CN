---
title: "步骤 7： 配置 MDN 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 983033ac-9d32-47c8-9bb8-b4161bcdf183
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0f70df6846553e2d64711f33e8c5a0b0e4d2cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-configure-the-mdn-send-port"></a>步骤 7： 配置 MDN 发送端口
![11 的第 7 步](../core/media/tut-step7-of-11.gif "Tut_Step7_of_11")  
  
 在此步骤中，你将设置动态发送端口发送异步 MDN 到\\_MDNToFabrikam 文件夹。 此发送端口使用 AS2Send 发送管道生成传出 MDN 响应。 由于这是动态发送端口，它将使用地址的回执送达选项行中消息的标头来将消息路由到\\_MDNToFabrikam 文件夹。 此地址为 Fabrikam 虚拟目录。 与此虚拟目录关联的 Default.aspx.cs 文件生成带扩展名 .msg 的 MDN，并将此文件发送到目标文件夹（也在 Receipt-Delivery-Option 中加以指定）。  
  
> [!NOTE]
>  您还可以通过用协议设置覆盖消息设置，将协议配置为将 MDN 发送到其他地址。 有关详细信息，请参阅  
  
 在此示例中，使用动态发送端口发送 MDN；但是您还可以使用静态发送端口将 MDN 发送到静态地址。 有关详细信息，请参阅[通过 AS2 异步 Mdn 的配置静态发送端口](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)和[通过 AS2 异步 Mdn 的配置动态发送端口](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-create-the-sendasyncmdn-send-port"></a>创建 Send_Async_MDN 发送端口  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，BizTalk 应用程序 1 节点下右键单击**发送端口**，指向**新建**，然后单击**动态单向发送端口**.  
  
2.  在**发送端口属性**对话框中，名称发送端口作为**Send_Async_MDN**。  
  
3.  选择**AS2Send**为**发送管道**。  
  
    > [!NOTE]
    >  使用 AS2Send 管道是由于对于 MDN 而言不需要进行 EDI 处理。  
  
4.  单击**筛选器**在控制台树中。 在筛选器窗格中，选择**EdiIntAS.IsAS2AsynchronousMdn**为**属性**，  **==** 为**运算符**，并输入**True**为**值**。  
  
    > [!NOTE]
    >  此筛选器可确保动态发送端口只从 MessageBox 中提取异步 MDN。  
  
5.  单击 **“确定”**。  
  
6.  在**发送端口**窗格[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**Send_Async_MDN**，然后单击**启动**。  
  
## <a name="next-steps"></a>后续步骤  
 配置发送端口 (**Send_Async_997**) 发送 997 确认重新为 Fabrikam 中, 所述[第 8 步： 配置 997 发送端口](../core/step-8-configure-the-997-send-port.md)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 将 AS2 消息的发送](../core/how-biztalk-server-sends-as2-messages.md)   
 [通过 AS2 异步 Mdn 的配置静态发送端口](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)   
 [通过 AS2 消息配置动态发送端口](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)
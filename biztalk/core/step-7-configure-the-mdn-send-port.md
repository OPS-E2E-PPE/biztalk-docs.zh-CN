---
title: 步骤 7： 配置 MDN 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 983033ac-9d32-47c8-9bb8-b4161bcdf183
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e65ac8f264e1d8784c97645383b055391397da1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987742"
---
# <a name="step-7-configure-the-mdn-send-port"></a>步骤 7： 配置 MDN 发送端口
![步骤 7 11](../core/media/tut-step7-of-11.gif "Tut_Step7_of_11")  
  
 在此步骤中，您将设置动态发送端口发送异步 MDN \\_MDNToFabrikam 文件夹。 此发送端口使用 AS2Send 发送管道生成传出 MDN 响应。 由于这是一个动态发送端口，它将使用地址中消息的标头中的回执送达选项行来将消息路由到\\_MDNToFabrikam 文件夹。 此地址为 Fabrikam 虚拟目录。 与此虚拟目录关联的 Default.aspx.cs 文件生成带扩展名 .msg 的 MDN，并将此文件发送到目标文件夹（也在 Receipt-Delivery-Option 中加以指定）。  
  
> [!NOTE]
>  您还可以通过用协议设置覆盖消息设置，将协议配置为将 MDN 发送到其他地址。 有关详细信息，请参阅  
  
 在此示例中，使用动态发送端口发送 MDN；但是您还可以使用静态发送端口将 MDN 发送到静态地址。 有关详细信息，请参阅[配置静态发送端口通过 AS2 发送异步 mdn](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)并[配置动态发送端口通过 AS2 发送异步 Mdn 的](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)。  
  
## <a name="prerequisites"></a>必要條件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-create-the-sendasyncmdn-send-port"></a>创建 Send_Async_MDN 发送端口  
  
1. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，在 BizTalk Application 1 节点中，右键单击**发送端口**，依次指向**新建**，然后单击**动态单向发送端口**.  
  
2. 在中**发送端口属性**对话框中，发送端口的名称作为**Send_Async_MDN**。  
  
3. 选择**AS2Send**有关**发送管道**。  
  
   > [!NOTE]
   >  使用 AS2Send 管道是由于对于 MDN 而言不需要进行 EDI 处理。  
  
4. 单击**筛选器**在控制台树中。 在筛选器窗格中，选择**EdiIntAS.IsAS2AsynchronousMdn**有关**属性**， **==** 有关**运算符**，并输入 **，则返回 true**有关**值**。  
  
   > [!NOTE]
   >  此筛选器可确保动态发送端口只从 MessageBox 中提取异步 MDN。  
  
5. 单击“确定” 。  
  
6. 在中**发送端口**窗格[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**Send_Async_MDN**，然后单击**启动**。  
  
## <a name="next-steps"></a>后续步骤  
 配置发送端口 (**Send_Async_997**) 以发送 997 确认回 Fabrikam，如中所述[步骤 8： 配置 997 发送端口](../core/step-8-configure-the-997-send-port.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 如何发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)   
 [配置通过 AS2 发送异步 Mdn 的静态发送端口](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)   
 [配置 AS2 消息的动态发送端口](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)
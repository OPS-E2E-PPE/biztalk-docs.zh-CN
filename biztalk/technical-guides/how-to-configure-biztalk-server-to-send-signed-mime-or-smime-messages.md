---
title: 如何配置 BizTalk Server 发送签名 MIME 或 SMIME 消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba42463b-2c12-4329-919e-aca427d14eee
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 623e8e6349494ce1d15089093b1620b4da76adbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297869"
---
# <a name="how-to-configure-biztalk-server-to-send-signed-mime-or-smime-messages"></a>如何配置 BizTalk Server 发送签名 MIME 或 SMIME 消息
本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用证书来发送签名的 MIME/SMIME 邮件。 下面的过程也适用于配置通过 AS2 传输发送签名的消息。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，你必须登录为的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。  
  
### <a name="to-configure-biztalk-server-to-send-signed-messages"></a>若要配置 BizTalk Server 发送签名的消息  
  
1.  创建管道用于发送签名的消息，如下所示：  
  
    > [!NOTE]
    >  配置 AS2 传输发送签名的消息，因为 AS2Send 和 AS2EdiSend 管道，都将纳入时，此步骤不需要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供此函数。  
  
    1.  创建发送管道，然后拖动到管道的编码阶段的 MIME/SMIME 编码器管道组件。  
  
    2.  在**属性**窗口中，配置到 ClearSign 或 BlobSign 的 MIME/SMIME 编码器管道组件签名类型属性。  
  
        > [!NOTE]
        >  如果你使用加密，只能选择 BlobSign。  
  
        > [!NOTE]
        >  您可以在将管道部署到某一 BizTalk 组中后使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置发送管道组件属性。  
  
        > [!NOTE]
        >  MIME/SMIME 编码器管道组件既执行加密，又执行数字签名（在配置为执行这两个功能时）。 因此，如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为发送加密和签名消息，则可以使用同一发送管道。 换言之，您不必为加密和数字签名创建各自的管道。  
  
    3.  生成并部署发送管道。  
  
2.  配置发送端口用于发送签名的消息，如下所示：  
  
    1.  添加你创建包含的 BizTalk 应用程序包括发送端口将签名的消息发送到发送管道的 BizTalk 程序集。  
  
        > [!NOTE]
        >  配置用于发送 AS2 传输签名消息，因为 AS2Send 和 AS2EdiSend 管道包含 BizTalk EDI 应用程序中时，此步骤不需要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
    2.  配置你在前面的过程中创建的发送管道的 BizTalk 应用程序中的发送端口。  
  
3.  使用的证书，如下所示发送签名的消息，配置组：  
  
    1.  通过展开 BizTalk 组中的安装签名证书配置 BizTalk 组[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台，用鼠标右键单击**BizTalk 组**，然后单击**属性**。  
  
    2.  单击证书选项卡，单击**浏览**，选择相应的证书，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [为 MIME 或 SMIME 消息配置证书](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)
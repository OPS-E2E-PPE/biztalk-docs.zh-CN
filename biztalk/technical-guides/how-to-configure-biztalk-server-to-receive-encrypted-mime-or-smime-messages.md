---
title: 如何配置 BizTalk Server 接收加密的 MIME 或 SMIME 消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d72002c8-6bd8-458f-8149-1c0c4cbbb682
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd9778d6fb37058cfb70d476590b5d32fe8936e1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008758"
---
# <a name="how-to-configure-biztalk-server-to-receive-encrypted-mime-or-smime-messages"></a>如何配置 BizTalk Server 接收加密的 MIME 或 SMIME 消息
本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用证书来接收加密的 MIME/SMIME 消息。 下面的过程也适用于通过 AS2 传输配置加密的消息的接收。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，你必须登录为的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。  
  
### <a name="to-configure-biztalk-server-to-receive-encrypted-messages"></a>若要配置 BizTalk Server 接收加密的消息  
  
1.  创建管道用于接收加密的消息，如下所示：  
  
    > [!NOTE]
    >  配置 AS2 传输收到加密的消息因为 BizTalk Server 中包含 AS2Receive 和 AS2EdiReceive 管道提供此函数时，不需要此步骤。  
  
    > [!NOTE]
    >  MIME/SMIME 解码器管道组件既执行解密，又执行数字签名验证（在配置为执行这两个功能时）。 因此，如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为接收加密和签名消息，则可以使用同一接收管道。 换言之，您不必为解密和数字签名验证创建不同的管道。  
  
    1.  创建接收管道，然后将 MIME/SMIME 解码器管道组件拖到管道的解码阶段。  
  
    2.  在**属性**窗口中，配置的 MIME/SMIME 解码器管道组件属性。  
  
        > [!NOTE]
        >  包括配置 MIME/SMIME 解码器管道组件属性将检查吊销列表属性设置为 True，如果你想要检查证书吊销列表中的发件人将用于对发送到的消息进行签名的证书[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 禁用此选项可提高该组件的性能。 与证书关联的证书吊销列表从适当的证书服务 Web 站点下载。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法连接到远程网站，而管道中，消息将失败。  
  
        > [!NOTE]
        >  您可以在将管道部署到某一 BizTalk 组中后，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置接收位置的管道属性。 还可以为 BizTalk 组中的每个接收位置配置不同的管道属性。  
  
    3.  生成并部署接收管道。  
  
2.  配置接收位置用于接收加密的消息，如下所示：  
  
    1.  添加你创建包含 BizTalk 应用程序包括接收位置接收加密的消息的接收管道的 BizTalk 程序集。  
  
        > [!NOTE]
        >  配置用于接收加密的消息，由于 AS2Receive 和 AS2EdiReceive 管道都包括 BizTalk EDI 应用程序中的 AS2 传输时不需要此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
    2.  配置你在上一步中创建接收管道的 BizTalk 应用程序中的接收位置。  
  
3.  配置用于的主机接收处理程序为使用解密证书中，接收位置，如下所示：  
  
    1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击 BizTalk，它是托管的处理程序接收已加密的消息，然后单击**属性**。  
  
        > [!NOTE]
        >  此过程不适用于 AS2 传输适用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 它适用于 BizTalk MIME 解码器不 AS2 解码器。 AS2 解码器将确定基于消息中的证书信息的证书。  
  
    2.  在**主机属性**对话框中，单击**证书**，然后单击**浏览**。  
  
        > [!NOTE]
        >  以上过程使你能够配置你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，因此，只有某些主机可以接收和处理特定消息。 如果主机配置要用于消息解码和解密的证书的指纹和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]为该主机的 MessageBox 数据库中创建应用程序属性。 保护接收的消息和解密使用此指纹则仅传送向此服务器和配置具有此指纹的其他主机。  
  
    3.  在**选择证书**对话框中，选择安装，解密证书，然后关闭所有对话框。  
  
## <a name="see-also"></a>另请参阅  
 [为 MIME 或 SMIME 消息配置证书](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)
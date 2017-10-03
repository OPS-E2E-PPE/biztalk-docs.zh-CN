---
title: "如何配置 BizTalk 服务器以接收注册 MIME 或 SMIME 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50570257-7bb6-4ede-9026-873eefd06483
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88487fb96c89b8a611ab591223fa1820f70de1cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-to-receive-signed-mime-or-smime-messages"></a>如何配置 BizTalk 服务器以接收注册 MIME 或 SMIME 消息
本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用证书来接收签名的 MIME/SMIME 消息。 下面的过程也适用于配置的签名的消息接收通过 AS2 传输。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，你必须登录为的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。  
  
### <a name="to-configure-biztalk-server-to-receive-signed-messages"></a>若要配置 BizTalk 服务器以接收签名消息  
  
1.  创建管道用于接收签名的消息，如下所示：  
  
    > [!NOTE]
    >  配置 AS2 传输，对于接收已签名消息，因为 AS2Receive 和 AS2EdiReceive 管道，都将纳入时，此步骤不需要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供此函数。  
  
    1.  创建接收管道，然后拖动到接收管道则解码阶段的 MIME/SMIME 解码器管道组件。  
  
    2.  在**属性**窗口中，配置的 MIME/SMIME 解码器管道组件属性。  
  
        > [!NOTE]
        >  您可以在将管道部署到某一 BizTalk 组中后，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置接收位置的管道属性。 还可以为 BizTalk 组中的每个接收位置配置不同的管道属性。  
  
    3.  生成并部署接收管道。  
  
2.  配置接收位置接收签名的消息，如下所示：  
  
    1.  添加你创建包含 BizTalk 应用程序包括接收位置接收签名的消息的接收管道的 BizTalk 程序集。  
  
        > [!NOTE]
        >  对于接收已签名消息，由于 AS2Receive 和 AS2EdiReceive 管道都包括 BizTalk EDI 应用程序中配置 AS2 传输时不需要此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
    2.  配置你在前面的过程中创建接收管道的 BizTalk 应用程序中的接收位置。  
  
3.  配置当事方，并且接收签名的消息，如下所示的证书：  
  
    -   打开**参与方属性**对话框在 BizTalk Server 管理控制台中，单击**证书**选项卡上，单击**浏览**，选择相应的证书，然后单击**确定**。  
  
        > [!NOTE]
        >  用于验证参与方签名的证书必须与用于验证其他参与方签名的证书不同。  
  
## <a name="see-also"></a>另请参阅  
 [为 MIME 或 SMIME 消息配置证书](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)
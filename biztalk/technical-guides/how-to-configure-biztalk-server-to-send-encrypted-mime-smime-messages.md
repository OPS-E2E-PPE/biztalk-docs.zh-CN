---
title: "如何配置 BizTalk Server 发送加密 MIME/SMIME 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14f67152-5f80-4040-a9d6-0819fab7fcb5
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c83b5f28ac3716376aa93cff22f933363825615e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-to-send-encrypted-mimesmime-messages"></a>如何配置 BizTalk Server 发送加密的 MIME/SMIME 消息
本主题介绍如何配置 BizTalk Server 使用证书来发送加密的 MIME/SMIME 消息。 下面的过程也适用于配置通过 AS2 传输发送加密的消息。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。  
  
### <a name="to-configure-biztalk-server-to-send-encrypted-messages"></a>若要配置 BizTalk Server 发送加密的消息  
  
1.  创建管道用于发送加密的消息，如下所示：  
  
    > [!NOTE]  
    >  配置用于发送加密的消息，因为 AS2Send 和 AS2EdiSend 管道的 AS2 传输中包含时，此步骤不需要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供此函数。  
  
    1.  创建发送管道，然后拖动到管道的编码阶段的 MIME/SMIME 编码器管道组件。  
  
    2.  在**属性**窗口中，配置到的 MIME/SMIME 编码器管道组件启用加密属性**True**。  
  
        > [!NOTE]  
        >  您可以在将管道部署到某一 BizTalk 组中后使用 BizTalk Server 管理控制台配置发送管道组件属性。  
  
    3.  生成并部署发送管道。  
  
2.  配置发送端口用于发送加密的消息、，如下所示：  
  
    1.  添加你创建包含 BizTalk 应用程序包括接收位置接收加密的消息的发送管道的 BizTalk 程序集。  
  
        > [!NOTE]  
        >  配置 AS2 传输发送加密的消息，因为 AS2Send 和 AS2EdiSend 管道都包括在 BizTalk EDI 应用程序时，不需要此步骤。  
  
    2.  配置你在前面的过程中创建的发送管道的 BizTalk 应用程序中的发送端口。  
  
    3.  通过右键单击发送端口中，单击安装的加密证书分配**属性**，然后单击**证书**。 单击**浏览**，浏览到你想要分配到此发送端口，，然后单击的证书**确定**。  
  
        > [!NOTE]  
        >  如果证书中不存在的本地计算机上，**指纹**框中，键入或粘贴证书指纹，，然后单击**确定**。 证书指纹的格式为 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数。
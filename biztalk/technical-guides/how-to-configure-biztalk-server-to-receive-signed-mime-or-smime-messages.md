---
title: 如何配置 BizTalk Server 以便接收签名的 MIME 或 SMIME 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50570257-7bb6-4ede-9026-873eefd06483
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2df073a27cb9e17851c9afec4b5531424d913fab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009182"
---
# <a name="how-to-configure-biztalk-server-to-receive-signed-mime-or-smime-messages"></a>如何配置 BizTalk Server 以便接收签名的 MIME 或 SMIME 消息
本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用证书以接收签名的 MIME/SMIME 消息。 下面的过程也适用于配置的签名消息接收通过 AS2 传输。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-configure-biztalk-server-to-receive-signed-messages"></a>若要配置 BizTalk Server 以便接收签名消息  
  
1. 创建一个管道以接收签名的消息，如下所示：  
  
   > [!NOTE]
   >  在配置 AS2 传输，用于接收签名消息，因为 AS2Receive 和 AS2EdiReceive 管道，包括在不需要执行此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供此函数。  
  
   1. 创建一个接收管道，然后将 MIME/SMIME 解码器管道组件拖至接收管道的解码阶段。  
  
   2. 在中**属性**窗口中，配置 MIME/SMIME 解码器管道组件属性。  
  
      > [!NOTE]
      >  您可以在将管道部署到某一 BizTalk 组中后，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置接收位置的管道属性。 还可以为 BizTalk 组中的每个接收位置配置不同的管道属性。  
  
   3. 生成并部署接收管道。  
  
2. 配置接收位置以便接收签名的消息，如下所示：  
  
   1. 添加你创建包含到包括接收位置的 BizTalk 应用程序以接收签名的消息的接收管道的 BizTalk 程序集。  
  
      > [!NOTE]
      >  对于接收已签名消息，因为 AS2Receive 和 AS2EdiReceive 管道包含在 BizTalk EDI 应用程序中配置 AS2 传输时不需要执行此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
   2. 在前面过程中创建的接收管道的 BizTalk 应用程序中配置接收位置。  
  
3. 配置参与方，并且证书以便接收签名的消息，如下所示：  
  
   -   打开**参与方属性**对话框的在 BizTalk Server 管理控制台中，单击**证书**选项卡上，单击**浏览**，选择相应的证书，然后单击**确定**。  
  
       > [!NOTE]
       >  用于验证参与方签名的证书必须与用于验证其他参与方签名的证书不同。  
  
## <a name="see-also"></a>请参阅  
 [为 MIME 或 SMIME 消息配置证书](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)
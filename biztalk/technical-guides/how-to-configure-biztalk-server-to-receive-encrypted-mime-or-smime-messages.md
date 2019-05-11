---
title: 如何配置 BizTalk Server 以便接收加密的 MIME 或 SMIME 消息 |Microsoft Docs
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
ms.openlocfilehash: 5b785e85f4d53feda47f4ebf4bf0ab34c56b830d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242621"
---
# <a name="how-to-configure-biztalk-server-to-receive-encrypted-mime-or-smime-messages"></a>如何配置 BizTalk Server 以便接收加密的 MIME 或 SMIME 消息
本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用证书以便接收加密的 MIME/SMIME 消息。 下面的过程也适用于配置的加密消息接收通过 AS2 传输。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-configure-biztalk-server-to-receive-encrypted-messages"></a>若要配置 BizTalk Server 以便接收加密的消息  
  
1. 创建管道以便接收加密的消息，如下所示：  
  
   > [!NOTE]
   >  配置 AS2 传输，以便接收加密的消息，因为 BizTalk Server 中包含的 AS2Receive 和 AS2EdiReceive 管道处理此函数时，不需要此步骤。  
   > 
   > [!NOTE]
   >  MIME/SMIME 解码器管道组件执行解密和数字签名验证 （如果配置为执行这两个函数）。 因此，如果你要配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收加密和签名消息，则可以使用相同的接收管道。 换而言之，不需要创建单独的管道解密和数字签名验证。  
  
   1. 创建一个接收管道，然后将 MIME/SMIME 解码器管道组件拖至管道的解码阶段。  
  
   2. 在中**属性**窗口中，配置 MIME/SMIME 解码器管道组件属性。  
  
      > [!NOTE]
      >  配置 MIME/SMIME 解码器管道组件属性包括检查吊销列表属性设置为 True，如果你想要检查证书吊销列表的证书，发件人用于签名消息发送到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. 如果禁用此选项会增加该组件的性能。 与证书关联的证书吊销列表从相应的证书服务 Web 站点下载。 如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法连接到远程网站，而管道中则消息将失败。  
      > 
      > [!NOTE]
      >  管道部署到 BizTalk 组使用后，可以配置接收位置的管道属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 每个接收位置在 BizTalk 组中，可以配置不同的管道属性。  
  
   3. 生成并部署接收管道。  
  
2. 配置接收位置以便接收加密的消息，如下所示：  
  
   1. 添加你创建包含到包括接收位置的 BizTalk 应用程序以便接收加密的消息的接收管道的 BizTalk 程序集。  
  
      > [!NOTE]
      >  配置 AS2 传输，以便接收加密的消息，因为 BizTalk EDI 应用程序中包含了 AS2Receive 和 AS2EdiReceive 管道时不需要执行此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
   2. 在上一步中创建的接收管道的 BizTalk 应用程序中配置接收位置。  
  
3. 配置用于的主机的接收处理程序的解密证书，接收位置，如下所示：  
  
   1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击 BizTalk，它是托管的处理程序，以便接收加密的消息，然后单击**属性**。  
  
      > [!NOTE]
      >  此过程不适用于 AS2 传输附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 它适用于 BizTalk MIME 解码器未 AS2 解码器。 AS2 解码器将确定基于消息中的证书信息的证书。  
  
   2. 在中**主机属性**对话框中，单击**证书**，然后单击**浏览**。  
  
      > [!NOTE]
      >  以上过程可以配置在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境，因此只有某些主机可以接收和处理特定消息。 要用于消息解码和解密，证书的指纹与配置主机时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MessageBox 数据库中为该主机创建应用程序属性。 保护消息的接收和解密使用此指纹被仅路由到此资源和配置具有此指纹的其他主机。  
  
   3. 在中**选择证书**对话框中，选择你安装的解密证书，然后关闭所有对话框。  
  
## <a name="see-also"></a>请参阅  
 [为 MIME 或 SMIME 消息配置证书](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)
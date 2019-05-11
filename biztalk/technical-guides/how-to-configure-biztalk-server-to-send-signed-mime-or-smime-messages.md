---
title: 如何配置 BizTalk Server 发送到签名的 MIME 或 SMIME 消息 |Microsoft Docs
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
ms.openlocfilehash: df13f4f1db23800f59acbc58ced1a619380fd032
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396686"
---
# <a name="how-to-configure-biztalk-server-to-send-signed-mime-or-smime-messages"></a>如何配置 BizTalk Server 以便发送签名的 MIME 或 SMIME 消息
本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以使用证书进行签名的 MIME/SMIME 消息发送。 下面的过程也适用于配置通过 AS2 传输发送签名消息。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-configure-biztalk-server-to-send-signed-messages"></a>若要配置 BizTalk Server 以便发送签名的消息  
  
1. 创建一个管道以发送签名的消息，如下所示：  
  
   > [!NOTE]
   >  在配置 AS2 传输以便发送签名的消息，因为 AS2Send 和 AS2EdiSend 管道，包括在不需要执行此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供此函数。  
  
   1. 创建一个发送管道，然后将 MIME/SMIME 编码器管道组件拖至管道的编码阶段。  
  
   2. 在中**属性**窗口中，配置到 ClearSign 或 BlobSign 的 MIME/SMIME 编码器管道组件签名类型属性。  
  
      > [!NOTE]
      >  如果您使用加密，只能选择 BlobSign。  
      > 
      > [!NOTE]
      >  可以配置使用的发送管道组件属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管道部署到 BizTalk 组后的管理控制台。  
      > 
      > [!NOTE]
      >  MIME/SMIME 编码器管道组件执行加密和数字签名 （如果配置为执行这两个函数）。 因此，如果你要配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到发送加密和签名消息，则可以使用同一发送管道。 换而言之，不需要创建单独的加密和数字签名的管道。  
  
   3. 生成并部署发送管道。  
  
2. 配置发送端口以便发送签名的消息，如下所示：  
  
   1. 添加你创建包含包括发送端口以发送签名的消息的 BizTalk 应用程序的发送管道的 BizTalk 程序集。  
  
      > [!NOTE]
      >  因为 AS2Send 和 AS2EdiSend 管道包含在 BizTalk EDI 应用程序中配置 AS2 传输发送签名消息时不需要执行此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
   2. 在上一过程中创建的发送管道的 BizTalk 应用程序中配置发送端口。  
  
3. 配置组，如下所示发送签名的消息的证书：  
  
   1. 配置 BizTalk 组的情况下展开 BizTalk 组中的安装签名证书[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右击**BizTalk 组**，然后单击**属性**。  
  
   2. 单击证书选项卡中，单击**浏览**，选择相应的证书，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [为 MIME 或 SMIME 消息配置证书](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)
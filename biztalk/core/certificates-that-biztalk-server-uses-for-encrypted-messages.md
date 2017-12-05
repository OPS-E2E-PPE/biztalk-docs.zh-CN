---
title: "BizTalk Server 使用的证书加密消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, message flow [encrypted messages]
- encrypted messages
- messages, encryption
ms.assetid: 44b06488-4ecd-436d-af3d-b95e285ecb3e
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f2dbd51506da7b505f66b3001b8bdc6fa0a58ac
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="certificates-that-biztalk-server-uses-for-encrypted-messages"></a>BizTalk Server 用于加密消息的证书
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持的基于安全多用途 Internet 邮件扩展 (S/MIME) 的入站邮件的出站消息的公共密钥加密和解密。 BizTalk Server 使用 S/MIME 版本 3 对出站消息进行加密，使用 S/MIME 版本 2 和 3 对入站消息进行解密。  
  
-   BizTalk Server 支持 RSA 和 Diffie Hellman 加密证书。  
  
-   BizTalk Server 支持数据加密标准 (DES)、3DES 和 RC2 加密算法。  
  
 下图显示了 BizTalk Server 接收加密消息时的消息流。  
  
 ![在收到加密的消息时消息流](../core/media/bpi-sp-msgsec-inboundencryption.gif "BPI_SP_MSGSEC_InboundEncryption")  
  
 BizTalk Server 接收加密消息时的消息流如下所示：  
  
1.  合作伙伴向 BizTalk Server 发送消息。 合作伙伴使用 BizTalk Server 公钥对消息进行加密。  
  
2.  相应的 BizTalk Server 接收处理程序接收该消息。  
  
3.  在接收管道的执行过程中，MIME/SMIME 解码器管道组件使用 BizTalk Server 私钥对消息进行解密。  
  
    > [!NOTE]
    >  对于在 IIS 7.0 的计算机上成功的管道解密，请确保为 IIS 应用程序池帐户和与接收处理程序关联的主机实例所使用的帐户是相同，并且此帐户是的成员\<machineName\>\IIS_WPG 组。 有关详细信息设置 IIS 进程有关 IIS 7.0，请参阅的标识[解决 IIS 权限问题的指导原则](../core/guidelines-for-resolving-iis-permissions-problems.md)。 这些进程必须以相同的帐户运行，以便确保加载的帐户配置文件还加载了在管道中执行解密所需的注册表项。 出于性能原因，IIS 7.0 在启动关联的 w3wp.exe 进程时不加载帐户配置文件，因此，必须使用相同的帐户配置 BizTalk 主机实例，以便 BizTalk 能够一起加载帐户配置文件和注册表项。  
  
4.  进行其他处理。  
  
 下图显示了 BizTalk Server 发送加密消息时的消息流。  
  
 ![发送加密的消息时消息流](../core/media/bpi-sp-msgsec-outboundencryption.gif "BPI_SP_MSGSEC_OutboundEncryption")  
  
 BizTalk Server 向合作伙伴发送加密消息时的消息流如下所示：  
  
1.  相应的 BizTalk Server 发送处理程序将消息发送给合作伙伴。  
  
2.  在发送管道的执行过程中，MIME/SMIME 编码器管道组件使用合作伙伴的公钥对消息进行加密。  
  
3.  合作伙伴接收来自 BizTalk Server 的消息。 合作伙伴使用其私钥对消息进行解密。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 用于签名的消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [BizTalk Server 使用的证书存储](../core/certificate-stores-that-biztalk-server-uses.md)   
 [加密和签名证书](../core/encryption-and-signing-certificates.md)   
 [发送和接收加密消息](../core/sending-and-receiving-encrypted-messages.md)
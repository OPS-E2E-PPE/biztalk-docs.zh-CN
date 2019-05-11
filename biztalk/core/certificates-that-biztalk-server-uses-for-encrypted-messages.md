---
title: BizTalk Server 使用的证书加密的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message flow [encrypted messages]
- encrypted messages
- messages, encryption
ms.assetid: 44b06488-4ecd-436d-af3d-b95e285ecb3e
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b96e47a84e94067cf197fd8614ef789af0a012ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358012"
---
# <a name="certificates-that-biztalk-server-uses-for-encrypted-messages"></a>BizTalk Server 用来加密消息的证书
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持的基于安全多用途 Internet 邮件扩展 (S/MIME) 入站消息的出站消息的公共密钥加密和解密。 BizTalk Server 使用 S/MIME 版本 3 对出站消息加密和 S/MIME 版本 2 和 3 的入站消息解密。  
  
- BizTalk Server 支持 RSA 和 Diffie Hellman 加密证书。  
  
- BizTalk Server 支持数据加密标准 (DES)、 3DES 和 RC2 加密算法。  
  
  BizTalk Server 接收加密的消息时下, 图显示的消息流。  
  
  ![接收加密的消息时，消息流](../core/media/bpi-sp-msgsec-inboundencryption.gif "BPI_SP_MSGSEC_InboundEncryption")  
  
  BizTalk Server 接收加密的消息时的消息流如下所示：  
  
1. 合作伙伴将消息发送到 BizTalk Server。 合作伙伴使用 BizTalk Server 公钥对消息进行加密。  
  
2. 相应的 BizTalk Server 接收处理程序接收的消息。  
  
3. 接收管道在执行期间，MIME/SMIME 解码器管道组件使用 BizTalk Server 私钥来解密该消息。  
  
   > [!NOTE]
   >  在 IIS 7.0 的计算机上成功执行管道解密，请确保为 IIS 应用程序池帐户和与接收处理程序关联的主机实例使用的帐户是相同的并且此帐户是属于\<machineName\>\IIS_WPG 组。 有关详细信息设置 IIS 进程有关 IIS 7.0，请参阅的标识[解决 IIS 权限疑难问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md)。 这些进程必须以确保在加载管道中执行解密所需的注册表项加载帐户配置文件的同一帐户下运行。 出于性能原因，IIS 7.0 不加载帐户配置文件，因此，以便 BizTalk 能够一起加载帐户配置文件和注册表项，必须使用相同的帐户配置 BizTalk 主机实例启动关联的 w3wp.exe 进程时。  
  
4. 进行其他处理。  
  
   BizTalk Server 发送加密的消息时下, 图显示的消息流。  
  
   ![发送加密的消息时消息流](../core/media/bpi-sp-msgsec-outboundencryption.gif "BPI_SP_MSGSEC_OutboundEncryption")  
  
   BizTalk Server 向合作伙伴发送加密的消息时的消息流如下所示：  
  
5. 相应的 BizTalk Server 向合作伙伴发送处理程序发送一条消息。  
  
6. 发送管道在执行期间，MIME/SMIME 编码器管道组件使用合作伙伴的公钥来加密消息。  
  
7. 合作伙伴从 BizTalk Server 接收的消息。 合作伙伴使用其私钥对消息进行解密。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 用于签名消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [BizTalk Server 使用的证书存储](../core/certificate-stores-that-biztalk-server-uses.md)   
 [加密和签名证书](../core/encryption-and-signing-certificates.md)   
 [发送和接收加密消息](../core/sending-and-receiving-encrypted-messages.md)
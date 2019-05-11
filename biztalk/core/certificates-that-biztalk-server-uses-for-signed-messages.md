---
title: BizTalk Server 使用的证书签名消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, signed messages
- messages, message flow [digital signatures]
- S/MIME messages
- signed messages
- digital signatures, message flow
- messages, certificates
ms.assetid: 0b521e11-73ef-424f-9e6a-4fb42dc263ff
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eba010d49bc3eec9fae2a17b6903734bc7c0d02
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357556"
---
# <a name="certificates-that-biztalk-server-uses-for-signed-messages"></a>BizTalk Server 用于签名消息的证书
BizTalk Server 支持入站安全多用途 Internet 邮件扩展 (S/MIME) 消息的出站消息签名和签名验证。 BizTalk Server 使用 S/MIME 版本 2 和 3 对出站消息进行签名并验证入站消息的签名。 同样，可以配置 BizTalk Server 以便签名和加密其发送到其合作伙伴的消息。  
  
- BizTalk Server 支持 sha-1 和 MD5 签名算法验证数字签名。 BizTalk Server 使用 sha-1 签名算法对出站消息进行签名。  
  
- 用于签名密钥由 BizTalk Server 支持的密钥交换系统是 Rivest 仅使用 Adleman (RSA) 算法和数字签名标准 (DSS)。 BizTalk Server 不支持用于签名密钥的高级加密标准 (AES) 交换系统。  
  
- BizTalk Server 支持的签名证书是 x.509 版本 3。  
  
  下图显示的消息流时 BizTalk Server 接收数字签名的邮件，并根据需要使用签名将合作伙伴标识解析到 BizTalk Server 环境中的参与方。  
  
  ![发送签名的消息时消息流](../core/media/6fd1674d-5a21-4272-83ca-608d7b400de7.gif "6fd1674d-5a21-4272-83ca-608d7b400de7")  
  
  BizTalk Server 接收数字签名的邮件时的消息流如下所示：  
  
1. 合作伙伴将消息发送到 BizTalk Server。 合作伙伴对其私钥证书的消息进行签名。  
  
2. 相应的 BizTalk Server 接收处理程序接收的消息。  
  
3. 在执行期间接收管道，MIME/SMIME 解码器管道组件使用合作伙伴的公钥来验证数字签名。  
  
4. 如果配置参与方解析组件，用于在接收管道参与方解析组件的执行过程中 BizTalk Server 系统标识参与方合作伙伴的公钥证书。  
  
5. 进行其他处理。  
  
   BizTalk Server 发送数字签名的邮件时下, 图显示的消息流。  
  
   ![](../core/media/bts-bpi-sp-msgsec-outboundsigning-r2c.gif "bts_BPI_SP_MSGSEC_OutboundSigning_R2c")  
  
   BizTalk Server 向合作伙伴发送数字签名的邮件时的消息流如下所示：  
  
6. 相应的 BizTalk Server 向合作伙伴发送处理程序发送一条消息。  
  
7. 执行过程中的发送管道，MIME/SMIME 编码器管道组件通过使用 BizTalk Server 私钥对签名消息。  
  
8. 合作伙伴从 BizTalk Server 接收的消息。 合作伙伴使用 BizTalk Server 公钥验证数字签名。  
  
   BizTalk Server 将验证与传入签名消息相关联通过验证的证书颁发机构 (CA) 信任链的证书并验证证书尚未过期的证书的有效性。 验证 CA 信任链的过程涉及遍历证书上的信任链，直到到达根证书颁发机构。 这会验证用于对消息进行签名的证书确实来自标识的参与方。 在运行时为每个已签名的消息进行此验证。  
  
   此外，BizTalk Server 可以验证证书颁发机构尚未吊销用于签名或加密消息的证书。 若要执行此操作，必须从证书颁发机构下载证书吊销列表 (CRL)，并使用 Windows 资源管理器安装它。 有关如何验证证书的详细信息，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 用来加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [BizTalk Server 使用的证书存储](../core/certificate-stores-that-biztalk-server-uses.md)   
 [加密和签名证书](../core/encryption-and-signing-certificates.md)   
 [发送和接收签名消息](../core/sending-and-receiving-signed-messages.md)
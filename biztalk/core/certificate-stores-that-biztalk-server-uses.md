---
title: "BizTalk Server 使用的证书存储 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- public key certificates
- certificate stores, warnings
- private key certificates
- certificates, private key
- Other People stores [certificates]
- certificate stores, Personal store
- Personal store [certificates]
- certificate stores, Windows stores
- certificates, public key
- certificates, certificate stores
- certificate stores
ms.assetid: 29b65913-be3b-45d9-9865-02e52e4370f4
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b142ff5b9c9007a86b09acd25f53f8c88796988c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="certificate-stores-that-biztalk-server-uses"></a>BizTalk Server 使用的证书存储
BizTalk Server 使用两种类型的证书存储：用于存储公钥的“其他人”证书存储和用于存储私钥的每个主机实例服务帐户的“个人”证书存储。  
  
 **其他人证书存储区。** 公钥证书，顾名思义，是指对存储该公钥证书的计算机具有访问权限的任何人可访问的公共证书。 BizTalk Server 使用公钥证书对发送给特定参与方的消息进行加密，并对来自特定参与方的传入消息的数字签名进行验证。 Windows 提供“其他人”证书存储来存储该计算机上所用的公钥证书。 所有用户都可读取和使用此存储区中的证书，而 Windows 管理员有维护此存储区的权限。  
  
> [!NOTE]
>  在具有 BizTalk 主机实例的本地计算机上，必须将用于验证发送到远程合作伙伴的签名或加密消息的公钥证书保存在“本地计算机”\“其他人”证书存储中。  
  
 下图显示了 BizTalk Server 用来存储公钥证书的“其他人”证书存储：  
  
 ![其他人的证书存储](../core/media/bpi-sp-msgsec-otherpeoplecertstore.gif "BPI_SP_MSGSEC_OTHERPEOPLECERTSTORE")  
  
 **个人证书存储区。** BizTalk Server 使用私钥证书来解密传入消息并对出站消息进行签名。 启用以交互方式登录的计算机上每个 Windows 帐户已通过操作系统，仅该帐户可以访问存储的个人证书。 BizTalk Server 使用对应于每个主机实例服务帐户的个人证书存储来访问每个服务帐户有权访问的私钥证书。 只有证书存储的所有者可以访问和维护他们的个人证书存储。 换句话说，您必须以每个主机服务帐户的身份登录到将作为 S/MIME 解码管道宿主的每台计算机上，然后使用证书管理单元将解密证书导入个人证书存储。  
  
 下图显示了 BizTalk Server 用来存储私钥证书的“个人”证书存储：  
  
 ![当前用户证书存储区](../core/media/bpi-sp-msgsec-mystore.gif "BPI_SP_MSGSEC_MYSTORE")  
  
> [!IMPORTANT]
>  对于运行 BizTalk 主机实例的每台计算机上的每个主机实例服务帐户，如果需要使用私钥证书进行解密或对出站消息进行签名，则私钥证书必须存储在“当前用户”\“个人”证书存储中。  
  
> [!NOTE]
>  将带有私钥的证书（用于对出站消息进行签名）添加到服务帐户的个人证书存储后，还必须在 BizTalk 管理控制台中指定此签名证书。 有关详细信息，请参阅[如何为发送签名消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)。  
  
> [!NOTE]
>  当个人证书存储用于编程操作，例如编写导入和导出证书的脚本时，个人证书存储也称为 MY 证书存储。  
  
 下表说明了在每个 Windows 证书存储中必须安装的证书。  
  
### <a name="table-1-certificates-for-each-windows-certificate-store"></a>表 1 证书对于每个 Windows 证书存储  
  
|**证书用途**|**证书类型**|**证书存储**|  
|-----------------------------|--------------------------|---------------------------|  
|签名|自己的私钥|对于配置为对消息进行签名的 MIME/SMIME 编码器管道组件具有的发送管道的主机实例的每个服务帐户的个人存储区 (**到消息中添加签名的证书**属性设置为`True`)。 有关详细信息，请参阅[如何为发送签名消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)|  
|验证签名|合作伙伴的公钥|每台具有主机实例的计算机上的“其他人”存储区，该存储区的接收管道中含有 MIME/SMIME 解码器管道组件。 有关详细信息，请参阅[如何为接收签名消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)。|  
|解密|自己的私钥|主机实例的每个服务帐户的“个人”存储区，该存储区的接收管道中含有 MIME/SMIME 解码器管道组件。 有关详细信息，请参阅[如何为接收加密的消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)。|  
|加密|合作伙伴的公钥|其他人将存储已配置为加密的消息的 MIME/SMIME 编码器管道组件具有的发送管道的主机实例的每台计算机上 (**启用加密**属性设置为`True)`。 有关详细信息，请参阅[如何为发送加密的消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)。|  
|参与方解析|合作伙伴的公钥|管理计算机上的“其他人”存储区，要在其中配置参与方解析。 有关详细信息，请参阅[使用证书的参与方解析](../core/using-certificates-for-party-resolution.md)。|  
  
 下图显示了 BizTalk Server 接收消息时，需要每个证书存储中的哪些证书。  
  
 ![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
 下图显示了 BizTalk Server 发送消息时，需要每个证书存储中的哪些证书。  
  
 ![将发送安全消息所需的证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
 有关 Microsoft 管理控制台 (MMC) 的证书存储和证书管理单元的详细信息，请参阅 Windows 帮助中的“证书控制台”。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 用于签名的消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [BizTalk Server 用于加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [加密和签名证书](../core/encryption-and-signing-certificates.md)   
 [实现消息安全性](../core/implementing-message-security.md)
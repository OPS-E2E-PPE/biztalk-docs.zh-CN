---
title: BizTalk Server 使用的证书存储 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55164b3c96bf0cc5ee5c9eac7d0d70a04b2a9d5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358022"
---
# <a name="certificate-stores-that-biztalk-server-uses"></a>BizTalk Server 使用的证书存储
BizTalk Server 将专用密钥的每个主机实例服务帐户使用两种类型的证书存储、 公共密钥的其他人证书存储和个人证书存储区。  
  
 **其他人证书存储区。** 公钥证书，正如其名，是公开的具有访问权限的任何人都在其存储他们的计算机可访问。 BizTalk Server 使用公钥证书来加密发送给特定参与方的消息并验证来自特定参与方的传入消息的数字签名。 Windows 提供了其他人证书存储来存储在计算机上使用的公钥证书。 所有用户可以读取和使用此存储区中的证书和 Windows 管理员有权维护此存储区。  
  
> [!NOTE]
>  必须将公钥证书保存在本地计算机 \ 其他人证书存储的本地计算机上没有用于验证签名或加密消息发送到远程合作伙伴的 BizTalk 主机实例。  
  
 下图显示了 BizTalk Server 使用的公钥证书的其他人证书存储：  
  
 ![其他人的证书存储区](../core/media/bpi-sp-msgsec-otherpeoplecertstore.gif "BPI_SP_MSGSEC_OTHERPEOPLECERTSTORE")  
  
 **个人证书存储区。** BizTalk Server 使用私钥证书来解密传入消息和出站消息进行签名。 若要以交互方式登录的计算机上启用了每个 Windows 帐户具有通过操作系统，只有相应的帐户可以访问存储的个人证书。 BizTalk Server 使用的个人证书存储为每个主机实例服务帐户来访问每个服务帐户有权访问的私钥证书。 只有证书存储区的所有者可以访问和维护他们的个人证书存储。 换而言之，你必须登录到每台计算机，将主机 S/MIME 解码管道为每个主机服务帐户，并导入到个人证书的解密证书存储区使用证书管理单元。  
  
 下图显示了 BizTalk Server 用于私钥证书的个人证书存储：  
  
 ![当前用户的证书存储](../core/media/bpi-sp-msgsec-mystore.gif "BPI_SP_MSGSEC_MYSTORE")  
  
> [!IMPORTANT]
>  必须具有 BizTalk 正在运行的主机实例，需要该证书进行解密或签名出站的每台计算机上每个主机实例服务帐户的当前用户 \ 个人证书存储中存储私钥证书消息。  
  
> [!NOTE]
>  你已使用私钥将证书添加到将出站消息进行签名的服务帐户的个人证书存储后，还必须在 BizTalk 管理控制台中指定此签名证书。 有关详细信息，请参阅[如何配置为发送签名消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)。  
  
> [!NOTE]
>  用于以编程方式操作，如脚本导入和导出证书时，个人证书存储区也被称为 MY 证书存储区。  
  
 下表描述了必须在每个 Windows 证书存储区中安装的证书。  
  
### <a name="table-1-certificates-for-each-windows-certificate-store"></a>每个 Windows 证书存储区的表 1 证书  
  
|**证书用途**|**证书类型**|**证书存储区**|  
|-----------------------------|--------------------------|---------------------------|  
|签名|自己的私钥|每个服务帐户配置为对消息进行签名的 MIME/SMIME 编码器管道组件都具有发送管道的主机实例的个人存储区 (**到消息中添加签名的证书**属性设置为`True`)。 有关详细信息，请参阅[如何为发送签名消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)|  
|验证签名|合作伙伴的公钥|已使用 MIME/SMIME 解码器管道组件的接收管道的主机实例的每台计算机上存储其他人。 有关详细信息，请参阅[如何配置为接收签名消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)。|  
|解密|自己的私钥|使用 MIME/SMIME 解码器管道组件的接收管道的主机实例的每个服务帐户的个人存储区。 有关详细信息，请参阅[如何配置为接收加密消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)。|  
|加密|合作伙伴的公钥|在已配置为对消息进行加密的 MIME/SMIME 编码器管道组件都具有发送管道的主机实例的每台计算机上存储其他人 (**启用加密**属性设置为`True)`。 有关详细信息，请参阅[如何配置为发送加密消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)。|  
|参与方解析|合作伙伴的公钥|要从其配置参与方解析在管理计算机上存储其他人。 有关详细信息，请参阅[使用证书进行参与方解析](../core/using-certificates-for-party-resolution.md)。|  
  
 下图显示了的证书，需要在每个证书存储在 BizTalk Server 专用于接收消息。  
  
 ![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
 下图显示了的证书，需要在每个证书存储在 BizTalk Server 专用于发送消息。  
  
 ![若要发送安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
 有关证书存储和中的 Microsoft 管理控制台 (MMC) 证书管理单元的详细信息，搜索"证书控制台"上的 Windows 帮助。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 用于签名消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [BizTalk Server 用来加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [加密和签名证书](../core/encryption-and-signing-certificates.md)   
 [实现消息安全性](../core/implementing-message-security.md)
---
title: 如何为加密消息安装证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e11fdb81-041c-4ba6-849d-d511ead0e8be
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc82981f142fa70ebdc852ae6629f6ffc2bb1208
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336966"
---
# <a name="how-to-install-the-certificates-for-encrypted-messages"></a>如何为加密消息安装证书
以下过程列出了您必须按照安装证书以便接收和发送加密的消息的高级步骤。  
  
-   若要解密的证书存储区中安装证书  
  
-   若要加密的证书存储中安装证书  
  
-   若要配置 BizTalk 主机以便接收加密的消息  
  
> [!NOTE]
>  你可以使用一个证书签名和加密操作，或可以为每个函数使用一个证书。  
  
### <a name="to-install-the-decryption-certificates-in-the-certificates-store"></a>若要在证书存储中安装解密证书  
  
1. 你的组织中的管理员请求用于从证书颁发机构 (CA) 加密的私钥 / 公钥对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用。  
  
2. 管理员将加密的公钥发送给合作伙伴 a。  
  
3. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，运行该处理程序的主机实例的服务帐户将从合作伙伴 A.安装接收消息的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]私钥证书用于解密消息的服务帐户的个人存储中。 下图显示了你在其中安装证书的证书存储区。  
  
    ![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
4. 在合作伙伴 A 中，安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]公钥证书以加密消息发送到合作伙伴 A 在适当的存储中。 (如果合作伙伴 A 使用[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]， [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]， [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，其他人存储中安装公钥。)  
  
### <a name="to-install-the-encryption-certificates-in-the-certificates-store"></a>若要安装的证书存储中的加密证书  
  
1. 合作伙伴 A 从 CA 请求用于加密的私钥 / 公钥对。  
  
2. 合作伙伴 A 中安装私钥证书用于解密在适当的存储中的消息。 (如果合作伙伴 A 使用[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]， [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]， [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，个人证书存储中安装私钥。)  
  
3. 合作伙伴 A 向您发送其公钥用于加密消息发送到合作伙伴 a。  
  
4. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，登录到具有主机实例运行将消息发送到合作伙伴 A.安装合作伙伴 A 的公钥证书用于加密发送到合作伙伴 A 在其他人存储中的消息的处理程序的服务器。 下图显示了你在其中安装证书的证书存储区。  
  
    ![若要发送安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
### <a name="to-configure-biztalk-hosts-for-receiving-encrypted-messages"></a>若要配置 BizTalk 主机以便接收加密的消息  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，展开**主机**。  
  
   1.  在右窗格中，右键单击以便接收加密的消息，处理程序的 BizTalk 主机，然后单击**属性**。  
  
   2.  上**主机属性**对话框中，单击**证书**，单击**浏览**。  
  
   3.  上**选择证书**对话框中，选择你安装的解密证书，然后关闭所有对话框。  
  
       > [!NOTE]
       >  有关详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
## <a name="next-steps"></a>后续步骤  
 创建管道以便接收加密的消息中[如何配置为接收加密消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)  
  
 创建管道以便发送加密的消息[如何为发送加密消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 用来加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [发送和接收加密消息](../core/sending-and-receiving-encrypted-messages.md)
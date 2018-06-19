---
title: 如何安装证书的加密消息 |Microsoft 文档
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
ms.openlocfilehash: 3b1df2e9e5bf42a215420dac155fafac8e92ae21
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254773"
---
# <a name="how-to-install-the-certificates-for-encrypted-messages"></a>如何安装的证书加密的邮件
下面的过程列出了安装证书以便接收和发送加密消息所需遵守的高级步骤。  
  
-   在证书存储中安装证书以进行解密  
  
-   在证书存储中安装证书以进行加密  
  
-   配置 BizTalk 主机以便接收加密消息  
  
> [!NOTE]
>  可以使用一个证书同时执行签名和加密操作，也可以对于每种功能使用一个证书。  
  
### <a name="to-install-the-decryption-certificates-in-the-certificates-store"></a>在证书存储中安装解密证书  
  
1.  组织中的管理员从证书颁发机构 (CA) 请求用于加密的私钥/公钥对以供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用。  
  
2.  管理员向合作伙伴 A 发送用于加密的公钥。  
  
3.  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，使用主机实例（该主机实例运行将从合作伙伴 A 接收消息的处理程序）的服务帐户登录。在服务帐户的个人存储中安装用于解密消息的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 私钥证书。 下图显示您安装证书的证书存储。  
  
     ![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
4.  在合作伙伴 A 中，在适当的存储中安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 公钥证书，以便对发送到合作伙伴 A 的消息进行加密。 （如果合作伙伴 A 使用 [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]  [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请安装“其他人”存储区中的公钥）。  
  
### <a name="to-install-the-encryption-certificates-in-the-certificates-store"></a>在证书存储中安装加密证书  
  
1.  合作伙伴 A 从 CA 请求用于加密的私钥/公钥对。  
  
2.  合作伙伴 A 在适当存储中安装私钥证书，以用于解密消息。 （如果合作伙伴 A 使用 [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请安装个人证书存储中的私钥）。  
  
3.  合作伙伴 A 向您发送它的公钥，将使用该公钥对发送到合作伙伴 A 的消息进行加密。  
  
4.  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，登录到具有主机实例（该主机实例运行将消息发送到合作伙伴 A 的处理程序）的服务器上。在“其他人”存储中安装合作伙伴 A 的公钥证书，以便对发送至合作伙伴 A 的消息进行加密。 下图显示您安装证书的证书存储。  
  
     ![将发送安全消息所需的证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
### <a name="to-configure-biztalk-hosts-for-receiving-encrypted-messages"></a>配置 BizTalk 主机以便接收加密消息  
  
1.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，展开**主机**。  
  
    1.  在右窗格中，右键单击处理程序接收加密的消息中，BizTalk 主机，然后单击**属性**。  
  
    2.  上**主机属性**对话框中，单击**证书**，单击**浏览**。  
  
    3.  上**选择证书**对话框中，选择安装，解密证书，然后关闭所有对话框。  
  
        > [!NOTE]
        >  有关详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
## <a name="next-steps"></a>后续步骤  
 创建管道用于接收中的加密的消息[如何为接收加密的消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)  
  
 创建管道用于发送加密的消息[如何为发送加密的消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 用于加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [发送和接收加密的消息](../core/sending-and-receiving-encrypted-messages.md)
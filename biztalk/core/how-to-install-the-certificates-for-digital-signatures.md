---
title: 如何安装进行数字签名的证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 910ccd84-c022-46a5-a9de-b99046a480b8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b924cbd0ddbbeada7e70dd178c979cb53872124e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000110"
---
# <a name="how-to-install-the-certificates-for-digital-signatures"></a>如何安装进行数字签名的证书
下面的过程列出了安装证书以便接收和发送签名消息需遵守的高级步骤。  
  
-   在证书存储中安装证书以接收签名消息  
  
-   在证书存储中安装签名证书以发送签名消息  
  
-   配置 BizTalk 组以发送签名消息  
  
> [!NOTE]
>  可以使用一个证书同时执行签名和加密操作，也可以对于每种功能使用一个证书。  
> 
> [!IMPORTANT]
>  您只能指定一个签名证书，供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用来对所有出站消息进行签名。 换句话说，您不能根据您要向其发送消息的人员来使用不同的签名证书。  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a>在证书存储中安装证书以接收签名消息  
  
1. 合作伙伴 A 从证书颁发机构 (CA) 请求数字签名的私钥/公钥对。  
  
2. 合作伙伴 A 向您发送它的数字签名的公钥。  
  
3. 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，登录到具有特定主机实例（该主机实例运行将从合作伙伴 A 接收消息的处理程序）的服务器上。在“其他人”存储中安装合作伙伴 A 的公钥证书以验证其签名。 下图显示您安装证书的证书存储。  
  
    ![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
4. 在合作伙伴 A 中，在适当的存储中安装合作伙伴 A 私钥证书以便对消息进行签名。 （如果合作伙伴 A 使用 [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，则在将对发送到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的消息进行签名的帐户的个人存储中安装私钥。）  
  
### <a name="to-install-the-signing-certificates-for-sending-signed-messages-in-the-certificates-store"></a>在证书存储中安装签名证书以发送签名消息  
  
1. 组织中的管理员从 CA 请求数字签名的私钥/公钥对以供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用。  
  
2. 管理员向合作伙伴 A（以及所有其他合作伙伴）发送数字签名的公钥。  
  
3. 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，作为特定主机实例（该主机实例运行将向合作伙伴 A 发送消息的处理程序）的服务帐户登录。安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 私钥证书以便对此服务帐户的个人存储中的消息进行签名。 下图显示您安装证书的证书存储。  
  
    ![若要发送安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
4. 在合作伙伴 A 中，在适当的存储中安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 公钥证书以验证其数字签名。 （如果合作伙伴 A 使用的是 [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请在“其他人”存储中安装公钥）。  
  
### <a name="to-configure-the-biztalk-group-for-sending-signed-messages"></a>配置 BizTalk 组以发送签名消息  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 右键单击**BizTalk 组**，然后单击**属性**。  
  
3. 上**组属性**对话框中，单击**证书**，单击**浏览**。  
  
4. 上**选择证书**对话框中，选择你安装的签名证书，然后关闭所有对话框。  
  
## <a name="next-steps"></a>后续步骤  
 创建一个管道以接收签名的消息[如何配置为接收签名消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)。  
  
 创建一个管道以发送签名的消息[如何配置为发送签名消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 用于签名消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [发送和接收签名消息](../core/sending-and-receiving-signed-messages.md)
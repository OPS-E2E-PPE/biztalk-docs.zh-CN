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
ms.openlocfilehash: 3bec4fd58532201efc430855464a90f03a824400
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384907"
---
# <a name="how-to-install-the-certificates-for-digital-signatures"></a>如何安装进行数字签名的证书
以下过程列出了您必须按照安装证书以便接收和发送签名的消息的高级步骤。  
  
-   若要以接收签名的消息的证书存储中安装证书  
  
-   若要安装的证书存储区中发送签名的消息的签名证书  
  
-   若要配置 BizTalk 组，以便发送签名的消息  
  
> [!NOTE]
>  你可以使用一个证书签名和加密操作，或可以为每个函数使用一个证书。  
> 
> [!IMPORTANT]
>  只能指定一个签名证书与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]对所有出站消息进行签名。 换而言之，不能使用不同的签名证书，具体取决于谁发送到的消息。  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a>若要以接收签名的消息的证书存储中安装证书  
  
1. 合作伙伴 A 从证书颁发机构 (CA) 请求数字签名的私钥 / 公钥对。  
  
2. 合作伙伴 A 向您发送其公钥数字签名。  
  
3. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，登录到服务器的已存储的主机实例运行将从合作伙伴 A.安装接收消息的处理程序的合作伙伴的公钥证书以验证其他人在其签名。 下图显示了你在其中安装证书的证书存储区。  
  
    ![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
4. 在合作伙伴 A 中，安装合作伙伴 A 私钥证书在适当的存储中的消息进行签名。 (如果合作伙伴 A 使用[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]， [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]，或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，将发送到的消息进行签名的帐户的个人存储中安装私钥[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。)  
  
### <a name="to-install-the-signing-certificates-for-sending-signed-messages-in-the-certificates-store"></a>若要安装的证书存储区中发送签名的消息的签名证书  
  
1. 在你的组织中的管理员从 CA 请求用于数字签名的私钥 / 公钥对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用。  
  
2. 管理员发送合作伙伴 A （以及所有其他合作伙伴） 数字签名的公钥。  
  
3. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，以运行将消息发送到合作伙伴 a。 安装的处理程序的主机实例的服务帐户身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]私钥证书的服务帐户的个人存储中的消息进行签名。 下图显示了你在其中安装证书的证书存储区。  
  
    ![若要发送安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")  
  
4. 在合作伙伴 A 中，安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]公钥证书以验证适当的存储其数字签名。 (如果合作伙伴 A 使用[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]， [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]，或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，在其他人存储中安装公钥。)  
  
### <a name="to-configure-the-biztalk-group-for-sending-signed-messages"></a>若要配置 BizTalk 组，以便发送签名的消息  
  
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
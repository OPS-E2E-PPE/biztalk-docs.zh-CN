---
title: 如何为参与方解析配置 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ac330b9-3498-4c98-a6e8-d2c02cd641dd
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6186b4b9d6f027738eacf79034afc739cb5f4619
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341559"
---
# <a name="how-to-configure-biztalk-server-for-party-resolution"></a>如何为参与方解析配置 BizTalk Server
以下过程列出了您必须按照配置的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行参与方解析。  
  
-   若要以接收签名的消息的证书存储中安装证书  
  
-   若要创建代表您合作伙伴的参与方  
  
-   若要创建使用证书的参与方解析管道  
  
-   若要配置使用证书的参与方解析的接收位置  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a>若要以接收签名的消息的证书存储中安装证书  
  
1. 合作伙伴 A 从证书颁发机构 (CA) 请求数字签名的私钥 / 公钥对。  
  
2. 合作伙伴 A 向您发送其公钥数字签名。  
  
3. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，登录到服务器的已存储的主机实例运行将从合作伙伴 A.安装接收消息的处理程序的合作伙伴的公钥证书以验证其他人在其签名。 下图显示了你在其中安装证书的证书存储区。  
  
    ![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
4. 在合作伙伴 A 中，安装合作伙伴 A 私钥证书在适当的存储中的消息进行签名。 (如果合作伙伴 A 使用[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]，或[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]，或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，将发送到的消息进行签名的帐户的个人存储中安装私钥[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。)  
  
   > [!NOTE]
   >  与"以接收签名的消息的证书存储中安装证书"步骤完全相同，则此步骤中[如何安装证书进行数字签名](../core/how-to-install-the-certificates-for-digital-signatures.md)。  
  
### <a name="to-create-a-party-to-represent-your-partner"></a>若要创建代表您合作伙伴的参与方  
  
1. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建代表合作伙伴 a。有关如何创建一个参与方的详细信息，请参阅[如何创建参与方](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)。  
  
2. 在中**证书**属性中，选择公钥签名证书，用于标识此参与方合作伙伴 a。  
  
### <a name="to-create-a-pipeline-for-party-resolution-using-certificates"></a>若要创建使用证书的参与方解析管道  
  
1. 在解决方案资源管理器在 microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，选择想要创建管道的项目。  
  
   1.  上**文件**菜单上，单击**添加新项**。  
  
   2.  在中**添加新项**对话框框中，展开 BizTalk 项目项，单击**管道文件**，然后单击**接收管道**模板。  
  
   3.  在中**名称**字段中，键入管道的名称。  
  
   4.  单击 **“添加”**。  
  
        在解决方案资源管理器中将显示新的管道。  
  
2. 将到 MIME/SMIME 解码器管道组件拖放**解码**接收管道阶段。  
  
    ![MIME&#47;SMIME 解码器管道组件](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")  
  
   -   配置 MIME/SMIME 解码器管道组件属性中的**属性**窗口。 有关 MIME/SMIME 解码器的详细信息，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。  
  
   > [!NOTE]
   >  管道部署到 BizTalk 组使用后，可以配置接收位置的管道属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 每个接收位置在 BizTalk 组中，可以配置不同的管道属性。 有关详细信息，请参阅[如何配置每个实例的接收位置的管道属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)。  
   > 
   > [!NOTE]
   >  MIME/SMIME 解码器管道组件执行解密和数字签名验证 （如果配置为执行这两个函数）。 因此，如果你要配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收加密和签名消息，则可以使用相同的接收管道。 换而言之，不需要创建单独的管道解密和数字签名验证。  
  
3. 将到参与方解析管道组件拖放**解析参与方**接收管道阶段。 有关参与方解析管道组件的详细信息，请参阅[如何配置参与方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md)。  
  
   > [!NOTE]
   >  此外可以使用默认的 XMLReceive 管道而不是创建新的接收管道。 XMLReceive 管道运行参与方解析组件，解析将证书使用者参与方 id。 请注意，XMLReceive 管道具有空的解码阶段，因此不能接收加密的消息或验证数字签名使用它。  
  
   -   在属性窗口中，将配置参与方解析管道属性**证书解析参与方**到`True`。  
  
4. 生成并部署接收管道。  
  
### <a name="to-configure-the-receive-location-for-party-resolution-using-certificates"></a>若要配置使用证书的参与方解析的接收位置  
  
1.  BizTalk 将添加到包括接收位置接收到 BizTalk 应用程序的上一个过程中创建程序集签名消息。 有关如何添加 BizTalk 程序集的详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
2.  在上一过程中创建的接收管道在 BizTalk 应用程序中配置的接收位置。 详细了解如何配置接收位置，请参阅[如何编辑接收位置属性](../core/how-to-edit-the-properties-of-a-receive-location.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何配置 BizTalk Server 以便接收签名消息](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)   
 [BizTalk Server 用于签名消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [入站的消息身份验证](../core/inbound-message-authentication.md)   
 [为参与方解析使用证书](../core/using-certificates-for-party-resolution.md)
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
ms.openlocfilehash: 8d6fc4f0f0dc61b111060aebb26b8dccfc32ec15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991054"
---
# <a name="how-to-configure-biztalk-server-for-party-resolution"></a>如何为参与方解析配置 BizTalk Server
下面的过程列出了配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以便用于参与方解析时需执行的步骤。  
  
-   在证书存储中安装证书以接收签名消息  
  
-   创建代表您合作伙伴的参与方  
  
-   创建使用证书进行参与方解析的管道  
  
-   配置使用证书进行参与方解析的接收位置  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a>在证书存储中安装证书以接收签名消息  
  
1. 合作伙伴 A 从证书颁发机构 (CA) 请求数字签名的私钥/公钥对。  
  
2. 合作伙伴 A 向您发送它的数字签名的公钥。  
  
3. 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，登录到具有特定主机实例（该主机实例运行将从合作伙伴 A 接收消息的处理程序）的服务器上。在“其他人”存储中安装合作伙伴 A 的公钥证书以验证其签名。 下图显示您安装证书的证书存储。  
  
    ![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")  
  
4. 在合作伙伴 A 中，在适当的存储中安装合作伙伴 A 私钥证书以便对消息进行签名。 （如果合作伙伴 A 使用 [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)] 或 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，则在将对发送到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的消息进行签名的帐户的个人存储中安装私钥。）  
  
   > [!NOTE]
   >  与"以接收签名的消息的证书存储中安装证书"步骤完全相同，则此步骤中[如何安装证书进行数字签名](../core/how-to-install-the-certificates-for-digital-signatures.md)。  
  
### <a name="to-create-a-party-to-represent-your-partner"></a>创建代表您合作伙伴的参与方  
  
1. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建代表合作伙伴 a。有关如何创建一个参与方的详细信息，请参阅[如何创建参与方](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)。  
  
2. 在中**证书**属性中，选择公钥签名证书，用于标识此参与方合作伙伴 a。  
  
### <a name="to-create-a-pipeline-for-party-resolution-using-certificates"></a>创建使用证书进行参与方解析的管道  
  
1. 在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的解决方案资源管理器中，选择要在其中创建管道的项目。  
  
   1.  上**文件**菜单上，单击**添加新项**。  
  
   2.  在中**添加新项**对话框框中，展开 BizTalk 项目项，单击**管道文件**，然后单击**接收管道**模板。  
  
   3.  在中**名称**字段中，键入管道的名称。  
  
   4.  单击 **“添加”**。  
  
        此时，新的管道将显示在解决方案资源管理器中。  
  
2. 将到 MIME/SMIME 解码器管道组件拖放**解码**接收管道阶段。  
  
    ![MIME&#47;SMIME 解码器管道组件](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")  
  
   -   配置 MIME/SMIME 解码器管道组件属性中的**属性**窗口。 有关 MIME/SMIME 解码器的详细信息，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。  
  
   > [!NOTE]
   >  您可以在将管道部署到某一 BizTalk 组中后，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置接收位置的管道属性。 还可以为 BizTalk 组中的每个接收位置配置不同的管道属性。 有关详细信息，请参阅[如何配置每个实例的接收位置的管道属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)。  
   > 
   > [!NOTE]
   >  MIME/SMIME 解码器管道组件既执行解密，又执行数字签名验证（在配置为执行这两个功能时）。 因此，如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为接收加密和签名消息，则可以使用同一接收管道。 换言之，您不必为解密和数字签名验证创建不同的管道。  
  
3. 将到参与方解析管道组件拖放**解析参与方**接收管道阶段。 有关参与方解析管道组件的详细信息，请参阅[如何配置参与方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md)。  
  
   > [!NOTE]
   >  您还可以使用默认的 XMLReceive 管道，而不用创建新的接收管道。 XMLReceive 管道运行参与方解析组件，解析将证书使用者参与方 id。 请注意，XMLReceive 管道具有空的解码阶段，因此不能接收加密的消息或验证数字签名使用它。  
  
   -   在属性窗口中，将配置参与方解析管道属性**证书解析参与方**到`True`。  
  
4. 生成并部署接收管道。  
  
### <a name="to-configure-the-receive-location-for-party-resolution-using-certificates"></a>配置使用证书进行参与方解析的接收位置  
  
1.  将您在前面过程中创建的 BizTalk 程序集添加到包括接收位置的 BizTalk 应用程序，以便接收签名消息。 有关如何添加 BizTalk 程序集的详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
2.  使用您在前面过程中创建的接收管道配置 BizTalk 应用程序中的接收位置。 详细了解如何配置接收位置，请参阅[如何编辑接收位置属性](../core/how-to-edit-the-properties-of-a-receive-location.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何配置 BizTalk Server 以便接收签名消息](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)   
 [BizTalk Server 用于签名消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [入站的消息身份验证](../core/inbound-message-authentication.md)   
 [为参与方解析使用证书](../core/using-certificates-for-party-resolution.md)
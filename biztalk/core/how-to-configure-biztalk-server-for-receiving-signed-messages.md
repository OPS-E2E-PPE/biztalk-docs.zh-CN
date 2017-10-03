---
title: "如何将 BizTalk Server 配置为接收注册消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48479532-24a9-41d9-a3b8-2a23f4e76457
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 814aa3f25866f18a1d7fe536bc47a996f286916d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-for-receiving-signed-messages"></a>如何将 BizTalk Server 配置为接收注册消息
下面的过程列出了配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以便接收加密消息需执行的步骤。  
  
-   创建管道以便接收签名消息  
  
-   配置接收位置以便接收签名消息  
  
## <a name="prerequisites"></a>先决条件  
 在配置之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于接收签名的邮件的 s，必须执行中的步骤[如何安装进行数字签名的证书](../core/how-to-install-the-certificates-for-digital-signatures.md)。  
  
### <a name="to-create-a-pipeline-to-receive-signed-messages"></a>创建管道以便接收签名消息  
  
1.  在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的解决方案资源管理器中，选择要在其中创建管道的项目。  
  
    1.  上**文件**菜单上，单击**添加新项**。  
  
    2.  在**添加新项**对话框框中，展开 BizTalk 项目项，单击**管道文件**，然后单击**接收管道**模板。  
  
    3.  在**名称**字段中，键入管道的名称。  
  
    4.  单击 **“添加”**。  
  
         此时，新的管道将显示在解决方案资源管理器中。  
  
2.  拖动到 MIME/SMIME 解码器管道组件**解码**接收管道的阶段。  
  
     ![MIME &#47;SMIME 解码器管道组件](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")  
  
    -   配置中的 MIME/SMIME 解码器管道组件属性**属性**窗口。 MIME/SMIME 解码器有关的详细信息，请参阅[如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。  
  
    > [!NOTE]
    >  您可以在将管道部署到某一 BizTalk 组中后，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置接收位置的管道属性。 还可以为 BizTalk 组中的每个接收位置配置不同的管道属性。 有关详细信息，请参阅[如何配置为接收位置的每个实例管道属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)。  
  
    > [!NOTE]
    >  MIME/SMIME 解码器管道组件既执行解密，又执行数字签名验证（在配置为执行这两个功能时）。 因此，如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为接收加密和签名消息，则可以使用同一接收管道。 换言之，您不必为解密和数字签名验证创建不同的管道。  
  
3.  生成并部署接收管道。  
  
### <a name="to-configure-the-receive-location-for-receiving-signed-messages"></a>配置接收位置以便接收签名消息  
  
1.  将您在前面过程中创建的 BizTalk 程序集添加到包括接收位置的 BizTalk 应用程序，以便接收签名消息。 有关如何添加 BizTalk 程序集的详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
2.  使用您在前面过程中创建的接收管道配置 BizTalk 应用程序中的接收位置。 有关如何配置的详细信息接收位置，请参阅[如何编辑接收位置的属性](../core/how-to-edit-the-properties-of-a-receive-location.md)。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 用于签名的消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [如何将 BizTalk Server 配置为发送注册消息](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)   
 [对一条消息的发送方进行身份验证](../core/authenticating-the-sender-of-a-message.md)   
 [发送和接收签名消息](../core/sending-and-receiving-signed-messages.md)
---
title: 如何配置 BizTalk Server 以便接收加密的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd1e7e4c-f80c-468e-aa86-7c18406feead
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765c47755e0d170473d92e755eba11e10a4dc3d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023571"
---
# <a name="how-to-configure-biztalk-server-for-receiving-encrypted-messages"></a>如何配置 BizTalk Server 以便接收加密消息
下面的过程列出了配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以便接收加密消息需执行的步骤。  
  
-   创建管道以便接收加密消息  
  
-   配置接收位置以便接收加密消息  
  
## <a name="prerequisites"></a>必要條件  
 配置之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以便接收加密的消息，必须首先执行中的步骤[如何为加密消息安装证书](../core/how-to-install-the-certificates-for-encrypted-messages.md)。  
  
### <a name="to-create-a-pipeline-to-receive-encrypted-messages"></a>创建管道以便接收加密消息  
  
1. 在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的解决方案资源管理器中，选择要在其中创建管道的项目。  
  
   1.  上**文件**菜单上，单击**添加新项**。  
  
   2.  在中**添加新项**对话框框中，展开 BizTalk 项目项，单击**管道文件**，然后单击**接收管道**模板。  
  
   3.  在中**名称**字段中，键入管道的名称。  
  
   4.  单击 **“添加”**。  
  
        此时，新的管道将显示在解决方案资源管理器中。  
  
2. 将 MIME/SMIME 解码器管道组件拖至接收管道的“解码”阶段。  
  
    ![MIME&#47;SMIME 解码器管道组件](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")  
  
   -   配置 MIME/SMIME 解码器管道组件属性中的**属性**窗口。 有关 MIME/SMIME 解码器的详细信息，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。  
  
   > [!NOTE]
   >  您可以在将管道部署到某一 BizTalk 组中后，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置接收位置的管道属性。 还可以为 BizTalk 组中的每个接收位置配置不同的管道属性。 有关详细信息，请参阅[如何配置每个实例的接收位置的管道属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)。  
   > 
   > [!NOTE]
   >  MIME/SMIME 解码器管道组件既执行解密，又执行数字签名验证（在配置为执行这两个功能时）。 因此，如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为接收加密和签名消息，则可以使用同一接收管道。 换言之，您不必为解密和数字签名验证创建不同的管道。  
  
3. 生成并部署接收管道。  
  
### <a name="to-configure-the-receive-location-for-receiving-encrypted-messages"></a>配置接收位置以便接收加密消息  
  
1.  将您在前面过程中创建的 BizTalk 程序集添加到包括接收位置的 BizTalk 应用程序，以便接收加密消息。 有关如何添加 BizTalk 程序集的详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
2.  使用您在前面过程中创建的接收管道配置 BizTalk 应用程序中的接收位置。 详细了解如何配置接收位置，请参阅[如何编辑接收位置属性](../core/how-to-edit-the-properties-of-a-receive-location.md)。  
  
3.  配置使用的接收处理程序过程中安装的解密证书的接收位置的主机"配置 BizTalk 主机以便接收加密的消息"在[如何安装证书的加密消息](../core/how-to-install-the-certificates-for-encrypted-messages.md)。 有关详细信息如何配置主机属性，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 用来加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [如何配置 BizTalk Server 以便发送加密的消息](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)   
 [发送和接收加密消息](../core/sending-and-receiving-encrypted-messages.md)
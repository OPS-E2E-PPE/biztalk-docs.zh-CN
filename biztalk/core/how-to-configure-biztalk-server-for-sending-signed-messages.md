---
title: 如何将 BizTalk Server 配置为发送注册消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be86fbb3-de80-4d9f-bcf0-c61347704229
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef71f5c11d6c1a000369644b822aa9f4d4ef792
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249021"
---
# <a name="how-to-configure-biztalk-server-for-sending-signed-messages"></a>如何配置 BizTalk Server 以便发送签名消息
以下过程列出了配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以便发送签名消息需遵守的步骤。  
  
-   创建管道以便发送签名消息  
  
-   配置用于发送签名消息的发送端口  
  
## <a name="prerequisites"></a>先决条件  
 在配置之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s 针对发送签名的消息，你必须执行中的步骤[如何安装进行数字签名的证书](../core/how-to-install-the-certificates-for-digital-signatures.md)。  
  
### <a name="to-create-a-pipeline-to-send-signed-messages"></a>创建管道以便发送签名消息  
  
1.  在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的解决方案资源管理器中，选择要在其中创建管道的项目。  
  
    1.  上**文件**菜单上，单击**添加新项**。  
  
    2.  在**添加新项**对话框框中，展开 BizTalk 项目项，单击**管道文件**，然后单击**发送管道**模板。  
  
    3.  在**名称**字段中，键入管道的名称。  
  
    4.  单击 **“添加”**。  
  
         此时，新的管道将显示在解决方案资源管理器中。  
  
2.  将 MIME/SMIME 编码器管道组件拖至接收管道的编码阶段。  
  
     ![MIME &#47;SMIME 编码器管道组件](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")  
  
3.  在属性窗口中，将配置 MIME/SMIME 编码器管道组件**签名类型**属性**ClearSign**或**BlobSign**。 有关详细信息**启用加密**属性，请参阅[如何配置 MIME SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)。  
  
    > [!IMPORTANT]
    >  如果你使用加密，你可以只选择**BlobSign**。  
  
    > [!NOTE]
    >  您可以在将管道部署到某一 BizTalk 组中后使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置发送管道组件属性。 有关详细信息，请参阅[如何配置每个实例管道发送端口属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)。  
  
    > [!NOTE]
    >  MIME/SMIME 编码器管道组件既执行加密，又执行数字签名（在配置为执行这两个功能时）。 因此，如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为发送加密和签名消息，则可以使用同一发送管道。 换言之，您不必为加密和数字签名创建各自的管道。  
  
4.  生成并部署发送管道。  
  
### <a name="to-configure-the-send-port-for-sending-signed-messages"></a>配置用于发送签名消息的发送端口  
  
1.  将您在前面过程中创建的 BizTalk 程序集添加到包括接收位置的 BizTalk 应用程序，以便发送签名消息。 有关如何添加 BizTalk 程序集的详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
2.  使用您在前面过程中创建的发送管道配置 BizTalk 应用程序中的发送端口。 有关如何配置发送端口的详细信息，请参阅[创建和配置发送端口](../core/creating-and-configuring-send-ports.md)。  
  
3.  配置 BizTalk 组中安装签名证书[如何安装进行数字签名的证书](../core/how-to-install-the-certificates-for-digital-signatures.md)。 有关详细信息如何配置 BizTalk 组，请参阅[如何修改组属性](../core/how-to-modify-group-properties.md)。  
  
## <a name="see-also"></a>另请参阅  
 [如何将 BizTalk Server 配置为接收注册消息](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)   
 [BizTalk Server 用于签名的消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)   
 [发送和接收签名消息](../core/sending-and-receiving-signed-messages.md)
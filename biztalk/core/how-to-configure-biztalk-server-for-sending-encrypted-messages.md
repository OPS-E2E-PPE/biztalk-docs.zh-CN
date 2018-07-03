---
title: 如何配置 BizTalk Server 以便发送加密消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb751d7c-49cd-46f0-9630-254cf06c497e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49f7388e9f6b8e56397a3b6efdf466aec3383746
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023899"
---
# <a name="how-to-configure-biztalk-server-for-sending-encrypted-messages"></a>如何配置 BizTalk Server 以便发送加密的消息
以下过程列出了配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以便发送加密消息需遵守的步骤。  
  
-   创建管道以便发送加密消息  
  
-   配置用于发送加密消息的发送端口  
  
## <a name="prerequisites"></a>必要條件  
 配置之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以便发送加密的消息，必须首先执行中的步骤[如何为加密消息安装证书](../core/how-to-install-the-certificates-for-encrypted-messages.md)。  
  
### <a name="to-create-a-pipeline-to-send-encrypted-messages"></a>创建管道以便发送加密消息  
  
1. 在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的解决方案资源管理器中，选择要在其中创建管道的项目。  
  
   1.  上**文件**菜单上，单击**添加新项**。  
  
   2.  在中**添加新项**对话框框中，展开 BizTalk 项目项，单击**管道文件**，然后单击**发送管道**模板。  
  
   3.  在中**名称**字段中，键入管道的名称。  
  
   4.  单击 **“添加”**。  
  
        此时，新的管道将显示在解决方案资源管理器中。  
  
2. 将 MIME/SMIME 编码器管道组件拖至接收管道的编码阶段。  
  
    ![MIME&#47;SMIME 编码器管道组件](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")  
  
   -   在属性窗口中配置 MIME/SMIME 编码器管道组件**启用加密**属性设置为`True`。 有关详细信息**启用加密**属性，请参阅[如何配置 MIME-SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)。  
  
   > [!NOTE]
   >  您可以在将管道部署到某一 BizTalk 组中后使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置发送管道组件属性。 有关详细信息，请参阅[如何为发送端口配置每个实例的管道属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)。  
   > 
   > [!NOTE]
   >  MIME/SMIME 编码器管道组件既执行加密，又执行数字签名（在配置为执行这两个功能时）。 因此，如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为发送加密和签名消息，则可以使用同一发送管道。 换言之，您不必为加密和数字签名创建各自的管道。  
  
3. 生成并部署发送管道。  
  
### <a name="to-configure-the-send-port-for-sending-encrypted-messages"></a>配置用于发送加密消息的发送端口  
  
1.  将您在前面过程中创建的 BizTalk 程序集添加到包括发送端口的 BizTalk 应用程序，以便发送加密消息。 有关如何添加 BizTalk 程序集的详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。  
  
2.  在前面过程中创建的发送管道在 BizTalk 应用程序中配置的发送端口，然后将分配中安装的加密证书[如何安装证书用于加密的消息](../core/how-to-install-the-certificates-for-encrypted-messages.md). 有关如何配置发送端口的详细信息，请参阅[如何为发送端口分配证书](../core/how-to-assign-a-certificate-to-a-send-port.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何配置 BizTalk Server 以便接收加密的消息](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)   
 [BizTalk Server 用来加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md)   
 [发送和接收加密消息](../core/sending-and-receiving-encrypted-messages.md)
---
title: 配置使用 MMC 导入的证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- decryption certificates
- certificates, decryption certificates
- certificates, signing certificates
- importing certificates
- signing certificates
- certificates, importing
ms.assetid: 64dbfbcf-6026-4c68-a93a-f483ec52deac
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24753e13bb09cd44bbd9fa7bb20c3ca24e6b62e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284682"
---
# <a name="configuring-certificates-imported-using-mmc"></a>配置使用 MMC 导入的证书
在导入证书管理单元中使用的 Microsoft 管理控制台 (MMC) 的证书后，必须配置它们的使用。 这要求配置 BizTalk 组、 BizTalk 主机和独立主机服务帐户、 合作伙伴接口流程 (Pip)、 贸易合作伙伴协议和合作伙伴。 必须执行以下步骤：  
  
> [!NOTE]
>  如果使用 CertWizard 实用工具导入和配置证书，你无需执行这些手动步骤。  
  
- 配置签名证书的本组织的使用。 这意味着使用私钥来标识在传出消息本组织。 若要执行此操作，请为 BizTalk 组配置签名证书。  
  
- 配置为本组织的解密证书的使用。 这意味着使用对应于合作伙伴的公钥，私钥来解密传入消息。 若要执行此操作，请为每个 BizTalk 主机和 BizTalk Isolated Host 服务帐户配置的解密证书。 必须输入相同的解密证书的主机和独立主机服务帐户，这对于[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]必须设置为相同的帐户。  
  
  > [!NOTE]
  >  BizTalk 主机和独立主机必须具有相同的解密证书，以便它们可以同时解密同一个加密的传入消息。 运行 HTTP 适配器的 BizTalk 独立主机必须要接收的消息的证书，因为它不具有访问主机证书。 BizTalk 主机还必须拥有证书后，才能处理消息后的执行消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收到。  
  
- 配置加密和签名证书的每个合作伙伴。 若要执行此操作，则输入证书**常规**选项卡**合作伙伴**在 microsoft 的属性页[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理控制台。 其中包括给合作伙伴，传出消息进行加密的公钥加密证书和公钥签名证书来验证对传入的消息的合作伙伴的标识。 有关详细信息，请参阅[创建或编辑合作伙伴](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)。  
  
- 配置本组织和贸易合作伙伴之间的加密策略。 若要执行此操作，您的贸易合作伙伴协议上配置**协议**选项卡**协议属性**页中[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台。 有关详细信息，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。  
  
### <a name="to-configure-the-signing-certificate-for-a-biztalk-group-or-the-decryption-certificate-for-a-biztalk-host"></a>为 BizTalk 主机配置为 BizTalk 组或解密证书的签名证书  
  
1. 单击**启动**，单击**运行**，类型**runas /user:\<承载服务\>mmc**，然后单击**确定**。  
  
   > [!NOTE]
   >  有关\<*承载服务*\>，键入你在安装时与主机服务关联的服务名称[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。  
  
2. 键入的密码\<*承载服务*\>，然后按 ENTER。  
  
3. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**。  
  
4. 展开**证书-当前用户**，展开**个人**，然后单击**证书**。  
  
5. 在右窗格中，双击私有证书。  
  
6. 在证书窗口上**详细信息**选项卡上，单击**指纹**，然后在显示窗口中选择十六进制标识号。 按 CTRL + C 以复制它。  
  
7. 单击**启动**，依次指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
8. 若要为 BizTalk 组配置签名证书，请右键单击**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**，然后单击**属性**。 在右侧的文本框中单击**指纹**，按 CTRL + V 将指纹码粘贴到文本框中，然后依次**确定**。  
  
9. 若要配置 BizTalk 主机的解密证书，依次展开**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**，展开**主机**，右键单击您要的主机配置，然后依次**属性**。  
  
10. 上**证书**选项卡上，单击右侧的文本框中**指纹**，按 CTRL + V 将指纹码粘贴到文本框中，然后单击**确定**。  
  
    > [!NOTE]
    >  必须在 BizTalk 主机 (BizTalkServerApplication) 和 BizTalk 独立主机 (BizTalkServerIsolatedHost) 上配置的解密证书。  
  
## <a name="see-also"></a>请参阅  
 [管理证书](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)
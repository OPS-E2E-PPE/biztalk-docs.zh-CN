---
title: 配置证书导入使用 MMC |Microsoft 文档
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
ms.openlocfilehash: 5d8896691557f48a8e85e67e09e35d20e1d606d0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961667"
---
# <a name="configuring-certificates-imported-using-mmc"></a>配置使用 MMC 导入的证书
使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] 管理控制台 (MMC) 的证书管理单元导入证书后，必须对证书的使用进行配置。 这要求配置 BizTalk 组、 BizTalk 主机和独立的主机服务帐户、 合作伙伴接口进程 (Pip)、 贸易合作伙伴协议和合作伙伴。 你必须执行以下步骤：  
  
> [!NOTE]
>  如果你使用 CertWizard 实用程序导入和配置证书，你不需要执行以下手动步骤。  
  
-   配置用于本组织使用签名证书。 这意味着使用私钥来标识主组织中为传出消息。 若要执行此操作，请为 BizTalk 组配置签名证书。  
  
-   配置用于本组织使用的解密证书。 这意味着使用私钥对应于合作伙伴的公共密钥，对传入消息进行解密。 若要执行此操作，请对每个 BizTalk 主机和 BizTalk 独立主机服务帐户配置解密证书。 您必须为主机和独立主机的服务帐户输入相同的解密证书，在使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 时，必须将这些帐户设置为同样的帐户。  
  
    > [!NOTE]
    >  BizTalk 主机和独立的主机必须具有相同的解密证书，以便它们可以同时解密已加密为相同的传入消息。 BizTalk 独立的主机运行 HTTP 适配器必须具有要接收的消息的证书，因为它不具有访问主机证书。 BizTalk 主机也必须拥有该证书，才能在 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 接收到消息后执行消息处理。  
  
-   配置加密和签名证书，每个伙伴。 若要执行此操作，则输入证书**常规**选项卡**合作伙伴**属性页中[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理控制台。 其中包括到合作伙伴的传出消息进行加密的公钥加密证书和公钥的签名证书，以验证对传入的消息的合作伙伴的标识。 有关详细信息，请参阅[创建或编辑合作伙伴](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)。  
  
-   配置本组织和贸易合作伙伴之间的加密策略。 若要执行此操作，你配置贸易合作伙伴协议上**协议**选项卡**协议属性**页面[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台。 有关详细信息，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。  
  
### <a name="to-configure-the-signing-certificate-for-a-biztalk-group-or-the-decryption-certificate-for-a-biztalk-host"></a>若要为 BizTalk 主机配置 BizTalk 组或解密证书的签名证书  
  
1.  单击**启动**，单击**运行**，类型**runas /user:\<承载服务\>mmc**，然后单击**确定**。  
  
    > [!NOTE]
    >  有关\<*承载服务*\>，键入你在安装时，在与主机服务关联的服务名称[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。  
  
2.  键入的密码\<*承载服务*\>，然后按 ENTER。  
  
3.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**。  
  
4.  展开**证书-当前用户**，展开**个人**，然后单击**证书**。  
  
5.  在右窗格中，双击私有证书。  
  
6.  在证书窗口上**详细信息**选项卡上，单击**指纹**，然后在显示窗口中选择的十六进制的标识号。 按 CTRL + C 将它复制。  
  
7.  单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。  
  
8.  若要配置 BizTalk 组签名证书，右键单击**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **（本地）**，然后单击**属性**。 在文本框中的右侧单击**指纹**，按 CTRL + V 粘贴到文本框中，指纹编号，然后单击**确定**。  
  
9. 若要配置 BizTalk 主机解密证书，请展开**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **（本地）**，展开**主机**，右键单击你希望的主机配置，，然后单击**属性**。  
  
10. 上**证书**选项卡上，单击文本框右侧的**指纹**，按 CTRL + V 粘贴到文本框中，指纹编号，然后单击**确定**。  
  
    > [!NOTE]
    >  你必须配置 BizTalk 主机 (BizTalkServerApplication) 和 BizTalk 独立主机 (BizTalkServerIsolatedHost) 上的解密证书。  
  
## <a name="see-also"></a>另请参阅  
 [管理证书](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)
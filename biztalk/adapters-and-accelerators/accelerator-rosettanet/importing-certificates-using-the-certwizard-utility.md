---
title: "导入证书使用 CertWizard 实用工具 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, root keys
- certificates, public keys
- certificates, private keys
- importing certificates
- public keys
- private keys
- CertWizard utility
- certificates, importing
- root keys
ms.assetid: 0c54d7ab-69cf-4f4a-b976-6f740a41280b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e887811b4aef771a33a1f4e4d8852d5815036a74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="importing-certificates-using-the-certwizard-utility"></a>导入证书使用 CertWizard 实用工具
本主题介绍如何使用 CertWizard 实用程序，分步的命令行实用程序中提供导入证书[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK。 本主题说明如何导入私钥、公钥和根钥， 还说明了用于配置证书的开关。  
  
 CertWizard 实用工具可使许多步骤自动完成，否则这些步骤必须使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] 管理控制台 (MMC) 手动完成的。 CertWizard 实用工具可执行**runas**命令以打开 MMC 作为主机服务帐户。 如果不希望添加**用户身份**开关，它将检测并使用主机服务帐户，提示你输入密码。 该实用工具存储并配置证书。  
  
 通过使用多个 CertWizard 实用工具命令创建批处理文件，可以同时导入多个证书。  
  
### <a name="to-import-a-private-key"></a>导入私钥  
  
1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  在命令提示符下，将移到[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 文件夹使用 MS-DOS **CD**命令，例如，键入**cd C:\Program Files\Microsoft BizTalk\<版本 > RosettaNet\SDK快捷键** .  
  
    > [!NOTE]
    >  使用 CertWizard 实用程序的帮助，请键入**CertWizard /？** 在命令提示符。  
  
3.  在命令提示符处，键入**CertWizard /Privatekey\<文件名 >.pfx**，其中\< *filename*>.pfx 包含的私有证书。 若要为文件提供密码，请将追加**/Filepassword \<filepassword >**到该命令。  
  
4.  如果你想要将证书导入 BizTalk 主机所使用的特定帐户中，追加**/Useridentity\<用户身份 > /Password\<密码 >**到该命令。  
  
5.  如果你想要指定特定的指纹，以防.pfx 文件包含多个证书，并追加**/Thumbprint\<指纹 >**到该命令。  
  
6.  如果你想要配置的证书的使用情况，追加**/Usage**到命令，然后追加以下值之一：  
  
    -   追加**登录**要为 BizTalk 组添加为签名证书的证书的指纹。 对话框中设置 microsoft [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] （本地） 的 BizTalk 管理控制台中。  
  
    -   追加**解密**要添加证书的指纹解密证书对于 BizTalk 主机中，为 BizTalk 管理控制台中每个主机组的属性页的证书选项卡上。  
  
    -   追加**同时**以添加该证书的指纹为这两个 BizTalk 组的签名证书，然后 BizTalk 主机的解密证书。  
  
    -   追加**无**不要设置的配置 BizTalk 组或 BizTalk 主机。  
  
7.  如果你想要配置为可导出的证书，则追加**/可导出 true**。 若要设置为非可导出的证书，请将追加**/可导出 false**，这是默认行为。  
  
8.  按 **Enter**。  
  
9. 如果你没有键入命令所要求的密码，该工具将提示你键入密码。 键入密码，，然后按**Enter**。  
  
10. 如果该文件包含多个证书，但是你在命令中没有键入指纹，则该工具将显示出可用的指纹并提示你选择其中一个。 键入的数目，然后按指纹**Enter**。  
  
     该工具将证书导入中指定的用户的 \Personal\Certificates 存储**/useridentity**切换。 如果未指定用户，默认的用户将是 BizTalkServerApplication 和 BizTalkServerIsolatedHost 主机的用户标识。  
  
### <a name="to-import-a-public-key"></a>导入公钥  
  
1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  在命令提示符下，将移到[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 文件夹使用 MS-DOS **CD**命令，例如，键入**cd C:\Program Files\Microsoft BizTalk\<版本 > RosettaNet\SDK 快捷键**.  
  
3.  在命令提示符处，键入**CertWizard /Publickey\<文件名 >.cer**，其中\< *filename*>.cer 包含的公用证书。  
  
4.  如果你想要指定.cer 或.der 文件中的证书指纹，追加**/Thumbprint\<指纹 >**到该命令。  
  
     该工具将证书导入“证书（本地计算机）”\“其他人”\“证书”存储区，然后设置其配置。  
  
### <a name="to-import-a-root-key"></a>导入根钥  
  
1.  单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  在命令提示符下，将移到[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 文件夹使用 MS-DOS **CD**命令，例如，键入**cd C:\Program Files\Microsoft BizTalk\<版本 > RosettaNet\SDK 快捷键**.  
  
3.  在命令提示符处，键入**CertWizard /Rootkey\<文件名 >.cer**，其中\< *filename*>.cer 包含的根证书。  
  
4.  如果你想要指定.cer 或.der 文件中的证书指纹，追加**/Thumbprint\<指纹 >**到该命令。  
  
     该工具将证书导入“证书（本地计算机）”\“受信任根证书授权机构”\“证书”存储区，然后设置其配置。  
  
## <a name="see-also"></a>另请参阅  
 [CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)   
 [管理证书](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)
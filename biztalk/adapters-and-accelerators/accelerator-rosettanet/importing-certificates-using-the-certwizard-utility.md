---
title: 使用 CertWizard 实用工具导入证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2545da0d4ac9e62e500a24a49c8b3a10dd37adac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283582"
---
# <a name="importing-certificates-using-the-certwizard-utility"></a>使用 CertWizard 实用工具导入证书
本主题介绍如何使用 CertWizard 实用程序，在 Microsoft 中可用的分步命令行实用工具导入证书[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]SDK。 本主题说明如何导入私钥、 公钥和根项。 它描述了用于配置该证书的开关。  
  
 CertWizard 实用工具可自动执行许多必须通过使用 Microsoft 管理控制台 (MMC) 手动执行的步骤。 CertWizard 实用工具可执行**runas**命令，以打开 MMC 主机服务帐户。 如果不添加**Useridentity**开关，它将检测并使用主机服务帐户，提示你输入密码。 它将存储并配置该证书。  
  
 可以在同一时间使用多个 CertWizard 实用工具命令创建批处理文件导入多个证书。  
  
### <a name="to-import-a-private-key"></a>若要导入私钥  
  
1. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 在命令提示符处，转到[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 文件夹使用 MS-DOS **CD**命令，例如，键入**cd C:\Program Files\Microsoft BizTalk\<版本\>Accelerator forRosettaNet\SDK** 。  
  
   > [!NOTE]
   >  使用 CertWizard 实用工具的帮助，请键入**CertWizard /？** 在命令提示符。  
  
3. 在命令提示符处，键入**CertWizard /Privatekey\<文件名\>.pfx**，其中\< *filename*\>.pfx 包含私有证书。 若要为该文件提供密码，请追加 **/Filepassword \<filepassword\>** 命令。  
  
4. 如果你想要将证书导入 BizTalk 主机所使用的特定帐户中，追加 **/Useridentity \<useridentity\> /Password\<密码\>** 命令。  
  
5. 如果你想要指定特定的指纹，以防.pfx 文件包含多个证书，并追加 **/Thumbprint\<指纹\>** 命令。  
  
6. 如果你想要配置的证书的使用情况，则将追加 **/Usage**到命令，然后追加以下值之一：  
  
   -   追加**登录**为 BizTalk 组签名证书添加证书的指纹。 在 BizTalk 管理控制台中的 Microsoft BizTalk server （本地） 对话框的上的设置。  
  
   -   追加**解密**添加证书的指纹解密证书的 BizTalk 主机中，作为 BizTalk 管理控制台中每个主机组的属性页的证书选项卡上。  
  
   -   追加**同时**以添加该证书的指纹为这两个 BizTalk 组的签名证书和 BizTalk 主机的解密证书。  
  
   -   追加**none**不要设置的 BizTalk 组或 BizTalk 主机配置。  
  
7. 如果你想要的证书配置为可导出，则将追加 **/可导出，则返回 true**。 若要设置为非可导出的证书，请追加 **/可导出 false**，这是默认行为。  
  
8. 按 **Enter**。  
  
9. 如果您没有键入命令所要求的密码之一，工具将提示您为它。 键入密码，然后按**Enter**。  
  
10. 如果该文件包含多个证书，但未在命令中键入指纹，该工具显示可用的指纹，并提示您选择一个。 键入指纹，然后按数**Enter**。  
  
     该工具将证书导入中指定的用户 \Personal\Certificates 存储 **/useridentity**切换。 如果未指定用户，默认用户是 BizTalkServerApplication 和 BizTalkServerIsolatedHost 主机的用户标识。  
  
### <a name="to-import-a-public-key"></a>若要导入公钥  
  
1. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 在命令提示符处，转到[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 文件夹，使用 MS-DOS **CD**命令，例如，键入**cd C:\Program Files\Microsoft BizTalk\<版本\>Accelerator forRosettaNet\SDK**。  
  
3. 在命令提示符处，键入**CertWizard /Publickey\<文件名\>.cer**，其中\< *filename*\>.cer 包含公用证书。  
  
4. 如果你想要指定.cer 或.der 文件中的证书指纹，则将追加 **/Thumbprint\<指纹\>** 命令。  
  
    该工具将证书导入证书 （本地计算机） \Other People\Certificates 存储，并设置其配置。  
  
### <a name="to-import-a-root-key"></a>若要导入根钥  
  
1. 单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 在命令提示符处，转到[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]SDK 文件夹，使用 MS-DOS **CD**命令，例如，键入**cd C:\Program Files\Microsoft BizTalk\<版本\>Accelerator forRosettaNet\SDK**。  
  
3. 在命令提示符处，键入**CertWizard /Rootkey\<文件名\>.cer**，其中\< *filename*\>.cer 包含根证书。  
  
4. 如果你想要指定.cer 或.der 文件中的证书指纹，则将追加 **/Thumbprint\<指纹\>** 命令。  
  
    该工具将证书导入证书 （本地计算机） \Trusted Root Certification Authority\Certificates 存储，并设置其配置。  
  
## <a name="see-also"></a>请参阅  
 [CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)   
 [管理证书](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)
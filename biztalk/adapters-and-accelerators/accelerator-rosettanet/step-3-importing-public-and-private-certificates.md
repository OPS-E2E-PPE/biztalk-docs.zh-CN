---
title: 步骤 3： 导入公用和私用证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public certificates
- importing certificates
- private certificates
- double action tutorial, importing certificates
- certificates, importing
ms.assetid: 955bdd69-9fbc-4100-ab8a-8f5dd4a17cbb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18074fd3b72322d79e10895214352837ccf907bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002342"
---
# <a name="step-3-importing-public-and-private-certificates"></a>步骤 3： 导入公用和私用证书
在此步骤中创建的证书导入[步骤 2： 创建公用和私用证书&#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/step-2-creating-public-and-private-certificates.md)到 Contoso 和 Fabrikam 计算机。 每台计算机将导入自己的私用证书和对方组织的公用证书。  
  
> [!NOTE]
>  你必须将 Fabrikam 私用证书和 Contoso 公用证书传输至 Fabrikam 计算机以导入它们。 此步骤假设你将这些证书存放在 Fabrikam 计算机的 C:\Certs 文件夹中。  
  
### <a name="to-import-the-contoso-private-certificates-on-the-contoso-computer"></a>在 Contoso 计算机上导入 Contoso 私用证书  
  
1. 在 Contoso 计算机上，单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2. 在命令提示符处，转到**\<**<em>驱动器</em>**\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator forRosettaNet\SDK** ，然后按**Enter**。  
  
3. 在命令提示符处，键入**CertWizard /Privatekey"\<**<em>驱动器</em>**\>: \Certs\Contoso Private Encryption.pfx"**，然后按**输入**。  
  
4. 在**请输入证书文件的密码**提示符下，键入**mysecret**，然后按**Enter**。  
  
5. 在**输入密码，用于标识 < contoso 计算机 > \HostSvc**提示中，键入 HostSvc 帐户密码，然后按**Enter**。  
  
   > [!NOTE]
   >  如果你的 BizTalkServerApplication 在非 HostSvc 的帐户名下运行，则提示符会有所不同。  
  
6. 在**此本组织证书将用于**提示符下，键入**D**，然后按**Enter**。  
  
    CertWizard 会将证书导入用户帐户（BizTalkServerApplication 和 BizTalkServerIsolatedHost 主机在该用户帐户下运行）的 \“个人”\“证书”存储区中。  
  
7. 重复步骤 3-6 Contoso Private Signature.pfx 证书指定它是签名证书，通过键入**S**处**此本组织证书将用于**提示符在步骤 6 中所述。  
  
### <a name="to-import-the-fabrikam-public-certificates-on-the-contoso-computer"></a>在 Contoso 计算机上导入 Fabrikam 公用证书  
  
1.  在 Contoso 计算机上，单击**启动**，单击**运行，请**类型**cmd**，然后单击**确定**。  
  
2.  在命令提示符处，转到*\<驱动器\>* * *:\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK**，然后按**Enter**.  
  
3.  在命令提示符处，键入**CertWizard /Publickey"***\<驱动器\>***: \Certs\Fabrikam Public Encryption.cer"**，然后按**Enter**.  
  
4.  为 Fabrikam Public Signature.cer 证书重复步骤 3。  
  
### <a name="to-import-the-fabrikam-private-certificates-on-the-fabrikam-computer"></a>在 Fabrikam 计算机上导入 Fabrikam 私用证书  
  
1.  将以下文件从 Contoso 计算机添加到复制\<驱动器\>: Fabrikam 计算机上的 \Certs 文件夹： Contoso Public Encryption.cer、 Contoso Public Signature.cer、 Fabrikam Private Encryption.pfx 和 Fabrikam PrivateSignature.pfx。  
  
2.  在 Fabrikum 计算机上，单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
3.  在命令提示符处，转到*\<驱动器\>* * *:\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK**，然后按**Enter**.  
  
4.  在命令提示符处，键入**CertWizard /Privatekey"***\<驱动器\>***: \Certs\Fabrikam Private Encryption.pfx"**，然后按**Enter**.  
  
5.  在**请输入证书文件的密码**提示符下，键入**mysecret**，然后按**Enter**。  
  
6.  在**输入密码，用于标识 < fabrikam_machine > \HostSvc**提示中，键入 HostSvc 帐户密码，然后按**Enter**。  
  
    > [!NOTE]
    >  如果你的 BizTalkServerApplication 在非 HostSvc 的帐户名下运行，则提示符会有所不同。  
  
7.  在**此本组织证书将用于**提示符下，键入**D**，然后按**Enter**。  
  
     CertWizard 会将证书导入用户帐户（BizTalkServerApplication 和 BizTalkServerIsolatedHost 主机在该用户帐户下运行）的 \“个人”\“证书”存储区中。  
  
8.  重复步骤 4-7 为 Fabrikam Private Signature.pfx 证书来指定它签名证书，通过键入**S**处**此本组织证书将用于**提示在步骤 6 中。  
  
### <a name="to-import-the-contoso-public-certificates-on-the-fabrikam-computer"></a>在 Fabrikam 计算机上导入 Contoso 公用证书  
  
1.  在 Fabrikum 计算机上，单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。  
  
2.  在命令提示符处，转到*\<驱动器\>* * *:\Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK**，然后按**Enter**.  
  
3.  在命令提示符处，键入**CertWizard /Publickey"***\<驱动器\>***: \Certs\Contoso Public Encryption.cer"**，然后按**Enter**。  
  
4.  为 Contoso Public Signature.cer 证书重复步骤 3。  
  
## <a name="see-also"></a>请参阅  
 [步骤 4：在 IIS 中启用安全套接字层](../../adapters-and-accelerators/accelerator-rosettanet/step-4-enabling-secure-sockets-layer-in-iis.md)